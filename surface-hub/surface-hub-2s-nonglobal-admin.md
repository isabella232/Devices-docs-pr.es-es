---
title: Configurar cuentas de administrador no globales en Surface Hub
description: En este artículo se describe cómo configurar cuentas de administrador no globales para administrar Surface Hub y Surface Hub 2S.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497701"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar cuentas de administrador no globales en Surface Hub

La actualización de Windows 10 Team 2020 agrega compatibilidad para configurar cuentas de administrador no globales que limitan los permisos para la administración de la aplicación de Configuración en dispositivos Surface Hub unidos a un dominio de Azure AD. Esto le permite limitar los permisos de administrador solo para Surface Hub y evitar el acceso de administrador potencialmente no deseado en todo un dominio de Azure AD. Antes de empezar, asegúrese de que la Surface Hub esté unida a Azure AD y Intune se inscriba automáticamente. Si no es así, tendrá que restablecer Surface Hub y completar el programa de instalación de la primera vez y de fábrica (OOBE), eligiendo la opción de unirse a Azure AD.

Windows 10 Team 2020 Update 2 agrega compatibilidad con el proveedor de servicios de [configuración LocalUsersAndGroups](/windows/client-management/mdm/policy-csp-localusersandgroups). Esto reemplaza el [CSP de RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups), que permanece disponible, pero ya no se recomienda, como se explica a continuación.

## <a name="summary"></a>Resumen

El proceso de creación de cuentas de administrador no globales implica los pasos siguientes:

1. En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub.
2. Obtenga Azure AD SID de grupo mediante PowerShell.
3. Cree un archivo XML que contenga Azure AD SID de grupo.
4. Cree un grupo de seguridad que contenga los dispositivos Surface Hub que administrará el grupo de seguridad de administradores no globales. 
5. Cree un perfil de configuración personalizado destinado al grupo de seguridad que contiene los dispositivos de Surface Hub.

## <a name="create-azure-ad-security-groups"></a>Creación de grupos de seguridad Azure AD

En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador. A continuación, cree otro grupo de seguridad para dispositivos Surface Hub.  

### <a name="create-security-group-for-admin-accounts"></a>Creación de un grupo de seguridad para cuentas de administrador

1. Inicie sesión en Intune a través del centro de [administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **GruposNuevo** **** >  grupo > y, en Tipo de grupo, seleccione **Seguridad.**
2. Escriba un nombre de grupo (por ejemplo, **Surface Hub Administradores locales**) y, a continuación, seleccione **Crear.**

     ![Cree un grupo de seguridad para administradores del centro.](images/sh-create-sec-group.png)

3. Abra el grupo, seleccione **Miembros** y elija **Agregar miembros** para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub. Para más información sobre cómo crear grupos en Intune, consulte [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Creación de un grupo de seguridad para dispositivos Surface Hub

1. Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos hub; por ejemplo, **Surface Hub dispositivos**.

     ![Cree un grupo de seguridad para dispositivos hub.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obtener Azure AD SID de grupo mediante PowerShell

1. Inicie PowerShell con privilegios de cuenta con privilegios elevados (**ejecutar como administrador**) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell. Para más información, consulte [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [Instale Azure PowerShell módulo](/powershell/azure/install-az-ps).
3. Inicie sesión en el inquilino de Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Cuando haya iniciado sesión en el inquilino, ejecute el siguiente commandlet. Le pedirá que escriba el identificador de objeto del grupo de Azure AD.

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. En Intune, seleccione el grupo que creó anteriormente y copie el id. de objeto, como se muestra en la ilustración siguiente.

     ![Copie el identificador de objeto del grupo de seguridad.](images/sh-objectid.png)

6. Ejecute el siguiente commandlet para obtener el SID del grupo de seguridad:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. Pegue el id. de objeto en el commandlet de PowerShell, presione **Entrar** y copie el **SID de grupo de Azure AD** en un editor de texto.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Creación de un archivo XML que contenga Azure AD SID de grupo

1. Copie lo siguiente en un editor de texto:

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. Reemplace el marcador de posición SID (a partir de S-1-12-1) por el **SID de grupo de Azure AD** y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**.

      > [!NOTE]
      > Aunque los grupos deben especificarse a través de su SID, si desea agregar usuarios de Azure directamente, especifique sus nombres principales de usuario (UPN) en este formato: `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>Creación de un perfil de configuración personalizado

1. En Endpoint Manager, seleccione **DispositivosPerfiles** >  >  **de** **configuraciónCrear perfil**.
2. En Plataforma, seleccione **Windows 10 y versiones posteriores.** En Perfil, seleccione **PlantillasCustomCreate** > **** > **.**
3. Agregue un nombre y una descripción y, a continuación, seleccione **Siguiente.**
4. En **ConfiguraciónConfiguración** >  **CONFIGURACIÓN DE URI** DEOMA, seleccione **Agregar**.
5. En el panel Agregar fila, agregue un nombre y, en     **OMA-URI**, agregue la cadena siguiente:

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > La configuración de directiva **RestrictedGroups/ConfigureGroupMembership** también permite configurar miembros (usuarios o grupos de AAD) en un grupo local Windows 10. Sin embargo, solo permite un reemplazo completo de los grupos existentes con los nuevos miembros. No se pueden agregar o quitar miembros de forma selectiva.  Disponible en Windows 10 Team 2020 Update 2, se recomienda usar la configuración de directiva **LocalUsersandGroups** en lugar de la configuración de directiva RestrictedGroups. No se admite la aplicación de ambas configuraciones de directiva a Surface Hub y puede producir resultados imprevisibles.

6. En Tipo de datos, seleccione **Xml de cadena** y busque para abrir el archivo XML que creó en el paso anterior.

     ![cargar el archivo de configuración xml de administrador local.](images/sh-local-admin-config.png)

7. Haz clic en **Guardar**.
8. Haga clic en **Seleccionar grupos para incluir** y elija el [grupo de seguridad que creó anteriormente](#create-security-group-for-surface-hub-devices) (**Surface Hub dispositivos**). Haz clic en **Siguiente**.
9. En Reglas de aplicabilidad, agregue una regla si lo desea. De lo contrario, seleccione **Siguiente** y, a continuación **, crear.**

Para más información sobre los perfiles de configuración personalizados mediante cadenas OMA-URI, consulte [Uso de la configuración personalizada para dispositivos Windows 10 en Intune](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>Administradores no globales que administran Surface Hub

Los miembros del grupo **de seguridad de administradores locales de Surface Hub** ahora pueden iniciar sesión en la aplicación Configuración en Surface Hub y administrar la configuración.

> [!IMPORTANT]
> Se quita el acceso predeterminado de los administradores globales a la aplicación Configuración (a menos que también sean miembros de este nuevo grupo de seguridad).

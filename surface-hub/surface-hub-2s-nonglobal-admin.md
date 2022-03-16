---
title: Configurar cuentas de administrador no globales en Surface Hub
description: En este artículo se describe cómo configurar cuentas de administrador que no son globales para administrar Surface Hub y Surface Hub 2S.
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
ms.openlocfilehash: 429a7c84605167aa5129999f516c18d17ee30e65
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449303"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar cuentas de administrador no globales en Surface Hub

La actualización de Windows 10 Team 2020 agrega compatibilidad para configurar cuentas de administrador no globales que limiten los permisos a la administración de la aplicación Configuración en dispositivos Surface Hub unidos a un dominio Azure AD. Esto le permite tener en cuenta los permisos de administración Surface Hub y evitar el acceso de administrador potencialmente no deseado en todo Azure AD dominio. Antes de comenzar, asegúrese de que el Surface Hub está unido a Azure AD e Intune autoinscribirse. Si no es así, deberá restablecer Surface Hub y completar el programa de instalación de la primera vez que se haya configurado (OOBE), eligiendo la opción de unirse a Azure AD.

Windows 10 Team 2020 Update 2 agrega compatibilidad con el proveedor de servicios de configuración [LocalUsersAndGroups](/windows/client-management/mdm/policy-csp-localusersandgroups). Esto reemplaza al [CSP de RestrictedGroups](/windows/client-management/mdm/policy-csp-restrictedgroups), que permanece disponible pero ya no se recomienda, como se explica a continuación.

## <a name="summary"></a>Resumen

El proceso de creación de cuentas de administración no globales implica los siguientes pasos:

1. En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub.
2. Obtenga Azure AD SID de grupo con PowerShell.
3. Cree un archivo XML que contenga Azure AD SID de grupo.
4. Cree un grupo de seguridad que contenga los Surface Hub que administrará el grupo de seguridad de administradores no globales. 
5. Crea un perfil de configuración personalizado destinado al grupo de seguridad que contiene los Surface Hub dispositivos.

## <a name="create-azure-ad-security-groups"></a>Crear Azure AD de seguridad

En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador. A continuación, cree otro grupo de seguridad para Surface Hub dispositivos.  

### <a name="create-security-group-for-admin-accounts"></a>Crear grupo de seguridad para cuentas de administrador

1. Inicie sesión en Intune a través [Microsoft Endpoint Manager centro](https://go.microsoft.com/fwlink/?linkid=2109431) de administración, seleccione **GruposNuevo** **** >  grupo > y, en Tipo de grupo, seleccione **Seguridad.**
2. Escriba un nombre de grupo (por ejemplo, **Surface Hub administradores locales**) y, a continuación, **seleccione Crear.**

     ![Crear grupo de seguridad para administradores de concentradores.](images/sh-create-sec-group.png)

3. Abra el grupo, seleccione **Miembros** y elija Agregar **** miembros para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub. Para obtener más información sobre la creación de grupos en Intune, consulta  [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).

### <a name="create-security-group-for-surface-hub-devices"></a>Crear grupo de seguridad para Surface Hub dispositivos

1. Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos concentradores; por ejemplo, **Surface Hub dispositivos**.

     ![Crear grupo de seguridad para dispositivos concentradores.](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obtener Azure AD SID de grupo con PowerShell

1. Inicie PowerShell con privilegios de cuenta elevados (**Ejecutar como** administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell. Para obtener más información, consulte [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).
2. [Instale Azure PowerShell módulo](/powershell/azure/install-az-ps).
3. Inicie sesión en su Azure AD inquilino.

    ```powershell
    Connect-AzureAD
    ```

4. Cuando haya iniciado sesión en el inquilino, ejecute el siguiente commandlet. Se le pedirá que "Escriba el identificador de objeto de su Azure AD grupo".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración.

     ![Copiar id. de objeto del grupo de seguridad.](images/sh-objectid.png)

6. Ejecute el siguiente commandlet para obtener el SID del grupo de seguridad:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. Pegue el id. de objeto en el commandlet de PowerShell, presione **Entrar** y copie el **SID** de grupo Azure AD en un editor de texto.

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Crear archivo XML que contenga Azure AD SID de grupo

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
2. Reemplace el SID de marcador de posición (empezando por S-1-12-1) por el **SID de grupo de Azure AD** y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**.

      > [!NOTE]
      > Aunque los grupos deben especificarse a través de su SID, si desea agregar usuarios de Azure directamente, especifique sus nombres principales de usuario (UPN) en este formato: `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>Crear perfil de configuración personalizado

1. En Endpoint Manager, seleccione **DevicesConfiguration** >  **profilesCreate** >  **profile**.
2. En Plataforma **, Windows 10 y versiones posteriores.** En Perfil, seleccione **Personalizado** y, a continuación, **seleccione Crear.**
3. Agregue un nombre y una descripción y, a continuación, **seleccione Siguiente.**
4. En **ConfiguraciónOMA-URI****** >  Configuración, seleccione **Agregar**.
5. En el panel Agregar fila, agregue un nombre y, en     **OMA-URI**, agregue la siguiente cadena:

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

> [!NOTE]
> La **configuración de directiva RestrictedGroups/ConfigureGroupMembership** también le permite configurar miembros (usuarios o AAD grupos) en un Windows 10 local. Sin embargo, solo permite una sustitución completa de los grupos existentes por los nuevos miembros. No puede agregar o quitar miembros de forma selectiva.  Disponible en Windows 10 Team 2020 Update 2, se recomienda usar la configuración de directiva **LocalUsersandGroups** en lugar de la configuración de directiva RestrictedGroups. La aplicación de ambas configuraciones de directiva Surface Hub no es compatible y puede producir resultados impredecibles.

6. En Tipo de datos, seleccione **String XML** y busque para abrir el archivo XML que creó en el paso anterior.

     ![cargar archivo de configuración xml de administración local.](images/sh-local-admin-config.png)

7. Haz clic en **Guardar**.
8. Haz **clic en Seleccionar grupos para incluir** y elegir el grupo de [seguridad que creaste anteriormente](#create-security-group-for-surface-hub-devices) (**Surface Hub dispositivos**). Haz clic en **Siguiente**.
9. En Reglas de aplicabilidad, agregue una regla si lo desea. De lo contrario, **seleccione Siguiente** y, a continuación, **seleccione Crear**.

Para obtener más información sobre los perfiles de configuración personalizados con cadenas OMA-URI, consulte Usar la configuración personalizada [para Windows 10 dispositivos en Intune](/mem/intune/configuration/custom-settings-windows-10).

## <a name="non-global-admins-managing-surface-hub"></a>Administradores no globales que administran Surface Hub

Los miembros del **Surface Hub seguridad** de administradores locales ahora pueden iniciar sesión en la aplicación Configuración en Surface Hub y administrar la configuración.

> [!IMPORTANT]
> Se quita el acceso predeterminado de los administradores globales a Configuración aplicación (a menos que también sean miembros de este nuevo grupo de seguridad).

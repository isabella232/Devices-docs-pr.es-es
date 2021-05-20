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
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 03359a7d8ea028a8094c064c1fcb82cc9a53fe6a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576770"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>Configurar cuentas de administrador no globales en Surface Hub

La actualización de Windows 10 Team 2020 agrega compatibilidad para configurar cuentas de administrador no globales que limiten los permisos a la administración de la aplicación Configuración en dispositivos Surface Hub unidos a un dominio de Azure AD. Esto le permite tener en cuenta los permisos de administración Surface Hub y evitar el acceso de administrador potencialmente no deseado en todo un dominio de Azure AD. Antes de comenzar, asegúrese de que el Surface Hub está unido a Azure AD e Intune autoinscribirse. Si no es así, tendrá que restablecer Surface Hub y completar el programa de instalación de la primera vez y sin necesidad de usar (OOBE), eligiendo la opción de unirse a Azure AD.

## <a name="summary"></a>Resumen 

El proceso de creación de cuentas de administración no globales implica los siguientes pasos: 

1. En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub.
2. Obtener SID de grupo de Azure AD con PowerShell.
3. Cree un archivo XML que contenga sid de grupo de Azure AD.
4. Cree un grupo de seguridad que contenga los Surface Hub que administrará el grupo seguridad de administradores no globales.
5. Crea un perfil de configuración personalizado destinado al grupo de seguridad que contiene los Surface Hub dispositivos. 


## <a name="create-azure-ad-security-groups"></a>Crear grupos de seguridad de Azure AD

En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador. A continuación, cree otro grupo de seguridad para Surface Hub dispositivos.  

### <a name="create-security-group-for-admin-accounts"></a>Crear grupo de seguridad para cuentas de administrador

1. Inicie sesión en Intune a [través Microsoft Endpoint Manager centro](https://go.microsoft.com/fwlink/?linkid=2109431)de administración, seleccione Grupos nuevos grupos > y, en Tipo de ****  >  **** grupo, seleccione **Seguridad.** 
2. Escriba un nombre de grupo (por ejemplo, **Surface Hub administradores locales)** y, a continuación, **seleccione Crear.** 

     ![Crear grupo de seguridad para administradores de concentradores](images/sh-create-sec-group.png)

3. Abra el grupo, seleccione **Miembros**y, a continuación, elija Agregar miembros para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub. **** Para obtener más información sobre cómo crear grupos en Intune, consulte [Agregar grupos para organizar usuarios y dispositivos.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-security-group-for-surface-hub-devices"></a>Crear grupo de seguridad para Surface Hub dispositivos

1. Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos concentradores; por ejemplo, **Surface Hub dispositivos**. 

     ![Crear grupo de seguridad para dispositivos concentradores](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>Obtener SID de grupo de Azure AD con PowerShell

1. Inicie PowerShell con privilegios de cuenta elevados **(Ejecutar**como administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell. Para obtener más información, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instalar Azure PowerShell módulo](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Inicie sesión en el inquilino de Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Cuando haya iniciado sesión en el inquilino, ejecute el siguiente commandlet. Se le pedirá que "Escriba el identificador de objeto de su grupo de Azure AD".

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración. 

     ![Copy Object id. del grupo de seguridad](images/sh-objectid.png)

6. Ejecute el siguiente commandlet para obtener el SID del grupo de seguridad:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Pegue el id. de objeto en el commandlet de PowerShell, presione **Entrar**y, a continuación, copie el **SID** de grupo de Azure AD en un editor de texto. 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>Crear archivo XML que contenga sid de grupo de Azure AD

1. Copie lo siguiente en un editor de texto: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > No quite el miembro de administrador predeterminado del archivo XML.

2. Reemplace el SID de marcador de posición (empezando por S-1-12-1) por su **SID** de grupo de Azure AD y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**. 

## <a name="create-custom-configuration-profile"></a>Crear perfil de configuración personalizado

1. En Endpoint Manager, seleccione **Perfiles**  >  **de configuración de dispositivos Crear**  >  **perfil**. 
2. En Plataforma, **seleccione Windows 10 y versiones posteriores.** En Perfil, seleccione **Personalizado**y, a continuación, **seleccione Crear.**
3. Agregue un nombre y una descripción y, a continuación, **seleccione Siguiente.**
4. En **Configuración**  >  **OMA-URI Configuración**, seleccione **Agregar**.
5. En el panel Agregar fila, agregue un nombre y, en     **OMA-URI,** agregue la siguiente cadena: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. En Tipo de datos, seleccione **String XML** y busque para abrir el archivo XML que creó en el paso anterior. 

     ![cargar archivo de configuración xml de administración local](images/sh-local-admin-config.png)

7. Haz clic en **Guardar**.
8. Haga **clic en Seleccionar grupos para incluir** y elegir el grupo de seguridad que [creó anteriormente](#create-security-group-for-surface-hub-devices) ( Surface Hub**dispositivos**). Haz clic en **Siguiente**.
9. En Reglas de aplicabilidad, agregue una regla si lo desea. De lo contrario, **seleccione Siguiente** y, a continuación, **seleccione Crear**.

Para obtener más información sobre los perfiles de configuración personalizados con cadenas OMA-URI, vea Usar la configuración personalizada para Windows 10 [dispositivos en Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## <a name="non-global-admins-managing-surface-hub"></a>Administradores no globales que administran Surface Hub

Los miembros del **Surface Hub seguridad** de administradores locales ahora pueden iniciar sesión en la aplicación Configuración en Surface Hub y administrar la configuración.

> [!IMPORTANT]
> Se quita el acceso predeterminado de los administradores globales a Configuración aplicación (a menos que también sean miembros de este nuevo grupo de seguridad).

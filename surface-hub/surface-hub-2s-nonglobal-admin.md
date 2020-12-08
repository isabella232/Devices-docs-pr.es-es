---
title: Configurar cuentas de administrador no global en Surface Hub 2S
description: En este artículo se describe cómo configurar cuentas de administrador que no son globales para administrar Surface Hub 2S.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196834"
---
# Configurar cuentas de administrador no global en Surface Hub 2S

Cuando se une a Surface Hub 2S a un dominio de Azure AD, puede configurar cuentas de administrador no globales que limiten los permisos para la administración de la aplicación de configuración en Surface Hub 2S. Esto le permite conceder permisos de administrador de ámbito solo para Surface Hub 2S e impedir el acceso de administrador potencialmente no deseado a todo un dominio de Azure AD. Antes de empezar, asegúrese de que Surface Hub 2S esté unido a Azure AD. Si no es así, tendrá que restablecer Surface Hub 2S y completar el programa de configuración de instalación fuera de servicio (OOBE) por primera vez, eligiendo la opción de unirse a Azure AD.

## Resumen 

El proceso de creación de cuentas de administrador que no sean globales implica los siguientes pasos: 

1. En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub 2S.
2. Obtén el SID de grupo de Azure AD con PowerShell.
3. Crear un archivo XML que contenga el SID de grupo de Azure AD.
4. Cree un grupo de seguridad que contenga los dispositivos Surface Hub 2S que administrará el grupo de seguridad administradores no globales.
5. Crear un perfil de configuración personalizado dirigido al grupo de seguridad que contiene los dispositivos Surface Hub 2S. 


## Crear grupos de seguridad de Azure AD

En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador. A continuación, cree otro grupo de seguridad para los dispositivos Surface Hub.  

### Crear un grupo de seguridad para cuentas de administrador

1. Inicie sesión en Intune a través del [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **grupos**  >  **nuevo grupo** > y en tipo de grupo, seleccione **seguridad.** 
2. Escriba un nombre de grupo, por ejemplo, **administrador local de Surface Hub** y, a continuación, seleccione **crear.** 

     ![Crear un grupo de seguridad para administradores de concentradores](images/sh-create-sec-group.png)

3. Abra el grupo, seleccione **miembros**y, a continuación, elija **Agregar miembros** para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub 2S. Para obtener más información sobre la creación de grupos en Intune, vea  [agregar grupos para organizar usuarios y dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).

### Crear un grupo de seguridad para dispositivos Surface Hub 2S

1. Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos de concentrador; por ejemplo, **dispositivos Surface Hub**. 

     ![Crear un grupo de seguridad para dispositivos concentradores](images/sh-create-sec-group-devices.png) 

## Obtener el SID de grupo de Azure AD con PowerShell

1. Inicie PowerShell con privilegios de cuenta elevados (**Ejecutar como administrador**) y asegúrese de que su sistema está configurado para ejecutar scripts de PowerShell. Para obtener más información, consulte [acerca de las directivas de ejecución](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instale el módulo de Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).
3. Inicie sesión en su inquilino de Azure AD.

    ```powershell
    Connect-AzureAD
    ```

4. Cuando haya iniciado sesión en su inquilino, ejecute el siguiente commandlet. Le pedirá que escriba el identificador de objeto de su grupo de Azure AD.

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración. 

     ![Copiar el identificador de objeto del grupo de seguridad](images/sh-objectid.png)

6. Ejecute los siguientes commandlet para obtener el SID del grupo de seguridad:

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. Pegue el identificador de objeto en la commandlet de PowerShell, presione **entrar**y, a continuación, copie el **SID de grupo de Azure ad** en un editor de texto. 

## Crear un archivo XML que contenga el SID de grupo de Azure AD

1. Copie lo siguiente en un editor de texto: 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. Reemplace el marcador de posición SID (que comienza con S-1-12-1) por el SID de su **grupo de Azure ad** y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**. 

## Crear Perfil de configuración personalizado

1. En Endpoint Manager, seleccione perfiles de configuración de **dispositivos**  >  **Configuration profiles**  >  **crear perfil**. 
2. En plataforma **, seleccione Windows 10 y versiones posteriores.** En perfil, seleccione **personalizado**y, a continuación, haga clic en **crear.**
3. Agregue un nombre y una descripción y, después, seleccione **siguiente.**
4. En **configuración**  >  **de configuración OMA-URI**, seleccione **Agregar**.
5. En el panel Agregar fila, agregue un nombre y, en     **OMA-URI**, agregue la siguiente cadena: 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. En tipo de datos, seleccione **cadena XML** y examinar para abrir el archivo XML que creó en el paso anterior. 

     ![Cargar archivo de configuración XML de administración local](images/sh-local-admin-config.png)

7. Haga clic en **Guardar**.
8. Haga clic en **seleccionar grupos para incluir** y elija el [grupo de seguridad que creó anteriormente](#create-security-group-for-surface-hub-2s-devices) (**dispositivos Surface Hub**). Haz clic en **Siguiente**.
9. En reglas de aplicabilidad, agregue una regla si lo desea. En caso contrario, seleccione **siguiente** y, después, haga clic en **crear**.

Para obtener más información sobre los perfiles de configuración personalizados que usan cadenas OMA-URI, consulte [usar la configuración personalizada para dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).


## Administradores no globales que administran Surface Hub 2S

Ahora, los miembros del grupo de seguridad de **Surface Hub local** se pueden iniciar sesión en la aplicación configuración en Surface Hub 2s y administrar la configuración.

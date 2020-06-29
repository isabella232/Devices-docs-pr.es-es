---
title: Implementación en línea con Office 365 (Surface Hub)
description: Este tema ofrece instrucciones para agregar una cuenta del dispositivo al Microsoft Surface Hub cuando haya una implementación totalmente en línea.
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: cuenta del dispositivo para Surface Hub, implementación en línea
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836130"
---
# Implementación en línea con Office 365 (Surface Hub)


Este tema ofrece instrucciones para agregar una cuenta del dispositivo al Microsoft Surface Hub cuando haya una implementación totalmente en línea.

Si tienes una implementación totalmente en línea (O365), puedes [usar los scripts de PowerShell proporcionados](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) para crear cuentas del dispositivo. 

1. Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange.

   Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Después de establecer una sesión, podrás crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón existente de la sala. Esto permitirá autenticar la cuenta en el Surface Hub.

   Si vas a cambiar un buzón de recursos existente:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Si vas a crear un nuevo buzón de recursos:

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

   Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False. Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).

   Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs". Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   Una vez que tengas una directiva compatible, tendrás que aplicar dicha directiva a la cuenta del dispositivo.

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. Es necesario establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Conexión a Azure AD.
    
   Primero debes instalar el módulo de Azure AD para PowerShell, versión 2. Desde un símbolo del sistema con privilegios elevados, ejecuta el siguiente comando:
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta. Puedes ejecutar este cmdlet para conectarte.

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. Si decides que la contraseña no expire, también puedes establecerlo con los cmdlets de PowerShell. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub requiere una licencia para la funcionalidad Skype Empresarial. Para habilitar Skype Empresarial, tu entorno deberá cumplir los [requisitos previos de Skype Empresarial Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).
   
   A continuación, puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.

   Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"
    
   Get-AzureADSubscribedSku | Select Sku*,*Units
   $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
   $License.SkuId = SkuId You selected 
    
   $AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
   $AssignedLicenses.AddLicenses = $License
   $AssignedLicenses.RemoveLicenses = @()
    
   Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
   ```

8. Habilita la cuenta del dispositivo con Skype Empresarial.
   Si no está instalado el módulo de PowerShell de Skype Empresarial, [descarga el módulo de Windows PowerShell de Skype Empresarial Online](https://www.microsoft.com/download/details.aspx?id=39366). 

   - Empieza por crear una sesión remota de PowerShell desde un PC.

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - A continuación, si no conoces con seguridad qué valor usar para el parámetro `RegistrarPool` en tu entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet (por ejemplo, <em>alice@contoso.com</em>):

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       O mediante el establecimiento de una variable
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - Habilita la cuenta de Surface Hub con el siguiente cmdlet:
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       O usando la variable $strRegistarPool de más arriba
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.






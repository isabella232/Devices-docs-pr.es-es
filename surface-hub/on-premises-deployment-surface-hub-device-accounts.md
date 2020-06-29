---
title: Implementación local de bosque único (Surface Hub)
description: En este tema se explica cómo agregar una cuenta del dispositivo al Microsoft Surface Hub cuando tengas una implementación de bosque único local.
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: implementación de bosque único, implementación local, cuenta del dispositivo, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836169"
---
# Implementación local de Surface Hub en un entorno de bosque único


En este tema se explica cómo agregar una cuenta del dispositivo al Microsoft Surface Hub cuando tengas una implementación de bosque único local.

Si tienes una implementación de bosque único local con Microsoft Exchange 2013 o superior y Skype Empresarial 2013 o posterior, puedes [usar los scripts de PowerShell proporcionados](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para crear cuentas del dispositivo. Si estás usando una implementación de bosques múltiples, consulta [On-premises deployment for Surface Hub in a multi-forest environment (Implementación local de Surface Hub en un entorno de bosques múltiples)](on-premises-deployment-surface-hub-multi-forest.md).

1. Inicia una sesión de PowerShell remoto desde un equipo y conéctate a Exchange.

   Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.

   Ten en cuenta aquí que `$strExchangeServer` es el nombre de dominio completo (FQDN) del servidor Exchange y que `$strLyncFQDN` es el FQDN de tu Skype Empresarial Server.

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. Después de establecer una sesión, podrás crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón existente de la sala. Esto permitirá autenticar la cuenta en el Surface Hub.

   Si vas a cambiar un buzón de recursos existente:

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   Si vas a crear un nuevo buzón de recursos:

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> Es necesario habilitar la autenticación básica del directorio virtual de ActiveSync porque Surface Hub no puede autenticarse con otros métodos de autenticación.

3. Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

   Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False. Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).

   Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs". Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   Una vez que tengas una directiva compatible, necesitarás aplicar la directiva a la cuenta del dispositivo. Sin embargo, las directivas solo se pueden aplicar a las cuentas de usuario y no a los buzones de recursos. Tienes que convertir el buzón en un tipo de usuario, aplicar la directiva y, a continuación, volver a convertirlo en un buzón; es posible que tengas que volver a habilitarlo y establecer la contraseña de nuevo también.

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión para los usuarios. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. Habilita la cuenta en Active Directory, de modo que se autenticará en el Surface Hub.

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. Habilita la cuenta del dispositivo con Skype Empresarial habilitando tu cuenta de AD de Surface Hub en un grupo de Skype Empresarial Server:

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   Debes usar la dirección de Protocolo de inicio de sesión (SIP) y el controlador de dominio en el Surface Hub, junto con tu propio identificador de grupo de Skype Empresarial Server e identidad de usuario.

8. OPCIONAL: también puedes permitir que el Surface Hub realice y reciba llamadas de red telefónica conmutada (RTC) habilitando Telefonía IP empresarial para tu cuenta. La Telefonía IP empresarial no es un requisito de Surface Hub, pero si quieres la funcionalidad de marcado RTC para el cliente de Surface Hub, aquí te mostramos cómo habilitarla:

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   De nuevo, debe reemplazar el controlador de dominio y los ejemplos de números de teléfono proporcionados por su propia información. El valor del parámetro `$true` permanece igual.
    

 ## Deshabilitar el correo electrónico anónimo y la mensajería instantánea




Surface Hub usa una cuenta de dispositivo para proporcionar servicios de correo electrónico y colaboración (mensajería instantánea, vídeo, voz). Esta cuenta de dispositivo se usa como la identidad de origen (la "de la" fiesta) Cuando envías mensajes de correo electrónico, mensajes instantáneos y llamadas. Puesto que esta cuenta no proviene de un usuario individual identificable, se considera "anónimo" porque se originó desde la cuenta de dispositivo de Surface Hub.  

Supongamos que tiene una directiva de cliente por usuario asignada a cada uno de los dispositivos de la sala de reuniones con una identidad de **SurfaceHubPolicy**. Para deshabilitar el correo electrónico anónimo y la mensajería, agregue un clientPolicyEntry a esta directiva de cliente con los comandos siguientes.

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

Para comprobar que la Directiva se ha configurado:

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

El resultado debe ser:

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
Para cambiar la entrada de la Directiva:

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
Para quitar la entrada de la Directiva:

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 






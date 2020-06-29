---
title: Implementación local de bosques múltiples (Surface Hub)
description: En este tema se explica cómo agregar una cuenta del dispositivo al Microsoft Surface Hub cuando tengas una implementación local de bosques múltiples.
keywords: implementación de bosques múltiples, implementación local, cuenta del dispositivo, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836137"
---
# Implementación local de Surface Hub en un entorno de bosques múltiples


En este tema se explica cómo agregar una cuenta del dispositivo al Microsoft Surface Hub cuando tengas una implementación local de bosques múltiples.

Si tienes una implementación local de bosques múltiples con Microsoft Exchange 2013 o superior y Skype Empresarial 2013 o posterior, puedes [usar los scripts de PowerShell proporcionados](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para crear cuentas del dispositivo. Si estás usando una implementación de bosque único, consulta [Implementación local de Surface Hub en un entorno de bosque único](on-premises-deployment-surface-hub-device-accounts.md).

1.  Inicia una sesión de PowerShell remoto desde un equipo y conéctate a Exchange.

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

2.  Después de establecer una sesión, crea un nuevo buzón de correo en el bosque de recursos. Esto permitirá autenticar la cuenta en el Surface Hub.

    Si vas a cambiar un buzón de recursos existente:

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

    Los dispositivos Surface Hub solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en **False**. Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).

    Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs". Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    Una vez que tengas una directiva compatible, tendrás que aplicar dicha directiva a la cuenta del dispositivo. 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión para los usuarios. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información. Esto debería configurarse en el bosque de usuarios.

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  Habilita la cuenta en Active Directory, de modo que se autenticará en el Surface Hub. Esto debería configurarse en el bosque de usuarios.

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. Ahora debes cambiar el buzón de correo de sala a un buzón de correo vinculado:

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  Habilita la cuenta del dispositivo con Skype Empresarial habilitando tu cuenta de AD de Surface Hub en un grupo de Skype Empresarial Server:

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    Debes usar la dirección de Protocolo de inicio de sesión (SIP) y el controlador de dominio en el Surface Hub, junto con tu propio identificador de grupo de Skype Empresarial Server e identidad de usuario.


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
 






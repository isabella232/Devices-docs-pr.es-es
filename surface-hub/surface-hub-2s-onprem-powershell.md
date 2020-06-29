---
title: Configurar las cuentas locales de Surface Hub 2 con PowerShell
description: Más información sobre cómo configurar Surface Hub 2 cuentas locales con PowerShell
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836642"
---
# Configurar las cuentas locales de Surface Hub 2 con PowerShell

## Conectarse a Exchange Server PowerShell

> [!IMPORTANT]
> Necesitará el nombre de dominio completo (FQDN) para el servicio de acceso de cliente del servidor de Exchange local para algunos de estos cmdlets.

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## Crear la cuenta del dispositivo

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## Configurar el procesamiento automático del calendario

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## Habilitar el objeto de Skype empresarial

> [!NOTE]
> Es importante que conozca el FQDN del grupo de servidores de registro de Skype empresarial.

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## Directiva de buzón de dispositivo móvil

Es posible que tenga que crear una directiva de buzón de dispositivo móvil (también conocida como Directiva de ActiveSync) para permitir que su Surface Hub se conecte a su entorno local o en línea.

## Crear una directiva de buzón de dispositivo móvil de Surface Hub

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## Configuración adicional

Se recomienda agregar una sugerencia a las salas de Surface hub para que los usuarios recuerden que la reunión es una reunión de Skype empresarial o de equipos:

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```

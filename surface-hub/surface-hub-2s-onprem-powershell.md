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
# <span data-ttu-id="bc590-104">Configurar las cuentas locales de Surface Hub 2 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc590-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="bc590-105">Conectarse a Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="bc590-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc590-106">Necesitará el nombre de dominio completo (FQDN) para el servicio de acceso de cliente del servidor de Exchange local para algunos de estos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="bc590-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="bc590-107">Crear la cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc590-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="bc590-108">Configurar el procesamiento automático del calendario</span><span class="sxs-lookup"><span data-stu-id="bc590-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="bc590-109">Habilitar el objeto de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="bc590-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="bc590-110">Es importante que conozca el FQDN del grupo de servidores de registro de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bc590-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="bc590-111">Directiva de buzón de dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="bc590-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="bc590-112">Es posible que tenga que crear una directiva de buzón de dispositivo móvil (también conocida como Directiva de ActiveSync) para permitir que su Surface Hub se conecte a su entorno local o en línea.</span><span class="sxs-lookup"><span data-stu-id="bc590-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="bc590-113">Crear una directiva de buzón de dispositivo móvil de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="bc590-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="bc590-114">Configuración adicional</span><span class="sxs-lookup"><span data-stu-id="bc590-114">Additional settings</span></span>

<span data-ttu-id="bc590-115">Se recomienda agregar una sugerencia a las salas de Surface hub para que los usuarios recuerden que la reunión es una reunión de Skype empresarial o de equipos:</span><span class="sxs-lookup"><span data-stu-id="bc590-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```

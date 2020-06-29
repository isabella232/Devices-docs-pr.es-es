---
title: Crear cuenta del dispositivo para Surface Hub 2S
description: Esta página describe el procedimiento para crear la cuenta del dispositivo Surface Hub 2S.
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
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836378"
---
# <span data-ttu-id="e457b-104">Crear cuenta del dispositivo para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="e457b-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="e457b-105">La creación de una cuenta de dispositivo de Surface Hub (también conocida como buzón de sala) permite a Surface Hub 2S recibir, aprobar o rechazar convocatorias de reunión y unirse a reuniones con Microsoft Teams o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e457b-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="e457b-106">Configurar la cuenta del dispositivo al configurar la configuración rápida (OOBE).</span><span class="sxs-lookup"><span data-stu-id="e457b-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="e457b-107">Si es necesario, puede cambiarlo más tarde (sin pasar por la configuración de OOBE).</span><span class="sxs-lookup"><span data-stu-id="e457b-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="e457b-108">A diferencia de los buzones de sala estándar que permanecen deshabilitados de forma predeterminada, debe habilitar la cuenta de dispositivo Surface Hub 2S para que inicie sesión en Microsoft Teams y Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="e457b-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="e457b-109">Surface Hub 2S depende de Exchange ActiveSync, que requiere una directiva de buzón de ActiveSync en la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e457b-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="e457b-110">Aplicar la Directiva de buzón de correo predeterminada de ActiveSync que se incluye con Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e457b-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="e457b-111">Cree la cuenta con el centro de administración de Microsoft 365 o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e457b-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="e457b-112">Puede usar Exchange Online PowerShell para configurar características específicas, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="e457b-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="e457b-113">Procesamiento de calendario para todas las cuentas de dispositivos de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="e457b-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="e457b-114">Respuestas automáticas personalizadas a solicitudes de programación.</span><span class="sxs-lookup"><span data-stu-id="e457b-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="e457b-115">Si la Directiva de buzón predeterminada de ActiveSync ya ha sido modificada por otra persona u otro proceso, probablemente tendrá que crear y asignar una nueva Directiva de buzón de ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="e457b-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="e457b-116">La cuenta del dispositivo Surface Hub no admite proveedores de identidades federados de terceros (FIPs) y debe ser una cuenta estándar de Active Directory o de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e457b-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="e457b-117">Crear una cuenta con el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e457b-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e457b-118">En el centro de administración de Microsoft 365, vaya a **recursos** y elija **salas & equipo** y, a continuación, seleccione **+ sala**.</span><span class="sxs-lookup"><span data-stu-id="e457b-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="e457b-119">Proporcione un nombre y una dirección de correo electrónico para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e457b-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="e457b-120">No cambie la configuración restante en el estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e457b-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Proporcionar un nombre y una dirección de correo electrónico](images/sh2-account2.png)

   ![Dejar los valores restantes sin cambios en el estado predeterminado](images/sh2-account3.png)

3. <span data-ttu-id="e457b-123">Establezca la contraseña de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e457b-123">Set the password for the device account.</span></span> <span data-ttu-id="e457b-124">Para establecer la contraseña, elija **usuarios** y, a continuación, seleccione **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="e457b-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="e457b-125">Ahora busque el usuario recién creado para establecer la contraseña.</span><span class="sxs-lookup"><span data-stu-id="e457b-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="e457b-126">Asegúrese de **no** seleccionar la opción hacer que **este usuario cambie la contraseña la primera vez que inicie sesión.**</span><span class="sxs-lookup"><span data-stu-id="e457b-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Establecer la contraseña de la cuenta del dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="e457b-128">Asigne el salón con una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e457b-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="e457b-129">Se recomienda asignar la licencia de la **sala de reuniones** de Office 365, una nueva opción que habilita automáticamente la cuenta de Skype empresarial online y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e457b-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Asignar licencia de Office 365](images/sh2-account5.png)

### <span data-ttu-id="e457b-131">Finalizar la configuración a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e457b-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="e457b-132">**Skype para empresas:** Solo para Skype empresarial (local o en línea), puede habilitar el objeto de Skype empresarial ejecutando **enable-CsMeetingRoom** para habilitar características como el aviso de la sala de reuniones para la suspensión de audio y recepción.</span><span class="sxs-lookup"><span data-stu-id="e457b-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="e457b-133">**Microsoft Teams y calendario de Skype empresarial:** Establecer el [**procesamiento automático de calendario**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="e457b-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="e457b-134">Crear una cuenta con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e457b-134">Create account using PowerShell</span></span>

<span data-ttu-id="e457b-135">En lugar de usar el portal del centro de administración de Microsoft, puede crear la cuenta con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e457b-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="e457b-136">Conectarse a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e457b-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="e457b-137">Crear un nuevo buzón de sala</span><span class="sxs-lookup"><span data-stu-id="e457b-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="e457b-138">Establecer el procesamiento automático de los calendarios</span><span class="sxs-lookup"><span data-stu-id="e457b-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="e457b-139">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="e457b-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="e457b-140">Conectarse a Skype empresarial online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e457b-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="e457b-141">Requisitos previos de instalación</span><span class="sxs-lookup"><span data-stu-id="e457b-141">Install pre-requisites</span></span>

- [<span data-ttu-id="e457b-142">Paquete redistribuible de Visual C++ 2017</span><span class="sxs-lookup"><span data-stu-id="e457b-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="e457b-143">Módulo de PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e457b-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```

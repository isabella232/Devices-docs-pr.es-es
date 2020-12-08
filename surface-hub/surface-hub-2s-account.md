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
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196733"
---
# <span data-ttu-id="dcf52-104">Crear cuenta del dispositivo para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="dcf52-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="dcf52-105">La creación de una cuenta de dispositivo de Surface Hub (también conocida como buzón de sala) permite a Surface Hub 2S recibir, aprobar o rechazar convocatorias de reunión y unirse a reuniones con Microsoft Teams o Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="dcf52-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="dcf52-106">Configurar la cuenta del dispositivo al configurar la configuración rápida (OOBE).</span><span class="sxs-lookup"><span data-stu-id="dcf52-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="dcf52-107">Si es necesario, puede cambiarlo más tarde (sin pasar por la configuración de OOBE).</span><span class="sxs-lookup"><span data-stu-id="dcf52-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="dcf52-108">A diferencia de los buzones de sala estándar que permanecen deshabilitados de forma predeterminada, debe habilitar la cuenta de dispositivo Surface Hub 2S para que inicie sesión en Microsoft Teams y Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="dcf52-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="dcf52-109">Surface Hub 2S depende de Exchange ActiveSync, que requiere una directiva de buzón de ActiveSync en la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dcf52-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="dcf52-110">Aplicar la Directiva de buzón de correo predeterminada de ActiveSync que se incluye con Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dcf52-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="dcf52-111">Cree la cuenta con el centro de administración de Microsoft 365 o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcf52-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="dcf52-112">Puede usar Exchange Online PowerShell para configurar características específicas, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dcf52-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="dcf52-113">Procesamiento de calendario para todas las cuentas de dispositivos de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="dcf52-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="dcf52-114">Respuestas automáticas personalizadas a solicitudes de programación.</span><span class="sxs-lookup"><span data-stu-id="dcf52-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="dcf52-115">Si la Directiva de buzón predeterminada de ActiveSync ya ha sido modificada por otra persona u otro proceso, probablemente tendrá que crear y asignar una nueva Directiva de buzón de ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="dcf52-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="dcf52-116">La cuenta del dispositivo Surface Hub no admite proveedores de identidades federados de terceros (FIPs) y debe ser una cuenta estándar de Active Directory o de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dcf52-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="dcf52-117">Crear una cuenta con el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dcf52-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="dcf52-118">En el centro de administración de Microsoft 365, vaya a **recursos** y elija **salas & equipo** y, a continuación, seleccione **+ sala**.</span><span class="sxs-lookup"><span data-stu-id="dcf52-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="dcf52-119">Proporcione un nombre y una dirección de correo electrónico para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dcf52-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="dcf52-120">No cambie la configuración restante en el estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dcf52-120">Leave remaining settings unchanged in the default state.</span></span>

   ![Proporcionar un nombre y una dirección de correo electrónico](images/sh2-account2.png)

   ![Dejar los valores restantes sin cambios en el estado predeterminado](images/sh2-account3.png)

3. <span data-ttu-id="dcf52-123">Establezca la contraseña de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dcf52-123">Set the password for the device account.</span></span> <span data-ttu-id="dcf52-124">Para establecer la contraseña, elija **usuarios** y, a continuación, seleccione **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="dcf52-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="dcf52-125">Ahora busque el usuario recién creado para establecer la contraseña.</span><span class="sxs-lookup"><span data-stu-id="dcf52-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="dcf52-126">Asegúrese de **no** seleccionar la opción hacer que **este usuario cambie la contraseña la primera vez que inicie sesión.**</span><span class="sxs-lookup"><span data-stu-id="dcf52-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Establecer la contraseña de la cuenta del dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="dcf52-128">Asigne el salón con una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dcf52-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="dcf52-129">Se recomienda asignar la licencia de la **sala de reuniones** de Office 365, una nueva opción que habilita automáticamente la cuenta de Skype empresarial online y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dcf52-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![Asignar licencia de Office 365](images/sh2-account5.png)

### <span data-ttu-id="dcf52-131">Finalizar la configuración a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcf52-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="dcf52-132">**Microsoft Teams y calendario de Skype empresarial:** Establecer el [**procesamiento automático de calendario**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="dcf52-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="dcf52-133">Crear una cuenta con PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcf52-133">Create account using PowerShell</span></span>

<span data-ttu-id="dcf52-134">En lugar de usar el portal del centro de administración de Microsoft, puede crear la cuenta con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcf52-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="dcf52-135">Conectarse a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcf52-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="dcf52-136">Crear buzón</span><span class="sxs-lookup"><span data-stu-id="dcf52-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="dcf52-137">Establecer el procesamiento automático de los calendarios</span><span class="sxs-lookup"><span data-stu-id="dcf52-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="dcf52-138">Habilitar ActiveSync si se requiere el uso de la aplicación de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="dcf52-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="dcf52-139">La directiva predeterminada de ActiveSync funcionará si unchnaged.</span><span class="sxs-lookup"><span data-stu-id="dcf52-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="dcf52-140">En caso contrario, crea una nueva Directiva y la asigna.</span><span class="sxs-lookup"><span data-stu-id="dcf52-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="dcf52-141">Conexión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="dcf52-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="dcf52-142">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="dcf52-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="dcf52-143">Comprobar si hay licencias disponibles</span><span class="sxs-lookup"><span data-stu-id="dcf52-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```
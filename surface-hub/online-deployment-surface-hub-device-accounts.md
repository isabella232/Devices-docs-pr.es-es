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
# <span data-ttu-id="854d5-104">Implementación en línea con Office 365 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="854d5-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="854d5-105">Este tema ofrece instrucciones para agregar una cuenta del dispositivo al Microsoft Surface Hub cuando haya una implementación totalmente en línea.</span><span class="sxs-lookup"><span data-stu-id="854d5-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="854d5-106">Si tienes una implementación totalmente en línea (O365), puedes [usar los scripts de PowerShell proporcionados](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) para crear cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="854d5-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="854d5-107">Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange.</span><span class="sxs-lookup"><span data-stu-id="854d5-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="854d5-108">Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="854d5-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="854d5-109">Después de establecer una sesión, podrás crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón existente de la sala.</span><span class="sxs-lookup"><span data-stu-id="854d5-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="854d5-110">Esto permitirá autenticar la cuenta en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="854d5-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="854d5-111">Si vas a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="854d5-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="854d5-112">Si vas a crear un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="854d5-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="854d5-113">Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="854d5-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="854d5-114">Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False.</span><span class="sxs-lookup"><span data-stu-id="854d5-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="854d5-115">Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).</span><span class="sxs-lookup"><span data-stu-id="854d5-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="854d5-116">Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="854d5-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="854d5-117">Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="854d5-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="854d5-118">Una vez que tengas una directiva compatible, tendrás que aplicar dicha directiva a la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="854d5-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="854d5-119">Es necesario establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="854d5-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="854d5-120">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="854d5-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="854d5-121">Conexión a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="854d5-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="854d5-122">Primero debes instalar el módulo de Azure AD para PowerShell, versión 2.</span><span class="sxs-lookup"><span data-stu-id="854d5-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="854d5-123">Desde un símbolo del sistema con privilegios elevados, ejecuta el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="854d5-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="854d5-124">Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="854d5-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="854d5-125">Puedes ejecutar este cmdlet para conectarte.</span><span class="sxs-lookup"><span data-stu-id="854d5-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="854d5-126">Si decides que la contraseña no expire, también puedes establecerlo con los cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="854d5-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="854d5-127">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="854d5-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="854d5-128">Surface Hub requiere una licencia para la funcionalidad Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="854d5-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="854d5-129">Para habilitar Skype Empresarial, tu entorno deberá cumplir los [requisitos previos de Skype Empresarial Online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="854d5-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="854d5-130">A continuación, puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.</span><span class="sxs-lookup"><span data-stu-id="854d5-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="854d5-131">Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="854d5-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="854d5-132">Habilita la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="854d5-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="854d5-133">Si no está instalado el módulo de PowerShell de Skype Empresarial, [descarga el módulo de Windows PowerShell de Skype Empresarial Online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="854d5-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="854d5-134">Empieza por crear una sesión remota de PowerShell desde un PC.</span><span class="sxs-lookup"><span data-stu-id="854d5-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="854d5-135">A continuación, si no conoces con seguridad qué valor usar para el parámetro `RegistrarPool` en tu entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet (por ejemplo, <em>alice@contoso.com</em>):</span><span class="sxs-lookup"><span data-stu-id="854d5-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="854d5-136">O mediante el establecimiento de una variable</span><span class="sxs-lookup"><span data-stu-id="854d5-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="854d5-137">Habilita la cuenta de Surface Hub con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="854d5-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="854d5-138">O usando la variable $strRegistarPool de más arriba</span><span class="sxs-lookup"><span data-stu-id="854d5-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="854d5-139">Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="854d5-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>






---
title: Implementación híbrida (Surface Hub)
description: Una implementación híbrida requiere un procesamiento especial para configurar una cuenta del dispositivo para Microsoft Surface Hub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: implementación híbrida, cuenta del dispositivo para Surface Hub, Exchange hospedado de forma local, Exchange hospedado en línea
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836202"
---
# <span data-ttu-id="b653a-104">Implementación híbrida (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b653a-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="b653a-105">Una implementación híbrida requiere un procesamiento especial para configurar una cuenta del dispositivo para Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="b653a-106">Si estás usando una implementación híbrida, en la que la organización tenga una mezcla de servicios, algunos hospedados de forma local y algunos hospedados en línea, tu configuración dependerá de dónde esté hospedado cada servicio.</span><span class="sxs-lookup"><span data-stu-id="b653a-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="b653a-107">Este tema se centra en las implementaciones híbridas para [Exchange hospedado de forma local](#exchange-on-premises), [Exchange hospedado en línea](#exchange-online), Skype Empresarial, Skype Empresarial Online y Skype Empresarial híbrido.</span><span class="sxs-lookup"><span data-stu-id="b653a-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="b653a-108">Dado que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas.</span><span class="sxs-lookup"><span data-stu-id="b653a-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="b653a-109">El siguiente proceso funcionará en muchas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="b653a-109">The following process will work for many configurations.</span></span> <span data-ttu-id="b653a-110">Si el proceso no es adecuado para la instalación, te recomendamos que uses PowerShell (consulta [Apéndice: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) para lograr el mismo resultado final que se describe aquí y para ver otras opciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="b653a-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="b653a-111">A continuación, debes usar el script de PowerShell proporcionado para comprobar tu configuración de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="b653a-112">(Consulta [Script de comprobación de cuenta](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)).</span><span class="sxs-lookup"><span data-stu-id="b653a-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="b653a-113">En un entorno híbrido de Exchange, siga los pasos para la [implementación local de Exchange](#exchange-on-premises).</span><span class="sxs-lookup"><span data-stu-id="b653a-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="b653a-114">Para mover objetos de Exchange a Office 365, use el cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .</span><span class="sxs-lookup"><span data-stu-id="b653a-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="b653a-115">Exchange local</span><span class="sxs-lookup"><span data-stu-id="b653a-115">Exchange on-premises</span></span>

<span data-ttu-id="b653a-116">Usa este procedimiento si usas Exchange de forma local.</span><span class="sxs-lookup"><span data-stu-id="b653a-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="b653a-117">Para este procedimiento, usaremos las herramientas de administración de AD para agregar una dirección de correo electrónico para tu cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="b653a-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="b653a-118">Esta cuenta se sincronizará con Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="b653a-119">En la herramienta de AD **Usuarios y equipos de Active Directory** , haz clic con el botón derecho en la carpeta o en la unidad organizativa en la que se crearán tus cuentas de Surface Hub, haz clic en **Nuevo**y **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="b653a-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="b653a-120">Escribe el nombre para mostrar del cmdlet anterior en el cuadro **Nombre completo** y, a continuación, el alias en el cuadro **Nombre de inicio de sesión de usuario** .</span><span class="sxs-lookup"><span data-stu-id="b653a-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="b653a-121">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b653a-121">Click **Next**.</span></span><p>

![Cuadro de objeto nuevo para crear un nuevo usuario en Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="b653a-123">Escribe la contraseña para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-123">Type the password for this account.</span></span> <span data-ttu-id="b653a-124">Debes escribirla de nuevo para su comprobación.</span><span class="sxs-lookup"><span data-stu-id="b653a-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="b653a-125">Asegúrate de que la casilla **La contraseña nunca expira** sea la única opción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b653a-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="b653a-126">**Importante** Seleccionar **La contraseña nunca expira** es un requisito de Skype Empresarial en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="b653a-127">Las reglas de dominio pueden prohibir las contraseñas que no expiren.</span><span class="sxs-lookup"><span data-stu-id="b653a-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="b653a-128">Si es así, debes crear una excepción para cada cuenta del dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Imagen que muestra el cuadro de diálogo de contraseña.](images/hybriddeployment-02a.png)

-   <span data-ttu-id="b653a-130">Haz clic en **Finalizar** para crear la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-130">Click **Finish** to create the account.</span></span>

![Imagen con el nombre de la cuenta, el nombre de inicio de sesión y las opciones de contraseña para el nuevo usuario.](images/hybriddeployment-03a.png)

2. <span data-ttu-id="b653a-132">Habilitar el buzón remoto.</span><span class="sxs-lookup"><span data-stu-id="b653a-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="b653a-133">Abre el shell de administración de Exchange local con permisos de administrador y ejecuta este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b653a-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="b653a-134">Si no tienes un entorno de Exchange local para ejecutar este cmdlet, puedes realizar los mismos cambios directamente en el objeto de Active Directory para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="b653a-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="b653a-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="b653a-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="b653a-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="b653a-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="b653a-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="b653a-138">Después de crear la cuenta, ejecuta una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="b653a-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="b653a-139">Cuando haya finalizado, vaya a la página usuarios del centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se ha fusionado en línea.</span><span class="sxs-lookup"><span data-stu-id="b653a-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="b653a-140">Conéctate a Microsoft Exchange Online y establece algunas propiedades para la cuenta en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="b653a-141">Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange.</span><span class="sxs-lookup"><span data-stu-id="b653a-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="b653a-142">Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="b653a-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="b653a-143">Los siguientes pasos se ejecutarán en tu inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="b653a-144">Crea una nueva directiva de Exchange ActiveSync o usa una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="b653a-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="b653a-145">Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="b653a-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="b653a-146">Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False.</span><span class="sxs-lookup"><span data-stu-id="b653a-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="b653a-147">Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).</span><span class="sxs-lookup"><span data-stu-id="b653a-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="b653a-148">Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="b653a-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="b653a-149">Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="b653a-150">Una vez que tenga una directiva compatible, tendrá que aplicar la Directiva a la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="b653a-151">Establecer las propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b653a-151">Set Exchange properties.</span></span>

<span data-ttu-id="b653a-152">Establecer propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b653a-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="b653a-153">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b653a-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="b653a-154">Conexión a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b653a-154">Connect to Azure AD.</span></span>

<span data-ttu-id="b653a-155">Primero debes instalar el módulo de Azure AD para PowerShell, versión 2.</span><span class="sxs-lookup"><span data-stu-id="b653a-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="b653a-156">En un símbolo del sistema de PowerShell con privilegios elevados, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b653a-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="b653a-157">Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="b653a-158">Puedes ejecutar este cmdlet para conectarte.</span><span class="sxs-lookup"><span data-stu-id="b653a-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="b653a-159">Asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="b653a-160">La cuenta del dispositivo debe tener una licencia válida de Office 365 (O365); de otro modo, Exchange y Skype Empresarial no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="b653a-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="b653a-161">Si tienes la licencia, debes asignar una ubicación de uso a tu cuenta del dispositivo; esto determina los SKU de la licencia que están disponibles para tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="b653a-162">Puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.</span><span class="sxs-lookup"><span data-stu-id="b653a-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="b653a-163">Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="b653a-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="b653a-164">A continuación, habilita la cuenta del dispositivo con [Skype Empresarial Online](#skype-for-business-online), [Skype Empresarial local](#skype-for-business-on-premises) o [Skype Empresarial híbrido](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="b653a-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="b653a-165">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b653a-165">Skype for Business Online</span></span>

<span data-ttu-id="b653a-166">Para habilitar Skype Empresarial Online, los usuarios de inquilino deben tener buzones de Exchange (se requiere al menos un buzón de Exchange en el inquilino).</span><span class="sxs-lookup"><span data-stu-id="b653a-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="b653a-167">En la siguiente tabla se explica qué planes o servicios adicionales necesitas.</span><span class="sxs-lookup"><span data-stu-id="b653a-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="b653a-168">Escenario de sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="b653a-168">Skype room system scenario</span></span> | <span data-ttu-id="b653a-169">Si tiene Office 365 Premium, aplicaciones de Microsoft 365 para empresas o plan independiente 2 de Skype empresarial, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b653a-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="b653a-170">Si tienes un plan de empresa, necesitas lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b653a-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="b653a-171">Si tiene Skype empresarial Server 2015 (local o híbrido), necesita:</span><span class="sxs-lookup"><span data-stu-id="b653a-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="b653a-172">Unirse a una reunión programada</span><span class="sxs-lookup"><span data-stu-id="b653a-172">Join a scheduled meeting</span></span> | <span data-ttu-id="b653a-173">Plan 1 independiente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b653a-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="b653a-174">E1, 3, 4 o 5</span><span class="sxs-lookup"><span data-stu-id="b653a-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="b653a-175">CAL estándar de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b653a-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="b653a-176">Iniciar una reunión ad-hoc</span><span class="sxs-lookup"><span data-stu-id="b653a-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="b653a-177">Plan 2 independiente de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b653a-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="b653a-178">E 1, 3, 4 o 5</span><span class="sxs-lookup"><span data-stu-id="b653a-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="b653a-179">CAL estándar o CAL empresarial de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b653a-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="b653a-180">Iniciar una reunión ad hoc y marcar de una reunión a números de teléfono</span><span class="sxs-lookup"><span data-stu-id="b653a-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="b653a-181">Plan independiente 2 de Skype empresarial con audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b653a-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="b653a-182">**Nota** La facturación de consumo RTC es opcional</span><span class="sxs-lookup"><span data-stu-id="b653a-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="b653a-183">E1 o E3 con audioconferencias o E5</span><span class="sxs-lookup"><span data-stu-id="b653a-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="b653a-184">CAL estándar o CAL empresarial de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b653a-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="b653a-185">Proporcionar a la sala un número de teléfono y realizar o recibir llamadas desde la sala, o unirse a una conferencia de acceso telefónico con un número de teléfono</span><span class="sxs-lookup"><span data-stu-id="b653a-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="b653a-186">Plan independiente 2 de Skype empresarial con sistema telefónico y un plan de llamadas de voz RTC</span><span class="sxs-lookup"><span data-stu-id="b653a-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="b653a-187">E1 o E3 con el sistema telefónico y un plan de llamadas de voz RTC, o E5</span><span class="sxs-lookup"><span data-stu-id="b653a-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="b653a-188">CAL estándar o CAL Plus de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b653a-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="b653a-189">En la siguiente tabla se indican los planes de Office 365 y las opciones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b653a-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="b653a-190">Plan de O365</span><span class="sxs-lookup"><span data-stu-id="b653a-190">O365 Plan</span></span> | <span data-ttu-id="b653a-191">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b653a-191">Skype for Business</span></span> | <span data-ttu-id="b653a-192">Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="b653a-192">Phone System</span></span> | <span data-ttu-id="b653a-193">Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="b653a-193">Audio Conferencing</span></span> | <span data-ttu-id="b653a-194">Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="b653a-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="b653a-195">O365 Empresa Essentials</span><span class="sxs-lookup"><span data-stu-id="b653a-195">O365 Business Essentials</span></span> | <span data-ttu-id="b653a-196">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-196">Included</span></span> |  |  |  |
| <span data-ttu-id="b653a-197">O365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="b653a-197">O365 Business Premium</span></span> | <span data-ttu-id="b653a-198">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-198">Included</span></span> |  |  |  |
| <span data-ttu-id="b653a-199">E1</span><span class="sxs-lookup"><span data-stu-id="b653a-199">E1</span></span> | <span data-ttu-id="b653a-200">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-200">Included</span></span> | <span data-ttu-id="b653a-201">Complemento</span><span class="sxs-lookup"><span data-stu-id="b653a-201">Add-on</span></span> | <span data-ttu-id="b653a-202">Complemento</span><span class="sxs-lookup"><span data-stu-id="b653a-202">Add-on</span></span> | <span data-ttu-id="b653a-203">Complemento (requiere el complemento del sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="b653a-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="b653a-204">E3</span><span class="sxs-lookup"><span data-stu-id="b653a-204">E3</span></span> | <span data-ttu-id="b653a-205">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-205">Included</span></span> | <span data-ttu-id="b653a-206">Complemento</span><span class="sxs-lookup"><span data-stu-id="b653a-206">Add-on</span></span> | <span data-ttu-id="b653a-207">Complemento</span><span class="sxs-lookup"><span data-stu-id="b653a-207">Add-on</span></span> | <span data-ttu-id="b653a-208">Complemento (requiere el complemento del sistema telefónico)</span><span class="sxs-lookup"><span data-stu-id="b653a-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="b653a-209">E5</span><span class="sxs-lookup"><span data-stu-id="b653a-209">E5</span></span> | <span data-ttu-id="b653a-210">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-210">Included</span></span> | <span data-ttu-id="b653a-211">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-211">Included</span></span> | <span data-ttu-id="b653a-212">Incluido</span><span class="sxs-lookup"><span data-stu-id="b653a-212">Included</span></span> | <span data-ttu-id="b653a-213">Complemento</span><span class="sxs-lookup"><span data-stu-id="b653a-213">Add-on</span></span>  |

1. <span data-ttu-id="b653a-214">Para comenzar, crea una sesión remota de PowerShell desde un equipo al entorno de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="b653a-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="b653a-215">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b653a-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="b653a-216">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b653a-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="b653a-217">Asigna la licencia de Skype Empresarial a tu cuenta de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="b653a-218">Una vez que hayas completado los pasos anteriores para habilitar tu cuenta de Surface Hub en Skype Empresarial Online, debes asignar una licencia al Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="b653a-219">Con el portal administrativo de O365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="b653a-220">Inicia sesión como administrador de inquilinos, abre el portal de administración de O365 y haz clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="b653a-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="b653a-221">Haz clic en **Usuarios y grupos locales** y después en **Agregar usuarios, restablecer contraseñas y más**.</span><span class="sxs-lookup"><span data-stu-id="b653a-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="b653a-222">Haz clic en la cuenta de Surface Hub y, a continuación, haz clic en el icono de lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="b653a-223">Haz clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="b653a-223">Click **Licenses**.</span></span>

- <span data-ttu-id="b653a-224">En **asignar licencias**, seleccione Skype empresarial (plan 1) o Skype empresarial (plan 2), en función de sus requisitos de licencia y telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b653a-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="b653a-225">Tendrá que usar una licencia de plan 2 Si desea usar la telefonía IP empresarial en su Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="b653a-226">Haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b653a-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b653a-227">También puedes usar el Módulo de Microsoft Azure Active Directory para Windows Powershell para ejecutar los cmdlets necesarios para asignar una de estas licencias, pero esto no se incluye aquí.</span><span class="sxs-lookup"><span data-stu-id="b653a-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="b653a-228">Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="b653a-229">Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="b653a-229">Skype for Business on-premises</span></span>

<span data-ttu-id="b653a-230">Para ejecutar este cmdlet, tendrás que conectarte a uno de los front-end de Skype.</span><span class="sxs-lookup"><span data-stu-id="b653a-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="b653a-231">Abre Skype PowerShell y ejecútalo:</span><span class="sxs-lookup"><span data-stu-id="b653a-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="b653a-232">Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="b653a-232">Skype for Business hybrid</span></span>

<span data-ttu-id="b653a-233">Si tu organización ha configurado la [conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](https://technet.microsoft.com/library/jj205403.aspx), las instrucciones para crear cuentas difiere de una implementación estándar de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="b653a-234">Surface Hub requiere una cuenta de Skype del tipo `meetingroom`, mientras que un usuario normal usaría una cuenta de tipo user en Skype.</span><span class="sxs-lookup"><span data-stu-id="b653a-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="b653a-235">Si el servidor de Skype se configuró para conectividad híbrida donde puede haber usuarios en el servidor local de Skype, así como usuarios hospedados en Office 365, es posible que se produzcan problemas al intentar crear una cuenta de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="b653a-236">En el entorno híbrido de Skype empresarial Server 2015, todos los usuarios que desee en Skype empresarial online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b653a-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="b653a-237">Después, puede mover el usuario a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b653a-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="b653a-238">El movimiento de una cuenta de usuario de local a conectada se realiza mediante el cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b653a-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="b653a-239">Para mover un objeto Csmeetingroom, usa el cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="b653a-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b653a-240">Para usar el cmdlet Move-CsMeetingRoom, debe tener instalado [el paquete de actualización acumulativa de mayo de 2017 6.0.9319.281 para Skype empresarial Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) o [la actualización acumulativa de julio 2017 5.0.8308.992 para Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="b653a-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="b653a-241">Exchange en línea</span><span class="sxs-lookup"><span data-stu-id="b653a-241">Exchange online</span></span>

<span data-ttu-id="b653a-242">Usa este procedimiento si usas Exchange en línea.</span><span class="sxs-lookup"><span data-stu-id="b653a-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="b653a-243">Crear una cuenta de correo electrónico en Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="b653a-244">Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange.</span><span class="sxs-lookup"><span data-stu-id="b653a-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="b653a-245">Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="b653a-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="b653a-246">Configurar un buzón.</span><span class="sxs-lookup"><span data-stu-id="b653a-246">Set up a mailbox.</span></span>

<span data-ttu-id="b653a-247">Después de establecer una sesión, podrás crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón existente de la sala.</span><span class="sxs-lookup"><span data-stu-id="b653a-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="b653a-248">Esto permitirá autenticar la cuenta en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="b653a-249">Si vas a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="b653a-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="b653a-250">Si vas a crear un nuevo buzón de recursos:</span><span class="sxs-lookup"><span data-stu-id="b653a-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="b653a-251">Crear la directiva de Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="b653a-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="b653a-252">Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="b653a-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="b653a-253">Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False.</span><span class="sxs-lookup"><span data-stu-id="b653a-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="b653a-254">Si esto no se establece correctamente, los servicios de Exchange en Surface Hub (correo, calendario y Unión a reuniones) no estarán habilitados.</span><span class="sxs-lookup"><span data-stu-id="b653a-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="b653a-255">Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="b653a-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="b653a-256">Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="b653a-257">Una vez que tenga una directiva compatible, tendrá que aplicar la Directiva a la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="b653a-258">Sin embargo, las directivas solo se pueden aplicar a las cuentas de usuario y no a los buzones de recursos.</span><span class="sxs-lookup"><span data-stu-id="b653a-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="b653a-259">Tienes que convertir el buzón en un tipo de usuario, aplicar la directiva y, a continuación, volver a convertirlo en un buzón; es posible que tengas que volver a habilitarlo y establecer la contraseña de nuevo también.</span><span class="sxs-lookup"><span data-stu-id="b653a-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="b653a-260">Establecer las propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b653a-260">Set Exchange properties.</span></span>

<span data-ttu-id="b653a-261">Se deben establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b653a-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="b653a-262">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b653a-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="b653a-263">Agregue una dirección de correo electrónico para su cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="b653a-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="b653a-264">Para este procedimiento, usaremos las herramientas de administración de AD para agregar una dirección de correo electrónico para tu cuenta de dominio local.</span><span class="sxs-lookup"><span data-stu-id="b653a-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="b653a-265">En la herramienta de AD **Usuarios y equipos de Active Directory** , haz clic con el botón derecho en la carpeta o en la unidad organizativa en la que se crearán tus cuentas de Surface Hub, haz clic en **Nuevo**y **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="b653a-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="b653a-266">Escribe el nombre para mostrar del cmdlet anterior en el cuadro **Nombre completo** y, a continuación, el alias en el cuadro **Nombre de inicio de sesión de usuario** .</span><span class="sxs-lookup"><span data-stu-id="b653a-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="b653a-267">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b653a-267">Click **Next**.</span></span>

![Cuadro de objeto nuevo para crear un nuevo usuario en Active Directory.](images/hybriddeployment-01a.png)

- <span data-ttu-id="b653a-269">Escribe la contraseña para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-269">Type the password for this account.</span></span> <span data-ttu-id="b653a-270">Debes escribirla de nuevo para su comprobación.</span><span class="sxs-lookup"><span data-stu-id="b653a-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="b653a-271">Asegúrate de que la casilla **La contraseña nunca expira** sea la única opción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b653a-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b653a-272">Seleccionar la **contraseña nunca vence** es un requisito para Skype empresarial en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="b653a-273">Las reglas de dominio pueden prohibir las contraseñas que no expiren.</span><span class="sxs-lookup"><span data-stu-id="b653a-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="b653a-274">Si es así, debes crear una excepción para cada cuenta del dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![Imagen que muestra el cuadro de diálogo de contraseña.](images/hybriddeployment-02a.png)

- <span data-ttu-id="b653a-276">Haz clic en **Finalizar** para crear la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-276">Click **Finish** to create the account.</span></span>

![Imagen con el nombre de la cuenta, el nombre de inicio de sesión y las opciones de contraseña para el nuevo usuario.](images/hybriddeployment-03a.png)

6. <span data-ttu-id="b653a-278">Ejecuta la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="b653a-278">Run directory synchronization.</span></span>

<span data-ttu-id="b653a-279">Después de crear la cuenta, ejecuta una sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="b653a-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="b653a-280">Una vez completa, ve a la página de usuarios y comprueba que se combinaron las dos cuentas creadas en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="b653a-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="b653a-281">Conexión a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b653a-281">Connect to Azure AD.</span></span>

<span data-ttu-id="b653a-282">Primero debes instalar el módulo de Azure AD para PowerShell, versión 2.</span><span class="sxs-lookup"><span data-stu-id="b653a-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="b653a-283">En un símbolo del sistema de PowerShell con privilegios elevados, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b653a-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="b653a-284">Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="b653a-285">Puede ejecutar este cmdlet para conectarse:</span><span class="sxs-lookup"><span data-stu-id="b653a-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="b653a-286">Asignar una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b653a-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="b653a-287">La cuenta del dispositivo debe tener una licencia válida de Office 365 (O365); de otro modo, Exchange y Skype Empresarial no funcionarán.</span><span class="sxs-lookup"><span data-stu-id="b653a-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="b653a-288">Si tienes la licencia, debes asignar una ubicación de uso a tu cuenta del dispositivo; esto determina los SKU de la licencia que están disponibles para tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="b653a-289">A continuación, puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.</span><span class="sxs-lookup"><span data-stu-id="b653a-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="b653a-290">Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.</span><span class="sxs-lookup"><span data-stu-id="b653a-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

<span data-ttu-id="b653a-291">A continuación, habilita la cuenta del dispositivo con [Skype Empresarial Online](#skype-for-business-online), [Skype Empresarial local](#skype-for-business-on-premises) o [Skype Empresarial híbrido](#skype-for-business-hybrid).</span><span class="sxs-lookup"><span data-stu-id="b653a-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="b653a-292">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="b653a-292">Skype for Business Online</span></span>

<span data-ttu-id="b653a-293">Para habilitar Skype Empresarial, tu entorno deberá cumplir los [requisitos previos de Skype Empresarial Online](#skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b653a-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="b653a-294">Para comenzar, crea una sesión remota de PowerShell al entorno de Skype Empresarial Online desde un equipo.</span><span class="sxs-lookup"><span data-stu-id="b653a-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="b653a-295">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b653a-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="b653a-296">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b653a-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="b653a-297">Asigna la licencia de Skype Empresarial a tu cuenta de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="b653a-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="b653a-298">Una vez que hayas completado los pasos anteriores para habilitar tu cuenta de Surface Hub en Skype Empresarial Online, debes asignar una licencia al Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="b653a-299">Con el portal administrativo de O365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b653a-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="b653a-300">Inicia sesión como administrador de inquilinos, abre el portal de administración de O365 y haz clic en la aplicación de administración.</span><span class="sxs-lookup"><span data-stu-id="b653a-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="b653a-301">Haz clic en **Usuarios y grupos locales** y después en **Agregar usuarios, restablecer contraseñas y más**.</span><span class="sxs-lookup"><span data-stu-id="b653a-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="b653a-302">Haz clic en la cuenta de Surface Hub y, a continuación, haz clic en el icono de lápiz para editar la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="b653a-303">Haz clic en **Licencias**.</span><span class="sxs-lookup"><span data-stu-id="b653a-303">Click **Licenses**.</span></span>

- <span data-ttu-id="b653a-304">En **Asignar licencias**, selecciona Skype Empresarial (Plan 2) o Skype Empresarial (Plan 3), según los requisitos de tu licencia y de Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b653a-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="b653a-305">Tendrás que usar una licencia de Plan 3 si quieres usar Telefonía IP empresarial en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="b653a-306">Haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b653a-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b653a-307">También puedes usar el Módulo Microsoft Azure Active Directory para Windows PowerShell para ejecutar los cmdlets necesarios para asignar una de estas licencias, pero esto no se incluye aquí.</span><span class="sxs-lookup"><span data-stu-id="b653a-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="b653a-308">Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b653a-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="b653a-309">Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="b653a-309">Skype for Business on-premises</span></span>

<span data-ttu-id="b653a-310">Para ejecutar este cmdlet, tendrás que conectarte a uno de los front-end de Skype.</span><span class="sxs-lookup"><span data-stu-id="b653a-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="b653a-311">Abre Skype PowerShell y ejecútalo:</span><span class="sxs-lookup"><span data-stu-id="b653a-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="b653a-312">Skype Empresarial híbrido</span><span class="sxs-lookup"><span data-stu-id="b653a-312">Skype for Business hybrid</span></span>

<span data-ttu-id="b653a-313">Si tu organización ha configurado la [conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](https://technet.microsoft.com/library/jj205403.aspx), las instrucciones para crear cuentas difiere de una implementación estándar de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="b653a-314">Surface Hub requiere una cuenta de Skype del tipo *meetingroom*, mientras que un usuario normal usaría una cuenta de tipo *user* en Skype.</span><span class="sxs-lookup"><span data-stu-id="b653a-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="b653a-315">Si el servidor de Skype se configuró para conectividad híbrida donde puede haber usuarios en el servidor local de Skype, así como usuarios hospedados en Office 365, es posible que se produzcan problemas al intentar crear una cuenta de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b653a-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="b653a-316">En el entorno híbrido de Skype empresarial Server 2015, todos los usuarios que desee en Skype empresarial online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b653a-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="b653a-317">Después, puede mover el usuario a Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b653a-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="b653a-318">El movimiento de una cuenta de usuario de local a conectada se realiza mediante el cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b653a-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="b653a-319">Para mover un objeto Csmeetingroom, usa el cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .</span><span class="sxs-lookup"><span data-stu-id="b653a-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b653a-320">Para usar el cmdlet Move-CsMeetingRoom, debe tener instalado [el paquete de actualización acumulativa de mayo de 2017 6.0.9319.281 para Skype empresarial Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) o [la actualización acumulativa de julio 2017 5.0.8308.992 para Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span><span class="sxs-lookup"><span data-stu-id="b653a-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>

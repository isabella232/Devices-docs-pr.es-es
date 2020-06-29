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
# <span data-ttu-id="38e81-104">Implementación local de Surface Hub en un entorno de bosques múltiples</span><span class="sxs-lookup"><span data-stu-id="38e81-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="38e81-105">En este tema se explica cómo agregar una cuenta del dispositivo al Microsoft Surface Hub cuando tengas una implementación local de bosques múltiples.</span><span class="sxs-lookup"><span data-stu-id="38e81-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="38e81-106">Si tienes una implementación local de bosques múltiples con Microsoft Exchange 2013 o superior y Skype Empresarial 2013 o posterior, puedes [usar los scripts de PowerShell proporcionados](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) para crear cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38e81-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="38e81-107">Si estás usando una implementación de bosque único, consulta [Implementación local de Surface Hub en un entorno de bosque único](on-premises-deployment-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="38e81-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="38e81-108">Inicia una sesión de PowerShell remoto desde un equipo y conéctate a Exchange.</span><span class="sxs-lookup"><span data-stu-id="38e81-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="38e81-109">Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.</span><span class="sxs-lookup"><span data-stu-id="38e81-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="38e81-110">Ten en cuenta aquí que `$strExchangeServer` es el nombre de dominio completo (FQDN) del servidor Exchange y que `$strLyncFQDN` es el FQDN de tu Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="38e81-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="38e81-111">Después de establecer una sesión, crea un nuevo buzón de correo en el bosque de recursos.</span><span class="sxs-lookup"><span data-stu-id="38e81-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="38e81-112">Esto permitirá autenticar la cuenta en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="38e81-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="38e81-113">Si vas a cambiar un buzón de recursos existente:</span><span class="sxs-lookup"><span data-stu-id="38e81-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="38e81-114">Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="38e81-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="38e81-115">Los dispositivos Surface Hub solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="38e81-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="38e81-116">Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).</span><span class="sxs-lookup"><span data-stu-id="38e81-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="38e81-117">Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs".</span><span class="sxs-lookup"><span data-stu-id="38e81-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="38e81-118">Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38e81-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="38e81-119">Una vez que tengas una directiva compatible, tendrás que aplicar dicha directiva a la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38e81-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="38e81-120">Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="38e81-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="38e81-121">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="38e81-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="38e81-122">Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también.</span><span class="sxs-lookup"><span data-stu-id="38e81-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="38e81-123">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="38e81-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="38e81-124">Esto debería configurarse en el bosque de usuarios.</span><span class="sxs-lookup"><span data-stu-id="38e81-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="38e81-125">Habilita la cuenta en Active Directory, de modo que se autenticará en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="38e81-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="38e81-126">Esto debería configurarse en el bosque de usuarios.</span><span class="sxs-lookup"><span data-stu-id="38e81-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="38e81-127">Ahora debes cambiar el buzón de correo de sala a un buzón de correo vinculado:</span><span class="sxs-lookup"><span data-stu-id="38e81-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="38e81-128">Habilita la cuenta del dispositivo con Skype Empresarial habilitando tu cuenta de AD de Surface Hub en un grupo de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="38e81-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="38e81-129">Debes usar la dirección de Protocolo de inicio de sesión (SIP) y el controlador de dominio en el Surface Hub, junto con tu propio identificador de grupo de Skype Empresarial Server e identidad de usuario.</span><span class="sxs-lookup"><span data-stu-id="38e81-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="38e81-130">Deshabilitar el correo electrónico anónimo y la mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="38e81-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="38e81-131">Surface Hub usa una cuenta de dispositivo para proporcionar servicios de correo electrónico y colaboración (mensajería instantánea, vídeo, voz).</span><span class="sxs-lookup"><span data-stu-id="38e81-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="38e81-132">Esta cuenta de dispositivo se usa como la identidad de origen (la "de la" fiesta) Cuando envías mensajes de correo electrónico, mensajes instantáneos y llamadas.</span><span class="sxs-lookup"><span data-stu-id="38e81-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="38e81-133">Puesto que esta cuenta no proviene de un usuario individual identificable, se considera "anónimo" porque se originó desde la cuenta de dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="38e81-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="38e81-134">Supongamos que tiene una directiva de cliente por usuario asignada a cada uno de los dispositivos de la sala de reuniones con una identidad de **SurfaceHubPolicy**.</span><span class="sxs-lookup"><span data-stu-id="38e81-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="38e81-135">Para deshabilitar el correo electrónico anónimo y la mensajería, agregue un clientPolicyEntry a esta directiva de cliente con los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="38e81-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="38e81-136">Para comprobar que la Directiva se ha configurado:</span><span class="sxs-lookup"><span data-stu-id="38e81-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="38e81-137">El resultado debe ser:</span><span class="sxs-lookup"><span data-stu-id="38e81-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="38e81-138">Para cambiar la entrada de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="38e81-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="38e81-139">Para quitar la entrada de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="38e81-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 






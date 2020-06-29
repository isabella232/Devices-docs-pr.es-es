---
title: Implementación en línea o híbrida con el entorno de Skype Hybrid Voice (Surface Hub)
description: En este tema se explica cómo habilitar Skype Empresarial Cloud PBX con la conectividad de RTC local a través de Cloud Connector Edition o el grupo de Skype Empresarial 2015.
keywords: implementación híbrida, Skype Hybrid Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836433"
---
# <span data-ttu-id="b0a71-104">Implementación en línea o híbrida con el entorno de Skype Hybrid Voice (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b0a71-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="b0a71-105">En este tema se explica cómo habilitar Skype Empresarial Cloud PBX con la conectividad de la red telefónica conmutada (RTC) local a través de Cloud Connector Edition o el grupo de Skype Empresarial 2015.</span><span class="sxs-lookup"><span data-stu-id="b0a71-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="b0a71-106">En esta opción,</span><span class="sxs-lookup"><span data-stu-id="b0a71-106">In this option.</span></span> <span data-ttu-id="b0a71-107">tus grupos de servidores principales de Skype Empresarial y servidores de Exchange se encuentran en la nube y están conectados mediante RTC a través de un grupo local que ejecuta Skype Empresarial 2015 o Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b0a71-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="b0a71-108">[Más información acerca de diferentes opciones de Cloud PBX](https://technet.microsoft.com/library/mt612869.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0a71-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="b0a71-109">Si implementaste Skype Empresarial Cloud PBX con una de las opciones de voz híbrida, sigue estos pasos para habilitar la cuenta de la sala para Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b0a71-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="b0a71-110">Es importante crear una cuenta de usuario normal primero, asignar todas las opciones de voz híbrida y números de teléfono y, a continuación, convertir la cuenta en una cuenta de la sala.</span><span class="sxs-lookup"><span data-stu-id="b0a71-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="b0a71-111">Si no sigues este orden, no podrás asignar a un número de teléfono híbrido.</span><span class="sxs-lookup"><span data-stu-id="b0a71-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="b0a71-112">Si creas una cuenta antes de la configuración de voz híbrida (ejecutas el comando Enable-CSMeetingRoom), no podrás configurar los parámetros de voz híbrida necesarios.</span><span class="sxs-lookup"><span data-stu-id="b0a71-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="b0a71-113">Para configurar parámetros de voz híbrida para una cuenta configurada anteriormente o volver a configurar un número de teléfono, elimina la licencia de complemento E5 o E3 + Cloud PBX y, a continuación, sigue los pasos siguientes, comenzando por el paso 3.</span><span class="sxs-lookup"><span data-stu-id="b0a71-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="b0a71-114">Crea una cuenta de usuario nueva para Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b0a71-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="b0a71-115">Este ejemplo usa <strong> surfacehub2@adatum.com </strong> .</span><span class="sxs-lookup"><span data-stu-id="b0a71-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="b0a71-116">La cuenta se puede crear en Active Directory local y sincronizarse con la nube o se puede crear directamente en la nube.</span><span class="sxs-lookup"><span data-stu-id="b0a71-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![nuevo usuario de objeto](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="b0a71-118">Seleccione **La contraseña nunca expira**.</span><span class="sxs-lookup"><span data-stu-id="b0a71-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="b0a71-119">Esto es importante para un dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b0a71-119">This is important for a Surface Hub device.</span></span>

   ![La contraseña nunca expira](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="b0a71-121">En Office 365, agrega la licencia **E5** o el complemento **E3 and Cloud PBX** a la cuenta de usuario creada para la sala.</span><span class="sxs-lookup"><span data-stu-id="b0a71-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="b0a71-122">Esto es necesario para que funcione Hybrid Voice.</span><span class="sxs-lookup"><span data-stu-id="b0a71-122">This is required for Hybrid Voice to work.</span></span>

   ![Agregar licencia de producto](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="b0a71-124">Espera unos 15 minutos hasta que aparezca la cuenta de usuario para la sala en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="b0a71-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="b0a71-125">Después de crear la cuenta de usuario para la sala en Skype Empresarial Online, para habilitarla para Hybrid Voice en PowerShell remoto de Skype Empresarial, ejecuta el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0a71-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="b0a71-126">Valida el flujo de llamadas de Hybrid Voice realizando llamadas de pruebas desde Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b0a71-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="b0a71-127">Inicia una sesión de PowerShell remota en un equipo y conéctate a Exchange ejecutando los siguientes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b0a71-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="b0a71-128">Después de establecer una sesión, modifica la cuenta de usuario para la sala para habilitarla como una **RoomMailboxAccount** ejecutando los siguientes cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b0a71-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="b0a71-129">Esto permite autenticar la cuenta con Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b0a71-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="b0a71-130">Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.</span><span class="sxs-lookup"><span data-stu-id="b0a71-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="b0a71-131">Los dispositivos Surface Hub solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="b0a71-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="b0a71-132">Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).</span><span class="sxs-lookup"><span data-stu-id="b0a71-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="b0a71-133">Si aún no has creado una directiva compatible, usa el siguiente cmdlet (este crea una directiva denominada "Surface Hubs").</span><span class="sxs-lookup"><span data-stu-id="b0a71-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="b0a71-134">Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0a71-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="b0a71-135">Una vez que tengas una directiva compatible, necesitarás aplicar la directiva a la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0a71-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="b0a71-136">Sin embargo, las directivas solo se pueden aplicar a las cuentas de usuario y no a los buzones de recursos.</span><span class="sxs-lookup"><span data-stu-id="b0a71-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="b0a71-137">Ejecute los siguientes cmdlets para convertir el buzón en un tipo de usuario, aplicar la directiva y, a continuación, volver a convertirlo en un buzón (es posible que tengas que volver la cuenta y establecer la contraseña de nuevo).</span><span class="sxs-lookup"><span data-stu-id="b0a71-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="b0a71-138">Es necesario establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="b0a71-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="b0a71-139">Puedes ver qué propiedades pueden establecerse en [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="b0a71-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="b0a71-140">Los siguientes cmdlets proporcionan un ejemplo de establecimiento de propiedades de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b0a71-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="b0a71-141">Habilita el buzón como dispositivo de reunión en Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="b0a71-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="b0a71-142">Ejecute el cmdlet siguiente, que habilita la cuenta como un dispositivo de reunión.</span><span class="sxs-lookup"><span data-stu-id="b0a71-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="b0a71-143">Como resultado de la ejecución de este cmdlet, a los usuarios se les preguntará si se encuentran en una sala de reuniones, como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="b0a71-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="b0a71-144">**Sí** silenciará el micrófono y el altavoz.</span><span class="sxs-lookup"><span data-stu-id="b0a71-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="b0a71-145">En este momento la cuenta de la sala estará totalmente configurada, incluida la voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="b0a71-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="b0a71-146">Si usas Skype local, puedes configurar atributos adicionales, como la descripción, la ubicación, etc., local.</span><span class="sxs-lookup"><span data-stu-id="b0a71-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="b0a71-147">Si creas una sala en Skype en línea, estos parámetros se pueden establecer en línea.</span><span class="sxs-lookup"><span data-stu-id="b0a71-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="b0a71-148">En la imagen siguiente, puedes ver cómo le aparece el dispositivo a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0a71-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)

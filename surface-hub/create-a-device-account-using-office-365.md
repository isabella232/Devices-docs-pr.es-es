---
title: Crear una cuenta del dispositivo mediante la interfaz de usuario (Surface Hub)
description: Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la Interfaz de usuario de Office 365 o el Centro de administración de Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: crear una cuenta de dispositivo, Office 365 UI, centro de administración de Exchange, centro de administración de Microsoft 365, Skype empresarial, Directiva de buzón de dispositivo móvil
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836745"
---
# <span data-ttu-id="0d18d-104">Crear una cuenta del dispositivo mediante la interfaz de usuario (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="0d18d-104">Create a device account using UI (Surface Hub)</span></span>


<span data-ttu-id="0d18d-105">Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la [Interfaz de usuario de Office 365](#create-device-acct-o365) o el [Centro de administración de Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="0d18d-105">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="0d18d-106">Crear una cuenta del dispositivo mediante Office 365</span><span class="sxs-lookup"><span data-stu-id="0d18d-106">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="0d18d-107">[Cree la cuenta en el centro de administración de Microsoft 365](#create-device-acct-o365-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="0d18d-107">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="0d18d-108">[Crear una directiva de buzón (ActiveSync) de dispositivos móviles desde el Centro de administración de Microsoft Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="0d18d-108">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="0d18d-109">[Usar PowerShell para completar la creación de cuentas de dispositivo](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="0d18d-109">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="0d18d-110">[Usar PowerShell para configurar las propiedades de Exchange de la cuenta](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="0d18d-110">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="0d18d-111">[Habilitar la cuenta con Skype Empresarial](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="0d18d-111">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="0d18d-112">Crear la cuenta en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="0d18d-112">Create the account in the admin center</span></span>

1.  <span data-ttu-id="0d18d-113">Inicie sesión en Office 365 visitandohttps://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="0d18d-113">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="0d18d-114">Proporciona las credenciales de administrador para tu inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d18d-114">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="0d18d-115">Esto le llevará a su centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d18d-115">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Centro de administración de Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="0d18d-117">En el centro de administración, vaya a **recursos** en el panel izquierdo y, a continuación, haga clic en **salas & equipo**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-117">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Opción salas & equipamiento en el centro de administración](images/room-equipment.png)

4. <span data-ttu-id="0d18d-119">Haga clic en **Agregar** para crear una nueva cuenta de la sala.</span><span class="sxs-lookup"><span data-stu-id="0d18d-119">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="0d18d-120">Introduce un nombre para mostrar y la dirección de correo electrónico y, a continuación, haz clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-120">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Crear nueva ventana de cuenta de la sala](images/room-add.png)

5. <span data-ttu-id="0d18d-122">Selecciona la cuenta de la sala que acabas de crear en la lista de usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="0d18d-122">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="0d18d-123">En el panel derecho, puedes ver las propiedades de la cuenta y varias acciones opcionales.</span><span class="sxs-lookup"><span data-stu-id="0d18d-123">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="0d18d-124">Haz clic en **Restablecer contraseña** para cambiar la contraseña y anular la selección de **Make this user change their password when they first sign in**, porque no es posible cambiar la contraseña desde el flujo de inicio de sesión de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-124">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="0d18d-125">Haz clic en **Editar** en la sección **Licencia asignada** y, luego, haz clic en la flecha desplegable situada junto a la licencia correspondiente para ampliar los detalles.</span><span class="sxs-lookup"><span data-stu-id="0d18d-125">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="0d18d-126">Selecciona una ubicación del usuario y en la lista de licencias, activa **Skype Empresarial Online (Plan 2)** y, a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-126">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="0d18d-127">La licencia puede variar en función de tu organización (por ejemplo, puedes tener Plan 2 o Plan 3).</span><span class="sxs-lookup"><span data-stu-id="0d18d-127">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="0d18d-128">Crear una directiva de buzón (ActiveSync) de dispositivo móvil desde el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-128">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="0d18d-129">En el panel izquierdo del centro de administración, haga clic en **Administrador**y, a continuación, en **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-129">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![Centro de administración, que muestra los usuarios activos de Exchange.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="0d18d-131">Se abrirá otra ficha en el explorador que te llevará al Centro de administración de Exchange, donde puedes crear y establecer la configuración del buzón de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-131">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Centro de administración de Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="0d18d-133">Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-133">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="0d18d-134">Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0d18d-134">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="0d18d-135">De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-135">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Centro de administración de Exchange: creación de una directiva de buzón de dispositivo móvil.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="0d18d-137">Para crear una nueva directiva de buzón de dispositivo móvil de Surface Hub, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="0d18d-137">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="0d18d-138">En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="0d18d-138">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="0d18d-139">Asegúrate de que la directiva no requiera una contraseña para los dispositivos a los que se ha asignado, de modo que asegúrate de que **Requerir una contraseña** permanezca sin marcar y, luego, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-139">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagen que muestra la nueva directiva de dispositivo móvil.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="0d18d-141">Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al **Centro de administración de Exchange** y verás la nueva directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="0d18d-141">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Imagen con la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="0d18d-143">Usar PowerShell para completar la creación de cuentas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0d18d-143">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="0d18d-144">De ahora en adelante, debes finalizar el proceso de creación de cuenta mediante PowerShell para establecer una configuración.</span><span class="sxs-lookup"><span data-stu-id="0d18d-144">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="0d18d-145">Para poder ejecutar los cmdlets usados por estos scripts de PowerShell, se debe instalar lo siguiente en la consola de administración de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0d18d-145">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="0d18d-146">Ayudante para el inicio de sesión de Microsoft Online Services para profesionales de ti RTW</span><span class="sxs-lookup"><span data-stu-id="0d18d-146">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="0d18d-147">Módulo de Windows Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d18d-147">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="0d18d-148">Skype Empresarial Online, módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d18d-148">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="0d18d-149">Instalar el siguiente módulo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d18d-149">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="0d18d-150">Conexión a servicios en línea</span><span class="sxs-lookup"><span data-stu-id="0d18d-150">Connecting to online services</span></span>

1.  <span data-ttu-id="0d18d-151">Ejecutar Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="0d18d-151">Run Windows PowerShell as Administrator.</span></span>

    ![Imagen que muestra cómo iniciar Windows PowerShell y ejecutarlo como administrador.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="0d18d-153">Crea un objeto de credenciales y luego crea una nueva sesión que se conecte a Skype Empresarial y proporciona la cuenta de administrador de inquilinos global; luego, haz clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-153">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Imagen de la solicitud de credenciales de Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="0d18d-155">Para conectarte a Microsoft Online Services, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="0d18d-155">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="0d18d-157">Ahora, para conectarte a Skype Empresarial Online, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="0d18d-157">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="0d18d-159">Por último, para conectarte a Exchange Online Services, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="0d18d-159">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="0d18d-161">Ahora tienes que importar la sesión de Skype Empresarial Online y la sesión de Exchange Online que acabas de crear, que importará los comandos de Exchange y Skype para que puedas usarlos de forma local.</span><span class="sxs-lookup"><span data-stu-id="0d18d-161">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="0d18d-162">Ten en cuenta que esto podría tardar un tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="0d18d-162">Note that this could take a while to complete.</span></span>

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="0d18d-164">Una vez que estés conectado a los servicios en línea, debes ejecutar unos cmdlets más para configurar esta cuenta como una cuenta del dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-164">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="0d18d-165">Usar PowerShell para configurar las propiedades de Exchange de la cuenta</span><span class="sxs-lookup"><span data-stu-id="0d18d-165">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="0d18d-166">Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d18d-166">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="0d18d-167">Usarás la dirección de correo electrónico de la cuenta del dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="0d18d-167">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="0d18d-168">Cambiar el tipo de buzón de "normal" a "de sala".</span><span class="sxs-lookup"><span data-stu-id="0d18d-168">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="0d18d-169">Establecer la contraseña y habilitar la cuenta de buzón de la sala</span><span class="sxs-lookup"><span data-stu-id="0d18d-169">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="0d18d-170">Cambiar varias propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-170">Change various Exchange properties</span></span>
-   <span data-ttu-id="0d18d-171">Establecer la contraseña de la cuenta de usuario para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="0d18d-171">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="0d18d-172">Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:</span><span class="sxs-lookup"><span data-stu-id="0d18d-172">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="0d18d-173">Para almacenar el valor, obtenlo a partir del buzón:</span><span class="sxs-lookup"><span data-stu-id="0d18d-173">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="0d18d-174">Imprimir el valor:</span><span class="sxs-lookup"><span data-stu-id="0d18d-174">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="0d18d-175">Verás la dirección de correo electrónico correcta.</span><span class="sxs-lookup"><span data-stu-id="0d18d-175">You will see the correct email address.</span></span>

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="0d18d-177">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d18d-177">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="0d18d-178">Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="0d18d-178">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="0d18d-179">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="0d18d-179">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="0d18d-181">Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también.</span><span class="sxs-lookup"><span data-stu-id="0d18d-181">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="0d18d-182">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d18d-182">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="0d18d-183">Habilitar la cuenta con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0d18d-183">Enable the account with Skype for Business</span></span>

<span data-ttu-id="0d18d-184">Habilitar la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d18d-184">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="0d18d-185">Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="0d18d-185">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="0d18d-186">Necesitará tener el plan independiente 2 o superior de Skype empresarial online en su plan de O365.</span><span class="sxs-lookup"><span data-stu-id="0d18d-186">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="0d18d-187">El plan debe admitir la funcionalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0d18d-187">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="0d18d-188">Si necesita Enterprise Voice (telefonía RTC) con proveedores de servicios de telefonía para Surface Hub, necesita el plan independiente 3 de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="0d18d-188">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="0d18d-189">Los usuarios de inquilino deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d18d-189">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="0d18d-190">La cuenta de Surface Hub requiere un plan independiente 2 de Skype empresarial online o una licencia de plan independiente 3 de Skype empresarial online, pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d18d-190">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="0d18d-191">Comienza creando una sesión de PowerShell remoto desde un equipo.</span><span class="sxs-lookup"><span data-stu-id="0d18d-191">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="0d18d-192">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d18d-192">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="0d18d-193">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d18d-193">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="0d18d-194">Crear una cuenta del dispositivo mediante el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-194">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="0d18d-195">Este método solo funciona si está sincronizando desde un Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="0d18d-195">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="0d18d-196">Puedes usar el Centro de administración de Exchange para crear una cuenta del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="0d18d-196">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="0d18d-197">[Crear una cuenta y un buzón mediante el Centro de administración de Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="0d18d-197">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="0d18d-198">[Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="0d18d-198">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="0d18d-199">[Usar PowerShell para configurar la cuenta](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="0d18d-199">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="0d18d-200">[Habilitar la cuenta con Skype Empresarial](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="0d18d-200">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="0d18d-201">Crear una cuenta y un buzón mediante el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-201">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="0d18d-202">Iniciar sesión en el Centro de administración de Exchange con las credenciales de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d18d-202">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="0d18d-203">Una vez que estés en el Centro de administración de Exchange (CEF), ve a **Destinatarios** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="0d18d-203">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Imagen que muestra buzones en el Centro de administración de Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="0d18d-205">En los controles situados encima de la lista de buzones, elige **+** para crear uno nuevo y proporcionar un **nombre para mostrar**, un **nombre** y un **nombre de inicio de sesión de usuario** y luego haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-205">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Imagen que muestra la creación de un nuevo buzón.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="0d18d-207">Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-207">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="0d18d-208">Si desea crear y asignar una directiva a la cuenta que ha creado, y está usando Exchange 2010, busque la información correspondiente relacionada con la creación de directivas y la asignación de directivas al usar EMC (consola de administración de Exchange).</span><span class="sxs-lookup"><span data-stu-id="0d18d-208">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="0d18d-209">Ve al Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d18d-209">Go to the Exchange Admin Center.</span></span>

    ![Imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="0d18d-211">Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-211">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="0d18d-212">Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0d18d-212">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="0d18d-213">De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-213">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Imagen que muestra el Centro de administración de Exchange para crear una directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="0d18d-215">Para crear una nueva directiva de buzón de cuenta del dispositivo móvil, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="0d18d-215">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="0d18d-216">En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="0d18d-216">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="0d18d-217">La directiva no debe estar protegida por contraseña, por lo tanto, asegúrate de que **Requerir una contraseña** permanece sin marcar y , a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-217">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="0d18d-219">Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al Centro de administración de Exchange y verás la nueva directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="0d18d-219">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="0d18d-221">Para aplicar la directiva de ActiveSync sin usar PowerShell, puedes hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d18d-221">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="0d18d-222">En el CEF, haz clic en **Destinatarios** &gt; **Buzones** y selecciona un buzón.</span><span class="sxs-lookup"><span data-stu-id="0d18d-222">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="0d18d-224">En el panel **Detalles** desplázate a **Características de teléfono y voz** y haz clic en **Ver detalles** para mostrar la pantalla **Detalles del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-224">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![imagen que muestra los detalles de buzón de correo.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="0d18d-226">Se muestra la directiva de buzón de dispositivo móvil que está asignada actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d18d-226">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="0d18d-227">Para cambiar la directiva de buzón de dispositivo móvil, haz clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-227">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![imagen que muestra la directiva de buzón de dispositivo móvil asignada actualmente.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="0d18d-229">Elige la directiva de buzón de dispositivo móvil adecuada en la lista, haz clic en **Aceptar** y, a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0d18d-229">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![imagen que muestra una lista de directivas de buzón de dispositivo móvil.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="0d18d-231">Usar PowerShell para configurar la cuenta</span><span class="sxs-lookup"><span data-stu-id="0d18d-231">Use PowerShell to configure the account</span></span>

<span data-ttu-id="0d18d-232">Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0d18d-232">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="0d18d-233">Usarás la dirección de correo electrónico de la cuenta del dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="0d18d-233">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="0d18d-234">Cambiar el tipo de buzón de "normal" a "de sala".</span><span class="sxs-lookup"><span data-stu-id="0d18d-234">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="0d18d-235">Cambiar varias propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="0d18d-235">Change various Exchange properties</span></span>
-   <span data-ttu-id="0d18d-236">Establecer la contraseña de la cuenta de usuario para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="0d18d-236">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="0d18d-237">Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:</span><span class="sxs-lookup"><span data-stu-id="0d18d-237">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="0d18d-238">Para almacenar el valor, obtenlo a partir del buzón:</span><span class="sxs-lookup"><span data-stu-id="0d18d-238">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="0d18d-239">Imprimir el valor ejecutando:</span><span class="sxs-lookup"><span data-stu-id="0d18d-239">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="0d18d-240">Verás la dirección de correo electrónico correcta.</span><span class="sxs-lookup"><span data-stu-id="0d18d-240">You will see the correct email address.</span></span>

2.  <span data-ttu-id="0d18d-241">Debe convertir la cuenta en un buzón de sala, así que ejecute:</span><span class="sxs-lookup"><span data-stu-id="0d18d-241">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="0d18d-242">Para autenticar la cuenta del dispositivo en un Surface Hub, debes habilitar la cuenta de buzón de la sala y establecer una contraseña para que la cuenta se pueda usar con el dispositivo para obtener información de la reunión mediante ActiveSync e iniciar sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d18d-242">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="0d18d-243">Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="0d18d-243">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="0d18d-244">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="0d18d-244">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="0d18d-245">Ahora debemos establecer algunas propiedades en AD.</span><span class="sxs-lookup"><span data-stu-id="0d18d-245">Now we have to set some properties in AD.</span></span> <span data-ttu-id="0d18d-246">Para ello, necesitas el alias de la cuenta (esta es la parte del UPN que aparece antes de "@").</span><span class="sxs-lookup"><span data-stu-id="0d18d-246">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="0d18d-247">El usuario debe estar habilitado en AD antes de poder autenticarse con un Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="0d18d-247">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="0d18d-248">Ejecutar:</span><span class="sxs-lookup"><span data-stu-id="0d18d-248">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="0d18d-249">Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también.</span><span class="sxs-lookup"><span data-stu-id="0d18d-249">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="0d18d-250">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d18d-250">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="0d18d-251">Habilitar la cuenta con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0d18d-251">Enable the account with Skype for Business</span></span>

<span data-ttu-id="0d18d-252">Habilitar la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d18d-252">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="0d18d-253">Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="0d18d-253">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="0d18d-254">Necesitará tener el plan independiente 2 o superior de Skype empresarial online en su plan de O365.</span><span class="sxs-lookup"><span data-stu-id="0d18d-254">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="0d18d-255">El plan debe admitir la funcionalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="0d18d-255">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="0d18d-256">Si necesita Enterprise Voice (telefonía RTC) con proveedores de servicios de telefonía para Surface Hub, necesita el plan independiente 3 de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="0d18d-256">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="0d18d-257">Los usuarios de inquilino deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0d18d-257">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="0d18d-258">La cuenta de Surface Hub requiere un plan independiente 2 de Skype empresarial online o una licencia de plan independiente 3 de Skype empresarial online, pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d18d-258">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="0d18d-259">Comienza creando una sesión de PowerShell remoto desde un equipo.</span><span class="sxs-lookup"><span data-stu-id="0d18d-259">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="0d18d-260">Recuperar el grupo de registrador de cuentas de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="0d18d-260">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="0d18d-261">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d18d-261">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. <span data-ttu-id="0d18d-262">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d18d-262">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    






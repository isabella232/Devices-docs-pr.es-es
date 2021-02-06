---
title: Crear una cuenta del dispositivo mediante la interfaz de usuario (Surface Hub v1)
description: Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la Interfaz de usuario de Office 365 o el Centro de administración de Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: crear cuenta del dispositivo, interfaz de usuario de Office 365, Centro de administración de Exchange, Centro de administración de Microsoft 365, Skype Empresarial, directiva de buzón de dispositivo móvil
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: 9e6d72dc2b36bb149ee09c2edab885c80e60ac14
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314473"
---
# <span data-ttu-id="8a002-104">Crear una cuenta del dispositivo mediante la interfaz de usuario (Surface Hub v1)</span><span class="sxs-lookup"><span data-stu-id="8a002-104">Create a device account using UI (Surface Hub v1)</span></span>

 > [!NOTE]
 ><span data-ttu-id="8a002-105">Esta página incluye información sobre el Surface Hub original (v1).</span><span class="sxs-lookup"><span data-stu-id="8a002-105">This page includes information about the original Surface Hub (v1).</span></span> <span data-ttu-id="8a002-106">Para Surface Hub 2S, consulta [Crear cuenta del dispositivo Surface Hub 2S.](surface-hub-2s-account.md)</span><span class="sxs-lookup"><span data-stu-id="8a002-106">For Surface Hub 2S, see [Create Surface Hub 2S device account](surface-hub-2s-account.md).</span></span>

<span data-ttu-id="8a002-107">Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la [Interfaz de usuario de Office 365](#create-device-acct-o365) o el [Centro de administración de Exchange](#create-device-acct-eac).</span><span class="sxs-lookup"><span data-stu-id="8a002-107">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="8a002-108">Crear una cuenta del dispositivo mediante Office 365</span><span class="sxs-lookup"><span data-stu-id="8a002-108">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="8a002-109">[Cree la cuenta en el Centro de administración de Microsoft 365.](#create-device-acct-o365-admin-ctr)</span><span class="sxs-lookup"><span data-stu-id="8a002-109">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="8a002-110">[Crear una directiva de buzón (ActiveSync) de dispositivos móviles desde el Centro de administración de Microsoft Exchange](#create-device-acct-o365-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="8a002-110">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="8a002-111">[Usar PowerShell para completar la creación de cuentas de dispositivo](#create-device-acct-o365-complete-acct).</span><span class="sxs-lookup"><span data-stu-id="8a002-111">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="8a002-112">[Usar PowerShell para configurar las propiedades de Exchange de la cuenta](#create-device-acct-o365-configure-exch-prop).</span><span class="sxs-lookup"><span data-stu-id="8a002-112">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="8a002-113">[Habilitar la cuenta con Skype Empresarial](#create-device-acct-o365-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="8a002-113">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="8a002-114">Crear la cuenta en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="8a002-114">Create the account in the admin center</span></span>

1.  <span data-ttu-id="8a002-115">Inicie sesión en Office 365 visitando https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="8a002-115">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="8a002-116">Proporciona las credenciales de administrador para tu inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a002-116">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="8a002-117">Esto le llevará al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a002-117">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Centro de administración de Microsoft 365.](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="8a002-119">En el centro de administración, vaya a **Recursos** en el panel izquierdo y, a continuación, haga clic en Salas **& equipo.**</span><span class="sxs-lookup"><span data-stu-id="8a002-119">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![Salas & opción de equipamiento en el Centro de administración](images/room-equipment.png)

4. <span data-ttu-id="8a002-121">Haga clic en **Agregar** para crear una nueva cuenta de la sala.</span><span class="sxs-lookup"><span data-stu-id="8a002-121">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="8a002-122">Introduce un nombre para mostrar y la dirección de correo electrónico y, a continuación, haz clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-122">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![Crear nueva ventana de cuenta de la sala](images/room-add.png)

5. <span data-ttu-id="8a002-124">Selecciona la cuenta de la sala que acabas de crear en la lista de usuarios activos.</span><span class="sxs-lookup"><span data-stu-id="8a002-124">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="8a002-125">En el panel derecho, puedes ver las propiedades de la cuenta y varias acciones opcionales.</span><span class="sxs-lookup"><span data-stu-id="8a002-125">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="8a002-126">Haz clic en **Restablecer contraseña** para cambiar la contraseña y anular la selección de **Make this user change their password when they first sign in**, porque no es posible cambiar la contraseña desde el flujo de inicio de sesión de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-126">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="8a002-127">Haz clic en **Editar** en la sección **Licencia asignada** y, luego, haz clic en la flecha desplegable situada junto a la licencia correspondiente para ampliar los detalles.</span><span class="sxs-lookup"><span data-stu-id="8a002-127">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="8a002-128">Selecciona una ubicación del usuario y en la lista de licencias, activa **Skype Empresarial Online (Plan 2)** y, a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-128">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="8a002-129">La licencia puede variar en función de tu organización (por ejemplo, puedes tener Plan 2 o Plan 3).</span><span class="sxs-lookup"><span data-stu-id="8a002-129">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="8a002-130">Crear una directiva de buzón (ActiveSync) de dispositivo móvil desde el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-130">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="8a002-131">En el panel izquierdo del centro de administración, haga clic en **ADMINISTRACIÓN**y, a continuación, haga clic **en Exchange.**</span><span class="sxs-lookup"><span data-stu-id="8a002-131">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![centro de administración, que muestra los usuarios activos de Exchange.](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="8a002-133">Se abrirá otra ficha en el explorador que te llevará al Centro de administración de Exchange, donde puedes crear y establecer la configuración del buzón de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-133">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Centro de administración de Exchange.](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="8a002-135">Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="8a002-135">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="8a002-136">Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="8a002-136">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="8a002-137">De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-137">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Centro de administración de Exchange: creación de una directiva de buzón de dispositivo móvil.](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="8a002-139">Para crear una nueva directiva de buzón de dispositivo móvil de Surface Hub, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="8a002-139">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="8a002-140">En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="8a002-140">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="8a002-141">Asegúrate de que la directiva no requiera una contraseña para los dispositivos a los que se ha asignado, de modo que asegúrate de que **Requerir una contraseña** permanezca sin marcar y, luego, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-141">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagen que muestra la nueva directiva de dispositivo móvil.](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="8a002-143">Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al **Centro de administración de Exchange** y verás la nueva directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="8a002-143">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Imagen con la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="8a002-145">Usar PowerShell para completar la creación de cuentas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8a002-145">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="8a002-146">De ahora en adelante, debes finalizar el proceso de creación de cuenta mediante PowerShell para establecer una configuración.</span><span class="sxs-lookup"><span data-stu-id="8a002-146">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="8a002-147">Para poder ejecutar los cmdlets usados por estos scripts de PowerShell, se debe instalar lo siguiente en la consola de administración de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a002-147">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="8a002-148">Microsoft Online Services Sign-In asistente para profesionales de TI RTW</span><span class="sxs-lookup"><span data-stu-id="8a002-148">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="8a002-149">Módulo de Windows Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a002-149">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="8a002-150">Skype Empresarial Online, módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a002-150">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="8a002-151">Instalar el siguiente módulo en PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a002-151">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="8a002-152">Conexión a servicios en línea</span><span class="sxs-lookup"><span data-stu-id="8a002-152">Connecting to online services</span></span>

1.  <span data-ttu-id="8a002-153">Ejecutar Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="8a002-153">Run Windows PowerShell as Administrator.</span></span>

    ![Imagen que muestra cómo iniciar Windows PowerShell y ejecutarlo como administrador.](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="8a002-155">Crea un objeto de credenciales y luego crea una nueva sesión que se conecte a Skype Empresarial y proporciona la cuenta de administrador de inquilinos global; luego, haz clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-155">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Imagen de la solicitud de credenciales de Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="8a002-157">Para conectarte a Microsoft Online Services, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="8a002-157">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="8a002-159">Ahora, para conectarte a Skype Empresarial Online, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="8a002-159">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="8a002-161">Por último, para conectarte a Exchange Online Services, ejecuta:</span><span class="sxs-lookup"><span data-stu-id="8a002-161">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="8a002-163">Ahora tienes que importar la sesión de Skype Empresarial Online y la sesión de Exchange Online que acabas de crear, que importará los comandos de Exchange y Skype para que puedas usarlos de forma local.</span><span class="sxs-lookup"><span data-stu-id="8a002-163">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="8a002-164">Ten en cuenta que esto podría tardar un tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="8a002-164">Note that this could take a while to complete.</span></span>

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="8a002-166">Una vez que estés conectado a los servicios en línea, debes ejecutar unos cmdlets más para configurar esta cuenta como una cuenta del dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-166">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="8a002-167">Usar PowerShell para configurar las propiedades de Exchange de la cuenta</span><span class="sxs-lookup"><span data-stu-id="8a002-167">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="8a002-168">Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a002-168">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="8a002-169">Usarás la dirección de correo electrónico de la cuenta del dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="8a002-169">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="8a002-170">Cambiar el tipo de buzón de "normal" a "de sala".</span><span class="sxs-lookup"><span data-stu-id="8a002-170">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="8a002-171">Establecer la contraseña y habilitar la cuenta de buzón de la sala</span><span class="sxs-lookup"><span data-stu-id="8a002-171">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="8a002-172">Cambiar varias propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-172">Change various Exchange properties</span></span>
-   <span data-ttu-id="8a002-173">Establecer la contraseña de la cuenta de usuario para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="8a002-173">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="8a002-174">Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:</span><span class="sxs-lookup"><span data-stu-id="8a002-174">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="8a002-175">Para almacenar el valor, obtenlo a partir del buzón:</span><span class="sxs-lookup"><span data-stu-id="8a002-175">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="8a002-176">Imprimir el valor:</span><span class="sxs-lookup"><span data-stu-id="8a002-176">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="8a002-177">Verás la dirección de correo electrónico correcta.</span><span class="sxs-lookup"><span data-stu-id="8a002-177">You will see the correct email address.</span></span>

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="8a002-179">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8a002-179">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="8a002-180">Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="8a002-180">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="8a002-181">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8a002-181">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="8a002-183">Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también.</span><span class="sxs-lookup"><span data-stu-id="8a002-183">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="8a002-184">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8a002-184">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="8a002-185">Habilitar la cuenta con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8a002-185">Enable the account with Skype for Business</span></span>

<span data-ttu-id="8a002-186">Habilitar la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a002-186">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="8a002-187">Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8a002-187">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="8a002-188">Necesitará tener Skype Empresarial Online plan independiente 2 o superior en su plan de O365.</span><span class="sxs-lookup"><span data-stu-id="8a002-188">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="8a002-189">El plan debe admitir la funcionalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8a002-189">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="8a002-190">Si necesitas usar Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para Surface Hub, necesitas skype empresarial online plan independiente 3.</span><span class="sxs-lookup"><span data-stu-id="8a002-190">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="8a002-191">Los usuarios de inquilino deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a002-191">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="8a002-192">Tu cuenta de Surface Hub requiere una licencia del Plan independiente 2 de Skype Empresarial Online o skype empresarial Online plan independiente 3, pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8a002-192">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="8a002-193">Comienza creando una sesión de PowerShell remoto desde un equipo.</span><span class="sxs-lookup"><span data-stu-id="8a002-193">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="8a002-194">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8a002-194">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="8a002-195">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8a002-195">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="8a002-196">Crear una cuenta del dispositivo mediante el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-196">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="8a002-197">Este método solo funcionará si está sincronizando desde un Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8a002-197">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="8a002-198">Puedes usar el Centro de administración de Exchange para crear una cuenta del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8a002-198">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="8a002-199">[Crear una cuenta y un buzón mediante el Centro de administración de Exchange](#create-device-acct-exch-admin-ctr).</span><span class="sxs-lookup"><span data-stu-id="8a002-199">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="8a002-200">[Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange](#create-device-acct-exch-mbx-policy).</span><span class="sxs-lookup"><span data-stu-id="8a002-200">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="8a002-201">[Usar PowerShell para configurar la cuenta](#create-device-acct-exch-powershell-conf).</span><span class="sxs-lookup"><span data-stu-id="8a002-201">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="8a002-202">[Habilitar la cuenta con Skype Empresarial](#create-device-acct-exch-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="8a002-202">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="8a002-203">Crear una cuenta y un buzón mediante el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-203">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="8a002-204">Iniciar sesión en el Centro de administración de Exchange con las credenciales de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a002-204">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="8a002-205">Una vez que estés en el Centro de administración de Exchange (CEF), ve a **Destinatarios** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="8a002-205">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![Imagen que muestra buzones en el Centro de administración de Exchange.](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="8a002-207">En los controles situados encima de la lista de buzones, elige **+** para crear uno nuevo y proporcionar un **nombre para mostrar**, un **nombre** y un **nombre de inicio de sesión de usuario** y luego haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-207">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![Imagen que muestra la creación de un nuevo buzón.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="8a002-209">Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-209">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="8a002-210">Si desea crear y asignar una directiva a la cuenta que creó y usa Exchange 2010, busque la información correspondiente sobre la creación de directivas y la asignación de directivas al usar la EMC (consola de administración de Exchange).</span><span class="sxs-lookup"><span data-stu-id="8a002-210">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="8a002-211">Ve al Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a002-211">Go to the Exchange Admin Center.</span></span>

    ![Imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="8a002-213">Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="8a002-213">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="8a002-214">Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="8a002-214">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="8a002-215">De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-215">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Imagen que muestra el Centro de administración de Exchange para crear una directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="8a002-217">Para crear una nueva directiva de buzón de cuenta del dispositivo móvil, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="8a002-217">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="8a002-218">En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*).</span><span class="sxs-lookup"><span data-stu-id="8a002-218">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="8a002-219">La directiva no debe estar protegida por contraseña, por lo tanto, asegúrate de que **Requerir una contraseña** permanece sin marcar y , a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-219">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="8a002-221">Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al Centro de administración de Exchange y verás la nueva directiva en la lista.</span><span class="sxs-lookup"><span data-stu-id="8a002-221">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="8a002-223">Para aplicar la directiva de ActiveSync sin usar PowerShell, puedes hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a002-223">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="8a002-224">En el CEF, haz clic en **Destinatarios** &gt; **Buzones** y selecciona un buzón.</span><span class="sxs-lookup"><span data-stu-id="8a002-224">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="8a002-226">En el panel **Detalles** desplázate a **Características de teléfono y voz** y haz clic en **Ver detalles** para mostrar la pantalla **Detalles del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="8a002-226">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![imagen que muestra los detalles de buzón de correo.](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="8a002-228">Se muestra la directiva de buzón de dispositivo móvil que está asignada actualmente.</span><span class="sxs-lookup"><span data-stu-id="8a002-228">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="8a002-229">Para cambiar la directiva de buzón de dispositivo móvil, haz clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-229">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![imagen que muestra la directiva de buzón de dispositivo móvil asignada actualmente.](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="8a002-231">Elige la directiva de buzón de dispositivo móvil adecuada en la lista, haz clic en **Aceptar** y, a continuación, haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a002-231">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![imagen que muestra una lista de directivas de buzón de dispositivo móvil.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="8a002-233">Usar PowerShell para configurar la cuenta</span><span class="sxs-lookup"><span data-stu-id="8a002-233">Use PowerShell to configure the account</span></span>

<span data-ttu-id="8a002-234">Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8a002-234">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="8a002-235">Usarás la dirección de correo electrónico de la cuenta del dispositivo para:</span><span class="sxs-lookup"><span data-stu-id="8a002-235">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="8a002-236">Cambiar el tipo de buzón de "normal" a "de sala".</span><span class="sxs-lookup"><span data-stu-id="8a002-236">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="8a002-237">Cambiar varias propiedades de Exchange</span><span class="sxs-lookup"><span data-stu-id="8a002-237">Change various Exchange properties</span></span>
-   <span data-ttu-id="8a002-238">Establecer la contraseña de la cuenta de usuario para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="8a002-238">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="8a002-239">Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:</span><span class="sxs-lookup"><span data-stu-id="8a002-239">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="8a002-240">Para almacenar el valor, obtenlo a partir del buzón:</span><span class="sxs-lookup"><span data-stu-id="8a002-240">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="8a002-241">Imprimir el valor ejecutando:</span><span class="sxs-lookup"><span data-stu-id="8a002-241">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="8a002-242">Verás la dirección de correo electrónico correcta.</span><span class="sxs-lookup"><span data-stu-id="8a002-242">You will see the correct email address.</span></span>

2.  <span data-ttu-id="8a002-243">Debe convertir la cuenta en un buzón de sala, por lo que ejecute:</span><span class="sxs-lookup"><span data-stu-id="8a002-243">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="8a002-244">Para autenticar la cuenta del dispositivo en un Surface Hub, debes habilitar la cuenta de buzón de la sala y establecer una contraseña para que la cuenta se pueda usar con el dispositivo para obtener información de la reunión mediante ActiveSync e iniciar sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a002-244">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="8a002-245">Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión.</span><span class="sxs-lookup"><span data-stu-id="8a002-245">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="8a002-246">Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="8a002-246">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="8a002-247">Ahora debemos establecer algunas propiedades en AD.</span><span class="sxs-lookup"><span data-stu-id="8a002-247">Now we have to set some properties in AD.</span></span> <span data-ttu-id="8a002-248">Para ello, necesitas el alias de la cuenta (esta es la parte del UPN que aparece antes de "@").</span><span class="sxs-lookup"><span data-stu-id="8a002-248">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="8a002-249">El usuario debe estar habilitado en AD antes de poder autenticarse con un Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8a002-249">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="8a002-250">Ejecutar:</span><span class="sxs-lookup"><span data-stu-id="8a002-250">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="8a002-251">Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también.</span><span class="sxs-lookup"><span data-stu-id="8a002-251">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="8a002-252">Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8a002-252">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="8a002-253">Habilitar la cuenta con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8a002-253">Enable the account with Skype for Business</span></span>

<span data-ttu-id="8a002-254">Habilitar la cuenta del dispositivo con Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a002-254">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="8a002-255">Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8a002-255">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

- <span data-ttu-id="8a002-256">Necesitará tener Skype Empresarial Online plan independiente 2 o superior en su plan de O365.</span><span class="sxs-lookup"><span data-stu-id="8a002-256">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="8a002-257">El plan debe admitir la funcionalidad de conferencia.</span><span class="sxs-lookup"><span data-stu-id="8a002-257">The plan needs to support conferencing capability.</span></span>
- <span data-ttu-id="8a002-258">Si necesitas usar Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para Surface Hub, necesitas skype empresarial online plan independiente 3.</span><span class="sxs-lookup"><span data-stu-id="8a002-258">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
- <span data-ttu-id="8a002-259">Los usuarios de inquilino deben tener buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8a002-259">Your tenant users must have Exchange mailboxes.</span></span>
- <span data-ttu-id="8a002-260">Tu cuenta de Surface Hub requiere una licencia del Plan independiente 2 de Skype Empresarial Online o skype empresarial Online plan independiente 3, pero no requiere una licencia de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8a002-260">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1. <span data-ttu-id="8a002-261">Comienza creando una sesión de PowerShell remoto desde un equipo.</span><span class="sxs-lookup"><span data-stu-id="8a002-261">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="8a002-262">Recuperar el grupo de registradores de cuentas de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="8a002-262">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="8a002-263">Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8a002-263">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

 ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
 ```

3. <span data-ttu-id="8a002-264">Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8a002-264">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```
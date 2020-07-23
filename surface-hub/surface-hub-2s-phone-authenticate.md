---
title: Configurar el inicio de sesión sin contraseña en Surface Hub
description: Aprenda a simplificar el inicio de sesión en Surface Hub.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893052"
---
# <span data-ttu-id="60a66-104">Configurar el inicio de sesión sin contraseña en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="60a66-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="60a66-105">El inicio de sesión sin contraseña simplifica el acceso a tus aplicaciones, reuniones y archivos.</span><span class="sxs-lookup"><span data-stu-id="60a66-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="60a66-106">Surface HUB permite iniciar sesión con la aplicación Microsoft Authenticator y las claves de seguridad de FIDO2 proporcionadas por su organización.</span><span class="sxs-lookup"><span data-stu-id="60a66-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="60a66-107">**Importante:** Este contenido va dirigido a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="60a66-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="60a66-108">Para usar el inicio de sesión sin contraseña, su administrador de TI debe habilitar la autenticación sin contraseña para su organización.</span><span class="sxs-lookup"><span data-stu-id="60a66-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="60a66-109">Para más información, consulta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60a66-109">For more information, see:</span></span>

- [<span data-ttu-id="60a66-110">Habilitar el inicio de sesión de teléfono sin contraseñas</span><span class="sxs-lookup"><span data-stu-id="60a66-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="60a66-111">Habilitar el inicio de sesión con una clave de seguridad sin contraseñas</span><span class="sxs-lookup"><span data-stu-id="60a66-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="60a66-112">Configurar el inicio de sesión con la aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="60a66-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="60a66-113">**Nota:** A partir de la actualización de Windows 10 Team 2020, los usuarios pueden usar sus alias de correo electrónico preferidos en Azure AD, así como su nombre principal de usuario (UPN), para iniciar sesión con Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="60a66-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="60a66-114">Por ejemplo, un usuario puede usar su alias preferido (John.Doe@contoso.com) o su UPN (jdoe@contoso.com) para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="60a66-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="60a66-115">La aplicación Microsoft Authenticator le ayuda a iniciar sesión en Surface Hub con el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="60a66-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="60a66-116">Para configurar el inicio de sesión con Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="60a66-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="60a66-117">En su dispositivo móvil, descargue la aplicación Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="60a66-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="60a66-118">Google Android: en su dispositivo Android, vaya a Google Play para [Descargar e instalar la aplicación Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span><span class="sxs-lookup"><span data-stu-id="60a66-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="60a66-119">IOS de Apple: en el dispositivo Apple iOS, vaya a App Store para [Descargar e instalar la aplicación Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span><span class="sxs-lookup"><span data-stu-id="60a66-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="60a66-120">En su equipo, [Configure la aplicación Microsoft Authenticator desde la página información de seguridad](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) de su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="60a66-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="60a66-121">Desde la aplicación Microsoft Authenticator en su dispositivo móvil, [Active y use el inicio de sesión](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) para su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="60a66-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="60a66-122">Configurar el inicio de sesión con las claves de seguridad de FIDO2</span><span class="sxs-lookup"><span data-stu-id="60a66-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="60a66-123">El inicio de sesión sin contraseñas en Surface Hub con claves de seguridad FIDO2 requiere la actualización de Windows 10 Team 2020.</span><span class="sxs-lookup"><span data-stu-id="60a66-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60a66-124">Surface Hub solo admite claves de seguridad USB.</span><span class="sxs-lookup"><span data-stu-id="60a66-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="60a66-125">También puede iniciar sesión en Surface Hub con una clave de seguridad FIDO2 proporcionada por su organización.</span><span class="sxs-lookup"><span data-stu-id="60a66-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="60a66-126">Para configurar el inicio de sesión con una clave de seguridad:</span><span class="sxs-lookup"><span data-stu-id="60a66-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="60a66-127">En su equipo, vaya a la [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) página e inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="60a66-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="60a66-128">Seleccione **información de seguridad** en el panel de navegación izquierdo o en el vínculo del bloque de **información de seguridad** y, a continuación, seleccione **Agregar método** en la página **información de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="60a66-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="60a66-129">En la página **Agregar un método** , seleccione **clave de seguridad** en la lista desplegable y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="60a66-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="60a66-130">En la página **clave de seguridad** , elija **dispositivo USB**.</span><span class="sxs-lookup"><span data-stu-id="60a66-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="60a66-131">Prepare su clave de seguridad y seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60a66-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="60a66-132">En el cuadro de diálogo que aparece, siga las instrucciones para insertar la clave de seguridad, cree o escriba un PIN y realice el gesto necesario (ya sea biométrico o táctil).</span><span class="sxs-lookup"><span data-stu-id="60a66-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="60a66-133">En la página **clave de seguridad** , asigne un nombre a la clave de seguridad y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60a66-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="60a66-134">Seleccione **listo** para completar el proceso.</span><span class="sxs-lookup"><span data-stu-id="60a66-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="60a66-135">Iniciar sesión en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="60a66-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="60a66-136">Una vez que haya configurado el inicio de sesión sin contraseñas, puede usarlo para facilitar el acceso a sus aplicaciones, reuniones y archivos en Surface Hub:</span><span class="sxs-lookup"><span data-stu-id="60a66-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="60a66-137">Únase rápidamente a sus reuniones y abra archivos recientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60a66-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="60a66-138">Para obtener más información, consulte [**iniciar sesión para ver sus reuniones y archivos**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span><span class="sxs-lookup"><span data-stu-id="60a66-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="60a66-139">Inicie sesión rápidamente en aplicaciones de Microsoft, como whiteboard, PowerPoint, Word, Excel, OneDrive y Power BI.</span><span class="sxs-lookup"><span data-stu-id="60a66-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="60a66-140">Inicia sesión rápidamente en el nuevo Microsoft Edge para acceder a tus preferencias de navegación y favoritos.</span><span class="sxs-lookup"><span data-stu-id="60a66-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="60a66-141">Para obtener más información, vea [instalar y configurar el nuevo Microsoft Edge](surface-hub-install-chromium-edge.md).</span><span class="sxs-lookup"><span data-stu-id="60a66-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="60a66-142">Una vez que haya iniciado sesión en Surface Hub, puede usar otras aplicaciones sin tener que iniciar sesión de nuevo hasta que seleccione **finalizar sesión**.</span><span class="sxs-lookup"><span data-stu-id="60a66-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="60a66-143">Al seleccionar **finalizar sesión** , se eliminan las credenciales, los archivos y los datos personales del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60a66-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="60a66-144">Para obtener más información, consulte [finalizar sesión](finishing-your-surface-hub-meeting.md).</span><span class="sxs-lookup"><span data-stu-id="60a66-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="60a66-145">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="60a66-145">Learn more</span></span>

- [<span data-ttu-id="60a66-146">Opciones de autenticación no de contraseña para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="60a66-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="60a66-147">Inicio de sesión sin contraseña con la aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="60a66-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="60a66-148">Inicio de sesión sin contraseñas con las claves de seguridad FIDO2</span><span class="sxs-lookup"><span data-stu-id="60a66-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


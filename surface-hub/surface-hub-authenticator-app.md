---
title: Iniciar sesión en Surface Hub con Microsoft Authenticator
description: Usa Microsoft Authenticator en tu dispositivo móvil para iniciar sesión en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835257"
---
# <span data-ttu-id="8466e-103">Iniciar sesión en Surface Hub con Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="8466e-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="8466e-104">Las personas de tu organización pueden iniciar sesión en un dispositivo Surface Hub sin una contraseña con la aplicación Microsoft Authenticator, disponible en Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="8466e-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <span data-ttu-id="8466e-105">Requisitos previos de la organización</span><span class="sxs-lookup"><span data-stu-id="8466e-105">Organization prerequisites</span></span>

<span data-ttu-id="8466e-106">Para permitir que las personas de tu organización inicien sesión en Surface Hub con sus teléfonos y otros dispositivos en lugar de una contraseña, tendrás que asegúrate de que la organización cumple estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8466e-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="8466e-107">La organización debe tener un entorno híbrido o solo en la nube, respaldada por la solución Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8466e-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="8466e-108">Para más información, consulta [¿Qué es Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="8466e-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="8466e-109">Asegúrate de tener como mínimo una suscripción a Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="8466e-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="8466e-110">[Configurar la autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span><span class="sxs-lookup"><span data-stu-id="8466e-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="8466e-111">Asegúrate de que la opción **Notificación a través de aplicación móvil** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8466e-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![opciones de autenticación multifactor](images/mfa-options.png)

- <span data-ttu-id="8466e-113">Habilitar el hospedaje de contenido en servicios de Azure AD como Office, SharePoint, etc.</span><span class="sxs-lookup"><span data-stu-id="8466e-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="8466e-114">Surface Hub debe ejecutar Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8466e-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="8466e-115">Surface Hub está configurado con una cuenta local o unida a un dominio.</span><span class="sxs-lookup"><span data-stu-id="8466e-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

<span data-ttu-id="8466e-116">Actualmente, no puedes usar Microsoft Authenticator para iniciar sesión en los Surface Hub que estén unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8466e-116">Currently, you cannot use Microsoft Authenticator to sign in to Surface Hubs that are joined to Azure AD.</span></span>

## <span data-ttu-id="8466e-117">Requisitos previos individuales</span><span class="sxs-lookup"><span data-stu-id="8466e-117">Individual prerequisites</span></span>

- <span data-ttu-id="8466e-118">Un teléfono Android que ejecuta 6.0 o versión posterior, o un iPhone o iPad que ejecuta iOS9 o versión posterior</span><span class="sxs-lookup"><span data-stu-id="8466e-118">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="8466e-119">La versión más reciente de la aplicación Microsoft Authenticator de la tienda de aplicaciones adecuada</span><span class="sxs-lookup"><span data-stu-id="8466e-119">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="8466e-120">En iOS, la versión de la aplicación debe ser 5.4.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="8466e-120">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="8466e-121">La aplicación Microsoft Authenticator en teléfonos con un sistema operativo Windows no pueden usarse para iniciar sesión en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8466e-121">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="8466e-122">El código de acceso o pantalla de bloqueo están habilitados en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="8466e-122">Passcode or screen lock on your device is enabled</span></span>

- <span data-ttu-id="8466e-123">Una dirección de correo electrónico SMTP estándar (ejemplo: jose@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8466e-123">A standard SMTP email address (example: joe@contoso.com).</span></span> <span data-ttu-id="8466e-124">Actualmente, las direcciones de correo electrónico SMTP no estándares o personalizadas (ejemplo: nombre.apellido@contoso.com) no funcionan.</span><span class="sxs-lookup"><span data-stu-id="8466e-124">Non-standard or vanity SMTP email addresses (example: firstname.lastname@contoso.com) currently don’t work.</span></span>

## <span data-ttu-id="8466e-125">Cómo configurar la aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="8466e-125">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="8466e-126">Si el Portal de empresa está instalado en tu dispositivo Android, desinstálalo antes de configurar Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="8466e-126">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="8466e-127">Después de configurar la aplicación, puedes reinstalar Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="8466e-127">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="8466e-128">Si ya has configurado Microsoft Authenticator en tu teléfono y has registrado tu dispositivos, ve a las instrucciones de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8466e-128">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="8466e-129">Agrega tu cuenta profesional o educativa a Microsoft Authenticator para la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="8466e-129">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="8466e-130">Necesitarás un código QR proporcionado por el departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="8466e-130">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="8466e-131">Para obtener ayuda, consulta [Introducción a la aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span><span class="sxs-lookup"><span data-stu-id="8466e-131">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="8466e-132">Ve a **Configuración** y registrar tu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8466e-132">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="8466e-133">Vuelve a la página de cuentas y elige **Habilitar el inicio de sesión en el teléfono** en el menú desplegable Cuenta.</span><span class="sxs-lookup"><span data-stu-id="8466e-133">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <span data-ttu-id="8466e-134">Cómo iniciar sesión en Surface Hub durante una reunión</span><span class="sxs-lookup"><span data-stu-id="8466e-134">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="8466e-135">Después de configurar una reunión, ve a Surface Hub y selecciona **Inicia sesión para ver las reuniones y los archivos**.</span><span class="sxs-lookup"><span data-stu-id="8466e-135">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8466e-136">Si no está seguro cómo programar una reunión en Surface Hub, consulta [Programar un Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span><span class="sxs-lookup"><span data-stu-id="8466e-136">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![captura de pantalla de la opción de inicio de sesión en Surface Hub](images/sign-in.png)

2. <span data-ttu-id="8466e-138">Verás una lista de las personas invitadas a la reunión.</span><span class="sxs-lookup"><span data-stu-id="8466e-138">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="8466e-139">Selecciónate a ti mismo (o selecciona la persona que quiere iniciar sesión, asegurándote de que esta persona haya realizado los pasos para configurar su dispositivo antes de la reunión) y luego selecciona **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="8466e-139">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![captura de pantalla de la lista de personas que asistirán a una reunión](images/attendees.png)

    <span data-ttu-id="8466e-141">Verás un código en el dispositivo Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8466e-141">You'll see a code on the Surface Hub.</span></span>

    ![captura de pantalla del código de aprobación de inicio de sesión](images/approve-signin.png)

3. <span data-ttu-id="8466e-143">Para aprobar el inicio de sesión, abre la aplicación Authenticator, escribe el código de cuatro dígitos que se muestra en Surface Hub y selecciona **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="8466e-143">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="8466e-144">Se te pedirá que especifiques el PIN o que uses tu huella digital para completar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8466e-144">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![captura de pantalla de la pantalla de inicio de sesión de aprobación en Microsoft Authenticator](images/approve-signin2.png)

<span data-ttu-id="8466e-146">Ahora puedes acceder a todos los archivos a través de la aplicación OneDrive.</span><span class="sxs-lookup"><span data-stu-id="8466e-146">You can now access all files through the OneDrive app.</span></span>
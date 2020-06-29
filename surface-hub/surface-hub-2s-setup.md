---
title: Configuración de primera vez para Surface Hub 2S
description: Más información sobre cómo completar la configuración por primera vez para Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836122"
---
# <span data-ttu-id="c3abe-104">Configuración de primera vez para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="c3abe-104">First time Setup for Surface Hub 2S</span></span>

<span data-ttu-id="c3abe-105">La primera vez que inicie Surface Hub 2S, el dispositivo entra automáticamente en modo de configuración para guiarle por la configuración de la cuenta y la configuración relacionada.</span><span class="sxs-lookup"><span data-stu-id="c3abe-105">When you first start Surface Hub 2S, the device automatically enters first time Setup mode to guide you through account configuration and related settings.</span></span>

## <span data-ttu-id="c3abe-106">Configuración de la cuenta de Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="c3abe-106">Configuring Surface Hub 2S account</span></span>

1. **<span data-ttu-id="c3abe-107">Configure su configuración regional.</span><span class="sxs-lookup"><span data-stu-id="c3abe-107">Configure your locale.</span></span>** <span data-ttu-id="c3abe-108">Escriba la región, el idioma, la distribución del teclado y la información de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="c3abe-108">Enter region, language, keyboard layout and time zone information.</span></span> <span data-ttu-id="c3abe-109">Selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c3abe-109">Select **Next**.</span></span>

   ![\* Configura tu configuración regional \*](images/sh2-run1.png) <br>
1. **<span data-ttu-id="c3abe-111">Conéctate a una red inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="c3abe-111">Connect  to a wireless network.</span></span>** <span data-ttu-id="c3abe-112">Elija su red inalámbrica preferida y seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="c3abe-112">Choose your preferred wireless network and select **Next.**</span></span>

- <span data-ttu-id="c3abe-113">Esta opción no se muestra si está conectada usando un cable de Ethernet.</span><span class="sxs-lookup"><span data-stu-id="c3abe-113">This option is not shown if connected using an Ethernet cable.</span></span>
- <span data-ttu-id="c3abe-114">No puedes conectarte a una red inalámbrica en puntos de acceso público (portales cautivos) que redirijan solicitudes de inicio de sesión al sitio web de un proveedor.</span><span class="sxs-lookup"><span data-stu-id="c3abe-114">You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider’s website.</span></span>

3. **<span data-ttu-id="c3abe-115">Escribe la información de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3abe-115">Enter device account info.</span></span>** <span data-ttu-id="c3abe-116">Use **dominio\usuario** para entornos locales e híbridos y el **usuario \ @example. com** para entornos en línea.</span><span class="sxs-lookup"><span data-stu-id="c3abe-116">Use **domain\user** for on-premises and hybrid environments and **user\@example.com** for online environments.</span></span> <span data-ttu-id="c3abe-117">Seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="c3abe-117">Select **Next.**</span></span>

   ![\* Escribe la información de la cuenta del dispositivo \*](images/sh2-run2.png) <br>
1. **<span data-ttu-id="c3abe-119">Escriba información adicional.</span><span class="sxs-lookup"><span data-stu-id="c3abe-119">Enter additional info.</span></span>** <span data-ttu-id="c3abe-120">Si se le solicita, escriba la dirección del servidor de Exchange y, a continuación, seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="c3abe-120">If requested, provide your Exchange server address and then select **Next.**</span></span>

    ![\* Escribe más información; por ejemplo, nombre de servidor de Exchange \*](images/sh2-run3.png) <br>

1. **<span data-ttu-id="c3abe-122">Nombre de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3abe-122">Name this device.</span></span>** <span data-ttu-id="c3abe-123">Escriba un nombre para el dispositivo o use el sugerido según el nombre para mostrar y el nombre principal de usuario [UPN] de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="c3abe-123">Enter a name for your device or use the suggested one based on your account’s display name and user principle name [UPN].</span></span> <span data-ttu-id="c3abe-124">**Seleccione siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c3abe-124">**Select Next**.</span></span>

- <span data-ttu-id="c3abe-125">El **nombre descriptivo** está visible en la esquina inferior izquierda de Surface Hub 2s y se muestra al proyectar en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3abe-125">The **Friendly name** is visible on the bottom left corner of Surface Hub 2S and is shown when projecting to the device.</span></span>

- <span data-ttu-id="c3abe-126">El **nombre del dispositivo** identifica el dispositivo cuando se afilia a Active Directory o Azure Active Directory, y al inscribir el dispositivo con Intune.</span><span class="sxs-lookup"><span data-stu-id="c3abe-126">The **Device name** identifies the device when affiliated with Active Directory or Azure Active Directory, and when enrolling the device with Intune.</span></span>

  ![\* Nombre de este dispositivo \*](images/sh2-run4.png) <br>
 
## <span data-ttu-id="c3abe-128">Configurar cuentas de administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3abe-128">Configuring device admin accounts</span></span>

<span data-ttu-id="c3abe-129">Solo puedes configurar administradores de dispositivos durante la configuración de primera vez.</span><span class="sxs-lookup"><span data-stu-id="c3abe-129">You can only set up device admins during first time Setup.</span></span> <span data-ttu-id="c3abe-130">Para obtener más información, consulte [afiliación del dispositivo Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).</span><span class="sxs-lookup"><span data-stu-id="c3abe-130">For more information, refer to [Surface Hub 2S device affiliation](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).</span></span>

 <span data-ttu-id="c3abe-131">En la ventana **administradores de la instalación de este dispositivo** , seleccione una de las siguientes opciones: servicios de dominio de Active Directory, Azure Active Directory o administrador local.</span><span class="sxs-lookup"><span data-stu-id="c3abe-131">In the **Setup admins for this device** window, select one of the following options: Active Directory Domain Services, Azure Active Directory, or Local admin.</span></span>

   ![\* Administradores de instalación para este dispositivo \*](images/sh2-run5.png) <br>

### <span data-ttu-id="c3abe-133">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="c3abe-133">Active Directory Domain Services</span></span>

1. <span data-ttu-id="c3abe-134">Escriba las credenciales de un usuario que tiene permisos para unir el dispositivo a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3abe-134">Enter the credentials of a user who has permissions to join the device to Active Directory.</span></span>

    ![\* Administradores de instalación que usan unirse a un dominio \*](images/sh2-run6.png) <br>

2. <span data-ttu-id="c3abe-136">Seleccione el grupo de seguridad de Active Directory que contiene miembros a los que se permite iniciar sesión en la aplicación configuración de Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="c3abe-136">Select the Active Directory Security Group containing members allowed to log on to the Settings app on Surface Hub 2S.</span></span>

    ![\* Introduce un grupo de seguridad \*](images/sh2-run7.png) <br>
1. <span data-ttu-id="c3abe-138">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c3abe-138">Select **Finish**.</span></span> <span data-ttu-id="c3abe-139">El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="c3abe-139">The device will restart.</span></span>

### <span data-ttu-id="c3abe-140">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c3abe-140">Azure Active Directory</span></span>

<span data-ttu-id="c3abe-141">Cuando elijas afiliar su dispositivo con Azure Active Directory, el dispositivo se reiniciará inmediatamente y mostrará la siguiente página.</span><span class="sxs-lookup"><span data-stu-id="c3abe-141">When choosing to affiliate your device with Azure Active Directory, the device will immediately restart and display the following page.</span></span> <span data-ttu-id="c3abe-142">Selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c3abe-142">Select **Next**.</span></span>

![\* Si su organización usa Office 365 u otros servicios empresariales de Microsoft, inscribiremos este dispositivo con su organización \*](images/sh2-run8.png) <br>

1. <span data-ttu-id="c3abe-144">Escriba la dirección de correo electrónico o el UPN de una cuenta **con plan 1** o superior y, después, seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="c3abe-144">Enter the email address or UPN of an account **with Intune Plan 1** or greater and then select **Next.**</span></span>

    ![\* Escriba una cuenta profesional o educativa \*](images/sh2-run9.png) <br>

2. <span data-ttu-id="c3abe-146">Si se redirige, autentique con la página de inicio de sesión de su organización y proporcione información de inicio de sesión adicional si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="c3abe-146">If redirected, authenticate using your organization’s sign-in page and provide additional logon information if requested.</span></span> <span data-ttu-id="c3abe-147">El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="c3abe-147">The device will restart.</span></span>

## <span data-ttu-id="c3abe-148">Cuenta de administrador local</span><span class="sxs-lookup"><span data-stu-id="c3abe-148">Local Administrator account</span></span>

- <span data-ttu-id="c3abe-149">Escriba un nombre de usuario y una contraseña para el administrador local. El dispositivo se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="c3abe-149">Enter a username and password for your local admin. The device will restart.</span></span>

     ![\* Configurar una cuenta de administrador \*](images/sh2-run10.png) <br>
 
## <span data-ttu-id="c3abe-151">Usar paquetes de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="c3abe-151">Using provisioning packages</span></span>

<span data-ttu-id="c3abe-152">Si inserta una unidad USB con un paquete de aprovisionamiento en uno de los puertos USB cuando inicia Surface Hub 2S, el dispositivo muestra la siguiente página.</span><span class="sxs-lookup"><span data-stu-id="c3abe-152">If you insert a USB thumb drive with a provisioning package into one of the USB ports when you start Surface Hub 2S, the device displays the following page.</span></span>

1. <span data-ttu-id="c3abe-153">Escriba la configuración solicitada y seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="c3abe-153">Enter the requested settings and select **Set up**.</span></span>

    ![\* Especificar la configuración regional para el paquete de aprovisionamiento \*](images/sh2-run11.png) <br>

    ![\* Aprovisionar este dispositivo desde medios extraíbles \*](images/sh2-run12.png) <br>
2. <span data-ttu-id="c3abe-156">Elige el paquete de aprovisionamiento que deseas usar.</span><span class="sxs-lookup"><span data-stu-id="c3abe-156">Choose the provisioning package you’d like to use.</span></span>

   ![\* Elige el paquete de aprovisionamiento para usar \*](images/sh2-run13.png) <br>

3. <span data-ttu-id="c3abe-158">Si has creado un archivo CSV de dispositivos múltiples, podrás elegir una configuración de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3abe-158">If you created a multiple devices CSV file, you will be able to choose a device configuration.</span></span> <span data-ttu-id="c3abe-159">Para obtener más información, consulte [crear paquetes de aprovisionamiento para Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span><span class="sxs-lookup"><span data-stu-id="c3abe-159">For more information, refer to [Create provisioning packages for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span></span>


    ![\* Seleccione una cuenta del dispositivo y un nombre descriptivo en el archivo de configuración \*](images/sh2-run14.png) <br>

4. <span data-ttu-id="c3abe-161">Siga las instrucciones para completar la configuración por primera vez.</span><span class="sxs-lookup"><span data-stu-id="c3abe-161">Follow the instructions to complete first time Setup.</span></span>

---
title: Administrar la configuración de la UEFI de Surface
description: Usar la configuración de UEFI de Surface para habilitar o deshabilitar dispositivos o componentes, configurar las opciones de seguridad y ajustar la configuración de arranque del dispositivo Surface.
keywords: firmware, seguridad, características, configurar, hardware
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/25/2021
ms.openlocfilehash: af9eac171dea5d29ce9776766a2c5842bea9eb8c
ms.sourcegitcommit: 1b12ea363785697ddc705b0a0cc7bb35cad6b327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "11300701"
---
# <span data-ttu-id="25b33-104">Administrar la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="25b33-105">Los dispositivos Surface PC están diseñados para usar una interfaz de firmware extensible unificada (UEFI) única diseñada por Microsoft específicamente para estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="25b33-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="25b33-106">La configuración de UEFI de Surface proporciona la capacidad de habilitar o deshabilitar dispositivos y componentes integrados, proteger la configuración de UEFI de cambios y ajustar la configuración de arranque del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="25b33-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="25b33-107">Productos admitidos</span><span class="sxs-lookup"><span data-stu-id="25b33-107">Supported products</span></span>

<span data-ttu-id="25b33-108">La administración de UEFI es compatible con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25b33-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="25b33-109">Surface Pro 4, Surface Pro (5ª generación), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="25b33-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="25b33-110">Surface Laptop (1.ª generación), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="25b33-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go</span></span>
- <span data-ttu-id="25b33-111">Surface Studio (1ª generación), Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="25b33-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="25b33-112">Surface Book, Surface Book 2, Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="25b33-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="25b33-113">Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="25b33-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <span data-ttu-id="25b33-114">Compatibilidad con la administración basada en la nube</span><span class="sxs-lookup"><span data-stu-id="25b33-114">Support for cloud-based management</span></span>

<span data-ttu-id="25b33-115">Con los perfiles de La interfaz de configuración de firmware de dispositivo (DFCI) integrados en Microsoft Intune (ahora disponible en la versión preliminar pública), la administración de LA UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware de UEFI.</span><span class="sxs-lookup"><span data-stu-id="25b33-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="25b33-116">DFCI admite el aprovisionamiento sin intervención táctil, elimina las contraseñas de BIOS, proporciona control de la configuración de seguridad, incluidas las opciones de arranque y periféricos integrados, y establece las bases para escenarios de seguridad avanzados en el futuro.</span><span class="sxs-lookup"><span data-stu-id="25b33-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="25b33-117">DFCI está disponible actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 y Surface Pro X.  Para obtener más información, consulta la administración [de Intune de la configuración de LA UEFI de Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="25b33-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="25b33-118">Menú Abrir UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="25b33-119">Para ajustar la configuración de UEFI durante el inicio del sistema:</span><span class="sxs-lookup"><span data-stu-id="25b33-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="25b33-120">Apaga Surface y espera unos 10 segundos para asegurarte de que está apagada.</span><span class="sxs-lookup"><span data-stu-id="25b33-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="25b33-121">Mantén presionado el **botón Subir** volumen y, al mismo tiempo, presiona y suelta el botón **De encendido.**</span><span class="sxs-lookup"><span data-stu-id="25b33-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="25b33-122">A medida que aparezca el logotipo de Microsoft \*\*\*\* o Surface en la pantalla, mantén presionado el botón Subir volumen hasta que aparezca la pantalla UEFI.</span><span class="sxs-lookup"><span data-stu-id="25b33-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="25b33-123">Página de información de UEFI PC</span><span class="sxs-lookup"><span data-stu-id="25b33-123">UEFI PC information page</span></span>

<span data-ttu-id="25b33-124">La página de información del equipo incluye información detallada sobre el dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="25b33-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="25b33-125">**Modelo:** el modelo del dispositivo Surface se mostrará aquí, como Surface Book 2 o Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="25b33-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="25b33-126">No se muestra la configuración exacta de tu dispositivo (por ejemplo, el procesador, el tamaño del disco o el tamaño de la memoria).</span><span class="sxs-lookup"><span data-stu-id="25b33-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="25b33-127">**UUID**: este número de identificación único universal es específico de tu dispositivo y se usa para identificar el dispositivo durante la implementación o la administración.</span><span class="sxs-lookup"><span data-stu-id="25b33-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="25b33-128">**Número de serie**: este número se usa para identificar este dispositivo de Surface específico para etiquetas de inventario y en escenarios de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="25b33-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="25b33-129">**Etiqueta de inventario**: la etiqueta de inventario se asigna al dispositivo de Surface con la [Herramienta de etiqueta de inventario](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="25b33-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="25b33-130">También encontrarás información detallada sobre el firmware del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="25b33-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="25b33-131">Los dispositivos Surface tienen varios componentes internos y cada uno ejecuta distintas versiones de firmware.</span><span class="sxs-lookup"><span data-stu-id="25b33-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="25b33-132">La versión de firmware de cada uno de los siguientes dispositivos se muestra en la página **Información del equipo** (como se muestra en la figura 1):</span><span class="sxs-lookup"><span data-stu-id="25b33-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="25b33-133">UEFI del sistema</span><span class="sxs-lookup"><span data-stu-id="25b33-133">System UEFI</span></span> 

- <span data-ttu-id="25b33-134">Controladora SAM</span><span class="sxs-lookup"><span data-stu-id="25b33-134">SAM Controller</span></span> 

- <span data-ttu-id="25b33-135">Motor de administración de Intel</span><span class="sxs-lookup"><span data-stu-id="25b33-135">Intel Management Engine</span></span> 

- <span data-ttu-id="25b33-136">Controlador integrado del sistema</span><span class="sxs-lookup"><span data-stu-id="25b33-136">System Embedded Controller</span></span> 

- <span data-ttu-id="25b33-137">Firmware de entrada táctil</span><span class="sxs-lookup"><span data-stu-id="25b33-137">Touch Firmware</span></span> 

![Información del sistema e información de la versión de firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="25b33-139">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="25b33-139">Figure 1.</span></span> <span data-ttu-id="25b33-140">Información del sistema e información de la versión de firmware</span><span class="sxs-lookup"><span data-stu-id="25b33-140">System information and firmware version information</span></span>*

<span data-ttu-id="25b33-141">Puedes encontrar información actualizada sobre la versión de firmware más reciente para el dispositivo Surface en el [Historial de actualizaciones Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25b33-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="25b33-142">Página Seguridad de UEFI</span><span class="sxs-lookup"><span data-stu-id="25b33-142">UEFI Security page</span></span> 

![Configuración de las opciones de seguridad de la UEFI de Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="25b33-144">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="25b33-144">Figure 2.</span></span> <span data-ttu-id="25b33-145">Configuración de las opciones de seguridad de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="25b33-146">La página Seguridad te permite establecer una contraseña para proteger la configuración de UEFI.</span><span class="sxs-lookup"><span data-stu-id="25b33-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="25b33-147">Esta contraseña se debe especificar cuando se arranque el dispositivo Surface en la UEFI.</span><span class="sxs-lookup"><span data-stu-id="25b33-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="25b33-148">La contraseña puede contener los siguientes caracteres (como se muestra en la figura 3):</span><span class="sxs-lookup"><span data-stu-id="25b33-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="25b33-149">Letras mayúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="25b33-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="25b33-150">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="25b33-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="25b33-151">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="25b33-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="25b33-152">Caracteres especiales: !@#$%^&\*()?<>{} []-_=+|.,;:''"</span><span class="sxs-lookup"><span data-stu-id="25b33-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="25b33-153">La contraseña debe tener al menos 6 caracteres y distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="25b33-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![Agregar una contraseña para proteger la configuración de la UEFI de Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="25b33-155">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="25b33-155">Figure 3.</span></span> <span data-ttu-id="25b33-156">Agregar una contraseña para proteger la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="25b33-157">En la página Seguridad también puedes cambiar la configuración de arranque seguro en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="25b33-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="25b33-158">La tecnología de arranque seguro impide que el código de arranque no autorizado arranque en el dispositivo Surface, lo que protege contra infecciones de malware de tipo bootkit y rootkit.</span><span class="sxs-lookup"><span data-stu-id="25b33-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="25b33-159">Puedes deshabilitar el arranque seguro para permitir el dispositivo Surface en sistemas operativos de terceros de arranque o medios de arranque.</span><span class="sxs-lookup"><span data-stu-id="25b33-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="25b33-160">También puedes configurar el arranque seguro para que funcione con certificados de terceros, como se muestra en la figura 4.</span><span class="sxs-lookup"><span data-stu-id="25b33-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="25b33-161">Lee más sobre el [Arranque seguro](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) en la biblioteca de TechNet.</span><span class="sxs-lookup"><span data-stu-id="25b33-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar el arranque seguro](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="25b33-163">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="25b33-163">Figure 4.</span></span> <span data-ttu-id="25b33-164">Configurar el arranque seguro</span><span class="sxs-lookup"><span data-stu-id="25b33-164">Configure Secure Boot</span></span>*

<span data-ttu-id="25b33-165">Según el dispositivo, es posible que también puedas ver si el TPM está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="25b33-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="25b33-166">Si no ves la opción Habilitar **TPM,**  abre tpm.msc en Windows para comprobar el estado, como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="25b33-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="25b33-167">El TPM se usa para autenticar el cifrado de datos de tu dispositivo con BitLocker.</span><span class="sxs-lookup"><span data-stu-id="25b33-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="25b33-168">Para obtener más información, consulta Información [general de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)</span><span class="sxs-lookup"><span data-stu-id="25b33-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Consola de TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="25b33-170">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="25b33-170">Figure 5.</span></span> <span data-ttu-id="25b33-171">Consola de TPM</span><span class="sxs-lookup"><span data-stu-id="25b33-171">TPM console</span></span>*


## <span data-ttu-id="25b33-172">Menú UEFI: Dispositivos</span><span class="sxs-lookup"><span data-stu-id="25b33-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="25b33-173">La página Dispositivos te permite habilitar o deshabilitar dispositivos y componentes específicos, como:</span><span class="sxs-lookup"><span data-stu-id="25b33-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="25b33-174">Acoplamiento y puertos USB</span><span class="sxs-lookup"><span data-stu-id="25b33-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="25b33-175">Ranura para tarjeta microSD o SD</span><span class="sxs-lookup"><span data-stu-id="25b33-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="25b33-176">Cámara trasera</span><span class="sxs-lookup"><span data-stu-id="25b33-176">Rear Camera</span></span> 

- <span data-ttu-id="25b33-177">Cámara frontal</span><span class="sxs-lookup"><span data-stu-id="25b33-177">Front Camera</span></span> 

- <span data-ttu-id="25b33-178">Cámara de infrarrojos (IR)</span><span class="sxs-lookup"><span data-stu-id="25b33-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="25b33-179">Wi-Fi y Bluetooth</span><span class="sxs-lookup"><span data-stu-id="25b33-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="25b33-180">Audio integrado (altavoces y micrófono)</span><span class="sxs-lookup"><span data-stu-id="25b33-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="25b33-181">Cada dispositivo aparece con un botón deslizante \*\*\*\* que puedes mover a la posición Activado (habilitado) o Desactivado **(deshabilitado),** como se muestra en la figura 6.</span><span class="sxs-lookup"><span data-stu-id="25b33-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar y deshabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="25b33-183">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="25b33-183">Figure 6.</span></span> <span data-ttu-id="25b33-184">Habilitar y deshabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="25b33-184">Enable and disable specific devices</span></span>*

## <span data-ttu-id="25b33-185">Menú UEFI: configuración de arranque</span><span class="sxs-lookup"><span data-stu-id="25b33-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="25b33-186">La página Configuración de arranque te permite cambiar el orden de los dispositivos de arranque, así como habilitar o deshabilitar el arranque de los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="25b33-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="25b33-187">Administración de arranque de Windows</span><span class="sxs-lookup"><span data-stu-id="25b33-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="25b33-188">Almacenamiento USB</span><span class="sxs-lookup"><span data-stu-id="25b33-188">USB Storage</span></span> 

- <span data-ttu-id="25b33-189">Red PXE</span><span class="sxs-lookup"><span data-stu-id="25b33-189">PXE Network</span></span> 

- <span data-ttu-id="25b33-190">Almacenamiento interno</span><span class="sxs-lookup"><span data-stu-id="25b33-190">Internal Storage</span></span> 

<span data-ttu-id="25b33-191">Puedes arrancar desde un dispositivo específico inmediatamente o puedes deslizar rápidamente hacia la izquierda en la entrada del dispositivo en la lista con la pantalla táctil.</span><span class="sxs-lookup"><span data-stu-id="25b33-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="25b33-192">También puedes arrancar inmediatamente en un dispositivo USB o un adaptador Ethernet USB cuando el dispositivo Surface esté apagado, presionando el botón **Bajar el volumen** y el botón **Inicio/apagado** simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="25b33-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="25b33-193">Para que el orden de arranque especificado \*\*\*\* entre en vigor, debes establecer la opción Habilitar secuencia de arranque alternativa en **Activar,** como se muestra en la figura 7.</span><span class="sxs-lookup"><span data-stu-id="25b33-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar el orden de arranque para el dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="25b33-195">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="25b33-195">Figure 7.</span></span> <span data-ttu-id="25b33-196">Configurar el orden de arranque para el dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="25b33-197">También puedes activar y desactivar la compatibilidad con IPv6 PXE con la opción **Habilitar IPv6 para el arranque de Red PXE**, por ejemplo, al realizar una implementación de Windows con PXE en el que el servidor PXE está configurado solo para IPv4.</span><span class="sxs-lookup"><span data-stu-id="25b33-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="25b33-198">Menú UEFI: Administración</span><span class="sxs-lookup"><span data-stu-id="25b33-198">UEFI menu: Management</span></span>
<span data-ttu-id="25b33-199">La página Administración te permite administrar el uso de la administración de UEFI sin entrada táctil y otras características en dispositivos elegibles, como Surface Pro 7, Surface Pro X y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="25b33-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="25b33-200">Administrar el acceso a zero Touch UEFI Management y otras características ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *de la figura 8. Administrar el acceso a zero Touch UEFI Management y otras características*</span><span class="sxs-lookup"><span data-stu-id="25b33-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="25b33-201">Zero Touch UEFI Management te permite administrar de forma remota la configuración de UEFI mediante un perfil de dispositivo en Intune denominado Device Firmware Configuration Interface (DFCI).</span><span class="sxs-lookup"><span data-stu-id="25b33-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="25b33-202">Si no configuras esta opción, la capacidad de administrar dispositivos elegibles con DFCI se establece en **Listo.**</span><span class="sxs-lookup"><span data-stu-id="25b33-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="25b33-203">Para evitar DFCI, seleccione **Optar por no participar.**</span><span class="sxs-lookup"><span data-stu-id="25b33-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="25b33-204">La página de configuración de administración de UEFI y el uso de DFCI están disponibles actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 y Surface Pro X. Para obtener más información, consulta [Administración de Intune de la configuración de LA UEFI de Surface.](surface-manage-dfci-guide.md)</span><span class="sxs-lookup"><span data-stu-id="25b33-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="25b33-205">Menú UEFI: Salir</span><span class="sxs-lookup"><span data-stu-id="25b33-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="25b33-206">Use el **botón Reiniciar ahora** de la página **Salir** para salir de la configuración de UEFI, como se muestra en la figura 9.</span><span class="sxs-lookup"><span data-stu-id="25b33-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Salir de la UEFI de Surface y reiniciar el dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="25b33-208">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="25b33-208">Figure 9.</span></span> <span data-ttu-id="25b33-209">Haz clic en Reiniciar ahora para salir de la UEFI de Surface y reiniciar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="25b33-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="25b33-210">Pantallas de arranque de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="25b33-211">Cuando actualizas el firmware del dispositivo Surface, ya sea mediante Windows Update o la instalación manual, las actualizaciones no se aplican de inmediato en el dispositivo, sino durante el próximo ciclo de reinicio.</span><span class="sxs-lookup"><span data-stu-id="25b33-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="25b33-212">Puedes encontrar más información sobre el proceso de actualización de firmware de Surface en [Administrar las actualizaciones de controladores y firmware de Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="25b33-212">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="25b33-213">El progreso de la actualización del firmware se muestra en una pantalla con barras de progreso de colores diferentes para indicar el firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="25b33-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="25b33-214">La barra de progreso de cada componente se muestra en las figuras 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="25b33-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Actualización del firmware de la UEFI de Surface con barra de progreso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="25b33-216">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="25b33-216">Figure 10.</span></span> <span data-ttu-id="25b33-217">La actualización del firmware de la UEFI de Surface muestra una barra de progreso azul</span><span class="sxs-lookup"><span data-stu-id="25b33-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador integrado del sistema con la barra de progreso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="25b33-219">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="25b33-219">Figure 11.</span></span> <span data-ttu-id="25b33-220">La actualización del firmware de controlador integrado del sistema muestra una barra de progreso verde</span><span class="sxs-lookup"><span data-stu-id="25b33-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Actualización del firmware de controladora SAM con barra de progreso naranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="25b33-222">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="25b33-222">Figure 12.</span></span> <span data-ttu-id="25b33-223">La actualización de firmware de la controladora SAM muestra una barra de progreso naranja</span><span class="sxs-lookup"><span data-stu-id="25b33-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware del motor de administración de Intel con barra de progreso roja](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="25b33-225">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="25b33-225">Figure 13.</span></span> <span data-ttu-id="25b33-226">La actualización del firmware del motor de administración de Intel muestra una barra de progreso roja</span><span class="sxs-lookup"><span data-stu-id="25b33-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Firmware de entrada táctil de Surface con barra de progreso gris](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="25b33-228">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="25b33-228">Figure 14.</span></span> <span data-ttu-id="25b33-229">La actualización del firmware de entrada táctil de Surface muestra una barra de progreso gris</span><span class="sxs-lookup"><span data-stu-id="25b33-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware surface DESP con barra de progreso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="25b33-231">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="25b33-231">Figure 15.</span></span> <span data-ttu-id="25b33-232">La actualización de firmware de SURFACE KIP muestra una barra de progreso verde claro</span><span class="sxs-lookup"><span data-stu-id="25b33-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Firmware ish de Surface con barra de progreso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="25b33-234">Figura 16 La actualización de firmware ish de Surface muestra una barra de progreso rosa claro</span><span class="sxs-lookup"><span data-stu-id="25b33-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware de Surface Trackpad con barra de progreso gris](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="25b33-236">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="25b33-236">Figure 17.</span></span> <span data-ttu-id="25b33-237">La actualización de firmware de Surface Trackpad muestra una barra de progreso rosa</span><span class="sxs-lookup"><span data-stu-id="25b33-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Firmware de Surface TCON con barra de progreso gris claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="25b33-239">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="25b33-239">Figure 18.</span></span> <span data-ttu-id="25b33-240">La actualización de firmware de Surface TCON muestra una barra de progreso gris claro</span><span class="sxs-lookup"><span data-stu-id="25b33-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Firmware de TPM de Surface con barra de progreso púrpura claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="25b33-242">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="25b33-242">Figure 19.</span></span> <span data-ttu-id="25b33-243">La actualización de firmware del TPM de Surface muestra una barra de progreso púrpura</span><span class="sxs-lookup"><span data-stu-id="25b33-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="25b33-244">Se muestra un mensaje de advertencia adicional que indica que el arranque seguro está deshabilitado, como se muestra en la figura 19.</span><span class="sxs-lookup"><span data-stu-id="25b33-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="25b33-246">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="25b33-246">Figure 20.</span></span> <span data-ttu-id="25b33-247">Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado en la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="25b33-248">Referencias</span><span class="sxs-lookup"><span data-stu-id="25b33-248">References</span></span>

1. <span data-ttu-id="25b33-249">Surface Go y Surface Go 2 usan una UEFI de terceros y no admiten DFCI.</span><span class="sxs-lookup"><span data-stu-id="25b33-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <span data-ttu-id="25b33-250">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="25b33-250">Related topics</span></span>

- [<span data-ttu-id="25b33-251">Administración de Intune de la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="25b33-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="25b33-252">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="25b33-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)

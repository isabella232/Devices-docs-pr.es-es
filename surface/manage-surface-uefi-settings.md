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
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835857"
---
# <span data-ttu-id="8d7d5-104">Administrar la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="8d7d5-105">Todas las generaciones actuales y futuras de dispositivos de superficie usan una interfaz de firmware extensible (UEFI) única diseñada por Microsoft específicamente para estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="8d7d5-106">La configuración de Surface UEFI ofrece la capacidad de habilitar o deshabilitar dispositivos y componentes integrados, proteger la configuración de UEFI y ajustar la configuración de inicio del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="8d7d5-107">Compatibilidad con la administración basada en la nube</span><span class="sxs-lookup"><span data-stu-id="8d7d5-107">Support for cloud-based management</span></span>

<span data-ttu-id="8d7d5-108">Con los perfiles de la interfaz de configuración de firmware (DFCI) integrado en Microsoft Intune (ahora disponible en la versión preliminar pública), la administración de Surface UEFI amplía la pila de administración moderna al nivel de hardware de UEFI.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="8d7d5-109">DFCI es compatible con el aprovisionamiento sin contacto, elimina las contraseñas del BIOS, proporciona el control de la configuración de seguridad, incluidas las opciones de arranque y los periféricos integrados, y establece las bases para escenarios de seguridad avanzada en el futuro.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="8d7d5-110">DFCI está disponible actualmente para Surface Pro 7, Surface Pro X y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="8d7d5-111">Para obtener más información, consulte la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="8d7d5-112">Menú abrir superficie UEFI</span><span class="sxs-lookup"><span data-stu-id="8d7d5-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="8d7d5-113">Para ajustar la configuración de UEFI durante el inicio del sistema:</span><span class="sxs-lookup"><span data-stu-id="8d7d5-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="8d7d5-114">Apaga tu superficie y espera unos 10 segundos para asegurarse de que está desactivada.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="8d7d5-115">Mantén pulsado el botón de **subir el volumen** y, al mismo tiempo, pulsa y suelta el **botón de encendido.**</span><span class="sxs-lookup"><span data-stu-id="8d7d5-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="8d7d5-116">Como el logotipo de Microsoft o de Surface aparece en la pantalla, siga manteniendo el botón **subir de volumen** hasta que aparezca la pantalla UEFI.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="8d7d5-117">Página de información de UEFI PC</span><span class="sxs-lookup"><span data-stu-id="8d7d5-117">UEFI PC information page</span></span>

<span data-ttu-id="8d7d5-118">La página información del PC incluye información detallada sobre el dispositivo Surface:</span><span class="sxs-lookup"><span data-stu-id="8d7d5-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="8d7d5-119">**Modelo** : el modelo del dispositivo Surface se mostrará aquí, como Surface Book 2 o Surface Pro 7.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="8d7d5-120">No se muestra la configuración exacta de tu dispositivo (por ejemplo, el procesador, el tamaño del disco o el tamaño de la memoria).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="8d7d5-121">**UUID**: este número de identificación único universal es específico de tu dispositivo y se usa para identificar el dispositivo durante la implementación o la administración.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="8d7d5-122">**Número de serie**: este número se usa para identificar este dispositivo de Surface específico para etiquetas de inventario y en escenarios de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="8d7d5-123">**Etiqueta de inventario**: la etiqueta de inventario se asigna al dispositivo de Surface con la [Herramienta de etiqueta de inventario](https://docs.microsoft.com/surface/assettag).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="8d7d5-124">También encontrarás información detallada sobre el firmware del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="8d7d5-125">Los dispositivos Surface tienen varios componentes internos y cada uno ejecuta distintas versiones de firmware.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="8d7d5-126">La versión de firmware de cada uno de los siguientes dispositivos se muestra en la página **Información del equipo** (como se muestra en la figura 1):</span><span class="sxs-lookup"><span data-stu-id="8d7d5-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="8d7d5-127">UEFI del sistema</span><span class="sxs-lookup"><span data-stu-id="8d7d5-127">System UEFI</span></span> 

- <span data-ttu-id="8d7d5-128">Controladora SAM</span><span class="sxs-lookup"><span data-stu-id="8d7d5-128">SAM Controller</span></span> 

- <span data-ttu-id="8d7d5-129">Motor de administración de Intel</span><span class="sxs-lookup"><span data-stu-id="8d7d5-129">Intel Management Engine</span></span> 

- <span data-ttu-id="8d7d5-130">Controlador integrado del sistema</span><span class="sxs-lookup"><span data-stu-id="8d7d5-130">System Embedded Controller</span></span> 

- <span data-ttu-id="8d7d5-131">Firmware de entrada táctil</span><span class="sxs-lookup"><span data-stu-id="8d7d5-131">Touch Firmware</span></span> 

![Información del sistema e información de la versión de firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="8d7d5-133">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-133">Figure 1.</span></span> <span data-ttu-id="8d7d5-134">Información del sistema e información de la versión de firmware</span><span class="sxs-lookup"><span data-stu-id="8d7d5-134">System information and firmware version information</span></span>*

<span data-ttu-id="8d7d5-135">Puedes encontrar información actualizada sobre la versión de firmware más reciente para el dispositivo Surface en el [Historial de actualizaciones Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="8d7d5-136">Página de seguridad UEFI</span><span class="sxs-lookup"><span data-stu-id="8d7d5-136">UEFI Security page</span></span> 

![Configuración de las opciones de seguridad de la UEFI de Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="8d7d5-138">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-138">Figure 2.</span></span> <span data-ttu-id="8d7d5-139">Configuración de las opciones de seguridad de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="8d7d5-140">La página seguridad le permite establecer una contraseña para proteger la configuración de UEFI.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="8d7d5-141">Esta contraseña se debe especificar cuando se arranque el dispositivo Surface en la UEFI.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="8d7d5-142">La contraseña puede contener los siguientes caracteres (como se muestra en la ilustración 3):</span><span class="sxs-lookup"><span data-stu-id="8d7d5-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="8d7d5-143">Letras mayúsculas: A-Z</span><span class="sxs-lookup"><span data-stu-id="8d7d5-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="8d7d5-144">Letras minúsculas: a-z</span><span class="sxs-lookup"><span data-stu-id="8d7d5-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="8d7d5-145">Números: 1-0</span><span class="sxs-lookup"><span data-stu-id="8d7d5-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="8d7d5-146">Caracteres especiales:! @ # $% ^& \* ()? <>{} []-_ = + |.,;: ' ' "</span><span class="sxs-lookup"><span data-stu-id="8d7d5-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="8d7d5-147">La contraseña debe tener al menos 6 caracteres y distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![Agregar una contraseña para proteger la configuración de la UEFI de Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="8d7d5-149">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-149">Figure 3.</span></span> <span data-ttu-id="8d7d5-150">Agregar una contraseña para proteger la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="8d7d5-151">En la página Seguridad también puedes cambiar la configuración de arranque seguro en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="8d7d5-152">La tecnología de arranque seguro impide que el código de arranque no autorizado arranque en el dispositivo Surface, lo que protege contra infecciones de malware de tipo bootkit y rootkit.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="8d7d5-153">Puedes deshabilitar el arranque seguro para permitir el dispositivo Surface en sistemas operativos de terceros de arranque o medios de arranque.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="8d7d5-154">También puede configurar el arranque seguro para que funcione con certificados de terceros, como se muestra en la figura 4.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="8d7d5-155">Lee más sobre el [Arranque seguro](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) en la biblioteca de TechNet.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![Configurar el arranque seguro](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="8d7d5-157">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-157">Figure 4.</span></span> <span data-ttu-id="8d7d5-158">Configurar el arranque seguro</span><span class="sxs-lookup"><span data-stu-id="8d7d5-158">Configure Secure Boot</span></span>*

<span data-ttu-id="8d7d5-159">Según el dispositivo que tenga, es posible que también pueda ver si TPM está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="8d7d5-160">Si no ve la opción **Habilitar TPM** , abra TPM. msc en Windows para comprobar el estado, como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="8d7d5-161">El TPM se usa para autenticar el cifrado de datos de tu dispositivo con BitLocker.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="8d7d5-162">Para obtener más información, consulte [información general de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![Consola de TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="8d7d5-164">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-164">Figure 5.</span></span> <span data-ttu-id="8d7d5-165">Consola de TPM</span><span class="sxs-lookup"><span data-stu-id="8d7d5-165">TPM console</span></span>*


## <span data-ttu-id="8d7d5-166">Menú UEFI: dispositivos</span><span class="sxs-lookup"><span data-stu-id="8d7d5-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="8d7d5-167">La página dispositivos le permite habilitar o deshabilitar dispositivos y componentes específicos, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8d7d5-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="8d7d5-168">Acoplamiento y puertos USB</span><span class="sxs-lookup"><span data-stu-id="8d7d5-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="8d7d5-169">Ranura para tarjeta microSD o SD</span><span class="sxs-lookup"><span data-stu-id="8d7d5-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="8d7d5-170">Cámara trasera</span><span class="sxs-lookup"><span data-stu-id="8d7d5-170">Rear Camera</span></span> 

- <span data-ttu-id="8d7d5-171">Cámara frontal</span><span class="sxs-lookup"><span data-stu-id="8d7d5-171">Front Camera</span></span> 

- <span data-ttu-id="8d7d5-172">Cámara de infrarrojos (IR)</span><span class="sxs-lookup"><span data-stu-id="8d7d5-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="8d7d5-173">Wi-Fi y Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8d7d5-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="8d7d5-174">Audio integrado (altavoces y micrófono)</span><span class="sxs-lookup"><span data-stu-id="8d7d5-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="8d7d5-175">Cada dispositivo aparece con un **botón de control** deslizante al que puede desplazarse a la posición (habilitada) o **desactivada** (deshabilitada), tal como se muestra en la figura 6.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![Habilitar y deshabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="8d7d5-177">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-177">Figure 6.</span></span> <span data-ttu-id="8d7d5-178">Habilitar y deshabilitar dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="8d7d5-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="8d7d5-179">Menú UEFI: configuración de arranque</span><span class="sxs-lookup"><span data-stu-id="8d7d5-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="8d7d5-180">La página Configuración de arranque le permite cambiar el orden de los dispositivos de inicio, así como habilitar o deshabilitar el inicio de los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="8d7d5-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="8d7d5-181">Administración de arranque de Windows</span><span class="sxs-lookup"><span data-stu-id="8d7d5-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="8d7d5-182">Almacenamiento USB</span><span class="sxs-lookup"><span data-stu-id="8d7d5-182">USB Storage</span></span> 

- <span data-ttu-id="8d7d5-183">Red PXE</span><span class="sxs-lookup"><span data-stu-id="8d7d5-183">PXE Network</span></span> 

- <span data-ttu-id="8d7d5-184">Almacenamiento interno</span><span class="sxs-lookup"><span data-stu-id="8d7d5-184">Internal Storage</span></span> 

<span data-ttu-id="8d7d5-185">Puedes arrancar desde un dispositivo específico inmediatamente o puedes deslizar rápidamente hacia la izquierda en la entrada del dispositivo en la lista con la pantalla táctil.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="8d7d5-186">También puedes arrancar inmediatamente en un dispositivo USB o un adaptador Ethernet USB cuando el dispositivo Surface esté apagado, presionando el botón **Bajar el volumen** y el botón **Inicio/apagado** simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="8d7d5-187">Para que el orden de arranque especificado surta efecto, debe establecer la opción **Habilitar la secuencia de inicio alternativa** en **activado**, como se muestra en la ilustración 7.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![Configurar el orden de arranque para el dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="8d7d5-189">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-189">Figure 7.</span></span> <span data-ttu-id="8d7d5-190">Configurar el orden de arranque para el dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="8d7d5-191">También puedes activar y desactivar la compatibilidad con IPv6 PXE con la opción **Habilitar IPv6 para el arranque de Red PXE**, por ejemplo, al realizar una implementación de Windows con PXE en el que el servidor PXE está configurado solo para IPv4.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="8d7d5-192">Menú UEFI: administración</span><span class="sxs-lookup"><span data-stu-id="8d7d5-192">UEFI menu: Management</span></span>
<span data-ttu-id="8d7d5-193">La página de administración le permite administrar el uso de la administración de UEFI con Zero Touch y otras características en los dispositivos aptos, entre los que se incluyen Surface Pro 7, Surface Pro X y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="8d7d5-194">Administra el acceso a la administración de UEFI sin interacción y otras características, ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *ilustración 8. Administrar el acceso a la administración de UEFI sin interacción y otras características*</span><span class="sxs-lookup"><span data-stu-id="8d7d5-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="8d7d5-195">La administración UEFI sin interacción permite administrar de forma remota la configuración de UEFI mediante un perfil de dispositivo en Intune denominado interfaz de configuración de firmware del dispositivo (DFCI).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="8d7d5-196">Si no establece esta configuración, la capacidad de administrar los dispositivos aptos con DFCI se establece en **listo**.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="8d7d5-197">Para evitar DFCI, seleccione **cancelación de la suscripción**.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="8d7d5-198">La página de configuración de administración UEFI y el uso de DFCI solo están disponibles en Surface Pro 7, Surface Pro X y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="8d7d5-199">Para obtener más información, consulte la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="8d7d5-200">Menú UEFI: salir</span><span class="sxs-lookup"><span data-stu-id="8d7d5-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="8d7d5-201">Use el botón **reiniciar ahora** de la página de **salida** para salir de la configuración de UEFI, como se muestra en la figura 9.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![Salir de la UEFI de Surface y reiniciar el dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="8d7d5-203">Figura 9.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-203">Figure 9.</span></span> <span data-ttu-id="8d7d5-204">Haz clic en Reiniciar ahora para salir de la UEFI de Surface y reiniciar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="8d7d5-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="8d7d5-205">Pantallas de arranque de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="8d7d5-206">Cuando actualizas el firmware del dispositivo Surface, ya sea mediante Windows Update o la instalación manual, las actualizaciones no se aplican de inmediato en el dispositivo, sino durante el próximo ciclo de reinicio.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="8d7d5-207">Puedes encontrar más información sobre el proceso de actualización de firmware de Surface en [Administrar las actualizaciones de controladores y firmware de Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="8d7d5-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="8d7d5-208">El progreso de la actualización del firmware se muestra en una pantalla con barras de progreso de colores diferentes para indicar el firmware para cada componente.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="8d7d5-209">La barra de progreso de cada componente se muestra en las figuras 9 a 18.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Actualización del firmware de la UEFI de Surface con barra de progreso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="8d7d5-211">Figura 10.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-211">Figure 10.</span></span> <span data-ttu-id="8d7d5-212">La actualización del firmware de la UEFI de Surface muestra una barra de progreso azul</span><span class="sxs-lookup"><span data-stu-id="8d7d5-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![Firmware de controlador integrado del sistema con la barra de progreso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="8d7d5-214">Figura 11.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-214">Figure 11.</span></span> <span data-ttu-id="8d7d5-215">La actualización del firmware de controlador integrado del sistema muestra una barra de progreso verde</span><span class="sxs-lookup"><span data-stu-id="8d7d5-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![Actualización del firmware de controladora SAM con barra de progreso naranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="8d7d5-217">Figura 12.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-217">Figure 12.</span></span> <span data-ttu-id="8d7d5-218">La actualización de firmware de la controladora SAM muestra una barra de progreso naranja</span><span class="sxs-lookup"><span data-stu-id="8d7d5-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Firmware del motor de administración de Intel con barra de progreso roja](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="8d7d5-220">Figura 13.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-220">Figure 13.</span></span> <span data-ttu-id="8d7d5-221">La actualización del firmware del motor de administración de Intel muestra una barra de progreso roja</span><span class="sxs-lookup"><span data-stu-id="8d7d5-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Firmware de entrada táctil de Surface con barra de progreso gris](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="8d7d5-223">Figura 14.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-223">Figure 14.</span></span> <span data-ttu-id="8d7d5-224">La actualización del firmware de entrada táctil de Surface muestra una barra de progreso gris</span><span class="sxs-lookup"><span data-stu-id="8d7d5-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![Firmware de KIP de superficie con barra de progreso de color claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="8d7d5-226">Figura 15.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-226">Figure 15.</span></span> <span data-ttu-id="8d7d5-227">La actualización del firmware del KIP de superficie muestra una barra de progreso de color verde claro</span><span class="sxs-lookup"><span data-stu-id="8d7d5-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![Surface ISH firmware con barra de progreso de color rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="8d7d5-229">Ilustración 16 la actualización del firmware Surface ISH muestra una barra de progreso de color rosa claro</span><span class="sxs-lookup"><span data-stu-id="8d7d5-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![Firmware de superficie del panel del panel con barra de progreso gris](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="8d7d5-231">Figura 17.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-231">Figure 17.</span></span> <span data-ttu-id="8d7d5-232">La actualización del firmware de Surface del panel muestra una barra de progreso de color rosa</span><span class="sxs-lookup"><span data-stu-id="8d7d5-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![Surface TCON firmware con barra de progreso de color gris claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="8d7d5-234">Figura 18.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-234">Figure 18.</span></span> <span data-ttu-id="8d7d5-235">La actualización de firmware Surface TCON muestra una barra de progreso de color gris claro</span><span class="sxs-lookup"><span data-stu-id="8d7d5-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![Surface firmware TPM con barra de progreso de color claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="8d7d5-237">Figura 19.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-237">Figure 19.</span></span> <span data-ttu-id="8d7d5-238">La actualización de firmware de la superficie de TPM muestra una barra de progreso de color púrpura</span><span class="sxs-lookup"><span data-stu-id="8d7d5-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="8d7d5-239">Aparece un mensaje de ADVERTENCIA adicional que indica que se ha deshabilitado el arranque seguro, como se muestra en la figura 19.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="8d7d5-241">Figura 20.</span><span class="sxs-lookup"><span data-stu-id="8d7d5-241">Figure 20.</span></span> <span data-ttu-id="8d7d5-242">Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado en la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="8d7d5-243">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8d7d5-243">Related topics</span></span>

- [<span data-ttu-id="8d7d5-244">Administración de Intune de la configuración de la UEFI de Surface</span><span class="sxs-lookup"><span data-stu-id="8d7d5-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="8d7d5-245">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="8d7d5-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)

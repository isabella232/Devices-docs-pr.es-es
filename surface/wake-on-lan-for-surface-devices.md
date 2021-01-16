---
title: Wake on LAN dispositivos Surface (Surface)
description: Consulta cómo puedes usar Wake on LAN para activar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o para habilitar soluciones de administración automáticamente, incluso si los dispositivos están apagados.
keywords: update, deploy, implementar, driver, driver, controlador, wake-on-lan, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271127"
---
# <span data-ttu-id="d527b-104">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="d527b-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d527b-105">Los dispositivos Surface que ejecutan Windows 10, versión 1607 (también conocida como Actualización de aniversario de Windows 10) o posterior y usan un adaptador Ethernet de Surface para conectarse a una red cableada, son capaces de Wake on LAN (WOL) desde el modo de espera conectado.</span><span class="sxs-lookup"><span data-stu-id="d527b-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d527b-106">Con ELSO, puede activar dispositivos de forma remota para realizar tareas de administración o mantenimiento o habilitar soluciones de administración (como Microsoft Endpoint Configuration Manager) automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d527b-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="d527b-107">Por ejemplo, puedes implementar aplicaciones en dispositivos Surface que quedan acoplados con Surface Dock o surface Pro 3 Docking Station mediante Microsoft Endpoint Configuration Manager durante una ventana en mitad de la noche, cuando la oficina está vacía.</span><span class="sxs-lookup"><span data-stu-id="d527b-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="d527b-108">Los dispositivos Surface deben estar conectados a la corriente alterna y en modo de espera conectado (suspensión) para admitir ELS.</span><span class="sxs-lookup"><span data-stu-id="d527b-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="d527b-109">NO es posible REALIZAR EL TRABAJO desde dispositivos que están en hibernación o apagados.</span><span class="sxs-lookup"><span data-stu-id="d527b-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="d527b-110">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="d527b-110">Supported devices</span></span>

<span data-ttu-id="d527b-111">Los siguientes dispositivos son compatibles con LAR:</span><span class="sxs-lookup"><span data-stu-id="d527b-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="d527b-112">Adaptador Ethernet de Surface</span><span class="sxs-lookup"><span data-stu-id="d527b-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="d527b-113">Surface USB-C a Ethernet y adaptador USB</span><span class="sxs-lookup"><span data-stu-id="d527b-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="d527b-114">Surface Dock</span><span class="sxs-lookup"><span data-stu-id="d527b-114">Surface Dock</span></span>
* <span data-ttu-id="d527b-115">Estación de acoplamiento de Surface para Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d527b-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="d527b-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="d527b-116">Surface 3</span></span>
* <span data-ttu-id="d527b-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d527b-117">Surface Pro 3</span></span>
* <span data-ttu-id="d527b-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="d527b-118">Surface Pro 4</span></span>
* <span data-ttu-id="d527b-119">Surface Pro (5ª generación)</span><span class="sxs-lookup"><span data-stu-id="d527b-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="d527b-120">Surface Pro (5ª generación) con LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="d527b-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="d527b-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="d527b-121">Surface Book</span></span>
* <span data-ttu-id="d527b-122">Surface Laptop (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="d527b-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="d527b-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="d527b-123">Surface Pro 6</span></span>
* <span data-ttu-id="d527b-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="d527b-124">Surface Book 2</span></span>
* <span data-ttu-id="d527b-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="d527b-125">Surface Laptop 2</span></span>
* <span data-ttu-id="d527b-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="d527b-126">Surface Go</span></span>
* <span data-ttu-id="d527b-127">Surface Go con LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="d527b-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="d527b-128">Surface Studio 2 (consulta las instrucciones de Surface Studio 2 a continuación)</span><span class="sxs-lookup"><span data-stu-id="d527b-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="d527b-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d527b-129">Surface Pro 7</span></span>
* <span data-ttu-id="d527b-130">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="d527b-130">Surface Laptop 3</span></span>
* <span data-ttu-id="d527b-131">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="d527b-131">Surface Laptop Go</span></span>
* <span data-ttu-id="d527b-132">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="d527b-132">Surface Pro 7+</span></span>

## <span data-ttu-id="d527b-133">Controlador DESOD</span><span class="sxs-lookup"><span data-stu-id="d527b-133">WOL driver</span></span>

<span data-ttu-id="d527b-134">Para habilitar la compatibilidad con LAR en dispositivos Surface, se requiere un controlador específico para el adaptador Ethernet de Surface.</span><span class="sxs-lookup"><span data-stu-id="d527b-134">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="d527b-135">Este controlador no está incluido en el paquete de controladores y firmware estándar para dispositivos Surface: debes descargarlo e instalarlo por separado.</span><span class="sxs-lookup"><span data-stu-id="d527b-135">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="d527b-136">Puedes descargar el controlador DESO de Surface (SurfaceWOL.msi) desde la página Herramientas de [Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d527b-136">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="d527b-137">Puedes ejecutar este archivo Microsoft Windows Installer (.msi) en un dispositivo Surface para instalar el controlador SURFACE WOL, o puedes distribuirlo a dispositivos Surface con una solución de implementación de aplicaciones, como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d527b-137">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d527b-138">Para incluir el controlador SURFACE WOL durante la implementación, puedes instalar el archivo .msi como una aplicación durante el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d527b-138">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="d527b-139">También puedes extraer los archivos de controlador de SURFACE WOL para incluirlos en el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d527b-139">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="d527b-140">Por ejemplo, puedes incluirlos en el recurso compartido de implementación de Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="d527b-140">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="d527b-141">Puedes leer más sobre la implementación de Surface con MDT en [Implementar Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)en dispositivos Surface con Microsoft Deployment Toolkit.</span><span class="sxs-lookup"><span data-stu-id="d527b-141">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="d527b-142">Durante la instalación de SurfaceWOL.msi, la siguiente clave del Registro se establece en un valor de 1, lo que permite identificar fácilmente los sistemas en los que se ha instalado el controlador DESA.</span><span class="sxs-lookup"><span data-stu-id="d527b-142">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="d527b-143">Si decidiste extraer e instalar estos controladores por separado durante la implementación, esta clave del Registro no se configurará y debe configurarse manualmente o con un script.</span><span class="sxs-lookup"><span data-stu-id="d527b-143">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="d527b-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="d527b-144">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="d527b-145">Para extraer el contenido de SurfaceWOL.msi, use la opción de instalación administrativa MSIExec (**/a**), como se muestra en el ejemplo siguiente, para extraer el contenido en la carpeta C:\WOL\:</span><span class="sxs-lookup"><span data-stu-id="d527b-145">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="d527b-146">Instrucciones de Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d527b-146">Surface Studio 2 instructions</span></span>

<span data-ttu-id="d527b-147">Para habilitar LAR en Surface Studio 2, debes usar el siguiente procedimiento</span><span class="sxs-lookup"><span data-stu-id="d527b-147">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="d527b-148">Cree las siguientes claves del Registro:</span><span class="sxs-lookup"><span data-stu-id="d527b-148">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d527b-149">Ejecute el comando siguiente</span><span class="sxs-lookup"><span data-stu-id="d527b-149">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="d527b-150">Uso de Surface WOL</span><span class="sxs-lookup"><span data-stu-id="d527b-150">Using Surface WOL</span></span>

<span data-ttu-id="d527b-151">El controlador SURFACE WOL cumple con el estándar DESA, por el que el dispositivo es resamplado por una comunicación de red especial conocida como paquete mágico.</span><span class="sxs-lookup"><span data-stu-id="d527b-151">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="d527b-152">El paquete mágico consta de 6 bytes de 255 (o FF en hexadecimal) seguido de 16 repeticiones de la dirección MAC del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d527b-152">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="d527b-153">Puede leer más sobre el paquete mágico y el estándar DESA en [Wikipedia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)</span><span class="sxs-lookup"><span data-stu-id="d527b-153">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="d527b-154">Para enviar un paquete mágico y activar un dispositivo mediante ELSO, debes conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d527b-154">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d527b-155">Dado que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d527b-155">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d527b-156">Muchas soluciones de administración, como Configuration Manager, proporcionan compatibilidad integrada con ELR.</span><span class="sxs-lookup"><span data-stu-id="d527b-156">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="d527b-157">También hay muchas soluciones, como aplicaciones de Microsoft Store, módulos de PowerShell, aplicaciones de terceros y soluciones de administración de terceros que te permiten enviar un paquete mágico para activar un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d527b-157">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="d527b-158">Por ejemplo, puede usar el módulo [Wake on LAN PowerShell desde](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) el Centro de scripts de TechNet.</span><span class="sxs-lookup"><span data-stu-id="d527b-158">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="d527b-159">Después de que un dispositivo se haya convertido en un paquete mágico, el dispositivo volverá a estar en suspensión si una aplicación no impide activamente la suspensión en el sistema o si la clave del Registro AllowSystemRequiredPowerRequests no está configurada en 1, lo que permite a las aplicaciones evitar el suspensión.</span><span class="sxs-lookup"><span data-stu-id="d527b-159">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="d527b-160">Vea la [sección del controlador DESO](#wol-driver) de este artículo para obtener más información acerca de esta clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="d527b-160">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>

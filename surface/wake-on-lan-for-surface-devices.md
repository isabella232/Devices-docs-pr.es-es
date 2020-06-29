---
title: Wake on LAN para dispositivos de superficie (Surface)
description: Vea cómo puede usar Wake on LAN para reactivar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o para habilitar soluciones de administración de forma automática, incluso si los dispositivos están apagados.
keywords: actualizar, implementar, controlador, WOL, Wake-on-LAN
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
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835513"
---
# <span data-ttu-id="d5c1a-104">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="d5c1a-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="d5c1a-105">Los dispositivos Surface que ejecutan Windows 10, versión 1607 (también conocida como actualización de aniversario de Windows 10) o una versión posterior, y usan un adaptador de Surface Ethernet para conectarse a una red cableada, son capaces de Wake on LAN (WOL) desde el modo de espera conectado.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="d5c1a-106">Con WOL, puede reactivar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o bien habilitar de forma automática soluciones de administración (como Microsoft Endpoint Configuration Manager).</span><span class="sxs-lookup"><span data-stu-id="d5c1a-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="d5c1a-107">Por ejemplo, puede implementar aplicaciones para Surface los dispositivos que se conectan con una estación de acoplamiento de Surface o Surface Pro 3 usando Microsoft Endpoint Configuration Manager durante una ventana en el medio de la noche, cuando la oficina está vacía.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="d5c1a-108">Los dispositivos Surface deben estar conectados a la alimentación de CA y al modo de espera conectado (dormir) para admitir WOL.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="d5c1a-109">WOL no es posible desde dispositivos que están en hibernación o apagados.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="d5c1a-110">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="d5c1a-110">Supported devices</span></span>

<span data-ttu-id="d5c1a-111">Los siguientes dispositivos son compatibles con WOL:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="d5c1a-112">Adaptador de Ethernet Surface</span><span class="sxs-lookup"><span data-stu-id="d5c1a-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="d5c1a-113">USB-C a Ethernet y adaptador USB Surface</span><span class="sxs-lookup"><span data-stu-id="d5c1a-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="d5c1a-114">Surface Dock</span><span class="sxs-lookup"><span data-stu-id="d5c1a-114">Surface Dock</span></span>
* <span data-ttu-id="d5c1a-115">Estación de acoplamiento para Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d5c1a-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="d5c1a-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="d5c1a-116">Surface 3</span></span>
* <span data-ttu-id="d5c1a-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d5c1a-117">Surface Pro 3</span></span>
* <span data-ttu-id="d5c1a-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="d5c1a-118">Surface Pro 4</span></span>
* <span data-ttu-id="d5c1a-119">Surface Pro (5º gen)</span><span class="sxs-lookup"><span data-stu-id="d5c1a-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="d5c1a-120">Surface Pro (5º gen) con LTE avanzado</span><span class="sxs-lookup"><span data-stu-id="d5c1a-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="d5c1a-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="d5c1a-121">Surface Book</span></span>
* <span data-ttu-id="d5c1a-122">Portátil Surface (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="d5c1a-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="d5c1a-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="d5c1a-123">Surface Pro 6</span></span>
* <span data-ttu-id="d5c1a-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="d5c1a-124">Surface Book 2</span></span>
* <span data-ttu-id="d5c1a-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="d5c1a-125">Surface Laptop 2</span></span>
* <span data-ttu-id="d5c1a-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="d5c1a-126">Surface Go</span></span>
* <span data-ttu-id="d5c1a-127">Surface Go con LTE Advanced</span><span class="sxs-lookup"><span data-stu-id="d5c1a-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="d5c1a-128">Surface Studio 2 (consulte las instrucciones de Surface Studio 2 a continuación)</span><span class="sxs-lookup"><span data-stu-id="d5c1a-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="d5c1a-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d5c1a-129">Surface Pro 7</span></span>
* <span data-ttu-id="d5c1a-130">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="d5c1a-130">Surface Laptop 3</span></span>

## <span data-ttu-id="d5c1a-131">Controlador WOL</span><span class="sxs-lookup"><span data-stu-id="d5c1a-131">WOL driver</span></span>

<span data-ttu-id="d5c1a-132">Para habilitar la compatibilidad con WOL en dispositivos Surface, se requiere un controlador específico para el adaptador Surface Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-132">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="d5c1a-133">Este controlador no se incluye en el paquete de firmware y el controlador estándar para dispositivos Surface: debes descargarlo e instalarlo por separado.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-133">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="d5c1a-134">Puede descargar el controlador de Surface WOL (SurfaceWOL.msi) desde la página [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-134">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="d5c1a-135">Puede ejecutar este archivo de Microsoft Windows Installer (. msi) en un dispositivo Surface para instalar el controlador Surface WOL, o bien puede distribuirlo a dispositivos Surface con una solución de implementación de aplicaciones, como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-135">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d5c1a-136">Para incluir el controlador de Surface WOL durante la implementación, puede instalar el archivo. msi como una aplicación durante el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-136">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="d5c1a-137">También puede extraer los archivos de controlador de la superficie de WOL para incluirlos en el proceso de implementación.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-137">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="d5c1a-138">Por ejemplo, puede incluirlos en el recurso compartido de implementación de Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="d5c1a-138">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="d5c1a-139">Puede obtener más información sobre la implementación de Surface con MDT en [implementar Windows 10 para Surface Devices con Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span><span class="sxs-lookup"><span data-stu-id="d5c1a-139">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="d5c1a-140">Durante la instalación de SurfaceWOL.msi, la siguiente clave del registro se establece en un valor de 1, lo que permite identificar fácilmente los sistemas en los que se ha instalado el controlador WOL.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-140">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="d5c1a-141">Si decide extraer e instalar estos drivers por separado durante la implementación, esta clave del registro no se configurará y se debe configurar manualmente o con un script.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-141">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="d5c1a-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="d5c1a-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="d5c1a-143">Para extraer el contenido de SurfaceWOL.msi, use la opción de instalación administrativa MSIExec (**/a**), como se muestra en el siguiente ejemplo, para extraer el contenido a la carpeta C:\WOL\:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-143">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="d5c1a-144">Instrucciones para Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="d5c1a-144">Surface Studio 2 instructions</span></span>

<span data-ttu-id="d5c1a-145">Para habilitar WOL en Surface Studio 2, debe seguir este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-145">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="d5c1a-146">Cree las siguientes claves de registro:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-146">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="d5c1a-147">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d5c1a-147">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="d5c1a-148">Uso de la superficie WOL</span><span class="sxs-lookup"><span data-stu-id="d5c1a-148">Using Surface WOL</span></span>

<span data-ttu-id="d5c1a-149">El controlador de Surface WOL cumple con las normas de WOL, por lo que el dispositivo es Woken por una comunicación de red especial conocida como un paquete mágico.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-149">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="d5c1a-150">El paquete mágico consta de 6 bytes de 255 (o FF en hexadecimal), seguidos de 16 repeticiones de la dirección MAC del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-150">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="d5c1a-151">Puede obtener más información sobre el paquete mágico y el estándar de WOL en [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span><span class="sxs-lookup"><span data-stu-id="d5c1a-151">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="d5c1a-152">Para enviar un paquete mágico y reactivar un dispositivo con WOL, debe conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-152">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="d5c1a-153">Debido a que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-153">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="d5c1a-154">Muchas soluciones de administración, como Configuration Manager, proporcionan compatibilidad integrada con WOL.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-154">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="d5c1a-155">También hay muchas soluciones, entre las que se incluyen aplicaciones de Microsoft Store, módulos de PowerShell, aplicaciones de terceros y soluciones de administración de terceros que permiten enviar un paquete mágico para reactivar un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-155">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="d5c1a-156">Por ejemplo, puede usar el [módulo Wake on LAN de PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) en el centro de scripts de TechNet.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-156">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="d5c1a-157">Después de que un dispositivo se ha Woken con un paquete mágico, el dispositivo volverá al modo de suspensión si una aplicación no impide activamente la suspensión en el sistema o si la clave del registro AllowSystemRequiredPowerRequests no está configurada en 1, lo que permite a las aplicaciones impedir la suspensión.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-157">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="d5c1a-158">Consulte la sección del [controlador de WOL](#wol-driver) de este artículo para obtener más información sobre esta clave del registro.</span><span class="sxs-lookup"><span data-stu-id="d5c1a-158">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>

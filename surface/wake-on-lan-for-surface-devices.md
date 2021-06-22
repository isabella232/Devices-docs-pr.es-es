---
title: Wake on LAN para dispositivos Surface
description: Consulta cómo puedes usar Wake on LAN activar dispositivos de forma remota para realizar tareas de administración automáticamente.
keywords: actualizar, implementar, controlador, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613809"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="da73d-104">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="da73d-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="da73d-105">Para mantener los dispositivos totalmente actualizados, los administradores de TI deben poder administrar dispositivos cuando no están en uso, normalmente durante las ventanas de mantenimiento nocturnas.</span><span class="sxs-lookup"><span data-stu-id="da73d-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="da73d-106">La activación en LAN (WOL) permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración con soluciones Microsoft Endpoint Manager o de terceros.</span><span class="sxs-lookup"><span data-stu-id="da73d-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="da73d-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da73d-107">Requirements</span></span>

<span data-ttu-id="da73d-108">Los dispositivos deben estar conectados a la alimentación de CA y tener una conexión por cable con uno de los siguientes adaptadores Ethernet compatibles:</span><span class="sxs-lookup"><span data-stu-id="da73d-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="da73d-109">Adaptador Ethernet De Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="da73d-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="da73d-110">Adaptador Ethernet de Surface</span><span class="sxs-lookup"><span data-stu-id="da73d-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="da73d-111">Adaptador USB-C a Ethernet y USB de Surface</span><span class="sxs-lookup"><span data-stu-id="da73d-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="da73d-112">Concentrador de adaptadores de viajes USB-C de Microsoft</span><span class="sxs-lookup"><span data-stu-id="da73d-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="da73d-113">Surface Dock</span><span class="sxs-lookup"><span data-stu-id="da73d-113">Surface Dock</span></span>
- <span data-ttu-id="da73d-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="da73d-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="da73d-115">Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN sin necesidad de ninguna configuración de TI adicional.</span><span class="sxs-lookup"><span data-stu-id="da73d-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="da73d-116">Para obtener más información, [consulta Activar la LAN para Surface Dock 2](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="da73d-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="da73d-117">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="da73d-117">How it works</span></span>

<span data-ttu-id="da73d-118">Cuando no están en uso, los dispositivos Surface entran en un estado inactivo y de bajo consumo conocido como Espera moderna o Espera conectada.</span><span class="sxs-lookup"><span data-stu-id="da73d-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="da73d-119">Los administradores de TI pueden desencadenar dispositivos de forma remota mediante una solicitud de activación (paquete mágico) que contiene la dirección de Control de acceso multimedia (MAC) del dispositivo Surface de destino.</span><span class="sxs-lookup"><span data-stu-id="da73d-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="da73d-120">Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL.</span><span class="sxs-lookup"><span data-stu-id="da73d-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="da73d-121">Para obtener más información sobre cómo activar dispositivos con Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span><span class="sxs-lookup"><span data-stu-id="da73d-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="da73d-122">La compatibilidad con Wake on LAN varía en función del estado de suspensión: Modo de espera conectado o Hibernación (estado de energía S4).</span><span class="sxs-lookup"><span data-stu-id="da73d-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="da73d-123">Modo de espera conectado</span><span class="sxs-lookup"><span data-stu-id="da73d-123">Connected Standby</span></span>

<span data-ttu-id="da73d-124">De forma predeterminada, Windows 10 activar en LAN para dispositivos Surface en modo de espera conectado.</span><span class="sxs-lookup"><span data-stu-id="da73d-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="da73d-125">Dispositivos Surface compatibles: modo de espera conectado</span><span class="sxs-lookup"><span data-stu-id="da73d-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="da73d-126">Surface Laptop 4 (solo procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="da73d-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="da73d-127">Surface Laptop 3 (solo procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="da73d-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="da73d-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="da73d-128">Surface Pro 7+</span></span>
- <span data-ttu-id="da73d-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="da73d-129">Surface Pro 7</span></span>
- <span data-ttu-id="da73d-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="da73d-130">Surface Pro X</span></span>
- <span data-ttu-id="da73d-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="da73d-131">Surface Go 2</span></span>
- <span data-ttu-id="da73d-132">Surface Laptop Ir</span><span class="sxs-lookup"><span data-stu-id="da73d-132">Surface Laptop Go</span></span>
- <span data-ttu-id="da73d-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="da73d-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="da73d-134">Hibernación</span><span class="sxs-lookup"><span data-stu-id="da73d-134">Hibernation</span></span>

<span data-ttu-id="da73d-135">Para activar dispositivos fuera de hibernación, es necesario habilitar una configuración de directiva UEFI a través del Modo de administración de [Surface Enterprise](surface-enterprise-management-mode.md) (SEMM) (no es necesario para dispositivos conectados a Surface Dock 2).</span><span class="sxs-lookup"><span data-stu-id="da73d-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="da73d-136">Dispositivos Surface compatibles: hibernación</span><span class="sxs-lookup"><span data-stu-id="da73d-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="da73d-137">Surface Laptop 4 (solo procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="da73d-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="da73d-138">Surface Laptop 3 (solo procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="da73d-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="da73d-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="da73d-139">Surface Pro 7+</span></span>
- <span data-ttu-id="da73d-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="da73d-140">Surface Pro 7</span></span>
- <span data-ttu-id="da73d-141">Surface Laptop Ir</span><span class="sxs-lookup"><span data-stu-id="da73d-141">Surface Laptop Go</span></span>
- <span data-ttu-id="da73d-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="da73d-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="da73d-143">Para habilitar la opción Activar en LAN UEFI</span><span class="sxs-lookup"><span data-stu-id="da73d-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="da73d-144">Para habilitar la configuración activar la UEFI de LAN, debes inscribir dispositivos de destino en SEMM, crear un paquete de configuración y aplicar el paquete a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="da73d-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="da73d-145">Para más información, consulta:</span><span class="sxs-lookup"><span data-stu-id="da73d-145">For more information, refer to:</span></span>

- [<span data-ttu-id="da73d-146">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="da73d-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="da73d-147">Inscribir y configurar los dispositivos Surface con SEMM</span><span class="sxs-lookup"><span data-stu-id="da73d-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="da73d-148">Descargar e instalar [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="da73d-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="da73d-149">Seleccione **Iniciar paquete**de  >  **configuración**  >  **Crear**+ Protección de  > **certificados**.</span><span class="sxs-lookup"><span data-stu-id="da73d-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="da73d-150">Vaya a **Configuración avanzada y** cambie Activar la **LAN** a **Activar**.</span><span class="sxs-lookup"><span data-stu-id="da73d-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="da73d-151">Aplicar el paquete a los dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="da73d-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Habilitar activación en la configuración de directiva UEFI de LAN](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="da73d-153">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="da73d-153">Learn more</span></span>

- [<span data-ttu-id="da73d-154">Activar la LAN para Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="da73d-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="da73d-155">Adaptador USB-C a Ethernet y USB de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="da73d-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="da73d-156">Adaptador Ethernet De Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="da73d-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

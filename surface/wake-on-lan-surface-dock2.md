---
title: Wake on LAN con Surface Dock 2
description: Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN (WOL) que permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración.
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
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643856"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="33b39-104">Wake on LAN con Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="33b39-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="33b39-105">Para mantener los dispositivos totalmente actualizados, los administradores de TI deben poder administrar dispositivos cuando no están en uso, normalmente durante las ventanas de mantenimiento nocturnas.</span><span class="sxs-lookup"><span data-stu-id="33b39-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="33b39-106">Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN (WOL) que permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración con Microsoft Endpoint Manager u otras soluciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="33b39-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="33b39-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33b39-107">Requirements</span></span>

<span data-ttu-id="33b39-108">Los dispositivos deben tener una conexión por cable con Surface Dock 2 y mantenerse conectados a AC Power.</span><span class="sxs-lookup"><span data-stu-id="33b39-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="33b39-110">Dispositivos Surface compatibles</span><span class="sxs-lookup"><span data-stu-id="33b39-110">Supported Surface devices</span></span>

- <span data-ttu-id="33b39-111">Surface Laptop 4 (procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="33b39-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="33b39-112">Surface Laptop 4 (procesadores AMD)</span><span class="sxs-lookup"><span data-stu-id="33b39-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="33b39-113">Surface Laptop 3 (procesadores Intel)</span><span class="sxs-lookup"><span data-stu-id="33b39-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="33b39-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="33b39-114">Surface Pro 7+</span></span>
- <span data-ttu-id="33b39-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="33b39-115">Surface Pro 7</span></span>
- <span data-ttu-id="33b39-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="33b39-116">Surface Pro X</span></span>
- <span data-ttu-id="33b39-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="33b39-117">Surface Go 2</span></span>
- <span data-ttu-id="33b39-118">Surface Laptop Ir</span><span class="sxs-lookup"><span data-stu-id="33b39-118">Surface Laptop Go</span></span>
- <span data-ttu-id="33b39-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="33b39-119">Surface Book 3</span></span>

<span data-ttu-id="33b39-120">Surface Dock 2 proporciona compatibilidad con WOL para dispositivos en los siguientes estados de energía:</span><span class="sxs-lookup"><span data-stu-id="33b39-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="33b39-121">Modo de espera conectado</span><span class="sxs-lookup"><span data-stu-id="33b39-121">Connected standby</span></span>
- <span data-ttu-id="33b39-122">Hibernación (estado de energía S4)</span><span class="sxs-lookup"><span data-stu-id="33b39-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="33b39-123">Apagado (estado de apagado suave de S5)</span><span class="sxs-lookup"><span data-stu-id="33b39-123">Shutdown (S5 “soft off” power state)</span></span>

<span data-ttu-id="33b39-124">Para obtener más información sobre los estados de energía, consulte [System Power States](/windows/win32/power/system-power-states).</span><span class="sxs-lookup"><span data-stu-id="33b39-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="33b39-125">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="33b39-125">How it works</span></span>

<span data-ttu-id="33b39-126">Cuando no están en uso, los dispositivos Surface entran en un estado inactivo y de bajo consumo conocido como Espera moderna o Espera conectada.</span><span class="sxs-lookup"><span data-stu-id="33b39-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="33b39-127">Los administradores de TI pueden desencadenar dispositivos de forma remota mediante una solicitud de activación (paquete mágico) que contiene la dirección de Control de acceso multimedia (MAC) del dispositivo Surface de destino.</span><span class="sxs-lookup"><span data-stu-id="33b39-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="33b39-128">Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL.</span><span class="sxs-lookup"><span data-stu-id="33b39-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="33b39-129">Para habilitar WOL en dispositivos sin Surface Dock 2, consulta [Activar en LAN para dispositivos Surface.](wake-on-lan-for-surface-devices.md)</span><span class="sxs-lookup"><span data-stu-id="33b39-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="33b39-130">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="33b39-130">Learn more</span></span>

- [<span data-ttu-id="33b39-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="33b39-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="33b39-132">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="33b39-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="33b39-133">Estados de energía del sistema</span><span class="sxs-lookup"><span data-stu-id="33b39-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="33b39-134">Configurar la activación en LAN: Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33b39-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

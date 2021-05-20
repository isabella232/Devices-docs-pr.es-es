---
title: Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento
description: información de solución de problemas Surface Hub actualizaciones automáticas
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub, ventana de mantenimiento, actualización
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577030"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="ebafd-104">Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="ebafd-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="ebafd-105">En determinadas circunstancias, Surface Hub las actualizaciones durante el horario laboral en lugar de durante la ventana de mantenimiento normal.</span><span class="sxs-lookup"><span data-stu-id="ebafd-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="ebafd-106">A continuación, el dispositivo se reinicia si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ebafd-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="ebafd-107">No puedes usar el dispositivo hasta que se complete el proceso.</span><span class="sxs-lookup"><span data-stu-id="ebafd-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="ebafd-108">Este no es un comportamiento esperado por falta de una ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ebafd-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="ebafd-109">Solo se produce si el dispositivo está fuera de fecha durante mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="ebafd-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="ebafd-110">Causa</span><span class="sxs-lookup"><span data-stu-id="ebafd-110">Cause</span></span>

<span data-ttu-id="ebafd-111">Para garantizar que Surface Hub esté disponible para su uso durante el horario comercial, el concentrador está configurado para realizar funciones administrativas durante una ventana de mantenimiento que se define en Configuración (vea "Referencias", a continuación).</span><span class="sxs-lookup"><span data-stu-id="ebafd-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="ebafd-112">Durante este período de mantenimiento, el concentrador instala automáticamente las actualizaciones disponibles a través de Windows Update o Windows Update for Business (WUfB).</span><span class="sxs-lookup"><span data-stu-id="ebafd-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="ebafd-113">Una vez completadas las actualizaciones, el concentrador puede reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="ebafd-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="ebafd-114">Las actualizaciones solo se pueden instalar durante la ventana de mantenimiento si el Surface Hub está activado pero no está en uso o reservado.</span><span class="sxs-lookup"><span data-stu-id="ebafd-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="ebafd-115">Por ejemplo, si el Surface Hub está programado para una reunión que dura 24 horas, las actualizaciones programadas para instalarse se aplazarán hasta que el concentrador esté disponible durante la siguiente ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ebafd-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="ebafd-116">Si el concentrador sigue ocupado y pierde varias ventanas de mantenimiento, el concentrador finalmente empezará a instalar y descargar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="ebafd-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="ebafd-117">Esto puede ocurrir durante o fuera de la ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="ebafd-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="ebafd-118">Una vez iniciada la descarga y la instalación, el dispositivo puede reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="ebafd-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="ebafd-119">Para evitar este problema</span><span class="sxs-lookup"><span data-stu-id="ebafd-119">To avoid this issue</span></span>

<span data-ttu-id="ebafd-120">Es importante que reserve el tiempo de mantenimiento para Surface Hub realizar funciones administrativas.</span><span class="sxs-lookup"><span data-stu-id="ebafd-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="ebafd-121">Reservar el Surface Hub durante intervalos de 24 horas o usar el dispositivo durante la ventana de mantenimiento retrasa la instalación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="ebafd-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="ebafd-122">Se recomienda no usar ni reservar el concentrador durante el período de mantenimiento programado.</span><span class="sxs-lookup"><span data-stu-id="ebafd-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="ebafd-123">Se debe reservar una ventana de dos horas para la actualización.</span><span class="sxs-lookup"><span data-stu-id="ebafd-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="ebafd-124">Una opción que puede usar para controlar la disponibilidad de actualizaciones es Windows Update for Business.</span><span class="sxs-lookup"><span data-stu-id="ebafd-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ebafd-125">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="ebafd-125">Learn more</span></span>
 
- [<span data-ttu-id="ebafd-126">Actualizar Surface Hub</span><span class="sxs-lookup"><span data-stu-id="ebafd-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="ebafd-127">Ventana de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="ebafd-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

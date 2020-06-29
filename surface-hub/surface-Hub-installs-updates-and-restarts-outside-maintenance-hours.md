---
title: Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento
description: información para la solución de problemas de Surface Hub acerca de las actualizaciones automáticas
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub, ventana de mantenimiento, actualización
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836402"
---
# <span data-ttu-id="c8e60-104">Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c8e60-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="c8e60-105">En circunstancias específicas, Surface Hub instala actualizaciones durante el horario laboral, en lugar de durante la ventana de mantenimiento habitual.</span><span class="sxs-lookup"><span data-stu-id="c8e60-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="c8e60-106">El dispositivo se reiniciará si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c8e60-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="c8e60-107">No puede usar el dispositivo hasta que el proceso se haya completado.</span><span class="sxs-lookup"><span data-stu-id="c8e60-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="c8e60-108">Este no es el comportamiento esperado para la falta de una ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c8e60-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="c8e60-109">Solo se produce si el dispositivo está anticuado durante mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="c8e60-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="c8e60-110">Causa</span><span class="sxs-lookup"><span data-stu-id="c8e60-110">Cause</span></span>
<span data-ttu-id="c8e60-111">Para asegurarse de que Surface Hub esté disponible para su uso durante el horario comercial, el concentrador está configurado para realizar funciones administrativas durante una ventana de mantenimiento definida en configuración (consulte "referencias" a continuación).</span><span class="sxs-lookup"><span data-stu-id="c8e60-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="c8e60-112">Durante este período de mantenimiento, el concentrador instala automáticamente todas las actualizaciones disponibles a través de Windows Update o Windows Server Update Services (WSUS).</span><span class="sxs-lookup"><span data-stu-id="c8e60-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="c8e60-113">Una vez que se completan las actualizaciones, es posible que el concentrador se reinicie.</span><span class="sxs-lookup"><span data-stu-id="c8e60-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="c8e60-114">Las actualizaciones se pueden instalar durante la ventana de mantenimiento solo si Surface Hub está activado, pero no en uso ni reservado.</span><span class="sxs-lookup"><span data-stu-id="c8e60-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="c8e60-115">Por ejemplo, si el Surface Hub está programado para una reunión que dura 24 horas, todas las actualizaciones programadas para su instalación se aplazarán hasta que el concentrador esté disponible en la siguiente ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c8e60-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="c8e60-116">Si el concentrador continúa estando ocupado y pierde varias ventanas de mantenimiento, el concentrador comenzará a instalar y descargar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c8e60-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="c8e60-117">Esto puede ocurrir durante o fuera de la ventana de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="c8e60-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="c8e60-118">Una vez iniciada la descarga e instalación, el dispositivo puede reiniciarse.</span><span class="sxs-lookup"><span data-stu-id="c8e60-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="c8e60-119">Para evitar este problema</span><span class="sxs-lookup"><span data-stu-id="c8e60-119">To avoid this issue</span></span>

<span data-ttu-id="c8e60-120">Es importante dedicar tiempo de mantenimiento para que Surface Hub realice funciones administrativas.</span><span class="sxs-lookup"><span data-stu-id="c8e60-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="c8e60-121">La reserva de Surface Hub durante un intervalo de 24 horas o el uso del dispositivo durante la ventana de mantenimiento retrasa la instalación de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c8e60-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="c8e60-122">Le recomendamos que no use ni Reserve el concentrador durante el período de mantenimiento programado.</span><span class="sxs-lookup"><span data-stu-id="c8e60-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="c8e60-123">Se debe reservar una ventana de dos horas para la actualización.</span><span class="sxs-lookup"><span data-stu-id="c8e60-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="c8e60-124">Una opción que puede usar para controlar la disponibilidad de las actualizaciones es Windows Server Update Services (WSUS).</span><span class="sxs-lookup"><span data-stu-id="c8e60-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="c8e60-125">WSUS proporciona control sobre las actualizaciones que se instalan y cuándo.</span><span class="sxs-lookup"><span data-stu-id="c8e60-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="c8e60-126">Referencias</span><span class="sxs-lookup"><span data-stu-id="c8e60-126">References</span></span> 
 
[<span data-ttu-id="c8e60-127">Actualizar Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c8e60-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="c8e60-128">Ventana de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c8e60-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="c8e60-129">Implementar las actualizaciones de Windows10 con Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="c8e60-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 



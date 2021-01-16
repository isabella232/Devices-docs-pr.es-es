---
title: Configuración del límite de batería (Surface)
description: Límite de batería es una configuración de UEFI que cambia la forma en que se carga la batería del dispositivo Surface y puede prolongar su longevidad.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271147"
---
# <span data-ttu-id="d00aa-103">Configuración del límite de batería</span><span class="sxs-lookup"><span data-stu-id="d00aa-103">Battery Limit setting</span></span>

<span data-ttu-id="d00aa-104">La opción límite de batería es una configuración de UEFI que cambia la forma en que se carga la batería del dispositivo Surface y puede prolongar su longevidad.</span><span class="sxs-lookup"><span data-stu-id="d00aa-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="d00aa-105">Esta configuración se recomienda en los casos en los que el dispositivo está conectado continuamente a la alimentación, por ejemplo, cuando los dispositivos están integrados en soluciones de quiosco.</span><span class="sxs-lookup"><span data-stu-id="d00aa-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="d00aa-106">Cómo funciona el límite de batería</span><span class="sxs-lookup"><span data-stu-id="d00aa-106">How Battery Limit works</span></span>

<span data-ttu-id="d00aa-107">Establecer el dispositivo en límite de batería cambia el protocolo para cargar la batería del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d00aa-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="d00aa-108">Cuando se habilita el límite de batería, la carga de la batería estará limitada al 50 % de su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="d00aa-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="d00aa-109">El nivel de cargo notificado en Windows reflejará este límite.</span><span class="sxs-lookup"><span data-stu-id="d00aa-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="d00aa-110">Por lo tanto, se mostrará que la batería se carga hasta un 50 % y no se cargará más allá de este límite.</span><span class="sxs-lookup"><span data-stu-id="d00aa-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="d00aa-111">Si habilitas el límite de batería mientras el dispositivo está por encima del 50 % de carga, el icono de batería mostrará que el dispositivo está conectado pero descargando hasta que el dispositivo alcanza el 50 % de su capacidad de carga máxima.</span><span class="sxs-lookup"><span data-stu-id="d00aa-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="d00aa-112">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="d00aa-112">Supported devices</span></span>

<span data-ttu-id="d00aa-113">La configuración de UEFI de límite de batería está integrada en los dispositivos Surface más recientes, incluidos Surface Pro 7+, Surface Pro 7 y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="d00aa-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="d00aa-114">Los dispositivos anteriores requieren una actualización de [firmware de LA UEFI](manage-surface-driver-and-firmware-updates.md)de Surface, disponible a través de Windows Update o a través de los paquetes de controladores y firmware MSI en el sitio de soporte técnico de [Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)</span><span class="sxs-lookup"><span data-stu-id="d00aa-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="d00aa-115">Activa [Habilitar "Límite](https://support.microsoft.com/help/4464941) de batería" para dispositivos Surface que tengan que estar conectados durante largos períodos de tiempo para la versión específica de UEFI de Surface necesaria para cada dispositivo compatible.</span><span class="sxs-lookup"><span data-stu-id="d00aa-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="d00aa-116">Habilitar el límite de batería en la UEFI de Surface (Surface Pro 4 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="d00aa-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="d00aa-117">La configuración de límite de batería de la UEFI de Surface se puede configurar iniciando en La UEFI de Surface (Energía **+ Vol Up** al activar el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="d00aa-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="d00aa-118">Elija **la configuración de**arranque y, a continuación, en Opciones **avanzadas,** cambie el modo Habilitar límite **de batería** a **Activar.**</span><span class="sxs-lookup"><span data-stu-id="d00aa-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Opciones avanzadas de límite de batería](images/enable-bl.png) 

## <span data-ttu-id="d00aa-120">Habilitar el límite de batería en Surface Go y Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="d00aa-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="d00aa-121">La configuración de límite de batería de Surface se puede configurar iniciando en la UEFI de Surface (energía **+ Vol Up** al activar el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="d00aa-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="d00aa-122">Elige **la configuración de**arranque y, a continuación, en modo de pantalla **completa,** mueve el control deslizante a la derecha para establecer el límite de batería en **Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="d00aa-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Límite de batería del modo de pantalla completa en Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="d00aa-124">Habilitar el límite de batería en la UEFI de Surface (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="d00aa-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="d00aa-125">La configuración de límite de batería de la UEFI de Surface se puede configurar iniciando en La UEFI de Surface (Energía **+ Vol Up** al activar el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="d00aa-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="d00aa-126">Elija **Modo de pantalla completa,** seleccione Límite **de**batería y, a continuación, **elija Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="d00aa-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Captura de pantalla de opciones avanzadas](images/enable-bl-sp3.png) 

![Opciones avanzadas](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="d00aa-129">Habilitar el límite de batería con los scripts de PowerShell de Surface Enterprise Management Mode (SEMM) o Surface Pro 3 firmware</span><span class="sxs-lookup"><span data-stu-id="d00aa-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="d00aa-130">El límite de batería de la UEFI de Surface también está disponible para la configuración mediante los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="d00aa-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="d00aa-131">Surface Pro 4 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d00aa-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="d00aa-132">Configurador de UEFI de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="d00aa-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="d00aa-133">Scripts de PowerShell de Surface UEFI Manager (SEMM_Powershell.zip) en las herramientas [de Surface para descargas de TI](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="d00aa-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="d00aa-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d00aa-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="d00aa-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="d00aa-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="d00aa-136">Uso del Configurador de UEFI de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="d00aa-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="d00aa-137">Para configurar el modo límite de batería, \*\*\*\* establece la opción **Invalidaciones** de quiosco en la página de configuración de Configuración avanzada de SEMM (Surface Pro 4 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="d00aa-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Captura de pantalla de la configuración avanzada](images/semm-bl.png)

### <span data-ttu-id="d00aa-139">Uso de scripts de PowerShell de Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="d00aa-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="d00aa-140">La característica de límite de batería se controla mediante la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="d00aa-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="d00aa-141">**Descripción:** esquema de administración activo para el patrón de uso de batería</span><span class="sxs-lookup"><span data-stu-id="d00aa-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="d00aa-142">**Valor**predeterminado:</span><span class="sxs-lookup"><span data-stu-id="d00aa-142">**Default**:</span></span>  `0` 

<span data-ttu-id="d00aa-143">Esta opción se establece `1` para habilitar el límite de batería.</span><span class="sxs-lookup"><span data-stu-id="d00aa-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="d00aa-144">Uso de herramientas de firmware de Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="d00aa-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="d00aa-145">La característica de límite de batería se controla mediante la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="d00aa-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="d00aa-146">**Nombre:** BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="d00aa-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="d00aa-147">**Descripción:** BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="d00aa-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="d00aa-148">**Valor actual:**</span><span class="sxs-lookup"><span data-stu-id="d00aa-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="d00aa-149">**Valor predeterminado:**</span><span class="sxs-lookup"><span data-stu-id="d00aa-149">**Default Value**:</span></span> `0`

<span data-ttu-id="d00aa-150">**Valor propuesto:**</span><span class="sxs-lookup"><span data-stu-id="d00aa-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="d00aa-151">Esta opción se establece `1` para habilitar el límite de batería.</span><span class="sxs-lookup"><span data-stu-id="d00aa-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="d00aa-152">Para configurar esta opción, debe [ usar ](https://www.microsoft.com/download/details.aspx?id=46703)SP3_Firmware_Powershell_Scripts.zip.</span><span class="sxs-lookup"><span data-stu-id="d00aa-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 


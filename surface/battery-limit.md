---
title: Configuración del límite de la batería (Surface)
description: El límite de la batería es una configuración de UEFI que cambia el modo en que se cobra la batería del dispositivo Surface y puede prolongar su longevidad.
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
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835986"
---
# <span data-ttu-id="15c92-103">Configuración del límite de batería</span><span class="sxs-lookup"><span data-stu-id="15c92-103">Battery Limit setting</span></span>

<span data-ttu-id="15c92-104">La opción de límite de batería es una configuración de UEFI que cambia el modo en que se cobra la batería del dispositivo Surface y puede prolongar su longevidad.</span><span class="sxs-lookup"><span data-stu-id="15c92-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="15c92-105">Esta configuración se recomienda en aquellos casos en los que el dispositivo está continuamente conectado a la alimentación eléctrica, por ejemplo cuando los dispositivos se integran en soluciones de quiosco.</span><span class="sxs-lookup"><span data-stu-id="15c92-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="15c92-106">Cómo funciona el límite de batería</span><span class="sxs-lookup"><span data-stu-id="15c92-106">How Battery Limit works</span></span>

<span data-ttu-id="15c92-107">Si estableces el dispositivo en el límite de la batería, se cambiará el protocolo para cargar la batería del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15c92-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="15c92-108">Cuando el límite de la batería está habilitado, la carga de la batería se limitará al 50% de su capacidad máxima.</span><span class="sxs-lookup"><span data-stu-id="15c92-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="15c92-109">El nivel de cargo registrado en Windows reflejará este límite.</span><span class="sxs-lookup"><span data-stu-id="15c92-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="15c92-110">Por lo tanto, mostrará que la batería se carga hasta el 50% y no se cobrará más allá de este límite.</span><span class="sxs-lookup"><span data-stu-id="15c92-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="15c92-111">Si habilita el límite de la batería mientras el dispositivo está por encima del 50% de cargo, el icono de la batería mostrará que el dispositivo está conectado, pero se descargará hasta que el dispositivo alcance el 50% de la capacidad máxima de carga.</span><span class="sxs-lookup"><span data-stu-id="15c92-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="15c92-112">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="15c92-112">Supported devices</span></span>
<span data-ttu-id="15c92-113">El ajuste de límite de batería de UEFI está integrado en los últimos dispositivos de Surface, incluidos Surface Pro 7 y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="15c92-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7 and Surface Laptop 3.</span></span> <span data-ttu-id="15c92-114">Los dispositivos anteriores requieren una [actualización de firmware de Surface UEFI](manage-surface-driver-and-firmware-updates.md), disponible a través de Windows Update o a través del controlador MSI y paquetes de firmware en el [sitio de asistencia de superficie](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span><span class="sxs-lookup"><span data-stu-id="15c92-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="15c92-115">Seleccione [Activar "límite de batería" para los dispositivos de Surface que deben conectarse durante largos períodos de tiempo](https://support.microsoft.com/help/4464941) para la versión UEFI de la superficie específica requerida para cada dispositivo admitido.</span><span class="sxs-lookup"><span data-stu-id="15c92-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="15c92-116">Habilitar límite de batería en Surface UEFI (Surface Pro 4 y posterior)</span><span class="sxs-lookup"><span data-stu-id="15c92-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="15c92-117">La configuración del límite de la batería de Surface UEFI se puede configurar arrancando en Surface UEFI (**Power + Vol up** al encender el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="15c92-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="15c92-118">Elija **configuración de arranque**y, a continuación, en **Opciones avanzadas**, Active activar el **modo de límite de batería** **en activado**.</span><span class="sxs-lookup"><span data-stu-id="15c92-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![Captura de pantalla de opciones avanzadas](images/enable-bl.png) 

## <span data-ttu-id="15c92-120">Habilitar el límite de batería en Surface Go y Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="15c92-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="15c92-121">La configuración del límite de batería de superficie se puede configurar al arrancar en Surface UEFI (**Power + Vol** al encender el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="15c92-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="15c92-122">Elija **configuración de arranque**y, a continuación, en **modo de pantalla completa**, mueva el control deslizante hacia la derecha para establecer límite de batería en **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="15c92-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![Captura de pantalla del límite de batería de modo quiosco en Surface Go](images/go-batterylimit.png) 

## <span data-ttu-id="15c92-124">Habilitar límite de batería en Surface UEFI (Surface Pro 3)</span><span class="sxs-lookup"><span data-stu-id="15c92-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="15c92-125">La configuración del límite de la batería de Surface UEFI se puede configurar arrancando en Surface UEFI (**Power + Vol up** al encender el dispositivo).</span><span class="sxs-lookup"><span data-stu-id="15c92-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="15c92-126">Elija **modo de pantalla completa**, seleccione **límite de batería**y, a continuación, seleccione **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="15c92-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![Captura de pantalla de opciones avanzadas](images/enable-bl-sp3.png) 

![Captura de pantalla de opciones avanzadas](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="15c92-129">Habilitar el límite de batería con el modo de administración de Surface Enterprise (SEMM) o los scripts de PowerShell de firmware Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="15c92-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="15c92-130">El límite de batería de Surface UEFI también está disponible para la configuración a través de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="15c92-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="15c92-131">Surface Pro 4 y posterior</span><span class="sxs-lookup"><span data-stu-id="15c92-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="15c92-132">Configurador UEFI de Surface de Microsoft</span><span class="sxs-lookup"><span data-stu-id="15c92-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="15c92-133">Scripts de PowerShell de Surface UEFI Manager (SEMM_Powershell.zip) en las [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="15c92-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="15c92-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="15c92-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="15c92-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="15c92-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="15c92-136">Uso del configurador Microsoft Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="15c92-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="15c92-137">Para configurar el modo de límite de batería, establezca la configuración de **invalidaciones de quiosco** en la página de configuración de **Configuración avanzada** en SEMM (Surface Pro 4 y posterior).</span><span class="sxs-lookup"><span data-stu-id="15c92-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![Captura de pantalla de configuración avanzada](images/semm-bl.png)

### <span data-ttu-id="15c92-139">Uso de scripts de PowerShell de Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="15c92-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="15c92-140">La característica de límite de batería se controla mediante la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="15c92-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="15c92-141">**Descripción**: Plan de administración activo para el patrón de uso de la batería</span><span class="sxs-lookup"><span data-stu-id="15c92-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="15c92-142">**Valor predeterminado**:</span><span class="sxs-lookup"><span data-stu-id="15c92-142">**Default**:</span></span>  `0` 

<span data-ttu-id="15c92-143">Establezca esta opción para `1` Habilitar el límite de batería.</span><span class="sxs-lookup"><span data-stu-id="15c92-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="15c92-144">Uso de las herramientas de firmware Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="15c92-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="15c92-145">La característica de límite de batería se controla mediante la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="15c92-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="15c92-146">**Nombre**: BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="15c92-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="15c92-147">**Descripción**: BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="15c92-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="15c92-148">**Valor actual**:</span><span class="sxs-lookup"><span data-stu-id="15c92-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="15c92-149">**Valor predeterminado**:</span><span class="sxs-lookup"><span data-stu-id="15c92-149">**Default Value**:</span></span> `0`

<span data-ttu-id="15c92-150">**Valor propuesto**:</span><span class="sxs-lookup"><span data-stu-id="15c92-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="15c92-151">Establezca esta opción para `1` Habilitar el límite de batería.</span><span class="sxs-lookup"><span data-stu-id="15c92-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="15c92-152">Para configurar esta opción, debe usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="15c92-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 


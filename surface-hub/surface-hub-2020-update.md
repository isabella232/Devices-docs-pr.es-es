---
title: Instalar la actualización 2020 de Windows10Team
description: Obtén la actualización más reciente del sistema operativo Surface Hub, Windows 10 Team 2020 Update.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470418"
---
# <a name="install-windows-10-team-2020-update"></a><span data-ttu-id="96a4c-104">Instalar la actualización 2020 de Windows10Team</span><span class="sxs-lookup"><span data-stu-id="96a4c-104">Install Windows 10 Team 2020 Update</span></span> 

<span data-ttu-id="96a4c-105">El nuevo sistema operativo Surface Hub, **Windows 10 Team 2020 Update,** basado en Windows 10 versión 20H2, ya está disponible para Surface Hub 2S y el Surface Hub original (v1).</span><span class="sxs-lookup"><span data-stu-id="96a4c-105">The new Surface Hub operating system, **Windows 10 Team 2020 Update**, based on Windows 10 version 20H2, is now available for Surface Hub 2S and the original Surface Hub (v1).</span></span> 

- <span data-ttu-id="96a4c-106">Vea también: [Problemas conocidos: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="96a4c-106">See also: [Known issues: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span></span>

## <a name="distribution"></a><span data-ttu-id="96a4c-107">Distribución</span><span class="sxs-lookup"><span data-stu-id="96a4c-107">Distribution</span></span>

<span data-ttu-id="96a4c-108">Puedes obtener Windows 2020 Update con uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="96a4c-108">You can obtain Windows 2020 Update using one of the following methods:</span></span>

- <span data-ttu-id="96a4c-109">**Windows Update para empresas**.</span><span class="sxs-lookup"><span data-stu-id="96a4c-109">**Windows Update for Business**.</span></span>
- <span data-ttu-id="96a4c-110">**Imagen de recuperación completa de metal (BMR).**</span><span class="sxs-lookup"><span data-stu-id="96a4c-110">**Bare metal recovery (BMR) image**.</span></span> <span data-ttu-id="96a4c-111">Opción recomendada para los clientes que unen sus dispositivos a Azure Active Directory o no permiten que sus dispositivos reciban actualizaciones de Internet.</span><span class="sxs-lookup"><span data-stu-id="96a4c-111">Recommended option for customers who join their devices to Azure Active Directory or don’t allow their devices to receive updates from the internet.</span></span> <span data-ttu-id="96a4c-112">Para empezar, consulta [Descargar una imagen de recuperación para Surface](https://support.microsoft.com/surfacerecoveryimage).</span><span class="sxs-lookup"><span data-stu-id="96a4c-112">To get started, see [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>
- **<span data-ttu-id="96a4c-113">Windows Update.</span><span class="sxs-lookup"><span data-stu-id="96a4c-113">Windows Update.</span></span>** <span data-ttu-id="96a4c-114">La disponibilidad varía según la región o el país, como se indica en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="96a4c-114">Availability varies by region/country, as noted in the following table:</span></span>

| <span data-ttu-id="96a4c-115">Fase</span><span class="sxs-lookup"><span data-stu-id="96a4c-115">Phase</span></span> | <span data-ttu-id="96a4c-116">País/región</span><span class="sxs-lookup"><span data-stu-id="96a4c-116">Country/Region</span></span>                         | <span data-ttu-id="96a4c-117">Inicio</span><span class="sxs-lookup"><span data-stu-id="96a4c-117">Starting</span></span>          |
| ----- | -------------------------------------- | ----------------- |
| <span data-ttu-id="96a4c-118">1</span><span class="sxs-lookup"><span data-stu-id="96a4c-118">1</span></span>     | <span data-ttu-id="96a4c-119">NZ, Australia, Canadá, Bélgica, México</span><span class="sxs-lookup"><span data-stu-id="96a4c-119">NZ, Australia, Canada, Belgium, Mexico</span></span> | <span data-ttu-id="96a4c-120">Octubre de 2020</span><span class="sxs-lookup"><span data-stu-id="96a4c-120">October 2020</span></span>  |
| <span data-ttu-id="96a4c-121">2</span><span class="sxs-lookup"><span data-stu-id="96a4c-121">2</span></span>     | <span data-ttu-id="96a4c-122">Reino Unido, Japón, Suiza, Italia</span><span class="sxs-lookup"><span data-stu-id="96a4c-122">UK, Japan, Switzerland, Italy</span></span>          | <span data-ttu-id="96a4c-123">Noviembre de 2020</span><span class="sxs-lookup"><span data-stu-id="96a4c-123">November 2020</span></span> |
| <span data-ttu-id="96a4c-124">3</span><span class="sxs-lookup"><span data-stu-id="96a4c-124">3</span></span>     | <span data-ttu-id="96a4c-125">Alemania, Países Bajos</span><span class="sxs-lookup"><span data-stu-id="96a4c-125">Germany, Netherlands</span></span>                   | <span data-ttu-id="96a4c-126">Finales de febrero de 2021</span><span class="sxs-lookup"><span data-stu-id="96a4c-126">Late February 2021</span></span> |
| <span data-ttu-id="96a4c-127">4</span><span class="sxs-lookup"><span data-stu-id="96a4c-127">4</span></span>     | <span data-ttu-id="96a4c-128">Global</span><span class="sxs-lookup"><span data-stu-id="96a4c-128">Global</span></span>                                 | <span data-ttu-id="96a4c-129">Principios de marzo de 2021</span><span class="sxs-lookup"><span data-stu-id="96a4c-129">Early March 2021</span></span> |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a><span data-ttu-id="96a4c-130">Mantenimiento de Surface Hubs con Windows 10 Team Edition versión 1703</span><span class="sxs-lookup"><span data-stu-id="96a4c-130">Servicing Surface Hubs with Windows 10 Team Edition version 1703</span></span> 

<span data-ttu-id="96a4c-131">El soporte técnico completo para [Windows 10 Team Edition versión 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) está programado para continuar hasta el 16 de marzo de 2021.</span><span class="sxs-lookup"><span data-stu-id="96a4c-131">Full servicing support for [Windows 10 Team Edition version 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) is scheduled to continue until March 16, 2021.</span></span>

### <a name="2s-devices"></a><span data-ttu-id="96a4c-132">Dispositivos 2S</span><span class="sxs-lookup"><span data-stu-id="96a4c-132">2S devices</span></span> 

<span data-ttu-id="96a4c-133">Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub 2S a la actualización de 2020 a través de Windows Update, Windows Update para empresas o mediante la imagen de recuperación completa (BMR), como se explica en [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span><span class="sxs-lookup"><span data-stu-id="96a4c-133">Customers in all regions can update their Surface Hub 2S devices to the 2020 Update through Windows Update, Windows Update for Business or by using the bare metal recovery (BMR) image, as explained in [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

### <a name="v1-devices"></a><span data-ttu-id="96a4c-134">Dispositivos V1</span><span class="sxs-lookup"><span data-stu-id="96a4c-134">V1 devices</span></span> 

<span data-ttu-id="96a4c-135">Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub v1 a 2020 Update a través de Windows Update, Windows Update para empresas o mediante la Herramienta de recuperación de [Surface Hub.](surface-hub-recovery-tool.md)</span><span class="sxs-lookup"><span data-stu-id="96a4c-135">Customers in all regions can update their Surface Hub v1 devices to the 2020 Update through Windows Update, Windows Update for Business, or by [using the Surface Hub Recovery Tool](surface-hub-recovery-tool.md).</span></span> <span data-ttu-id="96a4c-136">KB5000749 debe instalarse para recibir la actualización por aire.</span><span class="sxs-lookup"><span data-stu-id="96a4c-136">KB5000749 must be installed in order to receive the update over-the-air.</span></span> <span data-ttu-id="96a4c-137">Para obtener más información, consulta [Blog de Surface IT Pro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).</span><span class="sxs-lookup"><span data-stu-id="96a4c-137">To learn more, see [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).</span></span>
 
## <a name="whats-new"></a><span data-ttu-id="96a4c-138">Novedades</span><span class="sxs-lookup"><span data-stu-id="96a4c-138">What’s new</span></span>

<span data-ttu-id="96a4c-139">Windows 10 Team 2020 Update ofrece mejoras importantes en la implementación y la facilidad de administración de dispositivos, junto con las características más recientes de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="96a4c-139">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="96a4c-140">Para obtener más información, consulta [Novedades de Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="96a4c-140">To learn more, see [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).</span></span>
 
## <a name="before-you-begin"></a><span data-ttu-id="96a4c-141">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="96a4c-141">Before you begin</span></span>

<span data-ttu-id="96a4c-142">Antes de instalar Windows 10 Team 2020 Update, asegúrate de guardar la clave de BitLocker asociada al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96a4c-142">Prior to installing Windows 10 Team 2020 Update, make sure you save the BitLocker key associated with your device.</span></span> 

**<span data-ttu-id="96a4c-143">Para guardar manualmente la clave de BitLocker</span><span class="sxs-lookup"><span data-stu-id="96a4c-143">To manually save your BitLocker key</span></span>**

1. <span data-ttu-id="96a4c-144">Inserta una unidad USB en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="96a4c-144">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="96a4c-145">En Surface Hub, abre **Configuración** y escribe tus credenciales de administrador cuando se te pida.</span><span class="sxs-lookup"><span data-stu-id="96a4c-145">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="96a4c-146">Vaya a **Actualizar &**  >  **recuperación de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="96a4c-146">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="96a4c-147">En **BitLocker,** seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="96a4c-147">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="96a4c-148">La clave BitLocker se guarda en un archivo de texto en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="96a4c-148">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="96a4c-149">Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="96a4c-149">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="96a4c-150">Más información</span><span class="sxs-lookup"><span data-stu-id="96a4c-150">Learn more</span></span>

- [<span data-ttu-id="96a4c-151">Novedades de la actualización Windows10 Team 2020</span><span class="sxs-lookup"><span data-stu-id="96a4c-151">What's new in Windows 10 Team 2020 Update</span></span>](surface-hub-2020-update-whats-new.md)
- [<span data-ttu-id="96a4c-152">Actualización al lanzamiento de Windows 10 Team</span><span class="sxs-lookup"><span data-stu-id="96a4c-152">Update to the Windows 10 Team rollout</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)

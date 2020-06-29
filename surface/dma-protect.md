---
title: Protección de DMA de Surface
description: En este artículo se describe la protección de DMA en dispositivos de superficie compatibles
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835106"
---
# <span data-ttu-id="c25d8-103">Protección de DMA en dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="c25d8-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="c25d8-104">La protección de acceso directo a memoria (DMA) está diseñada para mitigar las posibles vulnerabilidades de seguridad asociadas al uso de SSDs extraíbles o dispositivos de almacenamiento externo.</span><span class="sxs-lookup"><span data-stu-id="c25d8-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="c25d8-105">Los dispositivos Surface más nuevos incluyen la protección de DMA habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c25d8-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="c25d8-106">Esto incluye Surface Pro 7, Surface Laptop 3 y Surface Pro X.  Para comprobar la característica de protección de DMA en el dispositivo, abra información del sistema (**Inicio**  >  **msinfo32.exe**), como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="c25d8-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![Información del sistema que muestra la protección de DMA habilitada](images/systeminfodma.png)

<span data-ttu-id="c25d8-108">Si se manipula un SSD extraíble de superficie, el dispositivo detendrá energía.</span><span class="sxs-lookup"><span data-stu-id="c25d8-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="c25d8-109">El reinicio resultante hace que UEFI Limpie la memoria, para borrar los datos residuales.</span><span class="sxs-lookup"><span data-stu-id="c25d8-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>

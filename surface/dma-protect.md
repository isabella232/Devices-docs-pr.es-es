---
title: Protección de DMA para Surface
description: En este artículo se describe la protección de DMA en dispositivos Surface compatibles
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/01/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: ae648f54f7abd97a6397dca5aa204205b582e4b0
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338053"
---
# <a name="dma-protection-on-surface-devices"></a>Protección de DMA en dispositivos Surface

La protección de acceso directo a la memoria (DMA) está diseñada para mitigar posibles vulnerabilidades de seguridad asociadas con el uso de UNIDADES de seguridad extraíbles o dispositivos de almacenamiento externo. Los dispositivos Surface más recientes vienen con protección DMA habilitada de forma predeterminada. Estos incluyen Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Laptop SE, Surface Pro 7+, Surface Pro 7, Surface Laptop 3 y Surface Pro  X.  Para comprobar la presencia de la característica de protección DMA en el dispositivo, abra Información del sistema (**Inicio** > **msinfo32.exe**), como se muestra en la figura siguiente.

![Información del sistema que muestra la protección de DMA habilitada.](images/systeminfodma.png)

Si se manipula un SSD extraíble de Surface, el dispositivo apagará la energía. El reinicio resultante hace que UEFI borre la memoria y borre los datos residuales.

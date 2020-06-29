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
# Protección de DMA en dispositivos Surface

La protección de acceso directo a memoria (DMA) está diseñada para mitigar las posibles vulnerabilidades de seguridad asociadas al uso de SSDs extraíbles o dispositivos de almacenamiento externo. Los dispositivos Surface más nuevos incluyen la protección de DMA habilitada de forma predeterminada. Esto incluye Surface Pro 7, Surface Laptop 3 y Surface Pro X.  Para comprobar la característica de protección de DMA en el dispositivo, abra información del sistema (**Inicio**  >  **msinfo32.exe**), como se muestra en la siguiente ilustración.

![Información del sistema que muestra la protección de DMA habilitada](images/systeminfodma.png)

Si se manipula un SSD extraíble de superficie, el dispositivo detendrá energía. El reinicio resultante hace que UEFI Limpie la memoria, para borrar los datos residuales.

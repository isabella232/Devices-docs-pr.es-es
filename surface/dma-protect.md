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
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270625"
---
# Protección DMA en dispositivos Surface

La protección de acceso directo a memoria (DMA) está diseñada para mitigar posibles vulnerabilidades de seguridad asociadas con el uso de SSD extraíbles o dispositivos de almacenamiento externo. Los dispositivos Surface más recientes vienen con protección DMA habilitada de forma predeterminada. Estos incluyen Surface Pro 7+. Surface Pro 7, Surface Laptop 3 y Surface Pro X.  Para comprobar la presencia de la característica de protección de DMA en el dispositivo, abra Información del sistema **(** Iniciomsinfo32.exe), como se muestra en la ilustración  >  ** **siguiente.

![Información del sistema que muestra la protección de DMA habilitada](images/systeminfodma.png)

Si se manipula un SSD extraíble de Surface, el dispositivo apagará la alimentación. El reinicio resultante hace que UEFI borre la memoria y borre los datos residuales.

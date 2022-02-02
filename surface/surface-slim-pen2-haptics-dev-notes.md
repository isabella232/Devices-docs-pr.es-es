---
title: Notas de desarrollo de Surface Slim Pen 2 hápticos
description: En esta página se proporcionan notas de implementación para desarrolladores de aplicaciones que desean ampliar Windows 11 funciones ink de Surface Slim Pen 2 para empresas.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: 8a3dbbdde85cfdceaf5674750a68fc21d3fcd877
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338708"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>Notas de desarrollo de Surface Slim Pen 2 hápticos

En esta página se proporcionan notas de implementación para desarrolladores de aplicaciones que desean ampliar Windows 11 funciones ink de [Surface Slim Pen 2 para empresas](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). Entre las características de hápticos personalizables se incluyen las siguientes:

- **Comentarios que simulan** la sensación de lápices, lápices y otras herramientas de escritura o dibujo.
- **Comentarios de interacción** que responden directamente a acciones del usuario, como pasar el mouse sobre un botón, hacer clic en un botón o completar una tarea con el lápiz.

Si estás personalizando una aplicación para Surface Slim Pen 2, consulta las directrices de Windows Ink [descritas](/windows/apps/design/input/pen-haptics) en Interacciones del lápiz y comentarios hápticos y consulta las siguientes notas.

## <a name="implementation-notes"></a>Notas de implementación

Surface Slim Pen 2 cumple con las Windows 11 ink con las siguientes excepciones:

- **Formas de onda de interacción.** Tal como se documenta [](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)en la sección Enviar y detener comentarios de interacción", el envío de una forma de onda de interacción cuando se reproduce una forma de onda de entrada mantica interrumpirá temporalmente la forma de onda de entrada mantica. Sin embargo, con la implementación actual de Lápiz delgado 2, es posible que la forma de onda de entrada no se reanude cuando se detenga la forma de onda de interacción. Por lo tanto, si aún es necesario, la forma de onda de entrada entinta debe volver a habilitarse después de los comentarios de interacción. No es necesario esperar a que se completen los comentarios de interacción.
- **Características no admitidas.** Como se documenta en la sección [Personalizaciones](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations) de comentarios hápticos", las siguientes características opcionales no se admiten en Surface Slim Pen 2: Recuento de reproducción e Intervalo de pausa de reproducción. Aunque estos usos aparecen en el descriptor, actualmente no se admiten. Por lo tanto, las siguientes funciones devuelven un valor incorrecto: IsPlayCountSupported, IsPlayDurationSupported, IsReplayPauseIntervalSupported.

## <a name="learn-more"></a>Obtén más información

- [Interacciones del lápiz y Windows Ink en Windows aplicaciones](/windows/apps/design/input/pen-and-stylus-interactions)
- [Lápiz de Surface Slim 2 para empresas](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Compatibilidad y características de lápiz de Surface](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)


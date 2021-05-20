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
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento

En determinadas circunstancias, Surface Hub las actualizaciones durante el horario laboral en lugar de durante la ventana de mantenimiento normal. A continuación, el dispositivo se reinicia si es necesario. No puedes usar el dispositivo hasta que se complete el proceso.

> [!NOTE]  
> Este no es un comportamiento esperado por falta de una ventana de mantenimiento. Solo se produce si el dispositivo está fuera de fecha durante mucho tiempo.

## <a name="cause"></a>Causa

Para garantizar que Surface Hub esté disponible para su uso durante el horario comercial, el concentrador está configurado para realizar funciones administrativas durante una ventana de mantenimiento que se define en Configuración (vea "Referencias", a continuación). Durante este período de mantenimiento, el concentrador instala automáticamente las actualizaciones disponibles a través de Windows Update o Windows Update for Business (WUfB). Una vez completadas las actualizaciones, el concentrador puede reiniciarse.

Las actualizaciones solo se pueden instalar durante la ventana de mantenimiento si el Surface Hub está activado pero no está en uso o reservado. Por ejemplo, si el Surface Hub está programado para una reunión que dura 24 horas, las actualizaciones programadas para instalarse se aplazarán hasta que el concentrador esté disponible durante la siguiente ventana de mantenimiento. Si el concentrador sigue ocupado y pierde varias ventanas de mantenimiento, el concentrador finalmente empezará a instalar y descargar actualizaciones. Esto puede ocurrir durante o fuera de la ventana de mantenimiento. Una vez iniciada la descarga y la instalación, el dispositivo puede reiniciarse.

## <a name="to-avoid-this-issue"></a>Para evitar este problema

Es importante que reserve el tiempo de mantenimiento para Surface Hub realizar funciones administrativas. Reservar el Surface Hub durante intervalos de 24 horas o usar el dispositivo durante la ventana de mantenimiento retrasa la instalación de actualizaciones. Se recomienda no usar ni reservar el concentrador durante el período de mantenimiento programado. Se debe reservar una ventana de dos horas para la actualización.

Una opción que puede usar para controlar la disponibilidad de actualizaciones es Windows Update for Business.

## <a name="learn-more"></a>Obtén más información
 
- [Actualizar Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 
- [Ventana de mantenimiento](manage-windows-updates-for-surface-hub.md#maintenance-window) 

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
# Surface Hub puede instalar actualizaciones y reiniciar fuera del horario de mantenimiento

En circunstancias específicas, Surface Hub instala actualizaciones durante el horario laboral, en lugar de durante la ventana de mantenimiento habitual. El dispositivo se reiniciará si es necesario. No puede usar el dispositivo hasta que el proceso se haya completado.

> [!NOTE]  
> Este no es el comportamiento esperado para la falta de una ventana de mantenimiento. Solo se produce si el dispositivo está anticuado durante mucho tiempo.

## Causa
Para asegurarse de que Surface Hub esté disponible para su uso durante el horario comercial, el concentrador está configurado para realizar funciones administrativas durante una ventana de mantenimiento definida en configuración (consulte "referencias" a continuación). Durante este período de mantenimiento, el concentrador instala automáticamente todas las actualizaciones disponibles a través de Windows Update o Windows Server Update Services (WSUS). Una vez que se completan las actualizaciones, es posible que el concentrador se reinicie.

Las actualizaciones se pueden instalar durante la ventana de mantenimiento solo si Surface Hub está activado, pero no en uso ni reservado. Por ejemplo, si el Surface Hub está programado para una reunión que dura 24 horas, todas las actualizaciones programadas para su instalación se aplazarán hasta que el concentrador esté disponible en la siguiente ventana de mantenimiento. Si el concentrador continúa estando ocupado y pierde varias ventanas de mantenimiento, el concentrador comenzará a instalar y descargar las actualizaciones. Esto puede ocurrir durante o fuera de la ventana de mantenimiento. Una vez iniciada la descarga e instalación, el dispositivo puede reiniciarse.

## Para evitar este problema

Es importante dedicar tiempo de mantenimiento para que Surface Hub realice funciones administrativas. La reserva de Surface Hub durante un intervalo de 24 horas o el uso del dispositivo durante la ventana de mantenimiento retrasa la instalación de actualizaciones. Le recomendamos que no use ni Reserve el concentrador durante el período de mantenimiento programado. Se debe reservar una ventana de dos horas para la actualización.

Una opción que puede usar para controlar la disponibilidad de las actualizaciones es Windows Server Update Services (WSUS). WSUS proporciona control sobre las actualizaciones que se instalan y cuándo.

## Referencias 
 
[Actualizar Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[Ventana de mantenimiento](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[Implementar las actualizaciones de Windows10 con Windows Server Update Services (WSUS)](/windows/deployment/update/waas-manage-updates-wsus) 



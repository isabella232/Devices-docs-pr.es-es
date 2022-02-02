---
title: Optimizar las videoconferencias en dispositivos Surface
description: Esta página proporciona procedimientos recomendados para usar Microsoft Teams y otras soluciones de videoconferencia en dispositivos Surface
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: dd72bf940309fe9f3d7b4bf334a94a557cffe016
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338659"
---
# <a name="optimize-video-conferencing-on-surface-devices"></a>Optimizar las videoconferencias en dispositivos Surface

Los dispositivos Surface aprovechan los últimos avances en el consumo de energía de dispositivos móviles para ofrecer una experiencia optimizada en todas las cargas de trabajo. Para la mayoría de las cargas de trabajo, esto proporciona una gran experiencia. Para algunas cargas de trabajo que usan Microsoft Teams u otras aplicaciones de videoconferencia, debe seguir estas recomendaciones para garantizar la mejor experiencia.

## <a name="surface-drivers-and-firmware"></a>Controladores y firmware de Surface

Microsoft publica actualizaciones periódicamente para dispositivos Surface y ha publicado varias actualizaciones de Surface destinadas a cargas de trabajo de videoconferencia, entre las que se incluyen:

- Mejoras en el rendimiento del sistema
- Mejoras en el consumo de energía en los controladores de cámara
- Actualizaciones de controladores gráficos
- Optimizaciones de configuración de energía

### <a name="get-updates-to-all-devices"></a>Obtener actualizaciones en todos los dispositivos

Asegúrese de que su organización tiene un proceso para que sus dispositivos reciban estas actualizaciones. Si estás usando Windows update o [Windows update para](/windows/deployment/update/waas-manage-updates-wufb) empresas, ya estás recibiendo las últimas actualizaciones de Surface cuando se lanzan. Comprueba si hay actualizaciones con Windows update y comprueba que se hayan instalado las actualizaciones más recientes de Surface. Para obtener más información, vea:

- [Historial de actualizaciones de Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [Instalar actualizaciones de Surface y Windows de dispositivos](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

Si usas otras opciones para instalar los controladores de Surface y las actualizaciones de firmware, deberás instalar las actualizaciones más recientes de Surface manualmente con los archivos MSI publicados o instalar las actualizaciones con Configuration Manager. Para obtener más información, vea:

- [Descargar controladores y firmware para Surface](https://support.microsoft.com/help/4023482)
- [Administrar e implementar actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md)
- [Cómo administrar las actualizaciones de controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906)

### <a name="graphics-driver-updates-for-microsoft-teams"></a>Actualizaciones de controladores gráficos para Microsoft Teams

Los modelos de dispositivos Surface más recientes con procesadores Intel de 10 y 11 generación han recibido actualizaciones de controladores gráficos que ayudan con las cargas de trabajo de videoconferencia. Para habilitar estas mejoras, asegúrese de instalar lo siguiente:

- Microsoft Teams versión **1.4.00.22472** o posterior.
- Controlador de gráficos **Intel 27.20.100.9621** o posterior.

### <a name="power-settings-optimizations"></a>Optimizaciones de configuración de energía

Los dispositivos Surface pueden ajustar la configuración de energía relacionada con el rendimiento cambiando la posición del control deslizante de potencia de rendimiento Windows en Windows 10, también conocido como modo de energía en Windows 11.

Algunos dispositivos Surface han recibido actualizaciones que incluyen optimizaciones de configuración de energía para cargas de trabajo de videoconferencia basadas en la posición del control deslizante de energía o el modo de alimentación. Sin embargo, como Windows 10 y Windows 11 usan la posición del control deslizante de **** energía recomendada y la posición del modo de alimentación para cargas de trabajo de videoconferencia, deberá ajustar el control deslizante de energía para habilitar estas optimizaciones:

1. Conectar a la alimentación de CA (las optimizaciones no se ejecutarán al usar la batería).  
2. Ajusta la posición del control deslizante o del modo de alimentación para usar **Mejor rendimiento** o **Mejor rendimiento.**

## <a name="learn-more"></a>Obtén más información

- [Procedimiento recomendado de configuración de energía para dispositivos Surface](maintain-optimal-power-settings-on-surface-devices.md)
- [Maximizar la duración de la batería de Surface](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)

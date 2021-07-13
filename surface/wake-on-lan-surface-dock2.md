---
title: Wake on LAN con Surface Dock 2
description: Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN (WOL) que permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración.
keywords: actualizar, implementar, controlador, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643856"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>Wake on LAN con Surface Dock 2

Para mantener los dispositivos totalmente actualizados, los administradores de TI deben poder administrar dispositivos cuando no están en uso, normalmente durante las ventanas de mantenimiento nocturnas. Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN (WOL) que permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración con Microsoft Endpoint Manager u otras soluciones de terceros.

## <a name="requirements"></a>Requisitos

Los dispositivos deben tener una conexión por cable con Surface Dock 2 y mantenerse conectados a AC Power.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a>Dispositivos Surface compatibles

- Surface Laptop 4 (procesadores Intel)
- Surface Laptop 4 (procesadores AMD)
- Surface Laptop 3 (procesadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Ir
- Surface Book 3

Surface Dock 2 proporciona compatibilidad con WOL para dispositivos en los siguientes estados de energía:

- Modo de espera conectado
- Hibernación (estado de energía S4)
- Apagado (estado de apagado suave de S5)

Para obtener más información sobre los estados de energía, consulte [System Power States](/windows/win32/power/system-power-states).

## <a name="how-it-works"></a>Cómo funciona

Cuando no están en uso, los dispositivos Surface entran en un estado inactivo y de bajo consumo conocido como Espera moderna o Espera conectada. Los administradores de TI pueden desencadenar dispositivos de forma remota mediante una solicitud de activación (paquete mágico) que contiene la dirección de Control de acceso multimedia (MAC) del dispositivo Surface de destino. Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL.

Para habilitar WOL en dispositivos sin Surface Dock 2, consulta [Activar en LAN para dispositivos Surface.](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>Obtén más información

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Wake on LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)
- [Estados de energía del sistema](/windows/win32/power/system-power-states)
- [Configurar la activación en LAN: Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)

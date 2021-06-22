---
title: Wake on LAN para dispositivos Surface
description: Consulta cómo puedes usar Wake on LAN activar dispositivos de forma remota para realizar tareas de administración automáticamente.
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
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613809"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake on LAN para dispositivos Surface

Para mantener los dispositivos totalmente actualizados, los administradores de TI deben poder administrar dispositivos cuando no están en uso, normalmente durante las ventanas de mantenimiento nocturnas. La activación en LAN (WOL) permite a los administradores activar dispositivos de forma remota y realizar automáticamente tareas de administración con soluciones Microsoft Endpoint Manager o de terceros.

## <a name="requirements"></a>Requisitos

Los dispositivos deben estar conectados a la alimentación de CA y tener una conexión por cable con uno de los siguientes adaptadores Ethernet compatibles:

- Adaptador Ethernet De Surface USB 3.0 Gigabit
- Adaptador Ethernet de Surface
- Adaptador USB-C a Ethernet y USB de Surface
- Concentrador de adaptadores de viajes USB-C de Microsoft
- Surface Dock
- Surface Dock 2

> [!NOTE]
> Surface Dock 2 proporciona la mejor compatibilidad con Wake on LAN sin necesidad de ninguna configuración de TI adicional. Para obtener más información, [consulta Activar la LAN para Surface Dock 2](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>Cómo funciona

Cuando no están en uso, los dispositivos Surface entran en un estado inactivo y de bajo consumo conocido como Espera moderna o Espera conectada. Los administradores de TI pueden desencadenar dispositivos de forma remota mediante una solicitud de activación (paquete mágico) que contiene la dirección de Control de acceso multimedia (MAC) del dispositivo Surface de destino. Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL. Para obtener más información sobre cómo activar dispositivos con Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).

La compatibilidad con Wake on LAN varía en función del estado de suspensión: Modo de espera conectado o Hibernación (estado de energía S4).

## <a name="connected-standby"></a>Modo de espera conectado

De forma predeterminada, Windows 10 activar en LAN para dispositivos Surface en modo de espera conectado.

### <a name="supported-surface-devices---connected-standby"></a>Dispositivos Surface compatibles: modo de espera conectado

- Surface Laptop 4 (solo procesadores Intel)
- Surface Laptop 3 (solo procesadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Ir
- Surface Book 3

## <a name="hibernation"></a>Hibernación

Para activar dispositivos fuera de hibernación, es necesario habilitar una configuración de directiva UEFI a través del Modo de administración de [Surface Enterprise](surface-enterprise-management-mode.md) (SEMM) (no es necesario para dispositivos conectados a Surface Dock 2).

### <a name="supported-surface-devices---hibernation"></a>Dispositivos Surface compatibles: hibernación

- Surface Laptop 4 (solo procesadores Intel)
- Surface Laptop 3 (solo procesadores Intel)
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop Ir
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>Para habilitar la opción Activar en LAN UEFI

Para habilitar la configuración activar la UEFI de LAN, debes inscribir dispositivos de destino en SEMM, crear un paquete de configuración y aplicar el paquete a los dispositivos. Para más información, consulta:

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Inscribir y configurar los dispositivos Surface con SEMM](enroll-and-configure-surface-devices-with-semm.md)

1. Descargar e instalar [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).
2. Seleccione **Iniciar paquete**de  >  **configuración**  >  **Crear**+ Protección de  > **certificados**.
3. Vaya a **Configuración avanzada y** cambie Activar la **LAN** a **Activar**.
4. Aplicar el paquete a los dispositivos de destino.

    > [!div class="mx-imgBorder"]
    > ![Habilitar activación en la configuración de directiva UEFI de LAN](images/wol-uefi.png)

## <a name="learn-more"></a>Obtén más información

- [Activar la LAN para Surface Dock 2](wake-on-lan-surface-dock2.md)
- [Adaptador USB-C a Ethernet y USB de Microsoft Surface](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Adaptador Ethernet De Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

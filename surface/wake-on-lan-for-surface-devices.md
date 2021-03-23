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
ms.date: 3/19/2021
ms.openlocfilehash: 9c3302616de97cf60b7d750948fed653456a7cba
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442894"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake on LAN para dispositivos Surface

Los dispositivos Surface que usan un adaptador Ethernet de Surface para conectarse a una red cableada pueden aprovechar Wake on LAN (WOL) desde el modo de espera conectado. Con WOL, puede activar dispositivos de forma remota y realizar automáticamente tareas de administración con soluciones de administración como Microsoft Endpoint Manager/Microsoft Intune.

## <a name="wol-supported-devices"></a>Dispositivos compatibles con WOL

- Adaptador Ethernet de Surface
- Adaptador USB-C a Ethernet y USB de Surface
- Surface Dock 2
- Surface Pro 6 y versiones posteriores
- Surface Book (todas las generaciones)
- Surface Laptop (todas las generaciones)
- Surface Go (todas las generaciones)
- Surface Studio 2 (consulta Apéndice)


## <a name="using-surface-wol"></a>Uso de Surface WOL

Los administradores de TI pueden desencadenar dispositivos mediante una activación en una solicitud LAN (paquete mágico) que contenga la dirección MAC del equipo de destino. Para enviar un paquete mágico y activar un dispositivo mediante WOL, debes conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet. Dado que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.

Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager y aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL. Ten en cuenta que los dispositivos deben estar en modo de espera conectado (suspensión) y conectados a la alimentación de CA. Para obtener más información sobre cómo activar dispositivos con Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).


### <a name="to-check-wol-is-enabled-on-your-device"></a>Para comprobar que WOL está habilitado en el dispositivo

1. En el dispositivo conectado a Ethernet, seleccione el adaptador de red y, a continuación, seleccione **Propiedades**.

   > [!div class="mx-imgBorder"]
   > ![Adaptador Ethernet de Surface](images/surface-ethernet.png)

2. Seleccione **Configurar**  >  **opciones avanzadas**.
3. Desplácese **hasta Paquete mágico woL de** espera moderno y asegúrese de que **Está** habilitado está seleccionado.

     ![Comprobar que WOL está habilitado en el dispositivo](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>Apéndice: Surface Studio 2

Para habilitar WOL en Surface Studio 2, usa el siguiente procedimiento.

1. Cree las siguientes claves del Registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Ejecute el siguiente comando

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>Más información

- [Adaptador USB-C a Ethernet y USB de Microsoft Surface](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Adaptador Ethernet De Surface USB 3.0 Gigabit](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

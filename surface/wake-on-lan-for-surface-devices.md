---
title: Wake on LAN para dispositivos Surface
description: Los dispositivos Surface que ejecutan Windows 10, versión 1607 o posterior y usan un adaptador Ethernet de Surface para conectarse a una red cableada pueden Wake on LAN (WOL) desde el modo de espera moderno.
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
ms.date: 11/30/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: f0d2215fae1ce8aa5cdc6d55fb36158d6a95af4d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448293"
---
# <a name="wake-on-lan-for-surface-devices"></a>Wake on LAN para dispositivos Surface 

Los dispositivos Surface que Windows 10 versión 1607 o posterior pueden usar Wake on LAN (WOL) desde el modo de espera moderno (también conocido como modo de espera conectado). Con WOL, los administradores de TI pueden activar dispositivos de forma remota y realizar automáticamente tareas de administración con Microsoft Endpoint Manager soluciones de terceros.

>[!NOTE]
>Para admitir WOL, los dispositivos Surface deben conectarse a la alimentación de CA y usar un adaptador Ethernet de Surface que esté conectado a una red cableada.

## <a name="supported-devices"></a>Dispositivos compatibles

Adaptadores Ethernet compatibles con WOL:

- Microsoft USB-C Travel Hub
- Adaptador Ethernet de Surface
- Adaptador de Surface USB-C a Ethernet y USB 3.0
- Adaptador Ethernet De Surface USB 3.0 Gigabit 
- Surface DockDocking Station para Surface Pro 3 
- Surface Dock 2
- Estación de acoplamiento para Surface 3
- Estación de acoplamiento para Surface Pro 3 

Dispositivos Surface compatibles con WOL:

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (5ª generación)
- Surface Pro (5ª generación) con LTE Advanced
- Surface Pro 6
- Surface Pro 7
- Surface Pro 7+
- SurfacePro8
- Surface Book (todas las generaciones)
- Surface Go (todas las generaciones)
- Surface Laptop (todas las generaciones)
- Surface Laptop Go
- Surface Laptop SE
- SurfaceLaptopStudio
- Surface Studio 2 (vea Surface Studio 2 instrucciones a continuación)


## <a name="using-wol"></a>Uso de WOL 

Cuando no están en uso, los dispositivos Surface entran en un estado inactivo y de bajo consumo conocido como Espera moderna o Espera conectada. Los administradores de TI pueden desencadenar dispositivos de forma remota mediante una solicitud de activación (paquete mágico) que contiene la dirección de Control de acceso multimedia (MAC) del dispositivo Surface de destino. La tarjeta de interfaz de red de destino (NIC) compara la dirección MAC con la suya propia antes de activar el dispositivo. Si la dirección MAC de la solicitud de activación de paquetes mágicos no coincide con la dirección MAC en la NIC de destino, la NIC no activará el dispositivo. Para obtener más información, revise [la documentación de orígenes de activación](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>Espera moderna

El modo de espera moderno se inicia cuando el usuario hace que el sistema entre en suspensión o cuando el dispositivo se pone en modo de suspensión en función de la Windows de energía que el usuario ha establecido. Por ejemplo, el usuario presiona el botón de encendido, cierra la tapa o selecciona Suspensión en el botón de encendido de la Windows menú Inicio. WOL funciona de forma predeterminada para dispositivos Surface en modo de espera moderno que Windows 10 versión 1607 o posterior. No se requiere ninguna configuración de TI adicional, excepto Surface Studio 2.

## <a name="surface-studio-2-instructions"></a>Surface Studio 2 instrucciones

Para habilitar WOL en Surface Studio 2, debe usar el siguiente procedimiento

1. Abra el Editor del** Registro **(**StartSearch** > **** > regedit.exe) y cree las siguientes claves del Registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. Ejecute el siguiente comando

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> Si actualiza la versión de Windows 10 en su Surface Studio 2 (por ejemplo, actualiza de Windows 10 20H2 a 21H1), deberá seguir estas instrucciones de nuevo para habilitar WOL.


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>Para activar desde la hibernación (S4) o el apagado (S5) 

- Para dispositivos conectados a Surface Dock 2, consulta [Activar la LAN para Surface Dock 2](wake-on-lan-surface-dock2.md)

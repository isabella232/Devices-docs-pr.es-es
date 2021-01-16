---
title: Wake on LAN dispositivos Surface (Surface)
description: Consulta cómo puedes usar Wake on LAN para activar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o para habilitar soluciones de administración automáticamente, incluso si los dispositivos están apagados.
keywords: update, deploy, implementar, driver, driver, controlador, wake-on-lan, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 709286cc0d62bd0b4c1e28e7626529fc4a215ae2
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271127"
---
# Wake on LAN para dispositivos Surface

Los dispositivos Surface que ejecutan Windows 10, versión 1607 (también conocida como Actualización de aniversario de Windows 10) o posterior y usan un adaptador Ethernet de Surface para conectarse a una red cableada, son capaces de Wake on LAN (WOL) desde el modo de espera conectado. Con ELSO, puede activar dispositivos de forma remota para realizar tareas de administración o mantenimiento o habilitar soluciones de administración (como Microsoft Endpoint Configuration Manager) automáticamente. Por ejemplo, puedes implementar aplicaciones en dispositivos Surface que quedan acoplados con Surface Dock o surface Pro 3 Docking Station mediante Microsoft Endpoint Configuration Manager durante una ventana en mitad de la noche, cuando la oficina está vacía.

>[!NOTE]
>Los dispositivos Surface deben estar conectados a la corriente alterna y en modo de espera conectado (suspensión) para admitir ELS. NO es posible REALIZAR EL TRABAJO desde dispositivos que están en hibernación o apagados.

## Dispositivos compatibles

Los siguientes dispositivos son compatibles con LAR:

* Adaptador Ethernet de Surface
* Surface USB-C a Ethernet y adaptador USB
* Surface Dock
* Estación de acoplamiento de Surface para Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5ª generación)
* Surface Pro (5ª generación) con LTE Advanced
* Surface Book
* Surface Laptop (1.ª generación)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go con LTE Advanced
* Surface Studio 2 (consulta las instrucciones de Surface Studio 2 a continuación)
* Surface Pro 7
* Surface Laptop 3
* Surface Laptop Go
* Surface Pro 7+

## Controlador DESOD

Para habilitar la compatibilidad con LAR en dispositivos Surface, se requiere un controlador específico para el adaptador Ethernet de Surface. Este controlador no está incluido en el paquete de controladores y firmware estándar para dispositivos Surface: debes descargarlo e instalarlo por separado. Puedes descargar el controlador DESO de Surface (SurfaceWOL.msi) desde la página Herramientas de [Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft.

Puedes ejecutar este archivo Microsoft Windows Installer (.msi) en un dispositivo Surface para instalar el controlador SURFACE WOL, o puedes distribuirlo a dispositivos Surface con una solución de implementación de aplicaciones, como Microsoft Endpoint Configuration Manager. Para incluir el controlador SURFACE WOL durante la implementación, puedes instalar el archivo .msi como una aplicación durante el proceso de implementación. También puedes extraer los archivos de controlador de SURFACE WOL para incluirlos en el proceso de implementación. Por ejemplo, puedes incluirlos en el recurso compartido de implementación de Microsoft Deployment Toolkit (MDT). Puedes leer más sobre la implementación de Surface con MDT en [Implementar Windows 10](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)en dispositivos Surface con Microsoft Deployment Toolkit.

> [!NOTE]
> Durante la instalación de SurfaceWOL.msi, la siguiente clave del Registro se establece en un valor de 1, lo que permite identificar fácilmente los sistemas en los que se ha instalado el controlador DESA. Si decidiste extraer e instalar estos controladores por separado durante la implementación, esta clave del Registro no se configurará y debe configurarse manualmente o con un script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Para extraer el contenido de SurfaceWOL.msi, use la opción de instalación administrativa MSIExec (**/a**), como se muestra en el ejemplo siguiente, para extraer el contenido en la carpeta C:\WOL\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instrucciones de Surface Studio 2

Para habilitar LAR en Surface Studio 2, debes usar el siguiente procedimiento

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

2. Ejecute el comando siguiente

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Uso de Surface WOL

El controlador SURFACE WOL cumple con el estándar DESA, por el que el dispositivo es resamplado por una comunicación de red especial conocida como paquete mágico. El paquete mágico consta de 6 bytes de 255 (o FF en hexadecimal) seguido de 16 repeticiones de la dirección MAC del equipo de destino. Puede leer más sobre el paquete mágico y el estándar DESA en [Wikipedia.](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)

>[!NOTE]
>Para enviar un paquete mágico y activar un dispositivo mediante ELSO, debes conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet. Dado que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.

Muchas soluciones de administración, como Configuration Manager, proporcionan compatibilidad integrada con ELR. También hay muchas soluciones, como aplicaciones de Microsoft Store, módulos de PowerShell, aplicaciones de terceros y soluciones de administración de terceros que te permiten enviar un paquete mágico para activar un dispositivo. Por ejemplo, puede usar el módulo [Wake on LAN PowerShell desde](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) el Centro de scripts de TechNet. 

>[!NOTE]
>Después de que un dispositivo se haya convertido en un paquete mágico, el dispositivo volverá a estar en suspensión si una aplicación no impide activamente la suspensión en el sistema o si la clave del Registro AllowSystemRequiredPowerRequests no está configurada en 1, lo que permite a las aplicaciones evitar el suspensión. Vea la [sección del controlador DESO](#wol-driver) de este artículo para obtener más información acerca de esta clave del Registro.

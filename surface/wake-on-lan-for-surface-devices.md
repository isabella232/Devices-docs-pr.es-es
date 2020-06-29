---
title: Wake on LAN para dispositivos de superficie (Surface)
description: Vea cómo puede usar Wake on LAN para reactivar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o para habilitar soluciones de administración de forma automática, incluso si los dispositivos están apagados.
keywords: actualizar, implementar, controlador, WOL, Wake-on-LAN
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
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835513"
---
# Wake on LAN para dispositivos Surface

Los dispositivos Surface que ejecutan Windows 10, versión 1607 (también conocida como actualización de aniversario de Windows 10) o una versión posterior, y usan un adaptador de Surface Ethernet para conectarse a una red cableada, son capaces de Wake on LAN (WOL) desde el modo de espera conectado. Con WOL, puede reactivar dispositivos de forma remota para realizar tareas de administración o mantenimiento, o bien habilitar de forma automática soluciones de administración (como Microsoft Endpoint Configuration Manager). Por ejemplo, puede implementar aplicaciones para Surface los dispositivos que se conectan con una estación de acoplamiento de Surface o Surface Pro 3 usando Microsoft Endpoint Configuration Manager durante una ventana en el medio de la noche, cuando la oficina está vacía.

>[!NOTE]
>Los dispositivos Surface deben estar conectados a la alimentación de CA y al modo de espera conectado (dormir) para admitir WOL. WOL no es posible desde dispositivos que están en hibernación o apagados.

## Dispositivos compatibles

Los siguientes dispositivos son compatibles con WOL:

* Adaptador de Ethernet Surface
* USB-C a Ethernet y adaptador USB Surface
* Surface Dock
* Estación de acoplamiento para Surface Pro 3
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro (5º gen)
* Surface Pro (5º gen) con LTE avanzado
* Surface Book
* Portátil Surface (1ª generación)
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* Surface Go con LTE Advanced
* Surface Studio 2 (consulte las instrucciones de Surface Studio 2 a continuación)
* Surface Pro 7
* Portátil Surface 3

## Controlador WOL

Para habilitar la compatibilidad con WOL en dispositivos Surface, se requiere un controlador específico para el adaptador Surface Ethernet. Este controlador no se incluye en el paquete de firmware y el controlador estándar para dispositivos Surface: debes descargarlo e instalarlo por separado. Puede descargar el controlador de Surface WOL (SurfaceWOL.msi) desde la página [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft.

Puede ejecutar este archivo de Microsoft Windows Installer (. msi) en un dispositivo Surface para instalar el controlador Surface WOL, o bien puede distribuirlo a dispositivos Surface con una solución de implementación de aplicaciones, como Microsoft Endpoint Configuration Manager. Para incluir el controlador de Surface WOL durante la implementación, puede instalar el archivo. msi como una aplicación durante el proceso de implementación. También puede extraer los archivos de controlador de la superficie de WOL para incluirlos en el proceso de implementación. Por ejemplo, puede incluirlos en el recurso compartido de implementación de Microsoft Deployment Toolkit (MDT). Puede obtener más información sobre la implementación de Surface con MDT en [implementar Windows 10 para Surface Devices con Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).

> [!NOTE]
> Durante la instalación de SurfaceWOL.msi, la siguiente clave del registro se establece en un valor de 1, lo que permite identificar fácilmente los sistemas en los que se ha instalado el controlador WOL. Si decide extraer e instalar estos drivers por separado durante la implementación, esta clave del registro no se configurará y se debe configurar manualmente o con un script.
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

Para extraer el contenido de SurfaceWOL.msi, use la opción de instalación administrativa MSIExec (**/a**), como se muestra en el siguiente ejemplo, para extraer el contenido a la carpeta C:\WOL\:

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Instrucciones para Surface Studio 2

Para habilitar WOL en Surface Studio 2, debe seguir este procedimiento:

1. Cree las siguientes claves de registro:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Ejecute el siguiente comando:

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## Uso de la superficie WOL

El controlador de Surface WOL cumple con las normas de WOL, por lo que el dispositivo es Woken por una comunicación de red especial conocida como un paquete mágico. El paquete mágico consta de 6 bytes de 255 (o FF en hexadecimal), seguidos de 16 repeticiones de la dirección MAC del equipo de destino. Puede obtener más información sobre el paquete mágico y el estándar de WOL en [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).

>[!NOTE]
>Para enviar un paquete mágico y reactivar un dispositivo con WOL, debe conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet. Debido a que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.

Muchas soluciones de administración, como Configuration Manager, proporcionan compatibilidad integrada con WOL. También hay muchas soluciones, entre las que se incluyen aplicaciones de Microsoft Store, módulos de PowerShell, aplicaciones de terceros y soluciones de administración de terceros que permiten enviar un paquete mágico para reactivar un dispositivo. Por ejemplo, puede usar el [módulo Wake on LAN de PowerShell](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) en el centro de scripts de TechNet. 

>[!NOTE]
>Después de que un dispositivo se ha Woken con un paquete mágico, el dispositivo volverá al modo de suspensión si una aplicación no impide activamente la suspensión en el sistema o si la clave del registro AllowSystemRequiredPowerRequests no está configurada en 1, lo que permite a las aplicaciones impedir la suspensión. Consulte la sección del [controlador de WOL](#wol-driver) de este artículo para obtener más información sobre esta clave del registro.

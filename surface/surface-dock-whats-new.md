---
title: Novedades de Surface Dock 2
description: En este artículo, se resaltan las nuevas características y funciones del Dock de Surface de próxima generación.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/25/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 92838599a9d05dbe75f1caad948b97c9cb75bcac
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834289"
---
# Novedades de Surface Dock 2

Surface Dock 2, el Dock de Surface de nueva generación, permite que los usuarios conecten monitores externos y varios periféricos para obtener una experiencia de escritorio completamente modernizada desde un dispositivo Surface. Diseñado para maximizar la eficacia en la oficina, en un espacio de trabajo flexible o en casa, Surface Dock 2 incluye siete puertos, entre los que se incluyen dos puertos USB-C de frontal, con 15 vatios de potencia de carga rápida para teléfonos y accesorios. 

### Compatibilidad con la administración completa de dispositivos

Surface Dock 2 está diseñado para simplificar la administración de ti, lo que permite a los administradores automatizar las actualizaciones de firmware mediante Windows Update o centralizar actualizaciones con herramientas de distribución de software interno.

- El modo Surface de administración empresarial (SEMM) permite a los administradores de ti proteger los puertos en Surface Dock 2. Para obtener más información, consulta [puertos de seguridad de Surface Dock 2 con el modo de administración de empresa de Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999).
-  La compatibilidad con instrumental de administración de Windows (WMI) permite a los administradores de ti supervisar y administrar de forma remota el firmware más reciente, el estado de la Directiva y los datos relacionados en dispositivos de pospuesto 2. Para obtener más información, consulte [administrar Surface Dock 2 con WMI](surface-dock2-wmi.md).

## Requisitos generales del sistema

- Windows 10 versión 1809. No hay soporte técnico para Windows 7, Windows 8 o los dispositivos de host no Surface. Surface Dock 2 funciona con los siguientes dispositivos de superficie:

  - Surface Pro (5º gen)
  - Surface Pro (5º gen) con LTE avanzado
  - Portátil Surface (1ª generación)
  - Surface Pro 6
  - Surface Book 2
  - Surface Laptop 2
  - Surface Go
  - Surface Go con LTE Advanced 
  - Surface Pro 7
  - Portátil Surface 3
  - Surface Book 3
  - Surface Go 2
  - Surface Go 2 con LTE avanzado


## Componentes de Surface docking 2

![Componentes de Surface docking 2](./images/surface-dock2.png)
 
### USB

- Dos puertos USB-C de cara frontal.
- Dos puertos USB-C (Gen 2) con conexión trasera.
- Dos puertos USB a la cara posterior. 

### Vídeo
    
- Dos 4K@60hz. Admite hasta dos pantallas en los siguientes dispositivos:

  - Surface Book 3
  - Surface Go 2
  - Surface Go 2 con LTE avanzado
  - Surface Pro 7
  - Surface Pro X
  - Portátil Surface 3

- 4K@30Hz de dos 4K@. Admite hasta dos pantallas en los siguientes dispositivos:

  - Surface Pro 6
  - Surface Pro (5º gen)
  - Surface Pro (5º gen) con LTE avanzado
  - Surface Laptop 2
  - Portátil Surface (1ª generación)
  - Surface Go
  - Surface Book 2.

### Ethernet

- 1 puerto Gigabit Ethernet. 

### Fuente de alimentación externa

- 199 vatios compatible con 100V-240 v.


## Comparación de Surface Dock 2 

### Tabla 1. Comparación de Surface Dock 2 Especificaciones técnicas

|Componente|Surface Dock|Muelle de superficie 2|
|---|---|---|
|Surflink|Sí|Sí|
|USB-A|2 USB con conexión frontal 3,1 gen 1<br>2 USB 3,1 gen.|2 USB 3,2 gen 2 de cara posterior (7,5 W de potencia)|
|Puerto de mini-Mostrar|2 cara posterior (DP 1.2)|Ninguno|
|USB-C|Ninguno|2 USB con conexión frontal 3,2 gen 2<br>(15W Power)<br>2 USB de cara posterior 3,2 gen 2 (DP 1.4 a)<br>(alimentación de 7,5 w)|
|salida de audio de 3,5 mm|Sí|Sí|
|Ethernet|Sí, 1 Gigabit|Sí 1 Gigabit|
|Encendido de CC|Sí|Sí|
|Bloqueo de Kensington|Sí|Sí|
|Longitud del cable de Surflink|65cm|80cm|
|Surflink de energía de host|60W|120W|
|Energía de carga USB|30W|60W|
|Velocidad de bits USB|5 Gbps|10 Gbps|
|Supervisar la compatibilidad|2 x 4 KB @30fps, o<br>1 x 4k @ 60fps|2 x 4K @ 60fps|
|Wake-on-LAN de Connected Standby <sup> 1</sup>|Sí|Sí|
|Wake-on-LAN de modos de suspensión S4/S5|No|Sí|
|Inicio PXE en red|Sí|Sí|
|Control de acceso de host de SEMM|No|Sí
|Control de acceso a puertos de SEMM <sup> 2</sup>|No|Sí|
|Soporte de mantenimiento|MSI|Windows Update o MSI|
||||

1. *Los dispositivos deben estar configurados para Wake on LAN a través del modo de administración de la empresa (SEMM) o la interfaz de control de firmware (DFCI) del dispositivo para reactivarlos desde el estado de hibernación o de apagado. La activación desde hibernación o apagado es compatible con Surface Pro 7, Surface Laptop 3, Surface Pro X, Surface Book 3 y Surface Go 2.  Se necesita una licencia de software para algunas características. Se vende por separado.*

2. *Se necesita una licencia de software para algunas características. Se vende por separado.*

## Administración de dispositivos simplificada

Surface ha lanzado una funcionalidad de administración simplificada a través de Windows Update, lo que permite a los administradores de ti utilizar las siguientes características empresariales:

- **Actualizaciones**inactivas. Actualice los muelles de forma silenciosa y automática, con Windows Update o Microsoft Endpoint Configuration Manager (anteriormente System Center Configuration Manager-SCCM) u otras herramientas de implementación de MSI. 
- **Reactivar desde la red**. Administre y obtenga acceso a dispositivos corporativos sin depender de los usuarios para mantener sus dispositivos encendidos. Incluso cuando un dispositivo acoplado está en modo de suspensión, hibernación o apagado, su equipo se puede reactivar desde la red para el servicio y la administración, usando el administrador de configuración de extremo u otras herramientas de administración empresarial.
- **Control de ti centralizado**. Controla quién puede conectarte a Surface Dock 2 activando y desactivando los puertos. Restringir los dispositivos de host que se pueden usar con el muelle de superficie 2. Limite el acceso de acoplamiento a un solo usuario o configure los acoplamientos para que solo los usuarios específicos de su equipo o toda la empresa puedan acceder a ellos.

## Pasos siguientes

- [Puertos 2 puertos de superficie segura con el modo de administración de empresa de Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/secure-surface-dock-2-ports-with-surface-enterprise-management/ba-p/1418999)
- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Procedimiento recomendado de configuración de energía para dispositivos Surface](maintain-optimal-power-settings-on-Surface-devices.md)

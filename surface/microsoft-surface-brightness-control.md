---
title: Control de brillo de Surface
description: En este tema se describe cómo usar la aplicación de control de brillo de la superficie para administrar el brillo de la pantalla en los escenarios de punto de venta y quiosco.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835809"
---
# Control de brillo de Surface

Al implementar dispositivos Surface en puntos de venta o en otros escenarios de quiosco "siempre disponible", puede optimizar la administración de energía con la nueva aplicación de control de brillo de la superficie.

Disponible para descargar con [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703).
El control de brillo de la superficie está diseñado para ayudar a reducir la carga térmica y reducir el tamaño total de carbono de los dispositivos de superficie implementados.
Si solo va a obtener esta herramienta de la página de descarga, seleccione el archivo **Surface_Brightness_Control_v1.16.137.0.msi** en la lista disponibles.
La herramienta atenúa automáticamente la pantalla cuando no está en uso e incluye las siguientes opciones de configuración:

- Período de inactividad antes de atenuar la pantalla.

- Nivel de brillo cuando está atenuado.

- Nivel de brillo máximo cuando está en uso.

**Para ejecutar el control de brillo de la superficie:**

- Instale surfacebrightnesscontrol.msi en el dispositivo de destino y el control de brillo de la superficie comenzará a funcionar inmediatamente.

## Configuración de control de brillo de superficie

Puede ajustar los valores predeterminados a través del registro de Windows. Para obtener más información sobre cómo usar el registro de Windows, consulte la [documentación del registro](https://docs.microsoft.com/windows/desktop/sysinfo/registry).

1.  Ejecute regedit desde un símbolo del sistema para abrir el editor del registro de Windows.
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface control de brillo \ 
    
    Si está ejecutando una versión anterior de control de brillo de superficie, ejecute el siguiente comando:
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface control de brillo \


| Configuración del registro | Datos| Descripción  
|-----------|------------|---------------
| Control de brillo habilitado  |  Valor predeterminado: 01  <br> Opción: 01, 00 <br> Escriba: REG_BINARY |  Esta configuración le permite activar o desactivar el control de brillo de la superficie. Para deshabilitar el control de brillo de la superficie, establezca el valor en 00. Si no establece esta configuración, el control de brillo de la superficie está activado. |
| Control de brillo en la energía habilitada| Valor predeterminado: 01 <br> Opciones: 01, 00 <br> Escriba: REG_BINARY | Esta configuración te permite desactivar el control del brillo de la superficie cuando el dispositivo está directamente conectado a la alimentación. Para deshabilitar el control del brillo de la superficie cuando se conecta la alimentación, establezca el valor en 00. Si no establece esta configuración, el control de brillo de la superficie está activado. |
| Brillo atenuado   | Valor predeterminado: 20  <br>Opción: intervalo del 0-100 por ciento del brillo de la pantalla <br> Tipo de datos: entero positivo <br> Escriba: REG_DWORD | Esta configuración le permite administrar el rango de brillo durante períodos de inactividad. Si no establece esta configuración, el nivel de brillo pasará al 20 por ciento del brillo completo después de 30 segundos de inactividad. |
Brillo completo   | Valor predeterminado: 100  <br>Opción: intervalo del 0-100 por ciento del brillo de la pantalla <br> Tipo de datos: entero positivo <br> Escriba: REG_DWORD  | Esta configuración le permite administrar el intervalo máximo de brillo para el dispositivo. Si no establece esta configuración, el intervalo de brillo máximo es 100 por ciento.|  
| Tiempo de espera de inactividad| Valor predeterminado: 30 segundos <br>Opción: cualquier valor numérico  <br>Tipo de datos: entero  <br> Escriba: REG_DWORD | Esta configuración te permite administrar el período de inactividad antes de atenuar el dispositivo. Si no establece esta configuración, el tiempo de espera de inactividad es de 30 segundos.|
| Telemetría habilitada | Valor predeterminado: 01 <br>Opción: 01, 00 <br> Escriba: REG_BINARY  | Esta configuración le permite administrar el uso compartido de la información de uso de aplicaciones para mejorar el software y proporcionar una mejor experiencia de usuario. Para deshabilitar la telemetría, establece el valor en 00. Si no establece esta configuración, la información de telemetría se comparte con Microsoft de acuerdo con la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). |

## Cambios y actualizaciones

### Versión 1.16.137<br>
*Fecha de lanzamiento: 22 de octubre de 2019*<br>
Esta versión del control de brillo de la superficie agrega compatibilidad con los siguientes elementos:-recompiled para x86, agrega compatibilidad para Surface Pro 7, Surface Pro X y Surface Laptop 3. 

### Versión 1.12.239.0
*Fecha de lanzamiento: 26 de abril de 2019*<br>
Esta versión del control de brillo de la superficie agrega compatibilidad con los siguientes elementos:
- Correcciones de retraso de la entrada táctil.


## Temas relacionados

- [Configuración del límite de batería](battery-limit.md)

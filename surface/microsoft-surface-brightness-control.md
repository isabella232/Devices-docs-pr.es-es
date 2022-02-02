---
title: Control de brillo de Surface
description: En este tema se describe cómo puedes usar la aplicación Control de brillo de Surface para administrar el brillo de la pantalla en escenarios de punto de venta y quiosco.
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
ms.openlocfilehash: 660a96a8825002c6d52d067dac77894bb0c0b7a9
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337833"
---
# <a name="surface-brightness-control"></a>Control de brillo de Surface

Al implementar dispositivos Surface en punto de venta u otros escenarios de quiosco de pantalla completa "siempre activos", puedes optimizar la administración de energía con la aplicación Control de brillo de Surface. El control de brillo de Surface está diseñado para ayudar a reducir la carga térmica y reducir la superficie de carbono general de los dispositivos Surface implementados. La herramienta atenua automáticamente la pantalla cuando no está en uso e incluye las siguientes opciones de configuración:

- Período de inactividad antes de atenuar la pantalla.
- Nivel de brillo cuando está atenuado.
- Nivel de brillo máximo cuando se usa.

Descarga Surface Brightness Control de [Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703). Seleccione el archivo **Surface_Brightness_Control_v1.16.137.0.msi** en la lista disponible.

## <a name="supported-devices"></a>Dispositivos compatibles

- Surface Pro 3 y posteriores
- Surface Pro X (todas las generaciones)
- Surface 3
- Surface Book (todas las generaciones)
- Surface Laptop Studio
- Surface Studio (todas las generaciones)
- Surface Laptop (todas las generaciones)
- Surface Laptop Go
- Surface Go (todas las generaciones)


## <a name="run-surface-brightness-control"></a>Ejecutar control de brillo de Surface

- Instala **Surface_Brightness_Control_v1.16.137.0.msi** en el dispositivo de destino y el control de brillo de Surface empezará a funcionar inmediatamente.

## <a name="configure-surface-brightness-control"></a>Configurar el control de brillo de Surface

Puede ajustar los valores predeterminados a través del Windows registro. Para obtener más información acerca del uso del Windows, consulte la [documentación del Registro](/windows/desktop/sysinfo/registry).

1. Ejecute **regedit** desde un símbolo del sistema para abrir Windows Editor del Registro.
2. Vaya a Pc\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control.
3. Ajuste los valores de clave del Registro, como se describe en la tabla siguiente.

> [!TIP]
> Si estás ejecutando una versión anterior del control de brillo de Surface, ve a: Pc\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\SurfaceBrightnessControl\

| Configuración del Registro | Datos| Descripción  
|-----------|------------|---------------
| BrightnessControlEnabled  |  Valor predeterminado: 01  <br> Opción: 01,00 <br> Tipo: REG_BINARY |  Esta configuración te permite activar o desactivar el Control de brillo de Surface. Para deshabilitar El control de brillo de Surface, establece el valor en 00. Si no configuras esta configuración, el Control de brillo de Surface está en. |
| BrightnessControlOnPowerEnabled| Valor predeterminado: 01 <br> Opciones: 01,00 <br> Tipo: REG_BINARY | Esta configuración te permite desactivar el Control de brillo de Surface cuando el dispositivo está conectado directamente a la alimentación. Para deshabilitar El control de brillo de Surface cuando la energía está conectada, establece el valor en 00. Si no configuras esta configuración, el Control de brillo de Surface está en. |
| DimmedBrightness   | Valor predeterminado: 20  <br>Opción: Intervalo de 0-100 por ciento del brillo de la pantalla <br> Tipo de datos: entero positivo <br> Tipo: REG_DWORD | Esta configuración permite administrar el intervalo de brillo durante períodos de inactividad. Si no configura esta configuración, el nivel de brillo bajará al 20 por ciento del brillo completo después de 30 segundos de inactividad. |
FullBrightness   | Valor predeterminado: 100  <br>Opción: Intervalo de 0-100 por ciento del brillo de la pantalla <br> Tipo de datos: entero positivo <br> Tipo: REG_DWORD  | Esta configuración te permite administrar el intervalo de brillo máximo para el dispositivo. Si no configura esta configuración, el intervalo de brillo máximo es del 100 por ciento.|  
| InactivityTimeout| Valor predeterminado: 30 segundos <br>Opción: cualquier valor numérico  <br>Tipo de datos: Integer  <br> Tipo: REG_DWORD | Esta configuración te permite administrar el período de inactividad antes de atenuar el dispositivo. Si no configura esta configuración, el tiempo de espera de inactividad es de 30 segundos.|
| TelemetryEnabled | Valor predeterminado: 01 <br>Opción: 01,00 <br> Tipo: REG_BINARY  | Esta configuración te permite administrar el uso compartido de la información de uso de la aplicación para mejorar el software y proporcionar una mejor experiencia de usuario. Para deshabilitar la telemetría, establezca el valor en 00. Si no configura esta configuración, la información de telemetría se comparte con Microsoft según la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). |

## <a name="changes-and-updates"></a>Cambios y actualizaciones

### <a name="version-116137br"></a>Versión 1.16.137<br>

*Fecha de lanzamiento: 22 de octubre de 2019*<br>
Esta versión de Surface Brightness Control agrega compatibilidad con lo siguiente: -Recompiled for x86, adding support for Surface Pro 7, Surface Pro X y Surface Laptop 3.

### <a name="version-1122390"></a>Versión 1.12.239.0

*Fecha de lanzamiento: 26 de abril de 2019*<br>
Esta versión del control de brillo de Surface agrega compatibilidad con lo siguiente:

- Correcciones de retraso táctil.

## <a name="related-topics"></a>Temas relacionados

- [Configuración del límite de batería](battery-limit.md)

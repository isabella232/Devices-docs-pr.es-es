---
title: Actualización de firmware de Microsoft Surface Dock 1
description: En este artículo se explica cómo usar La actualización de firmware de Microsoft Surface Dock para instalar y administrar el firmware en surface dock 1 original. Cuando se instale en el dispositivo Surface, se actualizarán los dispositivos Surface Dock 1 conectados a tu dispositivo Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 10/25/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 8d714ad9e7d301b4691655faaf9e39b0f4147301
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449383"
---
# <a name="surface-dock-1-firmware-update"></a>Actualización de firmware de Surface Dock 1

En este artículo se explica cómo usar La actualización de firmware de Microsoft Surface Dock 1 para instalar y administrar el firmware en surface dock 1 original. Cuando se instale en el dispositivo Surface, se actualizarán los dispositivos Surface Dock 1 conectados a tu dispositivo Surface.

> [!NOTE]
> Este artículo no se aplica a [Surface Dock 2](surface-dock-whats-new.md), que recibe actualizaciones automáticamente a través de Windows Update o mediante Microsoft Endpoint Configuration Manager u otras herramientas de implementación de MSI.

Esta herramienta reemplaza a la anterior herramienta Microsoft Surface Dock Updater, que anteriormente estaba disponible para su descarga como parte de Surface Tools para TI. La herramienta anterior se denominaba Surface_Dock_Updater_vx.xx.xxx.x.msi (donde x indica el número de versión) y ya no está disponible para su descarga y no debe usarse.

> [!IMPORTANT]
> Este artículo contiene instrucciones técnicas para los administradores de TI. Si eres usuario principal, consulta Cómo actualizar el [firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)  de Surface Dock en el sitio de soporte técnico de Microsoft. Las instrucciones del sitio de soporte técnico son las mismas que las siguientes, pero este artículo tiene información adicional para supervisar, comprobar e implementar la actualización en varios dispositivos de una red.

## <a name="supported-devices"></a>Dispositivos compatibles

La actualización de firmware de Surface Dock 1 se admite en los siguientes dispositivos:

- Surface Pro 3 y posteriores
- Surface Pro X (todas las generaciones)
- Surface 3
- Surface Book (todas las generaciones)
- SurfaceLaptopStudio
- Surface Studio (todas las generaciones)
- Surface Laptop (todas las generaciones)
- Surface Laptop Go
- Surface Go (todas las generaciones)

### <a name="minimum-os-requirement"></a>Requisito mínimo del sistema operativo

- Windows 10 versión 1803 o posterior

## <a name="install-surface-dock-1-firmware-update"></a>Instalar la actualización de firmware de Surface Dock 1

En esta sección se describe cómo instalar manualmente la actualización de firmware en Surface Dock 1.

> [!TIP]
> Microsoft publica periódicamente nuevas versiones de actualización de firmware de Surface Dock 1. El archivo MSI no se actualiza automáticamente. Si has implementado msi en dispositivos Surface y se libera una nueva versión del firmware, deberás implementar la nueva versión.

1. Ve a [Herramientas de Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI y descarga e instala el archivo .msi denominado **Surface_Dock_FwUpdate..**, seguido de la versión adecuada. Si está ejecutando Surface Pro X, descargue la **compilación .arm64**. Para el resto de dispositivos, use **la compilación .amd64** .  

    - La actualización requiere un dispositivo Surface que se Windows 10, versión 1803 o posterior.
    - La instalación del archivo MSI puede pedirte que reinicies Surface. Sin embargo, no es necesario reiniciar para realizar la actualización.

2. Desconecta el dispositivo Surface de Surface Dock, espera unos 5 segundos y, a continuación, vuelve a conectarlo. La actualización de firmware de Surface Dock 1 actualizará la base silenciosamente en segundo plano. El proceso puede tardar unos minutos en completarse y continuará incluso si se interrumpe.

## <a name="monitor-the-surface-dock-1-firmware-update"></a>Supervisar la actualización de firmware de Surface Dock 1

Esta sección es opcional y proporciona información general sobre cómo supervisar la instalación de la actualización de firmware.

Para supervisar la actualización:

1. Abra el Visor de eventos, vaya **a Windows Logs > Application y, a** continuación, en Acciones **** en el panel derecho, haga clic en **Filtrar** registro actual, escriba **SurfaceDockFwUpdate** junto a Orígenes de eventos **y,** a continuación, haga clic en **Aceptar**.

2. Escriba el siguiente comando en un símbolo del sistema con privilegios elevados:

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```

3. Instale la actualización tal como se describe en [la siguiente sección](#install-surface-dock-1-firmware-update) de este artículo.

4. El evento 2007 con el siguiente texto indica una actualización correcta: La actualización de firmware ha finalizado **. hr=0 DriverTelementry EventCode = 2007**.

   Si la actualización no se realiza correctamente, el identificador de evento 2007 se mostrará como **un evento Error** en lugar de **Como información**. Además, la versión notificada en el registro Windows no será actual.

5. Una vez completada la actualización, los valores DWORD actualizados se mostrarán en el registro de Windows, correspondiente a la versión actual de la herramienta. Vea la [sección Referencia de](#versions-reference) versiones de este artículo para obtener más información. Por ejemplo:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Si ves "No se puede encontrar la descripción del identificador de evento xxxx del origen SurfaceDockFwUpdate" en el texto del evento, se espera y se puede omitir.

Vea también las siguientes secciones de este artículo:

- [Cómo comprobar la finalización de la actualización de firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Registro de eventos](#event-logging)
  - [Recomendaciones para la solución de problemas](#troubleshooting-tips)
  - [Referencia de versiones](#versions-reference)

## <a name="network-deployment"></a>Implementación de red

Puedes usar los Windows Installer (Msiexec.exe) para implementar la actualización de firmware de Surface Dock 1 en varios dispositivos de la red. Al usar Microsoft Endpoint Configuration Manager u otra herramienta de implementación, escriba la siguiente sintaxis para asegurarse de que la instalación es silenciosa:

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart**

Por ejemplo:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> Un archivo de registro no se crea de forma predeterminada. Para crear un archivo de registro, deberá anexar "/*lv [ruta]". Por ejemplo: Msiexec.exe /i /lv \<path to msi file\>*%windir%\logs\ SurfaceDockFWI.log"

Para obtener más información, consulte [la documentación sobre opciones de línea de](/windows/win32/msi/command-line-options) comandos.

> [!IMPORTANT]
> Si quieres mantener tu Surface Dock actualizado con cualquier otro método, consulta [Actualizar Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obtener más información.

## <a name="intune-deployment"></a>Implementación de Intune

Puedes usar Intune para distribuir la actualización de firmware de Surface Dock 1 a tus dispositivos. Primero tendrá que convertir el archivo MSI al formato .intunewin, tal como se describe en la siguiente documentación: [Intune Standalone - Administración de aplicaciones de Win32](/intune/apps/apps-win32-app-management).

Use el siguiente comando:

- **msiexec /i \<path to msi file\> /quiet /q**

## <a name="how-to-verify-completion-of-the-firmware-update"></a>Cómo comprobar la finalización de la actualización de firmware

El firmware de Surface Dock consta de dos componentes:

- **Componente10:** Firmware de unidad de controlador micro (MCU)
- **Componente20:** Firmware de puerto para mostrar (DP).

La finalización correcta de la actualización de firmware de Surface Dock 1 da como resultado nuevos valores de clave del Registro para estos componentes de firmware.

### <a name="to-verify-updates"></a>Para comprobar actualizaciones

1. Abra Regedit y navegue a la siguiente ruta de acceso del Registro:

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Busque las claves del Registro: **Component10CurrentFwVersion y Component20CurrentFwVersion**, que hacen referencia al firmware que está actualmente en el dispositivo.

   ![Proceso de instalación de actualización de firmware de Surface Dock 1.](images/regeditDock.png)

3. Compruebe que los nuevos valores de clave del Registro coincidan con los valores de clave del Registro actualizados que aparecen en la referencia Versiones al final de este documento. Si los valores coinciden, el firmware se actualizó correctamente.

4. Si no se puede comprobar, revise El registro de eventos y las sugerencias de solución de problemas en la sección siguiente.

## <a name="event-logging"></a>Registro de eventos

### <a name="table-1-log-files-for-surface-dock-1-firmware-update"></a>Tabla 1. Archivos de registro para la actualización de firmware de Surface Dock 1

| Log                              | Ubicación                               | Notas                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Registro de actualización de firmware de Surface Dock 1 | Se debe especificar la ruta de acceso (vea la nota) | Las versiones anteriores de esta herramienta escribieron eventos en Registros de aplicaciones y servicios\Microsoft Surface Dock Updater.                                                                                                  |
| Windows de instalación de dispositivos       | %windir%\inf\setupapi.dev.log           | Para obtener más información acerca del uso del registro de instalación de dispositivos, consulte [la documentación del registro setupAPI](/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) . |

### <a name="table-2-event-log-ids-for-surface-dock-1-firmware-update"></a>Tabla 2. IDs de registro de eventos para la actualización de firmware de Surface Dock 1

Los eventos se registran en el registro de eventos de la aplicación.  Nota: Las versiones anteriores de esta herramienta escribieron eventos en Registros de aplicaciones y servicios\Microsoft Surface Dock Updater.

| Id. de evento | Tipo de evento                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Se ha iniciado la actualización de firmware de acoplamiento.                                    |
| 2002     | Se omitió la actualización de firmware de dock porque se sabe que dock está actualizado. |
| 2003     | No se pudo obtener la versión de firmware de la actualización de firmware de acoplamiento.                 |
| 2004     | Consulta de la versión de firmware.                                       |
| 2005     | No se pudo iniciar la actualización del firmware de acoplamiento.                                |
| 2006     | Error al enviar pares de oferta y carga.                                  |
| 2007     | La actualización de firmware ha finalizado.                                            |
| 2008     | Telemetría de acoplamiento BEGIN.                                                |
| 2011     | Telemetría de acoplamiento END.                                                  |

## <a name="troubleshooting-tips"></a>Recomendaciones para la solución de problemas

- Desconecta completamente la alimentación de Surface Dock de la alimentación de CA para restablecer Surface Dock.
- Desconecta todos los periféricos excepto Surface Dock.
- Desinstala cualquier actualización de firmware de Surface Dock 1 actual e instala la versión más reciente.
- Asegúrate de que Surface Dock esté desconectado y, a continuación, de permitir el tiempo suficiente para que la actualización se complete como se supervisa a través de un LED en el puerto Ethernet de la base de datos. Espere hasta que el LED deje de parpadear antes de desconectar Surface Dock de la alimentación.
- Conectar Surface Dock a otro dispositivo para ver si es capaz de actualizar la base de datos.

## <a name="versions-reference"></a>Referencia de versiones

>[!NOTE]
>El archivo de instalación se libera con el siguiente formato de nomenclatura: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por ejemplo, Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e instala de forma predeterminada en C:\Archivos de programa\SurfaceUpdate.

### <a name="version-1531390"></a>Versión 1.53.139.0

#### <a name="release-date-august-4-2020"></a>Fecha de lanzamiento: 4 de agosto de 2020

Esta versión de la actualización de firmware de Surface Dock 1 incluye correcciones de errores y compatibilidad con:

- Actualizar Surface Dock 1 con Surface Pro X.

#### <a name="registry-key-values"></a>Valores de clave del Registro

Los valores del Registro que indican el estado de las actualizaciones de firmware no se modifican con respecto a la versión anterior de esta herramienta:

- Component10CurrentFwVersion actualizado a **4ac3970**.
- Component20CurrentFwVersion actualizado a **4a1d570**.

### <a name="version-142139"></a>Versión 1.42.139

#### <a name="release-date-september-18-2019"></a>Fecha de lanzamiento: 18 de septiembre de 2019

Esta versión, incluida en Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, actualiza el firmware en segundo plano.

#### <a name="updated-registry-key-values"></a>Valores de clave del Registro actualizados

- Component10CurrentFwVersion actualizado a **4ac3970**.
- Component20CurrentFwVersion actualizado a **4a1d570**.

Agrega compatibilidad con Surface Pro 7 y Surface Laptop 3.

## <a name="legacy-versions"></a>Versiones heredadas

### <a name="version-2231390"></a>Versión 2.23.139.0

#### <a name="release-date-10-october-2018"></a>Fecha de lanzamiento: 10 de octubre de 2018

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Agregar compatibilidad con Surface Pro 6
- Agregar compatibilidad con Surface Laptop 2

### <a name="version-2221390"></a>Versión 2.22.139.0

#### <a name="release-date-26-july-2018"></a>Fecha de lanzamiento: 26 de julio de 2018

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Aumentar la confiabilidad de las actualizaciones
- Agregar compatibilidad con Surface Go

### <a name="version-2121360"></a>Versión 2.12.136.0

#### <a name="release-date-29-january-2018"></a>Fecha de lanzamiento: 29 de enero de 2018

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Actualización de firmware del conjunto de chips principal de Surface Dock

- Actualización de firmware de DisplayPort de Surface Dock

- Se ha mejorado la estabilidad de la pantalla para las pantallas externas cuando se usa con Surface Book o Surface Book 2

Además, en la instalación de esta versión de Surface Dock Updater en dispositivos Surface Book se incluye lo siguiente:

- Actualización de firmware de la base de Surface Book

- Se ha agregado soporte para las actualizaciones de firmware de Surface Dock con mejoras destinadas a dispositivos de Surface Book

### <a name="version-291360"></a>Versión 2.9.136.0

#### <a name="release-date-november-3-2017"></a>Fecha de lanzamiento: 3 de noviembre de 2017

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Actualización de firmware de DisplayPort de Surface Dock

- Resuelve un problema con el audio en adaptadores de puerto de pantalla pasivos

### <a name="version-21150"></a>Versión 2.1.15.0

#### <a name="release-date-june-19-2017"></a>Fecha de lanzamiento: 19 de junio de 2017

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Surface Laptop

- Surface Pro

### <a name="version-2160"></a>Versión 2.1.6.0

#### <a name="release-date-april-7-2017"></a>Fecha de lanzamiento: 7 de abril de 2017

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Actualización de firmware de DisplayPort de Surface Dock

- Requiere Windows 10

### <a name="version-20220"></a>Versión 2.0.22.0

#### <a name="release-date-october-21-2016"></a>Fecha de lanzamiento: 21 de octubre de 2016

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Actualización de firmware de USB de Surface Dock

- Fiabilidad mejorada de los puertos de audio, USB y Ethernet

### <a name="version-1080"></a>Versión 1.0.8.0

#### <a name="release-date-april-26-2016"></a>Fecha de lanzamiento: 26 de abril de 2016

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Actualización de firmware del conjunto de chips principal de Surface Dock

- Actualización de firmware de DisplayPort de Surface Dock

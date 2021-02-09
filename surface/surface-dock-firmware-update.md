---
title: Actualización de firmware de Microsoft Surface Dock 1
description: En este artículo se explica cómo usar Microsoft Surface Dock Firmware Update para instalar y administrar el firmware en Surface Dock 1 original. Cuando se instale en el dispositivo Surface, actualizará los dispositivos Surface Dock 1 conectados al dispositivo Surface.
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319214"
---
# Actualización de firmware de Microsoft Surface Dock

> [!IMPORTANT]
> Este artículo contiene instrucciones técnicas para los administradores de TI. Si eres un usuario principal, consulta Cómo actualizar el firmware de [Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)en el sitio de soporte técnico de   Microsoft. Las instrucciones del sitio de soporte técnico son las mismas que las que se indican a continuación, pero este artículo contiene información adicional para supervisar, comprobar e implementar la actualización en varios dispositivos de una red.

En este artículo se explica cómo usar Microsoft Surface Dock Firmware Update para instalar y administrar el firmware en Surface Dock 1 original. Cuando se instale en el dispositivo Surface, actualizará los dispositivos Surface Dock 1 conectados al dispositivo Surface.

> [!NOTE]
> Este artículo no se aplica a Surface Dock 2, que recibe actualizaciones automáticamente a través de Windows Update o mediante Microsoft Endpoint Configuration Manager u otras herramientas de implementación de MSI. Para obtener más información, consulta [Novedades de Surface Dock.](surface-dock-whats-new.md)

Esta herramienta reemplaza a la anterior herramienta Microsoft Surface Dock Updater, que anteriormente estaba disponible para su descarga como parte de Surface Tools para TI. La herramienta anterior se llamaba Surface_Dock_Updater_vx.xx.xxx.x.msi (donde x indica el número de versión) y ya no está disponible para su descarga y no debe usarse.

## Instalar la actualización de firmware de Surface Dock

En esta sección se describe cómo instalar manualmente la actualización de firmware.

> [!NOTE]
> Microsoft publica periódicamente nuevas versiones de La actualización de firmware de Surface Dock. El archivo MSI no se actualiza automáticamente. Si has implementado msi en dispositivos Surface y se lanza una nueva versión del firmware, deberás implementar la nueva versión.

1. Descargar e instalar [la actualización de firmware de Microsoft Surface Dock.](https://www.microsoft.com/download/details.aspx?id=46703)
    - La actualización requiere un dispositivo Surface que ejecute Windows 10, versión 1803 o posterior.
    - Instalar el archivo MSI puede solicitarte que reinicies Surface. Sin embargo, no es necesario reiniciar para realizar la actualización.

2. Desconecta el dispositivo Surface de Surface Dock, espera ~5 segundos y vuelve a conectarte. La actualización de firmware de Surface Dock actualizará la base de datos silenciosamente en segundo plano. El proceso puede tardar unos minutos en completarse y continuará incluso si se interrumpe. 

## Supervisar la actualización de firmware de Surface Dock

Esta sección es opcional y proporciona información general sobre cómo supervisar la instalación de la actualización de firmware. 

Para supervisar la actualización:

1. Abra el Visor de eventos, vaya a Registros **** de Windows > Aplicación y, a continuación, en **** Acciones en el panel derecho, haga clic en Filtrar registro actual **,** escriba **SurfaceDockFwUpdate junto** a Orígenes de eventos y, **a**continuación, haga clic en **Aceptar.**

2. Escriba el siguiente comando en un símbolo del sistema con privilegios elevados:

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Instale la actualización tal como se describe en [la siguiente sección](#install-the-surface-dock-firmware-update) de este artículo.

4. Evento 2007 con el siguiente texto indica una actualización correcta: La actualización de **firmware finalizó. hr=0 DriverTelementry EventCode = 2007**. 

   Si la actualización no se realiza correctamente, el identificador de evento 2007 se mostrará como un **evento Error** en lugar de **Como información.** Además, la versión notificada en el Registro de Windows no será actual.
   
5. Una vez completada la actualización, los valores DWORD actualizados se mostrarán en el Registro de Windows, correspondiente a la versión actual de la herramienta. Vea la [sección de referencia](#versions-reference) de versiones de este artículo para obtener más información. Por ejemplo:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Si ves "No se puede encontrar la descripción del identificador de evento xxxx del surfaceDockFwUpdate de origen" en el texto del evento, esto se espera y se puede omitir.

Vea también las siguientes secciones de este artículo: 
  - [Cómo comprobar la finalización de la actualización de firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Registro de eventos](#event-logging)
  - [Recomendaciones para la solución de problemas](#troubleshooting-tips)
  - [Referencia de versiones](#versions-reference)

## Implementación de red

Puedes usar comandos de Windows Installer (Msiexec.exe) para implementar La actualización de firmware de Surface Dock en varios dispositivos de la red. Cuando use Microsoft Endpoint Configuration Manager u otra herramienta de implementación, escriba la siguiente sintaxis para asegurarse de que la instalación sea silenciosa:

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart** 

Por ejemplo:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> Un archivo de registro no se crea de forma predeterminada. Para crear un archivo de registro, deberá anexar "/l*v [ruta de acceso]". Por ejemplo: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"

Para obtener más información, consulte la [documentación de opciones de la línea de](https://docs.microsoft.com/windows/win32/msi/command-line-options) comandos.

> [!IMPORTANT]
> Si quieres mantener Surface Dock actualizado con cualquier otro método, consulta [Actualizar Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obtener más información.

## Implementación de Intune

Puedes usar Intune para distribuir la actualización de firmware de Surface Dock a los dispositivos. Primero tendrá que convertir el archivo MSI al formato .intunewin, como se describe en la siguiente documentación: Intune independiente - Administración de [aplicaciones de Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).

Use el siguiente comando:
  - **msiexec /i \<path to msi file\> /quiet /q**

## Cómo comprobar la finalización de la actualización de firmware

El firmware de Surface Dock consta de dos componentes:

- **Componente 10:** Firmware de la unidad de controladora micro (MCU)
- **Componente 20:** Firmware de puerto de visualización (DP).

La finalización correcta de la actualización de firmware de Surface Dock da como resultado nuevos valores de clave del Registro para estos componentes de firmware.

**Para comprobar las actualizaciones:**

1. Abra Regedit y vaya a la siguiente ruta de acceso del Registro:

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Busque las claves del Registro: **Component10CurrentFwVersion y Component20CurrentFwVersion**, que hacen referencia al firmware que se encuentra actualmente en el dispositivo.

   ![Proceso de instalación de actualización de firmware de Surface Dock](images/regeditDock.png)

3. Compruebe que los nuevos valores de clave del Registro coincidan con los valores de clave del Registro actualizados que aparecen en la referencia de versiones al final de este documento. Si los valores coinciden, el firmware se actualizó correctamente.

4. Si no se puede comprobar, revise el registro de eventos y las sugerencias para la solución de problemas en la siguiente sección.

## Registro de eventos

**Tabla 1. Archivos de registro para la actualización de firmware de Surface Dock**

| Log                              | Ubicación                               | Notas                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Registro de actualización de firmware de Surface Dock | Debe especificarse la ruta de acceso (vea la nota) | Las versiones anteriores de esta herramienta escribieron eventos en registros de aplicaciones y servicios\Microsoft Surface Dock Updater.                                                                                                  |
| Registro de instalación de dispositivos Windows       | %windir%\inf\setupapi.dev.log           | Para obtener más información acerca del uso del registro de instalación de dispositivos, consulte la documentación de registro [de SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) |


**Tabla 2. IDs del registro de eventos para la actualización de firmware de Surface Dock**<br>
Los eventos se registran en el registro de eventos de la aplicación.  Nota: Las versiones anteriores de esta herramienta escribieron eventos en registros de aplicaciones y servicios\Microsoft Surface Dock Updater.

| Id. de evento | Tipo de evento                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Se ha iniciado la actualización de firmware de dock.                                    |
| 2002     | Se omitió la actualización de firmware de dock porque se sabe que dock está actualizado. |
| 2003     | No se pudo obtener la versión de firmware de la actualización de firmware de dock.                 |
| 2004     | Consulta de la versión del firmware.                                       |
| 2005     | El firmware de dock no pudo iniciar la actualización.                                |
| 2006     | No se pudieron enviar pares de oferta/carga útil.                                  |
| 2007     | La actualización de firmware finalizó.                                            |
| 2008     | Telemetría de dock BEGIN.                                                |
| 2011     | Telemetría de acoplamiento final.                                                  |

## Recomendaciones para la solución de problemas

- Desconecta completamente la alimentación de Surface Dock de la corriente alterna para restablecer Surface Dock.
- Desconecta todos los periféricos excepto Surface Dock.
- Desinstala cualquier actualización de firmware actual de Surface Dock y, a continuación, instala la versión más reciente.
- Asegúrate de que Surface Dock esté desconectado y, a continuación, deja tiempo suficiente para que la actualización se complete como se supervisa a través de un LED en el puerto Ethernet de la base de datos. Espera hasta que el LED deje de parpadear antes de desconectar Surface Dock de la alimentación.
- Conecta Surface Dock a un dispositivo diferente para ver si es capaz de actualizar la base dock.

## Referencia de versiones

>[!NOTE]
>El archivo de instalación se publica con el siguiente formato de nomenclatura: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por ejemplo, Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) y se instala de forma predeterminada en C:\Archivos de programa\SurfaceUpdate.

### Versión 1.53.139.0
*Fecha de lanzamiento: 4 de agosto de 2020*

Esta versión de la actualización de firmware de Surface Dock incluye correcciones de errores y compatibilidad con:
- Actualizar Surface Dock 1 con Surface Pro X. 
   > [!NOTE]
   > Si estás ejecutando Surface Pro X, descarga el archivo . Compilación arm64. Para todos los demás dispositivos, usa la compilación AMD64. 

#### Valores de clave del Registro

Los valores del Registro que indican el estado de las actualizaciones de firmware no han cambiado con respecto a la versión anterior de esta herramienta: 

- Component10CurrentFwVersion actualizado a **4ac3970**.
- Component20CurrentFwVersion actualizado a **4a1d570**.
 
### Versión 1.42.139 
*Fecha de lanzamiento: 18 de septiembre de 2019*

Esta versión, incluida en Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, actualiza el firmware en segundo plano. 

#### Valores de clave del Registro actualizados

- Component10CurrentFwVersion actualizado a **4ac3970**.
- Component20CurrentFwVersion actualizado a **4a1d570**.

Agrega compatibilidad con Surface Pro 7 y Surface Laptop 3.

## Versiones heredadas

### Versión 2.23.139.0
*Fecha de lanzamiento: 10 de octubre de 2018*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Agregar compatibilidad con Surface Pro 6
- Agregar compatibilidad con Surface Laptop 2


### Versión 2.22.139.0
*Fecha de lanzamiento: 26 de julio de 2018*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Aumentar la confiabilidad de las actualizaciones
- Agregar compatibilidad con Surface Go

### Versión 2.12.136.0
*Fecha de lanzamiento: 29 de enero de 2018*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:
* Actualización de firmware del conjunto de chips principal de Surface Dock
* Actualización de firmware de DisplayPort de Surface Dock
* Se ha mejorado la estabilidad de la pantalla para las pantallas externas cuando se usa con Surface Book o Surface Book 2

Además, en la instalación de esta versión de Surface Dock Updater en dispositivos Surface Book se incluye lo siguiente:
* Actualización de firmware de la base de Surface Book
* Se ha agregado soporte para las actualizaciones de firmware de Surface Dock con mejoras destinadas a dispositivos de Surface Book


### Versión 2.9.136.0
*Fecha de lanzamiento: 3 de noviembre de 2017*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

* Actualización de firmware de DisplayPort de Surface Dock
* Resuelve un problema con el audio en adaptadores de puerto de pantalla pasivos

### Versión 2.1.15.0
*Fecha de lanzamiento: 19 de junio de 2017*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

* Surface Laptop
* Surface Pro

### Versión 2.1.6.0
*Fecha de lanzamiento: 7 de abril de 2017*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

* Actualización de firmware de DisplayPort de Surface Dock
* Requiere Windows 10

### Versión 2.0.22.0
*Fecha de lanzamiento: 21 de octubre de 2016*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

* Actualización de firmware de USB de Surface Dock
* Fiabilidad mejorada de los puertos de audio, USB y Ethernet

### Versión 1.0.8.0
*Fecha de lanzamiento: 26 de abril de 2016*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

* Actualización de firmware del conjunto de chips principal de Surface Dock
* Actualización de firmware de DisplayPort de Surface Dock


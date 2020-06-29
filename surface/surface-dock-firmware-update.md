---
title: 'Actualización del firmware Microsoft Surface Dock: información técnica para administradores de ti'
description: En este artículo se explica cómo usar la actualización de firmware Microsoft Surface Dock para actualizar el firmware de Surface Docking. Cuando se instale en tu dispositivo Surface, se actualizará cualquier muelle de superficie conectado al dispositivo Surface.
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
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834633"
---
# Actualización del firmware Microsoft Surface Dock: información técnica para administradores de ti

> [!IMPORTANT]
> Este artículo contiene instrucciones técnicas para los administradores de ti. Si es un usuario doméstico, consulte [Cómo actualizar el firmware de Surface docking](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   en el sitio de soporte técnico de Microsoft. Las instrucciones del sitio de asistencia son las mismas que se describen a continuación, pero en este artículo encontrará información adicional para supervisar, comprobar e implementar la actualización en varios dispositivos en una red.

En este artículo se explica cómo usar la actualización de firmware Microsoft Surface Dock para actualizar el firmware de Surface Docking. Cuando se instale en tu dispositivo Surface, se actualizará cualquier muelle de superficie conectado al dispositivo Surface. 

Esta herramienta reemplaza la herramienta anterior de actualización de Microsoft Surface Dock, que anteriormente estaba disponible para descargar como parte de las herramientas de Surface. La herramienta anterior se denominaba Surface_Dock_Updater_vx.xx.xxx.x.msi (donde x indica el número de versión) y ya no se puede descargar y no debe usarse.

## Instalar la actualización del firmware de Surface Dock

En esta sección se describe cómo instalar manualmente la actualización del firmware.

> [!NOTE]
> Microsoft lanza periódicamente nuevas versiones de la actualización del firmware Surface Dock. El archivo MSI no se actualiza automáticamente. Si ha implementado el MSI en dispositivos Surface y se publica una nueva versión del firmware, tendrá que implementar la nueva versión.

1. Descargue e instale la [actualización de firmware Microsoft Surface Dock](https://www.microsoft.com/download/details.aspx?id=46703).
    - La actualización requiere un dispositivo Surface que ejecute Windows 10, versión 1803 o posterior.
    - Si instalas el archivo MSI, es posible que se te pida que reinicies la superficie. Sin embargo, no es necesario reiniciar para realizar la actualización.

2. Desconecta el dispositivo Surface del muelle de superficie (con el adaptador de alimentación), espera ~ 5 segundos y, a continuación, vuelve a conectarte. La actualización del firmware de Surface docking actualizará el Dock silenciosamente en segundo plano. El proceso puede demorar unos minutos en completarse y continuará aunque se interrumpa. 

## Supervisar la actualización del firmware de Surface Dock

Esta sección es opcional y proporciona información general sobre cómo supervisar la instalación de la actualización del firmware. 

Para supervisar la actualización:

1. Abra el visor de eventos, vaya a **registros de Windows > aplicación**y, a continuación, en **acciones** , en el panel derecho, haga clic en **filtrar registro actual**, escriba **SurfaceDockFwUpdate** junto a **orígenes de eventos**y, a continuación, haga clic en **Aceptar**.

2. Escriba el comando siguiente en un símbolo del sistema con privilegios elevados:

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. Instale la actualización como se describe en la [siguiente sección](#install-the-surface-dock-firmware-update) de este artículo.
4. El evento 2007 con el siguiente texto indica una actualización correcta: **actualización del firmware finalizada. hr = 0 DriverTelementry EventCode = 2007**. 
    - Si la actualización no se realiza correctamente, se mostrará el identificador de evento 2007 como un evento de **error** en lugar de la **información**. Además, la versión notificada en el registro de Windows no estará actualizada.
5. Una vez completada la actualización, los valores DWORD actualizados se mostrarán en el registro de Windows, que corresponde a la versión actual de la herramienta. Para obtener más información, consulte la sección [referencia de versiones](#versions-reference) en este artículo. Por ejemplo:
    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>Si ve "no se puede encontrar la descripción del identificador de evento xxxx del origen SurfaceDockFwUpdate" en el texto del evento, esto es lo que se espera y se puede ignorar.

Consulte también las secciones siguientes de este artículo: 
  - [Cómo comprobar la finalización de la actualización del firmware](#how-to-verify-completion-of-the-firmware-update)
  - [Registro de eventos](#event-logging)
  - [Recomendaciones para la solución de problemas](#troubleshooting-tips)
  - [Referencia de versiones](#versions-reference)

## Implementación de red

Puede usar los comandos de Windows Installer (Msiexec.exe) para implementar la actualización del firmware Surface Dock en varios dispositivos de la red. Cuando use Microsoft Endpoint Configuration Manager u otra herramienta de implementación, escriba la siguiente sintaxis para asegurarse de que la instalación es silenciosa:

- **Msiexec.exe/i \<path to msi file\> /Quiet/norestart** 

  Por ejemplo:
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > No se crea un archivo de registro de forma predeterminada. Para crear un archivo de registro, tendrá que anexar "/l*v [rutaDeAcceso]". Por ejemplo: Msiexec.exe/i \<path to msi file\> /l*v%WINDIR%\logs\ SurfaceDockFWI. log "

  Para obtener más información, consulte la documentación de [Opciones de línea de comandos](https://docs.microsoft.com/windows/win32/msi/command-line-options) .

> [!IMPORTANT]
> Si desea mantener el Dock de Surface actualizado con cualquier otro método, consulte [actualizar su Dock de Surface](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obtener más información.

## Implementación de Intune

Puede usar Intune para distribuir la actualización del firmware Surface Dock en sus dispositivos. En primer lugar, tendrá que convertir el archivo MSI al formato. intunewin, como se describe en la siguiente documentación: [Intune administración de aplicaciones independiente-Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).

Use el siguiente comando:
  - **msiexec/i \<path to msi file\> /Quiet/q**

## Cómo comprobar la finalización de la actualización del firmware

El firmware de Surface docking consta de dos componentes:

- **Component10:** Firmware de unidad Micro Controller (MCU)
- **Component20:** Firmware del puerto de visualización (DP).

La finalización satisfactoria de la actualización del firmware Surface docking genera nuevos valores de clave del registro para estos componentes de firmware.

**Para comprobar las actualizaciones:**

1. Abra Regedit y vaya a la siguiente ruta del registro:

    - **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Busque las claves del registro: **Component10CurrentFwVersion y Component20CurrentFwVersion**, que hacen referencia al firmware que se encuentra actualmente en el dispositivo.

   ![Proceso de instalación de actualización de firmware Surface Dock](images/regeditDock.png)

3. Compruebe que los nuevos valores de la clave del registro coincidan con los valores de la clave del registro actualizadas que aparecen en la referencia de versiones al final de este documento. Si los valores coinciden, el firmware se actualizó correctamente.

4. Si no puede comprobar, revise el registro de eventos y las sugerencias para la solución de problemas en la siguiente sección.

## Registro de eventos

**Tabla 1. Archivos de registro de la actualización del firmware Surface Dock**

| Log                              | Ubicación                               | Notas                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Registro de actualización de firmware de Surface Dock | Es necesario especificar la ruta de acceso (vea la nota) | Las versiones anteriores de esta herramienta escribían eventos a aplicaciones y servicios de la actualización de Logs\Microsoft.                                                                                                  |
| Registro de instalación de dispositivo de Windows       | %windir%\inf\setupapi.dev.log           | Para obtener más información sobre cómo usar el registro de instalación de dispositivos, consulte la documentación de [registro de SetupAPI](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) . |


**Tabla 2. Identificadores de registro de eventos para la actualización de firmware Surface Dock**<br>
Los eventos se registran en el registro de eventos de la aplicación.  Nota: las versiones anteriores de esta herramienta escribieron eventos para las aplicaciones y servicios de la actualización del Dock Logs\Microsoft.

| Id. de evento | Tipo de evento                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Se inició la actualización del firmware del Dock.                                    |
| 2002     | Se ha omitido la actualización del firmware del Dock porque se sabe que Dock está actualizado. |
| 2003     | Error al descargar la versión del firmware en la actualización del firmware del Dock.                 |
| 2004     | Consultando la versión de firmware.                                       |
| 2005     | El firmware del Dock no pudo iniciar la actualización.                                |
| 2006     | No se pudieron enviar los pares de oferta o carga.                                  |
| 2007     | Actualización de firmware finalizada.                                            |
| 2008     | COMIENZA la telemetría de acoplamiento.                                                |
| 2011     | FINALIZAR la telemetría del Dock.                                                  |

## Recomendaciones para la solución de problemas

- Desconecta por completo la energía del muelle de superficie desde la alimentación de CA para restablecer el muelle de superficie.
- Desconecte todos los periféricos excepto el del Dock.
- Desinstale la actualización de firmware de Surface Dock actual y, a continuación, instale la última versión.
- Asegúrese de que el muelle de superficie esté desconectado y deje el tiempo suficiente para que se complete la actualización mediante un LED en el puerto Ethernet del Dock. Espere hasta que el LED deje de parpadear antes de desconectar la superficie del Dock.
- Conecte el muelle de superficie a un dispositivo diferente para ver si es capaz de actualizar el Dock.

## Referencia de versiones

>[!NOTE]
>El archivo de instalación se publica con el siguiente formato de nombre: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por ejemplo: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) e instala de forma predeterminada en C:\Archivos de Files\SurfaceUpdate.

### Versión 1.42.139 
*Fecha de lanzamiento: Septiembre 18 2019*

Esta versión, que se encuentra en Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, actualiza el firmware en segundo plano. 
**Valores de clave del registro actualizados:**<br>

- Component10CurrentFwVersion actualizado a **4ac3970**.
- Component20CurrentFwVersion actualizado a **4a1d570**.

Agrega compatibilidad para Surface Pro 7 y el portátil Surface 3.

## Versiones heredadas

### Versión 2.23.139.0
*Fecha de lanzamiento: 10 de octubre de 2018*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Agregar compatibilidad con Surface Pro 6
- Agregar compatibilidad para Surface Laptop 2


### Versión 2.22.139.0
*Fecha de lanzamiento: 26 de julio de 2018*

Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:

- Aumentar la confiabilidad de la actualización
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


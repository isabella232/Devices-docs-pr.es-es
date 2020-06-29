---
title: Actualizar el firmware del lápiz en Surface Hub 2S
description: Esta página describe cómo actualizar el firmware para el lápiz de Surface Hub 2.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835385"
---
# Actualizar el firmware del lápiz en Surface Hub 2S

Puede actualizar el firmware en el lápiz de Surface Hub 2 desde Windows Update para empresas o descargando la actualización del firmware en un equipo diferente. El firmware actualizado está disponible en Windows Update, a partir del 26 de febrero de 2020. 

## Actualizar el firmware del lápiz con Windows Update para empresas

En esta sección se describe cómo actualizar el firmware del lápiz a través de los ciclos de mantenimiento automáticos para Windows Update, configurado de forma predeterminada para que se produzcan por la noche a las 3 a.m. Tendrá que planear dos ciclos de mantenimiento para completarlos antes de aplicar la actualización al lápiz de Surface Hub 2. Como alternativa, como cualquier otra actualización, puede usar Windows Server Update Services (WSUS) para aplicar el firmware del lápiz. Para obtener más información, vea [administrar actualizaciones de Windows en Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Asegúrate de que el lápiz de Surface Hub 2 esté emparejado con Surface Hub 2S: Mantén pulsado el botón **superior** hasta que la luz LED del indicador blanco empiece a parpadear. <br>
![Lápiz de Surface Hub 2](images/sh2-pen-1.png) <br>
2. En Surface Hub, inicie sesión como administrador, Abra **configuración**y, a continuación, busque nuevos dispositivos Bluetooth.
3. Seleccione el lápiz para completar el proceso de emparejamiento.
4. Presione el botón **superior** del lápiz para aplicar la actualización. Puede demorar hasta dos horas en completarse.

## Actualizar el firmware del lápiz descargando a otro equipo

Puede actualizar el firmware en el lápiz de Surface Hub 2 desde un PC independiente que ejecute Windows 10. Este método también le permite comprobar que el firmware del lápiz se ha actualizado correctamente a la versión más reciente.

1. Emparejar el lápiz del Surface Hub 2 a tu equipo con capacidad Bluetooth: Mantén pulsado el botón **superior** hasta que la luz LED del indicador blanco empiece a parpadear. <br>
![Lápiz de Surface Hub 2](images/sh2-pen-1.png) <br>
2. En el PC, busca nuevos dispositivos Bluetooth.
3. Seleccione el lápiz para completar el proceso de emparejamiento.
4. Desconecte el resto de plumas de Surface Hub 2s antes de iniciar una nueva actualización.
3. Descarga la [herramienta de actualización del firmware de Surface Hub 2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) en tu PC.
4. Ejecute **PenCfu.exe.** El progreso de instalación se muestra en la herramienta. Finalizar la actualización puede demorar unos minutos. 


## Comprobar la versión de firmware del lápiz de Surface Hub 2

1. Ejecute **get_version.bat** y presione el botón **superior** del lápiz.
2. La herramienta informará de la versión de firmware del lápiz. Por ejemplo:
    - El firmware anterior es 468.2727.368
    - El nuevo firmware es 468.2863.369

## Opciones de línea de comandos

Puede ejecutar la herramienta de actualización del firmware de Surface Hub 2 (PenCfu.exe) desde la línea de comandos.

1. Empareje el lápiz con su PC y haga clic en el botón **superior** del lápiz.
2. Haga doble clic en **PenCfu.exe** para iniciar la actualización de firmware. Tenga en cuenta que el archivo de configuración y los archivos de imagen de firmware deben almacenarse en la misma carpeta que la herramienta.
3. Para obtener opciones adicionales, ejecute **PenCfu.exe-h** para mostrar los parámetros disponibles, como se muestra en la tabla siguiente.  
    - Ejemplo: PenCfu.exe-h
4. Presione **Ctrl + C** para cerrar la herramienta de forma segura.

 

| **Comando**    | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h ayuda        | Herramienta de visualización ayuda y salida de la interfaz de línea de comandos.                                                                                                                                                                                                                                                                                                                                             |
| versión de-v     | Mostrar la versión de la herramienta y salir.                                                                                                                                                                                                                                                                                                                                                                 |
| -l log: filtrar  | Establezca un nivel de filtro para el archivo de registro. Los mensajes de registro tienen 4 niveles posibles: DEBUG (menor), INFO, WARNING y ERROR (la más alta). La configuración de un nivel de filtro de registro filtra los mensajes de registro a solo los mensajes con el mismo nivel o superior. Por ejemplo, si el nivel de filtro se establece en ADVERTENCIA, solo se registrarán los mensajes de advertencia y de ERROR. De forma predeterminada, esta opción está desactivada, lo cual deshabilita el registro. |
| -g Get-version | Si se especifica, la herramienta solo obtendrá la versión de FW del lápiz conectado que coincida con el archivo de configuración almacenado en la misma carpeta que la herramienta.                                                                                                                                                                                                                                    
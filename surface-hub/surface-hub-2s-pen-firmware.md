---
title: Actualizar el firmware del lápiz en Surface Hub 2S
description: En esta página se describe cómo actualizar el firmware del Surface Hub 2 plumas.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6f1ca4f05653ec798ed1b47d2e42e974e7f7414d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576960"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Actualizar el firmware del lápiz en Surface Hub 2S

Puede actualizar el firmware en Surface Hub 2 pen desde Windows Update for Business o descargando la actualización de firmware en un equipo independiente. El firmware actualizado está disponible desde Windows actualización a partir del 26 de febrero de 2020. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>Actualizar el firmware del lápiz con Windows update para empresas

En esta sección se describe cómo actualizar el firmware del lápiz a través de los ciclos de mantenimiento automatizados de Windows Update, configurados de forma predeterminada para que se produzcan cada noche a las 3 a. m. Deberá planear dos ciclos de mantenimiento para completar antes de aplicar la actualización al Surface Hub 2 plumas. Como alternativa, como cualquier otra actualización, puede usar Windows Update for Business (WUfB) para aplicar el firmware del lápiz. Para obtener más información, vea [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Asegúrese de Surface Hub 2 plumas esté emparejada a Surface Hub 2S: mantenga presionado el botón superior hasta que la luz LED indicadora blanca comience a parpadear. **** <br>
![Surface Hub 2 plumas](images/sh2-pen-1.png) <br>
2. On Surface Hub, login as an Admin, open **Configuración**, and then scan for new Bluetooth devices.
3. Seleccione el lápiz para completar el proceso de emparejamiento.
4. Presione el **botón** superior del lápiz para aplicar la actualización. Puede tardar hasta dos horas en completarse.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>Actualizar el firmware del lápiz descargando en un equipo independiente

Puede actualizar el firmware en un Surface Hub 2 pen desde un equipo independiente que ejecute Windows 10. Este método también permite comprobar que el firmware del lápiz se actualizó correctamente a la versión más reciente.

1. Empareja el Surface Hub 2 plumas al equipo compatible con Bluetooth: **** mantén presionado el botón superior hasta que la luz LED indicadora blanca comience a parpadear. <br>
![Surface Hub 2 plumas](images/sh2-pen-1.png) <br>
2. En el equipo, busca nuevos Bluetooth dispositivos.
3. Seleccione el lápiz para completar el proceso de emparejamiento.
4. Desconecte el resto Surface Hub 2 lápices antes de iniciar una nueva actualización.
3. Descargue la herramienta Surface Hub actualización de firmware de [2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) plumas en el equipo.
4. Ejecute **PenCfu.exe.** El progreso de instalación se muestra en la herramienta. Puede tardar varios minutos en finalizar la actualización. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>Comprobar la versión de firmware de Surface Hub 2 plumas

1. Ejecute **get_version.bat** y presione el **botón superior** del lápiz.
2. La herramienta mostrará la versión de firmware del lápiz. Por ejemplo:
    - El firmware antiguo es 468.2727.368
    - El nuevo firmware es 468.3347.368

## <a name="command-line-options"></a>Opciones de línea de comandos

Puede ejecutar Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) desde la línea de comandos.

1. Empareja el lápiz con el equipo y haz clic en **el botón superior** del lápiz.
2. Haga doble ** clicPenCfu.exe** para iniciar la actualización de firmware. Tenga en cuenta que el archivo de configuración y los archivos de imagen de firmware deben almacenarse en la misma carpeta que la herramienta.
3. Para obtener opciones adicionales, ** ejecutePenCfu.exe -h para** mostrar los parámetros disponibles, como se muestra en la tabla siguiente.  
    - Ejemplo: PenCfu.exe -h
4. Escriba **Ctrl+C para** apagar la herramienta de forma segura.

 

| **Comando**    | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ayuda de -h        | Mostrar ayuda y salida de la interfaz de línea de comandos de la herramienta.                                                                                                                                                                                                                                                                                                                                             |
| -v version     | Mostrar versión y salida de la herramienta.                                                                                                                                                                                                                                                                                                                                                                 |
| -l log-filter  | Establecer un nivel de filtro para el archivo de registro. Los mensajes de registro tienen 4 niveles posibles: DEBUG (más bajo), INFO, WARNING y ERROR (más alto). Al establecer un nivel de filtro de registro, los mensajes de registro solo se filtran en mensajes con el mismo nivel o superior. Por ejemplo, si el nivel de filtro está establecido en WARNING, solo se registrarán los mensajes WARNING y ERROR. De forma predeterminada, esta opción se establece en OFF, que deshabilita el registro. |
| -g get-version | Si se especifica, la herramienta solo recibirá la versión FW del lápiz conectado que coincida con el archivo de configuración almacenado en la misma carpeta que la herramienta.                                                                                                                                                                                                                                    

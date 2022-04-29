---
title: Actualizar el firmware del lápiz en Surface Hub 2S
description: En esta página se describe cómo actualizar el firmware del lápiz Surface Hub 2.
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
ms.openlocfilehash: b1955f1806c963ce553d5d2eef99e72e90c5adfe
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497723"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>Actualizar el firmware del lápiz en Surface Hub 2S

Puede actualizar el firmware en Surface Hub lápiz de 2 desde Windows Update para empresas o descargando la actualización de firmware en un equipo independiente. El firmware actualizado está disponible desde Windows Update a partir del 26 de febrero de 2020. 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>Actualización del firmware del lápiz mediante Windows Update para empresas

En esta sección se describe cómo actualizar el firmware del lápiz a través de los ciclos de mantenimiento automatizados para Windows Update, configurados de forma predeterminada para que se produzcan por la noche a las 3 a. m. Tendrá que planear que se completen dos ciclos de mantenimiento antes de aplicar la actualización al lápiz Surface Hub 2. Como alternativa, como cualquier otra actualización, puede usar Windows Update para empresas (WUfB) para aplicar el firmware del lápiz. Para obtener más información, consulte [Administración de actualizaciones de Windows en Surface Hub](manage-windows-updates-for-surface-hub.md).

1. Asegúrese de que el lápiz Surface Hub 2 esté emparejado con Surface Hub 2S: Mantenga presionado el botón **superior** hasta que la luz LED del indicador blanco comience a parpadear.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 plumas.](images/sh2-pen-1.png)

2. En Surface Hub, inicie sesión como administrador, abra **Configuración** y busque nuevos dispositivos Bluetooth.

3. Seleccione el lápiz para completar el proceso de emparejamiento.

4. Presione el botón **superior** del lápiz para aplicar la actualización. Puede tardar hasta dos horas en completarse.

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>Actualización del firmware del lápiz mediante la descarga en un equipo independiente

Puede actualizar el firmware en Surface Hub lápiz 2 desde un equipo independiente que ejecute Windows 10 o Windows 11. Este método también le permite comprobar que el firmware del lápiz se ha actualizado correctamente a la versión más reciente.

1. Empareja el lápiz Surface Hub 2 a tu PC compatible con Bluetooth: Mantén presionado el botón **superior** hasta que la luz LED del indicador blanco comience a parpadear.

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 plumas.](images/sh2-pen-1.png)

2. En el equipo, busque nuevos dispositivos Bluetooth.

3. Seleccione el lápiz para completar el proceso de emparejamiento.

4. Desconecte todas las demás plumas de Surface Hub 2s antes de iniciar una nueva actualización.

5. Descargue la [herramienta de actualización de firmware del lápiz Surface Hub 2](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) en su PC.

6. Ejecute **PenCfu.exe.** El progreso de la instalación se muestra en la herramienta. Puede tardar varios minutos en finalizar la actualización. 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>Comprobación de la versión de firmware del lápiz de Surface Hub 2

1. Ejecute **get_version.bat** y presione el botón **superior** del lápiz.

2. La herramienta notificará la versión de firmware del lápiz. 

   Por ejemplo:
    - El firmware antiguo es 468.2727.368
    - El nuevo firmware es 468.3347.368

## <a name="command-line-options"></a>Opciones de línea de comandos

Puede ejecutar Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) desde la línea de comandos.

1. Empareje el lápiz con su PC y haga clic en el botón **superior** del lápiz.

2. Haga doble clic en **PenCfu.exe** para iniciar la actualización del firmware. Tenga en cuenta que el archivo de configuración y los archivos de imagen de firmware deben almacenarse en la misma carpeta que la herramienta.

3. Para obtener opciones adicionales, ejecute **PenCfu.exe -h** para mostrar los parámetros disponibles, como se muestra en la tabla siguiente.  

   Por ejemplo: `PenCfu.exe -h`

4. Escriba **Ctrl+C** para apagar la herramienta de forma segura.


| Comando | Descripción |
| -------------- |---------------------------- |
| -h ayuda        | Mostrar la ayuda y salida de la interfaz de la línea de comandos de la herramienta. |
| Versión de -v     | Mostrar la versión de la herramienta y salir. |
| -l log-filter  | Establezca un nivel de filtro para el archivo de registro. Los mensajes de registro tienen 4 niveles posibles: DEBUG (más bajo), INFO, WARNING y ERROR (más alto). Al establecer un nivel de filtro de registro, los mensajes de registro se filtran solo en mensajes con el mismo nivel o superior. Por ejemplo, si el nivel de filtro está establecido en WARNING, solo se registrarán los mensajes WARNING y ERROR. De forma predeterminada, esta opción se establece en OFF, lo que deshabilita el registro. |
| -g get-version | Si se especifica, la herramienta solo obtendrá la versión fw del lápiz conectado que coincida con el archivo de configuración almacenado en la misma carpeta que la herramienta.  |


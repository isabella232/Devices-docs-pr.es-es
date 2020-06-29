---
title: Uso de la herramienta de recuperación de Surface Hub
description: Cómo usar la herramienta de recuperación de Surface hub para volver a crear una imagen de SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: administrar Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836894"
---
# Uso de la herramienta de recuperación de Surface Hub

La [herramienta de recuperación de Surface Hub de Microsoft](https://www.microsoft.com/download/details.aspx?id=52210) le ayuda a volver a crear una imagen de la unidad de estado sólido (SSD) del concentrador de Surface con un dispositivo de escritorio Windows 10, sin llamar a soporte técnico ni reemplazar el SSD. Con esta herramienta, puede rehacer la imagen de una SSD que tiene una contraseña de administrador desconocida, errores de inicio, que no pudo completar una recuperación de la nube o para un dispositivo que tiene una versión anterior del sistema operativo. La herramienta no solucionará la SSDs físicamente dañada.

Para volver a crear una imagen de la SSD del Surface Hub con la herramienta de recuperación, tendrá que quitar el SSD de Surface Hub, conectar la unidad al cable USB a SATA y, a continuación, conectar el cable al equipo de escritorio en el que está instalada la herramienta de recuperación. Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, consulte [sustitución de SSD en Surface Hub](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> No deje que el dispositivo pase al estado de suspensión o interrumpa la descarga del archivo de imagen.

Si la herramienta no se completa correctamente, póngase en contacto [con el soporte técnico de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## Requisitos previos

### Mandatory

- EQUIPO host que ejecuta la versión de 64 bits de Windows 10, versión 1607 o superior.
- Acceso a Internet
- Puerto USB 2,0 o superior abierto
- Cable USB a SATA
- 10 GB de espacio libre en el disco del equipo host
- SSDs se distribuyó con Surface Hub o un SSD proporcionado por el soporte técnico como reemplazo. SSDs no suministrado por Microsoft no es compatible.

### Recomendaciones

- Conexión a Internet de alta velocidad
- Puerto USB 3,0 abierto
- Cable USB 3,0 o superior USB a SATA
- La herramienta de creación de imágenes se probó con la siguiente marca y modelo de cables:
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## Descargar la herramienta de recuperación de Surface Hub

La herramienta de recuperación de Surface Hub está disponible para su descarga desde las [herramientas de Surface hub para ello](https://www.microsoft.com/download/details.aspx?id=52210) bajo el nombre de archivo **SurfaceHub_Recovery_v1.14.137.0.msi**.

Para iniciar la descarga, haga clic en **Descargar**, elija **SurfaceHub_Recovery_v1.14.137.0.msi** de la lista y haga clic en **siguiente**. En el menú emergente, elija una de las siguientes opciones:

- Haga clic en **Ejecutar** para iniciar la instalación inmediatamente.
- Haga clic en **Guardar** para copiar la descarga en el equipo para su instalación posterior.

Instale la herramienta de recuperación de Surface Hub en el equipo host.

## Ejecutar la herramienta de recuperación de Surface Hub

1. En el equipo host, seleccione el botón **Inicio** , desplácese por la lista alfabética de la izquierda y seleccione el método abreviado de la herramienta de recuperación.

    ![Acceso directo a la herramienta de recuperación de Surface Hub de Microsoft](images/shrt-shortcut.png)

2. Haz clic en **Inicio**.

    ![Botón Inicio de la herramienta de recuperación](images/shrt-start.png)

3. En la ventana de **guías** , haga clic en **siguiente**.

    ![No deje que su equipo pase a la guía de suspensión](images/shrt-guidance.png)

4. Haga clic en **sí** para descargar la imagen. La descarga de la imagen de recuperación depende de la velocidad de conexión a Internet. En una conexión corporativa media, la descarga del archivo de imagen de 8 GB puede tardar hasta una hora.

    ![¿Descargar la imagen?](images/shrt-download.png)

5. Una vez completada la descarga, la herramienta le indica que conecte una unidad SSD. Si la herramienta no puede ubicar la unidad conectada, existe la posibilidad de que el cable utilizado no informe al nombre de la SSD en Windows.  La herramienta de creación de imágenes debe encontrar el nombre de la unidad como "dispositivo USB LITEon L CH-128V2S" antes de que pueda continuar.  Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, consulte [sustitución de SSD en Surface Hub](surface-hub-ssd-replacement.md).

    ![Conectar SSD](images/shrt-drive.png)

6. Cuando se reconozca la unidad, haga clic en **iniciar** para comenzar el proceso de creación de imágenes. En la advertencia de que se borrarán todos los datos de la unidad, haga clic en **Aceptar**.

    ![Iniciar la creación de imágenes de SSD](images/shrt-drive-start.png)

    Antes de aplicar la imagen del sistema a la unidad, se vuelve a particionar y formatear SSD. La copia de los archivos binarios del sistema tardará aproximadamente 30 minutos, pero puede tardar más tiempo en función de la velocidad de su bus USB, el cable que se usa o el software antivirus instalado en su sistema.

    ![Copia finalizada](images/shrt-done.png)

    ![Recreación de imágenes completada](images/shrt-complete.png)

## Solución de problemas y problemas comunes

Problema | Notas
--- | ---
La herramienta no puede hacer una imagen de la SSD | Asegúrate de estar usando un SSD suministrado por fábrica y uno de los cables probados.
El proceso de recreación de imágenes aparece detenido o inmovilizado | Es seguro cerrar y reiniciar la herramienta de recuperación de Surface Hub sin ningún efecto indebido a la SSD.
La herramienta no reconoce la unidad | Verifica que la SSD del Surface Hub se Enumere como una unidad Lite-on, "dispositivo USB LITE-CH de 128V2S".  Si la unidad se reconoce como otro dispositivo con nombre, el cable actual no es compatible. Prueba otro cable o uno de los cables probados mencionados arriba.
Error:-2147024809 | Abra Disk Manager y quite las particiones de la unidad Surface Hub.  Desconecte y vuelva a conectar la unidad al equipo host. Vuelva a iniciar la herramienta de creación de imágenes.

Si la herramienta no se completa correctamente, póngase en contacto [con el soporte técnico de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

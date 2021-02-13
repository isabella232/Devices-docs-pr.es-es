---
title: Uso de la herramienta de recuperación de Surface Hub
description: Cómo usar la Herramienta de recuperación de Surface Hub para volver a crear una imagen del SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: administrar Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 34a05eeabd284e0ad43317577b8e7ff9348ffe21
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327344"
---
# Uso de la herramienta de recuperación de Surface Hub

La Herramienta de recuperación de [Microsoft Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) te ayuda a volver a crear una imagen de la unidad de estado sólido (SSD) de Surface Hub con un dispositivo de escritorio Windows 10, sin llamar al soporte técnico ni reemplazar el SSD. Con esta herramienta, puedes volver a crear una imagen de un SSD que tenga una contraseña de administrador desconocida, errores de arranque, no haya podido completar una recuperación en la nube o para un dispositivo que tenga una versión anterior del sistema operativo. La herramienta no corregirá los SSD físicamente dañados.

Para volver a crear una imagen de la SSD de Surface Hub con la Herramienta de recuperación, tendrás que quitar el SSD de Surface Hub, conectar la unidad al cable USB a SATA y, a continuación, conectar el cable al equipo de escritorio en el que está instalada la herramienta de recuperación. Para obtener más información sobre cómo quitar la unidad existente de Surface Hub, consulta reemplazo de [SSD de Surface Hub.](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> No deje que el dispositivo se ponga en modo de suspensión ni interrumpa la descarga del archivo de imagen.

Si la herramienta no consigue restablecer la unidad, ponte en contacto con el soporte [técnico de Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Requisitos previos

### Mandatory

- Equipo host que ejecuta la versión de 64 bits de Windows 10, versión 1607 o posterior.
- Acceso a Internet
- Puerto USB 2.0 abierto o posterior
- Cable USB a SATA
- 10 GB de espacio libre en disco en el equipo host
- Ssd que se suministran con Surface Hub o un SSD proporcionado por el soporte técnico como reemplazo. Los SSD no proporcionados por Microsoft no son compatibles.

### Recomendaciones

- Conexión a Internet de alta velocidad
- Puerto USB 3.0 abierto
- Cable USB 3.0 o superior de USB a SATA
- La herramienta de creación de imágenes se probó con la siguiente creación y modelo de cables:
    - Startech USB312SAT3CB
    - Rosawill RCUC16001
    - Ugreen 20231

## Descargar la Herramienta de recuperación de Surface Hub

La Herramienta de recuperación de Surface Hub está disponible para su descarga desde [herramientas de Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) para TI en el nombre de archivo **SurfaceHub_Recovery_v2.7.139.0.msi. **

> [!IMPORTANT]
> Esta versión, publicada el 11 de febrero de 2021, reemplaza a la compilación anterior, que ya no funciona. Si has descargado esta herramienta anteriormente, descarta y usa la versión actual.

Para iniciar la descarga, haga **clic en Descargar**, elija **SurfaceHub_Recovery_v2.7.139.0.msi** de la lista y haga clic en **Siguiente.** En la ventana emergente, elija una de las siguientes opciones:

- Haga **clic en Ejecutar** para iniciar la instalación inmediatamente.
- Haga **clic en** Guardar para copiar la descarga en el equipo para su instalación posterior.

Instala la Herramienta de recuperación de Surface Hub en el equipo host.

## Ejecutar la Herramienta de recuperación de Surface Hub

1. En el equipo host, selecciona el botón Inicio, desplázate por la lista alfabética de la izquierda y selecciona el acceso directo de la herramienta de recuperación. ****

    ![Acceso directo de la Herramienta de recuperación de Microsoft Surface Hub](images/shrt-shortcut.png)

2. Haz clic en **Inicio**.

    ![Botón Inicio de la herramienta de recuperación](images/shrt-start.png)


3. En la **ventana Guía,** haga clic en **Siguiente**.

    ![No dejar que la máquina vaya a la guía de suspensión](images/shrt-guidance.png)

4. En la ventana Seleccionar imagen, haga clic en **RS2** o en su **sucesora 20H2,** seleccione Continuar **y,** a continuación, **seleccione Descargar imagen.**

     ![Imagen de descarga de la herramienta de ](images/shrt-select-image.png) ![ recuperación de la herramienta de recuperación de la selección de la herramienta de recuperación de la](images/shrt-download-image.png)

5. El tiempo para descargar la imagen de recuperación depende de las velocidades de conexión a Internet. En una conexión corporativa promedio, puede tardar hasta una hora descargar el archivo de imagen de 8 GB.

    ![Descargar imagen](images/shrt-download.png)



5. Una vez completada la descarga, la herramienta te indica que conectes una unidad SSD. Si la herramienta no puede encontrar la unidad conectada, es muy posible que el cable que se usa no notifique el nombre del SSD a Windows.  La herramienta de creación de imágenes debe encontrar el nombre de la unidad como "Dispositivo USB LITEON L CH-128V2S" para poder continuar.  Para obtener más información sobre cómo quitar la unidad existente de Surface Hub, consulta reemplazo de [SSD de Surface Hub.](surface-hub-ssd-replacement.md)

    ![Connect SSD](images/shrt-drive.png)

6. Cuando se reconozca la unidad, haz clic en **Inicio** para comenzar el proceso de creación de imágenes de nuevo. En la advertencia de que se borrarán todos los datos de la unidad, haga clic en **Aceptar.**



    Antes de aplicar la imagen del sistema a la unidad, el SSD se vuelve a particionar y formatear. La copia de los archivos binarios del sistema llevará aproximadamente 30 minutos, pero puede tardar más en función de la velocidad del bus USB, el cable que se usa o el software antivirus instalado en el sistema.



## Solución de problemas y problemas comunes

Problema | Notas
--- | ---
La herramienta no puede crear una imagen del SSD | Asegúrate de que estás usando un SSD suministrado por fábrica y uno de los cables probados.
The reimaging process appears halted/frozen | Es seguro cerrar y reiniciar la herramienta de recuperación de Surface Hub sin ningún efecto negativo en el SSD.
La herramienta no reconoce la unidad | Comprueba que el SSD de Surface Hub se enumeró como una Lite-On, "LiteON L CH-128V2S USB Device".  Si la unidad se reconoce como otro dispositivo con nombre, el cable actual no es compatible. Pruebe otro cable o uno de los cable probados enumerados anteriormente.
Error: -2147024809 | Abre el Administrador de discos y quita las particiones de la unidad de Surface Hub.  Desconecte y vuelva a conectar la unidad al equipo host. Reinicia la herramienta de creación de imágenes de nuevo.

Si la herramienta no consigue restablecer la unidad, ponte en contacto con el soporte [técnico de Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Historial de versiones


### Versión v2.7.139.0

*Fecha de lanzamiento: 11 de febrero de 2021*<br>
Esta versión de la Herramienta de recuperación de Surface Hub agrega compatibilidad con lo siguiente:

- Actualización de seguridad


### Versión v2.0.139.0

> [!IMPORTANT]
> Esta versión ya no funciona. Descargue la versión actual, enumerada anteriormente. 

*Fecha de lanzamiento: 18 de diciembre de 2020*<br>
Esta versión de la Herramienta de recuperación de Surface Hub agrega compatibilidad con lo siguiente:
- Actualización para admitir Windows 10 Team 2020 Update (20H2)
- Mejoras en la experiencia del usuario
- Cambios en la arquitectura
- Adiciones de telemetría


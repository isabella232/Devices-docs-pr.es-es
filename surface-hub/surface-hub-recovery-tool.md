---
title: Uso de la herramienta de recuperación de Surface Hub
description: Cómo usar la herramienta Surface Hub recuperación de archivos para volver a crear una imagen del SSD.
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
ms.openlocfilehash: f472d42bba9270b117cfa8cb9b54eaeb020aefc4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910985"
---
# <a name="using-the-surface-hub-recovery-tool"></a>Uso de la herramienta de recuperación de Surface Hub

La [herramienta de](https://www.microsoft.com/download/details.aspx?id=52210) recuperación de Microsoft Surface Hub ayuda a volver a crear una imagen de la unidad de estado sólido (SSD) de Surface Hub con un dispositivo de escritorio Windows 10, sin llamar al soporte técnico ni reemplazar el SSD. Con esta herramienta, puedes volver a crear una imagen de un SSD que tiene una contraseña de administrador desconocida, errores de arranque, no pudo completar una recuperación en la nube o para un dispositivo que tiene una versión anterior del sistema operativo. La herramienta no corregirá los SSD dañados físicamente.

Para volver a crear una imagen de la SSD de Surface Hub con la herramienta de recuperación, deberá quitar el SSD del Surface Hub, conectar la unidad al cable USB a SATA y, a continuación, conectar el cable al equipo de escritorio en el que está instalada la herramienta de recuperación. Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, vea [Surface Hub reemplazo de SSD](surface-hub-ssd-replacement.md).

> [!IMPORTANT]
> No deje que el dispositivo se ponga en reposo ni interrumpa la descarga del archivo de imagen.

Si la herramienta no ha sido correcta al reimaging de la unidad, póngase en contacto [Surface Hub soporte técnico](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="prerequisites"></a>Requisitos previos

### <a name="mandatory"></a>Mandatory

- Equipo host que ejecuta una versión de 64 bits de Windows 10 versión 1607 o posterior.
- Acceso a Internet
- Abrir puerto USB 2.0 o posterior
- Cable USB a SATA
- 10 GB de espacio libre en disco en el equipo host
- Ssd enviados con Surface Hub ssd proporcionados por el soporte técnico como reemplazo. Los SSD no proporcionados por Microsoft no son compatibles.

### <a name="recommended"></a>Recomendaciones

- Conexión a Internet de alta velocidad
- Abrir puerto USB 3.0
- Cable USB 3.0 o superior USB a SATA
- La herramienta de creación de imágenes se ha probado con la siguiente creación y modelo de cables:
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## <a name="download-surface-hub-recovery-tool"></a>Descargar Surface Hub recuperación

Surface Hub Recovery Tool está disponible para su descarga desde [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210) bajo el nombre de archivo **SurfaceHub_Recovery_v2.7.139.0.msi**.

> [!IMPORTANT]
> Esta versión, publicada el 11 de febrero de 2021, reemplaza a la compilación anterior, que ya no es funcional. Si descargó esta herramienta anteriormente, desinstale e instale la versión actual.

Para iniciar la descarga, haga clic **en Descargar**, ** elijaSurfaceHub_Recovery_v2.7.139.0.msi**  de la lista y haga clic en **Siguiente**. En la ventana emergente, elija una de las siguientes opciones:

- Haga **clic en** Ejecutar para iniciar la instalación inmediatamente.
- Haga **clic en** Guardar para copiar la descarga en el equipo para su instalación posterior.

Instalar Surface Hub recuperación en el equipo host.

## <a name="run-surface-hub-recovery-tool"></a>Ejecutar Surface Hub recuperación

1. En el equipo host, seleccione **el** botón Inicio, desplácese por la lista alfabética de la izquierda y seleccione el acceso directo de la herramienta de recuperación.

    ![Microsoft Surface Hub Acceso directo de la herramienta de recuperación.](images/shrt-shortcut.png)

2. Haz clic en **Inicio**.

    ![Botón Inicio de la herramienta de recuperación.](images/shrt-start.png)


3. En la **ventana Guía,** haga clic **en Siguiente**.

    ![No deje que la máquina vaya a instrucciones de suspensión.](images/shrt-guidance.png)

4. En la ventana Seleccionar imagen, haga clic en **RS2** o en su **sucesor 20H2,** seleccione **Continuar y,** a continuación, **seleccione Descargar imagen.**

     ![Imagen de selección de la herramienta de recuperación.](images/shrt-select-image.png)
    ![Imagen de descarga de la herramienta de recuperación.](images/shrt-download-image.png)

5. El tiempo para descargar la imagen de recuperación depende de las velocidades de conexión a Internet. En una conexión corporativa promedio, puede tardar hasta una hora en descargar el archivo de imagen de 8 GB.

    ![Descargar imagen.](images/shrt-download.png)



5. Una vez completada la descarga, la herramienta le indica que conecte una unidad SSD. Si la herramienta no puede localizar la unidad adjunta, es muy posible que el cable que se usa no informe del nombre del SSD a Windows.  La herramienta de creación de imágenes debe encontrar el nombre de la unidad como "Dispositivo USB LITEON L CH-128V2S" para poder continuar.  Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, vea [Surface Hub reemplazo de SSD](surface-hub-ssd-replacement.md).

    ![Conectar SSD.](images/shrt-drive.png)

6. Cuando se reconozca la unidad, haga clic **en Inicio** para iniciar el proceso de re-creación de imágenes. En la advertencia de que se borrarán todos los datos de la unidad, haga clic en **Aceptar**.



    Antes de aplicar la imagen del sistema a la unidad, el SSD se vuelve a particionar y dar formato. Copiar los archivos binarios del sistema llevará aproximadamente 30 minutos, pero puede tardar más en función de la velocidad del bus USB, el cable que se usa o el software antivirus instalado en el sistema.



## <a name="troubleshooting-and-common-problems"></a>Solución de problemas y problemas comunes

Problema | Notas
--- | ---
La herramienta no puede crear una imagen del SSD | Asegúrese de usar un SSD suministrado de fábrica y uno de los cables probados.
El proceso de reimplante aparece detenido o inmovilizado | Es seguro cerrar y reiniciar la herramienta de Surface Hub recuperación sin ningún efecto negativo para la SSD.
La herramienta no reconoce la unidad | Compruebe que el SSD Surface Hub está enumerado como una unidad Lite-On, "Liteon L CH-128V2S USB Device".  Si la unidad se reconoce como otro dispositivo con nombre, el cable actual no es compatible. Pruebe otro cable o uno de los cables probados enumerados anteriormente.
Error: -2147024809 | Abra el Administrador de discos y quite las particiones de la Surface Hub disco.  Desconecte y vuelva a conectar la unidad al equipo host. Reinicie la herramienta de creación de imágenes de nuevo.

Si la herramienta no ha sido correcta al reimaging de la unidad, póngase en contacto [Surface Hub soporte técnico](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="version-history"></a>Historial de versiones


### <a name="version-v271390"></a>Versión v2.7.139.0

*Fecha de lanzamiento: 11 de febrero de 2021*<br>
Esta versión de Surface Hub Recovery Tool agrega compatibilidad con lo siguiente:

- Actualización de seguridad


### <a name="version-v201390"></a>Versión v2.0.139.0

> [!IMPORTANT]
> Esta versión ya no es funcional. Descargue la versión actual, enumerada anteriormente. 

*Fecha de lanzamiento: 18 de diciembre de 2020*<br>
Esta versión de Surface Hub Recovery Tool agrega compatibilidad con lo siguiente:
- Actualización para admitir Windows 10 Team 2020 Update (20H2)
- Mejoras en la experiencia del usuario
- Cambios en la arquitectura
- Adiciones de telemetría


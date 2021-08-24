---
title: Borrador de datos de Microsoft Surface (Surface)
description: Descubre cómo puedes usar la herramienta Borrador de datos de Microsoft Surface para eliminar los datos de tus dispositivos Surface de manera segura.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: herramienta, USB, datos, borrar
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 05/17/2021
ms.openlocfilehash: 292c20c9999d9f226f28daed87069c78b43fd4bf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911195"
---
# <a name="microsoft-surface-data-eraser"></a>Borrador de datos de Microsoft Surface

Descubre cómo puedes usar la herramienta Borrador de datos de Microsoft Surface para eliminar los datos de tus dispositivos Surface de manera segura.

[Borrador de datos de Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703) es una herramienta que se inicia desde un stick USB y que te permite borrar con seguridad todos los datos de un dispositivo Surface compatible. Para iniciar el stick USB del Borrador de datos Microsoft Surface únicamente necesitas un puerto USB. Asimismo, te resultará simple crear el stick USB si usas el asistente proporcionado a tal fin: el Contenedor de borrado de datos de Microsoft Surface; este asistente es muy fácil de usar ya que tiene una interfaz gráfica sencilla y no precisa de una línea de comandos. Para obtener más información acerca de las funcionalidades y las prácticas para borrar los datos que Microsoft usa durante el proceso de servicio de Surface, consulta [P+F: proteger sus datos si envía su Surface para reparación](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Borrador de datos de Microsoft Surface usa el comando de formato NVM Express (NVMe) para borrar los datos según se autoriza en [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf).

Los dispositivos Surface compatibles incluyen:

- Surface Book (todas las ediciones)
- Surface Go (todas las ediciones)
- Surface Pro X (todas las ediciones)
- Surface Laptop (todas las ediciones)
- Surface Laptop Ir
- Surface Studio (todas las ediciones)
- Surface Pro 2 y posteriores
- Surface 3
- Windows 10 Pro y Enterprise en Surface Hub 2

A continuación encontrarás algunos escenarios donde el Borrador de datos de Microsoft Surface puede serte útil para realizar lo siguiente:

- Preparar un dispositivo Surface para que se envíe para su reparación.
- Retirar un dispositivo Surface que se va a quitar. de uso corporativo u organizativo.
- Vuelva a usar un dispositivo Surface para usarlo en un nuevo departamento o para que lo use un usuario nuevo.
- Práctica estándar al realizar la re-creación de imágenes para dispositivos usados con datos confidenciales.

>[!NOTE]
>Los dispositivos de terceros, los dispositivos Surface que ejecutan Windows RT (incluidos Surface y Surface 2) y Surface Pro no son compatibles con el Borrador de datos de Microsoft Surface.

>[!NOTE]
>Dado que la capacidad para el arranque desde el USB es necesaria para ejecutar el Borrador de datos de Microsoft Surface, si el dispositivo no está configurado para arrancar desde el USB o si no es capaz de arrancar o realizar pruebas automáticas de encendido (POST) correctamente, el Borrador de datos de Microsoft Surface no funcionará.

>[!NOTE]
>Surface Data Eraser en Surface Studio y Surface Studio 2 pueden tardar hasta 6 minutos en arrancarse en WinPE antes de que se produzca la eliminación del disco.

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>Cómo crear un stick USB del Borrador de datos de Microsoft Surface

Para crear un stick USB del Borrador de datos de Microsoft Surface, primero debes instalar la herramienta de instalación del Borrador de datos de Microsoft Surface que encontrarás en el Centro de descarga de Microsoft, al cual podrás acceder mediante el vínculo que está al principio de este artículo. No necesitas un dispositivo Surface para *crear* el stick USB. Una vez hayas descargado el archivo de instalación en el equipo, sigue estos pasos para instalar la herramienta que te permitirá crear el Borrador de datos de Microsoft Surface.

1. Ejecute el DataEraserSetup.msi de instalación que descargó desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703).

2. Selecciona la casilla para aceptar los términos del contrato de licencia y, a continuación, haz clic en **Instalar**.

3. Haz clic en **Finalizar** para cerrar la ventana de configuración del Borrador de datos de Microsoft Surface.

Cuando tengas instalada la herramienta de creación, sigue estos pasos para crear el stick USB del Borrador de datos de Microsoft Surface. Antes de realizar estos pasos, asegúrate de que haya un stick USB 3.0 que sea de 4 GB, o mayor, conectado al equipo.

1. Inicia el Borrador de datos de Microsoft Surface en el menú Inicio o en la pantalla Inicio.

2. Haz clic en **Crear** para comenzar el proceso de creación del USB del Borrador de datos de Microsoft Surface.

3. Haz clic en **Inicio** para confirmar que tienes un stick USB de al menos 4 GB conectado, tal como se muestra en la imagen 1.

   ![Inicia la herramienta Borrador de datos de Microsoft Surface.](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Figura 1. Iniciar la herramienta del Borrador de datos de Microsoft Surface*
4. Elige **x64 para** la mayoría de dispositivos Surface o **ARM64** para Surface Pro X en la página **Selección** de arquitectura, como se muestra en la figura 2. Selecciona **Continuar**.

    ![Selección de arquitectura.](images/dataeraser-arch.png "Architecture Selection")<br>
       *Figura 2. Seleccionar arquitectura de dispositivo*

5. Selecciona la unidad USB que **** prefieras en la página Selección de unidad **** usb como se muestra en la figura 3 y, a continuación, haz clic en Inicio para iniciar el proceso de creación de USB. Se formateará la unidad que selecciones y los datos que tengas guardados en esa unidad se perderán.

   >[!TIP]
   >Si ves que el botón Inicio está deshabilitado, comprueba que la unidad extraíble tenga una capacidad total de 4 GB, como mínimo.
  
   ![Selección de unidad usb.](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Figura 3. Selección de unidad USB*

6. Después de finalizar el proceso de creación, verás que se ha formateado la unidad USB y que tiene copiados todos los archivos binarios. Haz clic en **Finalizó con éxito**.

7. Cuando veas la pantalla de **Enhorabuena**, podrás expulsar y retirar la unidad USB. De esta manera, ya tienes la unidad lista para conectarla a un dispositivo Surface, arrancarlo desde esa unidad y eliminar cualquier dato del dispositivo. Haga **clic en** Completar para finalizar el proceso de creación de USB, como se muestra en la figura 4.

   ![Proceso de creación de Surface Data Eraser USB.](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Figura 4. Completar el proceso de creación del USB del Borrador de datos de Microsoft Surface*

8. Haz clic en **X** para cerrar el Borrador de datos de Microsoft Surface.

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>Cómo usar un stick USB del Borrador de datos de Microsoft Surface

Después de crear un stick USB del Borrador de datos de Microsoft Surface, puedes arrancar un dispositivo Surface compatible desde la memoria USB, si sigues estos pasos:

1. Inserta el stick USB de arranque del Borrador de datos de Microsoft Surface en el dispositivo Surface compatible.

2. Arranca el dispositivo Surface desde el stick USB del Borrador de datos de Microsoft Surface. Para arrancar el dispositivo desde el stick USB, sigue estos pasos:

   a. Desactiva el dispositivo Surface.
   b. Mantén presionado el botón **Bajar el volumen**.
   c. Presiona y suelta el botón **Inicio/Apagado**.
   d. Suelta el botón para **Bajar el volumen**.

   >[!TIP]
   >Si el dispositivo no arranca desde USB tras seguir estos pasos, es posible que debas activar la opción **Enable Alternate Boot Sequence** en la UEFI de Surface. Puedes leer más sobre la configuración de arranque de la UEFI de Surface en [Administrar la configuración de la UEFI de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Cuando se inicia el dispositivo Surface, se muestra un archivo de texto **SoftwareLicenseTerms,** como se muestra en la figura 5.

   ![Arranque del stick USB borrador de datos de Microsoft Surface.](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Figura 5. Arrancar el stick USB del Borrador de datos de Microsoft Surface*

4. Lee los términos de licencia de software y luego cierra el archivo del Bloc de notas.

5. Para aceptar o rechazar los términos de licencia de software, escribe **Aceptar** o **Rechazar**. Debes aceptar los términos de licencia para continuar.

6. El script del Borrador de datos de Microsoft Surface detecta los dispositivos de almacenamiento que están presentes en el dispositivo Surface y muestra los detalles del dispositivo de almacenamiento nativo. Para continuar, presiona **Y** (esta acción ejecuta el Borrador de datos de Microsoft Surface y quita todos los datos del dispositivo de almacenamiento) o presiona **N** (esta acción apaga el dispositivo sin quitar los datos).

   >[!CAUTION]
   >La herramienta Borrador de datos de Microsoft Surface eliminará todos los datos, incluidos los archivos del sistema operativo Windows necesarios para arrancar el dispositivo, de forma segura e irrecuperable. Para arrancar un dispositivo Surface que se ha borrado con el Borrador de datos de Microsoft Surface, primero deberás reinstalar el sistema operativo Windows. Para quitar los datos de un dispositivo Surface sin quitar el sistema operativo Windows, puedes usar la función **Restablecer tu PC**. Sin embargo, esto no impide que se recuperen los datos mediante capacidades forenses o de recuperación de datos. Para obtener más información, consulta [Opciones de recuperación de Windows10](https://support.microsoft.com/help/12415/windows-10-recovery-options).

   ![Se muestra la partición que se va a borrar.](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Figura 6. La partición que se borrará se muestra en el Borrador de datos de Microsoft Surface*

7. Si presionaste **Y** en el paso 6, debido a la naturaleza destructiva del proceso de eliminación de datos, se muestra un cuadro de diálogo adicional para confirmar tu elección.

8. Haz clic en el botón **Sí** para continuar con el borrado de datos del dispositivo Surface.

   >[!TIP]
   >Al ejecutar el Borrador de datos Surface en la unidad USB del Borrador de datos Surface, se genera un archivo de registro en la carpeta **SurfaceDataEraserLogs**.

## <a name="changes-and-updates"></a>Cambios y actualizaciones

Microsoft actualiza de vez en cuando el Borrador de datos de Microsoft Surface. Para obtener información sobre los cambios que se proporcionan en cada nueva versión, consulta lo siguiente:

### <a name="3391390"></a>3.39.139.0

*Fecha de lanzamiento: 13 de abril de 2021*

Esta versión del Borrador de datos de Surface incluye:

- Compatibilidad con Surface Laptop 4

### <a name="2341390"></a>2.34.139.0

*Fecha de lanzamiento: 15 de enero de 2021*

Esta versión de Surface Data Eraser:

- Incluye correcciones de errores

### <a name="333139"></a>3.33.139

*Fecha de lanzamiento: 9 de septiembre de 2020*

Esta versión de Surface Data Eraser incluye correcciones de errores y agrega compatibilidad para: 

- Volver a diseñar la arquitectura para reducir la necesidad de actualizar con las nuevas versiones de productos
- Notificación disponible para actualizaciones de nuevas herramientas
- Adiciones de telemetría
- Windows 10 Pro y Enterprise en Surface Hub 2

### <a name="330139"></a>3.30.139

*Fecha de lanzamiento: 11 de mayo de 2020*

Esta versión de Surface Data Eraser agrega compatibilidad para:

- Surface Book 3
- Surface Go 2
- Nueva SSD en Surface Go

### <a name="328137"></a>3.28.137

*Fecha de lanzamiento: 11 de noviembre de 2019*

Esta versión de Surface Data Eraser:

- Incluye correcciones de errores

### <a name="version-321137"></a>Versión 3.21.137

*Fecha de lanzamiento: 21 de octubre de 2019*

Esta versión de Surface Data Eraser se compila para x86 y agrega compatibilidad con los siguientes dispositivos:

- Surface Pro 7, Surface Pro X y Surface Laptop 3

### <a name="version-32780"></a>Versión 3.2.78.0

*Fecha de lanzamiento: 4 de diciembre de 2018*

Esta versión de Surface Data Eraser:

- Incluye correcciones de errores

### <a name="version-32750"></a>Versión 3.2.75.0

*Fecha de lanzamiento: 12 de noviembre de 2018*

Esta versión de Surface Data Eraser:

- Agrega compatibilidad a Surface Studio 2
- Corrige problemas con la tarjeta SD

### <a name="version-32690"></a>Versión 3.2.69.0

*Fecha de lanzamiento: 12 de octubre de 2018*

Esta versión de Surface Data Eraser agrega compatibilidad con lo siguiente:

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>Versión 3.2.68.0

Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Go

### <a name="version-32580"></a>Versión 3.2.58.0

Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Dispositivos de almacenamiento adicionales (unidades) para Surface Pro y Surface Laptop dispositivos

### <a name="version-32460"></a>Versión 3.2.46.0

Esta versión del Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Pro con LTE avanzada

### <a name="version-32450"></a>Versión 3.2.45.0

Esta versión del Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Book 2
- Surface Pro 1TB

   >[!NOTE]
   >El Borrador de datos de Surface v3.2.45.0 y versiones superiores puede usarse para restablecer dispositivos Surface Pro o Surface Laptop con la opción de almacenamiento de 1TB en el caso de que el dispositivo muestre dos volúmenes de 512GB independientes o se encuentre con errores al tratar de implementar o instalar Windows10. Consulta [Surface Pro modelo 1796 y Surface Laptop 1TB muestran dos unidades](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives) para obtener más información.

### <a name="version-32360"></a>Versión 3.2.36.0

Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Pro
- Surface Laptop

>[!NOTE]
>La herramienta de creación de unidad USB del Borrador de datos de Microsoft Surface no se puede ejecutar en Windows 10S. Para borrar un dispositivo Surface Laptop que ejecuta Windows 10S, primero debes crear la unidad USB del Borrador de datos de Microsoft Surface en otro equipo con Windows 10 Pro o Windows 10 Enterprise.

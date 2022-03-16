---
title: Borrador de datos de Microsoft Surface (Surface)
description: La herramienta Borrador de datos de Microsoft Surface te permite borrar de forma segura los datos de tus dispositivos Surface.
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
ms.date: 10/06/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e40c967003fc6dd40725e5015c01497eb3fa141a
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449653"
---
# <a name="microsoft-surface-data-eraser"></a>Borrador de datos de Microsoft Surface

Descubre cómo puedes usar la herramienta Borrador de datos de Microsoft Surface para eliminar los datos de tus dispositivos Surface de manera segura.

[Borrador de datos de Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703) es una herramienta que se inicia desde un stick USB y que te permite borrar con seguridad todos los datos de un dispositivo Surface compatible. Para iniciar el stick USB del Borrador de datos Microsoft Surface únicamente necesitas un puerto USB. Para obtener más información acerca de las funcionalidades y las prácticas para borrar los datos que Microsoft usa durante el proceso de servicio de Surface, consulta [P+F: proteger sus datos si envía su Surface para reparación](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Borrador de datos de Microsoft Surface usa el comando de formato NVM Express (NVMe) para borrar los datos según se autoriza en [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf).

Los dispositivos Surface compatibles incluyen:

- SurfaceLaptopStudio
- Surface Book (todas las ediciones)
- Surface Go (todas las ediciones)
- Surface Pro X (todas las ediciones)
- Surface Laptop (todas las ediciones)
- Surface Laptop Go
- Surface Studio (todas las ediciones)
- Surface Pro 2 y posteriores
- Surface 3
- Windows 10 Pro y Enterprise en Surface Hub 2

A continuación encontrarás algunos escenarios donde el Borrador de datos de Microsoft Surface puede serte útil para realizar lo siguiente:

- Preparar un dispositivo Surface para que se envíe para su reparación.
- Retirar un dispositivo Surface del uso corporativo u organizativo.
- Reutilizar un dispositivo Surface para un nuevo usuario.
- Reimagen dispositivos que contienen datos confidenciales.

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>Cómo crear un stick USB del Borrador de datos de Microsoft Surface

Cuando tengas instalada la herramienta de creación, sigue estos pasos para crear el stick USB del Borrador de datos de Microsoft Surface. Antes de realizar estos pasos, asegúrate de que haya un stick USB 3.0 que sea de 4 GB, o mayor, conectado al equipo.

1. Ejecute el DataEraserSetup.msi de instalación que descargó desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703).

2. Selecciona **Crear** para iniciar el proceso de creación usb del Borrador de datos de Microsoft Surface, como se muestra en la figura 1.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig1-build.png" alt-text="Figura 1. Iniciar la herramienta Borrador de datos de Microsoft Surface":::<br>
  *Figura 1. Iniciar la herramienta Borrador de datos de Microsoft Surface*

3. Seleccione **Continuar** para confirmar que tiene una unidad USB de al menos 4 GB conectada, como se muestra en la figura 2.
   
   :::image type="content" source="images/microsoft-surface-data-eraser/fig2-continue.png" alt-text="Figura 2. Confirmar que la unidad USB de al menos 4 GB está conectada":::<br>
   *Figura 2. Confirmar que la unidad USB de al menos 4 GB está conectada*

4. Elija **x64 (solo para dispositivos 2021+)** para dispositivos 2021 o más recientes, elija **x64** para dispositivos 2020 y anteriores o **ARM64** para Surface Pro X en la página **** Selección de arquitectura, como se muestra en la figura 3. Selecciona **Continuar**.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig3-select.png" alt-text="Figura 3. Seleccionar arquitectura de dispositivo":::

5. Selecciona la unidad USB que prefieras en la **** página Selección de la unidad usb como se muestra en la figura 4 y, **** a continuación, selecciona Inicio para iniciar el proceso de creación usb. Se formateará la unidad que selecciones y los datos que tengas guardados en esa unidad se perderán.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig4-start.png" alt-text="Figura 4. Selección de unidad usb>":::<br>
   *Figura 4. Selección de unidad USB*

  >[!TIP]
   >Si ves que el botón Inicio está deshabilitado, comprueba que la unidad extraíble tenga una capacidad total de 4 GB, como mínimo.

6. Después de finalizar el proceso de creación, verás que se ha formateado la unidad USB y que tiene copiados todos los archivos binarios. Seleccione **Correcto**.

7. Cuando veas la pantalla de **Enhorabuena**, podrás expulsar y retirar la unidad USB. De esta manera, ya tienes la unidad lista para conectarla a un dispositivo Surface, arrancarlo desde esa unidad y eliminar cualquier dato del dispositivo. Seleccione **Completar** para finalizar el proceso de creación usb, como se muestra en la figura 5.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig5-complete.png" alt-text="Completar la herramienta Borrador de datos de Microsoft Surface":::<br>
   *Figura 5. Completar el proceso de creación del USB del Borrador de datos de Microsoft Surface*

8. Selecciona **X** para cerrar El borrador de datos de Microsoft Surface.

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>Cómo usar un stick USB del Borrador de datos de Microsoft Surface

Después de crear un stick USB del Borrador de datos de Microsoft Surface, puedes arrancar un dispositivo Surface compatible desde la memoria USB, si sigues estos pasos:

>[!NOTE]
>Surface Data Eraser en Surface Studio y Surface Studio 2 pueden tardar hasta 6 minutos en arrancar en WinPE antes de que se produzca la eliminación del disco.

1. Inserta el stick USB de arranque del Borrador de datos de Microsoft Surface en el dispositivo Surface compatible.

2. Arranca el dispositivo Surface desde el stick USB del Borrador de datos de Microsoft Surface. Para arrancar el dispositivo desde el stick USB, sigue estos pasos:

   a. Desactiva el dispositivo Surface.
   b. Mantén presionado el botón **Bajar el volumen**.
   c. Presiona y suelta el botón **Inicio/Apagado**.
   d. Suelta el botón para **Bajar el volumen**.

   >[!TIP]
   >Si el dispositivo no arranca desde USB tras seguir estos pasos, es posible que debas activar la opción **Enable Alternate Boot Sequence** en la UEFI de Surface. Puedes leer más sobre la configuración de arranque de la UEFI de Surface en [Administrar la configuración de la UEFI de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Cuando se inicia el dispositivo Surface, se muestra un archivo de texto **SoftwareLicenseTerms** , como se muestra en la figura 5.

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

8. Selecciona **Sí** para continuar borrando datos en el dispositivo Surface.

   >[!TIP]
   >Al ejecutar el Borrador de datos Surface en la unidad USB del Borrador de datos Surface, se genera un archivo de registro en la carpeta **SurfaceDataEraserLogs**.

## <a name="changes-and-updates"></a>Cambios y actualizaciones

Microsoft actualiza de vez en cuando el Borrador de datos de Microsoft Surface. Para obtener información sobre los cambios que se proporcionan en cada nueva versión, consulta lo siguiente:

### <a name="3421390"></a>3.42.139.0

*Fecha de lanzamiento: 5 de octubre de 2021*

Esta versión del Borrador de datos de Surface incluye:

- Opción independiente para 2021 y compatibilidad con dispositivos más recientes, incluidos Surface Laptop Studio, Surface Pro 8 y Surface Go 3.

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

- SurfaceBook3
- SurfaceGo2
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

- Agrega compatibilidad con Surface Studio 2
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
>La herramienta de creación de la unidad USB borrador de datos de Microsoft Surface no se puede ejecutar en Windows 10 S. Para borrar un Surface Laptop que ejecuta Windows 10 S, primero debes crear la unidad USB borrador de datos de Microsoft Surface en otro equipo con Windows 10/11 Pro o Windows 10/11 Enterprise.

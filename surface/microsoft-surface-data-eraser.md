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
ms.date: 09/18/2020
ms.openlocfilehash: dc1a9b4480f37af6d74699a2e693ef8d5318da76
ms.sourcegitcommit: 8bd03770279d5e53446436781226ffd51eeec916
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "11029234"
---
# Borrador de datos de Microsoft Surface


Descubre cómo puedes usar la herramienta Borrador de datos de Microsoft Surface para eliminar los datos de tus dispositivos Surface de manera segura.

[Borrador de datos de Microsoft Surface](https://www.microsoft.com/download/details.aspx?id=46703) es una herramienta que se inicia desde un stick USB y que te permite borrar con seguridad todos los datos de un dispositivo Surface compatible. Para iniciar el stick USB del Borrador de datos Microsoft Surface únicamente necesitas un puerto USB. Asimismo, te resultará simple crear el stick USB si usas el asistente proporcionado a tal fin: el Contenedor de borrado de datos de Microsoft Surface; este asistente es muy fácil de usar ya que tiene una interfaz gráfica sencilla y no precisa de una línea de comandos. Para obtener más información acerca de las funcionalidades y las prácticas para borrar los datos que Microsoft usa durante el proceso de servicio de Surface, consulta [P+F: proteger sus datos si envía su Surface para reparación](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Borrador de datos de Microsoft Surface usa el comando de formato NVM Express (NVMe) para borrar los datos según se autoriza en [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf). 

Los dispositivos Surface compatibles incluyen:

- Surface Book (todas las ediciones)
- Surface Go (todas las ediciones)
- Surface Pro X (todas las ediciones)
- Portátil Surface (todas las ediciones)
- Surface Studio (todas las ediciones)
- Surface Pro 2 y posterior
- Windows 10 Pro y Enterprise en Surface Hub 2

A continuación encontrarás algunos escenarios donde el Borrador de datos de Microsoft Surface puede serte útil para realizar lo siguiente:

-   Preparar un dispositivo Surface que se enviará a reparar

-   Retirar un dispositivo Surface que ya no se usará en la empresa u organización

-   Reasignar un dispositivo Surface y así poder usarlo en un nuevo departamento o para que lo use un nuevo usuario

-   Como práctica habitual cuando se restablece la imagen inicial de aquellos dispositivos que poseen datos confidenciales

>[!NOTE]
>Los dispositivos de terceros, los dispositivos Surface que ejecutan Windows RT (incluidos Surface y Surface 2) y Surface Pro no son compatibles con el Borrador de datos de Microsoft Surface.

>[!NOTE]
>Dado que la capacidad para el arranque desde el USB es necesaria para ejecutar el Borrador de datos de Microsoft Surface, si el dispositivo no está configurado para arrancar desde el USB o si no es capaz de arrancar o realizar pruebas automáticas de encendido (POST) correctamente, el Borrador de datos de Microsoft Surface no funcionará.

>[!NOTE]
>El borrador de datos de superficie en Surface Studio y Surface Studio 2 puede demorar hasta 6 minutos en iniciar WinPE antes de que se produzca la eliminación de disco.


## Cómo crear un stick USB del Borrador de datos de Microsoft Surface


Para crear un stick USB del Borrador de datos de Microsoft Surface, primero debes instalar la herramienta de instalación del Borrador de datos de Microsoft Surface que encontrarás en el Centro de descarga de Microsoft, al cual podrás acceder mediante el vínculo que está al principio de este artículo. No necesitas un dispositivo Surface para *crear* el stick USB. Una vez hayas descargado el archivo de instalación en el equipo, sigue estos pasos para instalar la herramienta que te permitirá crear el Borrador de datos de Microsoft Surface.

1.  Ejecute el DataEraserSetup.msi archivo de instalación que ha descargado desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703).

2.  Selecciona la casilla para aceptar los términos del contrato de licencia y, a continuación, haz clic en **Instalar**.

3.  Haz clic en **Finalizar** para cerrar la ventana de configuración del Borrador de datos de Microsoft Surface.

Cuando tengas instalada la herramienta de creación, sigue estos pasos para crear el stick USB del Borrador de datos de Microsoft Surface. Antes de realizar estos pasos, asegúrate de que haya un stick USB 3.0 que sea de 4 GB, o mayor, conectado al equipo.

1. Inicia el Borrador de datos de Microsoft Surface en el menú Inicio o en la pantalla Inicio.

2. Haz clic en **Crear** para comenzar el proceso de creación del USB del Borrador de datos de Microsoft Surface. 

3. Haz clic en **Inicio** para confirmar que tienes un stick USB de al menos 4 GB conectado, tal como se muestra en la imagen 1.

   ![Iniciar la herramienta del Borrador de datos de Microsoft Surface](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *Figura 1. Iniciar la herramienta del Borrador de datos de Microsoft Surface*
4.  Elija **x64** para la mayoría de los dispositivos de la superficie o  **ARM64** para Surface Pro X en la página de **selección de arquitectura** , como se muestra en la ilustración 2. Selecciona **Continuar**.

    ![Selección de arquitectura](images/dataeraser-arch.png "Architecture Selection")<br>
       *Figura 2. Seleccionar arquitectura de dispositivo*
    

4. Seleccione la unidad USB que elija en la página de **selección de unidad USB** , como se muestra en la ilustración 3 y, a continuación, haga clic en **iniciar** para iniciar el proceso de creación de USB. Se formateará la unidad que selecciones y los datos que tengas guardados en esa unidad se perderán.

   >[!NOTE]
   >Si ves que el botón Inicio está deshabilitado, comprueba que la unidad extraíble tenga una capacidad total de 4 GB, como mínimo.
  
   ![Selección de unidad USB](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *Figura 3. Selección de unidad USB*

5. Después de finalizar el proceso de creación, verás que se ha formateado la unidad USB y que tiene copiados todos los archivos binarios. Haz clic en **Finalizó con éxito**.

6. Cuando veas la pantalla de **Enhorabuena**, podrás expulsar y retirar la unidad USB. De esta manera, ya tienes la unidad lista para conectarla a un dispositivo Surface, arrancarlo desde esa unidad y eliminar cualquier dato del dispositivo. Haga clic en **Finalizar** para finalizar el proceso de creación de USB, como se muestra en la ilustración 4.

   ![Proceso de creación del USB del Borrador de datos de Surface](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *Figura 4. Completar el proceso de creación del USB del Borrador de datos de Microsoft Surface*

7. Haz clic en **X** para cerrar el Borrador de datos de Microsoft Surface.

## Cómo usar un stick USB del Borrador de datos de Microsoft Surface


Después de crear un stick USB del Borrador de datos de Microsoft Surface, puedes arrancar un dispositivo Surface compatible desde la memoria USB, si sigues estos pasos:

1. Inserta el stick USB de arranque del Borrador de datos de Microsoft Surface en el dispositivo Surface compatible.

2. Arranca el dispositivo Surface desde el stick USB del Borrador de datos de Microsoft Surface. Para arrancar el dispositivo desde el stick USB, sigue estos pasos:

   a. Desactiva el dispositivo Surface.

   b. Mantén presionado el botón **Bajar el volumen**.

   c. Presiona y suelta el botón **Inicio/Apagado**.

   d. Suelta el botón para **Bajar el volumen**.
    
   >[!NOTE]
   >Si el dispositivo no arranca desde USB tras seguir estos pasos, es posible que debas activar la opción **Enable Alternate Boot Sequence** en la UEFI de Surface. Puedes leer más sobre la configuración de arranque de la UEFI de Surface en [Administrar la configuración de la UEFI de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. Cuando se inicia el dispositivo Surface, se muestra un archivo de texto **SoftwareLicenseTerms** , tal como se muestra en la figura 5.

   ![Arrancar el stick USB del Borrador de datos de Microsoft Surface](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *Figura 5. Arrancar el stick USB del Borrador de datos de Microsoft Surface*

4. Lee los términos de licencia de software y luego cierra el archivo del Bloc de notas.

5. Para aceptar o rechazar los términos de licencia de software, escribe **Aceptar** o **Rechazar**. Debes aceptar los términos de licencia para continuar.

6. El script del Borrador de datos de Microsoft Surface detecta los dispositivos de almacenamiento que están presentes en el dispositivo Surface y muestra los detalles del dispositivo de almacenamiento nativo. Para continuar, presiona **Y** (esta acción ejecuta el Borrador de datos de Microsoft Surface y quita todos los datos del dispositivo de almacenamiento) o presiona **N** (esta acción apaga el dispositivo sin quitar los datos).

   >[!NOTE]
   >La herramienta Borrador de datos de Microsoft Surface eliminará todos los datos, incluidos los archivos del sistema operativo Windows necesarios para arrancar el dispositivo, de forma segura e irrecuperable. Para arrancar un dispositivo Surface que se ha borrado con el Borrador de datos de Microsoft Surface, primero deberás reinstalar el sistema operativo Windows. Para quitar los datos de un dispositivo Surface sin quitar el sistema operativo Windows, puedes usar la función **Restablecer tu PC**. Sin embargo, esto no impide que se recuperen los datos mediante capacidades forenses o de recuperación de datos. Para obtener más información, consulta [Opciones de recuperación de Windows10](https://support.microsoft.com/help/12415/windows-10-recovery-options).

   ![Se muestra la partición que se borrará](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *Figura 6. La partición que se borrará se muestra en el Borrador de datos de Microsoft Surface*

7. Si presionaste **Y** en el paso 6, debido a la naturaleza destructiva del proceso de eliminación de datos, se muestra un cuadro de diálogo adicional para confirmar tu elección.

8. Haz clic en el botón **Sí** para continuar con el borrado de datos del dispositivo Surface.

   >[!NOTE]
   >Al ejecutar el Borrador de datos Surface en la unidad USB del Borrador de datos Surface, se genera un archivo de registro en la carpeta **SurfaceDataEraserLogs**.

## Cambios y actualizaciones

Microsoft actualiza de vez en cuando el Borrador de datos de Microsoft Surface. Para obtener información sobre los cambios que se proporcionan en cada nueva versión, consulta lo siguiente:

### 3.33.139
*Fecha de lanzamiento: 9 de septiembre de 2020*

Esta versión del borrador de datos de superficie incluye correcciones de errores y agrega compatibilidad con: 

- Rediseño de arquitectura para reducir la necesidad de actualizar con nuevas versiones de productos
- Notificación disponible para nuevas actualizaciones de herramientas
- Adiciones de telemetría
- Windows 10 Pro y Enterprise en Surface Hub 2


### 3.30.139
*Fecha de lanzamiento: 11 de mayo de 2020*

Esta versión del borrador de datos de superficie agrega compatibilidad con: 
- Surface Book 3
- Surface Go 2
- Nuevo SSD en Surface Go

### 3.28.137
*Fecha de lanzamiento: 11 de noviembre de 2019* Esta versión del borrador de datos de superficie:

- Incluye correcciones de errores

### Versión 3.21.137
*Fecha de lanzamiento: 21 Oct 2019* Esta versión del borrador de datos de superficie está compilada para x86 y agrega compatibilidad con los siguientes dispositivos:

- Compatible con Surface Pro 7, Surface Pro X y portátil Surface 3

### Versión 3.2.78.0
*Fecha de lanzamiento: 4 Dic 2018*

Esta versión del borrador de datos de superficie:

- Incluye correcciones de errores


### Versión 3.2.75.0
*Fecha de lanzamiento: 12 de noviembre de 2018*

Esta versión del borrador de datos de superficie:

- Agrega compatibilidad a Surface Studio 2
- Soluciona problemas con la tarjeta SD

### Versión 3.2.69.0
*Fecha de lanzamiento: 12 de octubre de 2018*

Esta versión del borrador de datos de superficie agrega compatibilidad para los siguientes elementos:

- Surface Pro 6
- Surface Laptop 2

### Versión 3.2.68.0
Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Go


### Versión 3.2.58.0
Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Dispositivos de almacenamiento adicionales (unidades) para dispositivos Surface Pro y Surface portátil


### Versión 3.2.46.0
Esta versión del Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Pro con LTE avanzada


### Versión 3.2.45.0

Esta versión del Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Book 2

- Surface Pro 1TB

   >[!NOTE]
   >El Borrador de datos de Surface v3.2.45.0 y versiones superiores puede usarse para restablecer dispositivos Surface Pro o Surface Laptop con la opción de almacenamiento de 1TB en el caso de que el dispositivo muestre dos volúmenes de 512GB independientes o se encuentre con errores al tratar de implementar o instalar Windows10. Consulta [Surface Pro modelo 1796 y Surface Laptop 1TB muestran dos unidades](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives) para obtener más información.


### Versión 3.2.36.0

Esta versión de Borrador de datos de Microsoft Surface agrega compatibilidad con lo siguiente:

- Surface Pro

- Surface Laptop

>[!NOTE]
>La herramienta de creación de unidad USB del Borrador de datos de Microsoft Surface no se puede ejecutar en Windows 10S. Para borrar un dispositivo Surface Laptop que ejecuta Windows 10S, primero debes crear la unidad USB del Borrador de datos de Microsoft Surface en otro equipo con Windows 10 Pro o Windows 10 Enterprise.

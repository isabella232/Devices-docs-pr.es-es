---
title: Implementar la aplicación Surface con la Microsoft Store para Empresas o la Microsoft Store para Educación (Surface)
description: Descubre cómo agregar y descargar la aplicación Surface con la Microsoft Store para Empresas o la Microsoft Store para Educación, así como instalar la aplicación Surface con PowerShell y MDT.
keywords: aplicación surface, aplicación, implementación, personalizar
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271077"
---
# Implementar la aplicación Surface con la Microsoft Store para Empresas y Educación

**Se aplica a**

- Surface Pro 7+
- Surface Laptop Go
- Surface Pro 7
- Surface Laptop 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Surface Go con LTE
- Surface Book 2
- Surface Pro con LTE avanzada (modelo 1807)
- Surface Pro (modelo 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


La aplicación Surface es una aplicación ligera de Microsoft Store que proporciona control de muchas opciones y configuraciones específicas de Surface, entre las que se incluyen: 

* Habilitar o deshabilitar el botón Windows en el dispositivo Surface 
 

* Ajustar la sensibilidad de un Lápiz para Surface 
 

* Personalizar las acciones del botón de Lápiz para Surface 
 

* Habilitar o deshabilitar las mejoras de audio de Surface 
 

* Acceso rápido a la documentación de soporte técnico e información para el dispositivo

Normalmente, los clientes que usan Windows Update recibirán la aplicación Surface como parte de las actualizaciones automáticas. Pero si tu organización está preparando imágenes para su implementación en los dispositivos Surface, es posible que quieras incluir la aplicación Surface (anteriormente denominada Surface Hub) en el proceso de creación de imágenes e implementación en lugar de requerir que los usuarios de cada dispositivo individual descarguen e instalen la aplicación desde Microsoft Store o la Microsoft Store para Empresas. 

> [!NOTE]
> Este artículo no se aplica a Surface Pro X. Para obtener más información, consulta [Implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md)

## Introducción a la aplicación Surface

La aplicación Surface está disponible como descarga gratuita desde [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P) Los usuarios pueden descargarla e instalarla desde Microsoft Store, pero si tu organización usa la Microsoft Store para Empresas en su lugar, deberás agregarla al inventario de la tienda y posiblemente incluir la aplicación como parte del proceso de implementación de Windows. Estos procesos se de abordan a lo largo de este artículo. Para obtener más información sobre la Microsoft Store para Empresas, consulta [Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/) en el TechCenter de Windows. 

## Agregar una aplicación Surface a una cuenta de la Microsoft Store para Empresas 

Antes de que los usuarios puedan instalar o implementar una aplicación desde la cuenta de la Microsoft Store para Empresas de una empresa, las aplicaciones deseadas deben estar disponibles y tener una licencia para los usuarios de una empresa. 

1. Si aún no lo has hecho, crea una [cuenta de la Microsoft Store para Empresas.](https://www.microsoft.com/business-store) 

2. Inicie sesión en el portal. 

3. Habilita las licencias sin conexión: haz clic en **** Administrar **>** Configuración de la Tienda y, a continuación, selecciona la casilla Mostrar aplicaciones con licencia sin conexión a las personas que compran en la tienda, como se muestra en la figura 1. Para obtener más información sobre los modelos de licencias de aplicaciones de la Microsoft Store para Empresas, consulta Aplicaciones de [la Microsoft Store para Empresas y Educación.](https://docs.microsoft.com/microsoft-store/)

   > [!div class="mx-imgBorder"]
   > ![Casilla Mostrar aplicaciones de licencias sin conexión](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicaciones para su uso sin conexión*

4. Agrega la aplicación Surface a tu cuenta de la Microsoft Store para Empresas siguiendo este procedimiento:

    * Haz clic en **el menú** Tienda.
    
    * En el cuadro de búsqueda, escribe **la aplicación Surface**y, a continuación, haz clic en el icono de búsqueda.
    
    * Después de que la aplicación Surface se presente en los resultados de búsqueda, haz clic en el icono de la aplicación.
    
    * Se le presenta una opción (seleccione **En** línea o **sin**conexión), como se muestra en la figura 2.
    
      > [!div class="mx-imgBorder"]
      > ![Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figura 2. Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario*
    
    * Haga clic **en Sin** conexión para seleccionar el modo de licencias sin conexión.
    
    * Haz **clic en Obtener la** aplicación para agregarla al inventario de la Microsoft Store para Empresas. Como se muestra en la figura 3, verás un cuadro de diálogo que te pide que reconozcas que las aplicaciones sin conexión se pueden implementar mediante una herramienta de administración o descargar desde la página de inventario de la empresa en su tienda privada.
    
      > [!div class="mx-imgBorder"]
      > ![Ventana de confirmación de aplicaciones con licencia sin conexión ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *figura 3. Confirmación de la aplicación con licencia sin conexión*
      
    * Haga clic en **Aceptar**.

## Descargar la aplicación Surface desde una cuenta de la Microsoft Store para Empresas
Después de agregar una aplicación a la cuenta de la Microsoft Store para Empresas en modo sin conexión, puedes descargarla y agregarla como appxBundle a un recurso compartido de implementación.

1. Inicie sesión en la cuenta de la Microsoft Store para Empresas en https://businessstore.microsoft.com .

2. Haga **clic en Administrar >aplicaciones & software.** Se muestra una lista de todas las aplicaciones de tu empresa, incluida la aplicación Surface que agregaste en la sección Agregar aplicación Surface a una cuenta de la [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) para Empresas de este artículo.

3. En **Acciones,** haz clic en los puntos suspensivos (**...**) y, a continuación, haz clic en Descargar para su uso **sin conexión** para la aplicación Surface.

4. Seleccione las opciones **de plataforma** **y arquitectura** deseadas de las selecciones disponibles para la aplicación seleccionada, como se muestra en la figura 4.

    > [!div class="mx-imgBorder"]
    > ![Ejemplo del paquete AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figura 4. Descargar el paquete AppxBundle para una aplicación*
    
5. Haga **clic en Descargar**. Se descargará el paquete AppxBundle. Asegúrese de tomar nota de la ruta de acceso del archivo descargado porque lo necesitará más adelante en este artículo.

6. Haga clic en **la opción de licencia codificada** o **sin** codificar. Usa la opción de licencia codificada con herramientas de administración como Microsoft Endpoint Configuration Manager o cuando usas el Diseñador de configuraciones de Windows para crear un paquete de aprovisionamiento. Selecciona la opción de licencia sin codificar cuando usas administración y mantenimiento de imágenes de implementación (DISM) o soluciones de implementación basadas en imágenes, incluido Microsoft Deployment Toolkit (MDT).

7. Haz **clic en** Generar para generar y descargar la licencia de la aplicación. Asegúrese de tomar nota de la ruta de acceso del archivo de licencia, ya que lo necesitará más adelante en este artículo.

>[!NOTE]
>Al descargar una aplicación para su uso sin conexión, como la aplicación Surface, es posible que observes una sección en la parte inferior de la página con la etiqueta **Marcos necesarios.** Los equipos de destino deben tener los marcos instalados para que se ejecute la aplicación, por lo que es posible que deba repetir el proceso de descarga para cada uno de los marcos necesarios para la arquitectura (x86 o x64) e incluirlos también como parte de la implementación de Windows que se describe más adelante en este artículo.

La figura 5 muestra los marcos necesarios para la aplicación Surface.

> [!div class="mx-imgBorder"]
> ![Marcos necesarios para la aplicación Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figura 5. Marcos necesarios para la aplicación Surface*

>[!NOTE]
>Los números de versión de la aplicación Surface y los marcos necesarios cambiarán a medida que se actualicen las aplicaciones. Busca la versión más reciente de la aplicación Surface y cada marco de la Microsoft Store para Empresas. Usa siempre la aplicación Surface y las versiones de marco recomendadas según lo proporcionado por la Microsoft Store para Empresas. El uso de marcos obsoletos o las versiones incorrectas puede provocar errores o bloqueos de aplicaciones.

Para descargar los marcos necesarios para la aplicación Surface, sigue estos pasos:

1. Haga clic **en** el botón Descargar **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Esto descarga la Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Archivo Appx en la carpeta especificada.

2. Haga clic **en** el botón **Descargar Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Esto descarga el archivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx en la carpeta especificada.

>[!NOTE]
>Solo se requiere la versión de 64 bits (x64) de cada marco para dispositivos Surface. Los dispositivos Surface son dispositivos UEFI nativos de 64 bits y no son compatibles con versiones de 32 bits (x86) de Windows que requerirían marcos de 32 bits. 

## Instalar la aplicación Surface en el equipo con PowerShell
El siguiente procedimiento aprovisiona la aplicación Surface en el equipo y la pone a disposición de las cuentas de usuario creadas en el equipo posteriormente.

1. Mediante el procedimiento descrito en la sección Cómo descargar la aplicación Surface desde una cuenta de la [Microsoft Store](#download-surface-app-from-a-microsoft-store-for-business-account) para Empresas de este artículo, descarga la aplicación Surface AppxBundle y el archivo de licencia. 

2. Comienza una sesión de PowerShell con privilegios elevados.

    >[!NOTE]
    >Si no ejecuta PowerShell como administrador, la sesión no tendrá los permisos necesarios para instalar la aplicación.
    
3. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Dónde `<DownloadPath>` está la carpeta en la que descargaste el appxBundle y el archivo de licencia de la cuenta de la Microsoft Store para Empresas.

    Por ejemplo, si descargó los archivos en c:\Temp, el comando que ejecuta es:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. La aplicación Surface ahora estará disponible en tu equipo Windows actual. 

   Antes de que la aplicación Surface sea funcional en el equipo donde se ha aprovisionado, también debes aprovisionar los marcos descritos anteriormente en este artículo. Para aprovisionar estos marcos, usa el siguiente procedimiento en la sesión de PowerShell con privilegios elevados que usste para aprovisionar la aplicación Surface.

5. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Instalar la aplicación Surface con MDT
El siguiente procedimiento usa MDT para automatizar la instalación de la aplicación Surface en el momento de la implementación. MDT aprovisiona la aplicación automáticamente durante la implementación y, por lo tanto, puedes usar este proceso con las imágenes existentes. Este es el proceso recomendado para implementar la aplicación Surface como parte de una implementación de Windows en dispositivos Surface porque no reduce la compatibilidad entre plataformas de la imagen de Windows.

1. Mediante el procedimiento descrito [anteriormente en este artículo,](#download-surface-app-from-a-microsoft-store-for-business-account)descarga la aplicación Surface AppxBundle y el archivo de licencia. 

2. Con el Asistente para nueva aplicación en MDT Deployment Workbench, importa los archivos descargados como una nueva **aplicación con archivos de origen.**

3. En la **página Detalles del** comando del **** Asistente para nueva **** aplicación, especifique el directorio de trabajo predeterminado y, para el comando, especifique el nombre de archivo de AppxBundle, como se muestra a continuación:

   * Comando:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Directorio de trabajo: %DEPLOYROOT%\Applications\SurfaceApp

Para que la aplicación Surface funcione en el equipo de destino, también requerirá los marcos descritos anteriormente en este artículo. Usa el siguiente procedimiento para importar los marcos necesarios para la aplicación Surface en MDT y configurarlos como dependencias.

1. Mediante el procedimiento descrito anteriormente en este artículo, descargue los archivos de marco. Almacena cada marco en una carpeta independiente.

2. Con el Asistente para nueva aplicación en MDT Deployment Workbench, importa los archivos descargados como una nueva **aplicación con archivos de origen.**

3. En la **página Detalles del** comando, escriba el nombre **** de archivo de cada aplicación que descargó en el campo Comando y en el directorio de trabajo predeterminado.

Para configurar los marcos como dependencias de la aplicación Surface, usa este proceso:

1. Abre las propiedades de la aplicación Surface en MDT Deployment Workbench.

2. Haga clic en **la pestaña** Dependencias y, a continuación, haga clic **en Agregar**.

3. Active la casilla de cada marco con el nombre que proporcionó en el Asistente para nuevas aplicaciones.

Después de la importación, la aplicación Surface estará disponible para su selección en el paso **Aplicaciones** del Asistente para la implementación de Windows. Para instalar la aplicación automáticamente, también puedes especificar la aplicación en la secuencia de tareas de implementación siguiendo este proceso:

1. Abre la secuencia de tareas de implementación en Deployment Workbench de MDT.

2. Agrega una nueva tarea **Instalar aplicación** en la sección **Restaurar estado** de la implementación.

3. Selecciona **Instalar una sola aplicación y** especifica la aplicación **Surface** como la aplicación que **se instalará.**

Para obtener más información sobre cómo incluir aplicaciones en las implementaciones de Windows, consulta [Implementar Windows 10 con Microsoft Deployment Toolkit.](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)

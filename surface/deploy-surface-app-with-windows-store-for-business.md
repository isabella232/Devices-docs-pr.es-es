---
title: Implementar la aplicación Surface con Microsoft Store para Empresas o Microsoft Store para Educación (Surface)
description: Descubra cómo agregar y descargar la aplicación Surface con Microsoft Store para Empresas o Microsoft Store para Educación, así como instalar la aplicación Surface con PowerShell y MDT.
keywords: aplicación surface, aplicación, implementación, personalización
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
ms.date: 4/16/2021
ms.openlocfilehash: 463f5670c5e2b7eac9ac7a41b5b2b04da3ebb83e
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911185"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a>Implementar la aplicación Surface con Microsoft Store para Empresas y Educación

**Aplicable a**

- Surface Laptop 4
- Surface Pro 7+
- Surface Laptop Ir
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


La aplicación Surface es una aplicación Microsoft Store ligera que proporciona control de muchas opciones y configuraciones específicas de Surface con acceso rápido a la información del dispositivo, incluido el número de serie, el nombre del modelo de Surface, la versión UEFI y los controladores relacionados.  

Los clientes que Windows update recibirán normalmente la aplicación Surface como parte de las actualizaciones automáticas. Pero si tu organización prepara imágenes para la implementación en tus dispositivos Surface, es posible que quieras incluir la aplicación Surface (anteriormente denominada Surface Hub) en el proceso de creación de imágenes e implementación en lugar de requerir que los usuarios de cada dispositivo individual descarguen e instalen la aplicación desde el Microsoft Store o desde tu Microsoft Store para Empresas. 

> [!NOTE]
> Este artículo no se aplica a Surface Pro X. Para obtener más información, consulte [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)

## <a name="surface-app-overview"></a>Introducción a la aplicación Surface

La aplicación Surface está disponible como descarga gratuita desde el [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Los usuarios pueden descargarlo e instalarlo desde el Microsoft Store, pero si su organización usa Microsoft Store para Empresas en su lugar, tendrá que agregarlo al inventario de la tienda y posiblemente incluir la aplicación como parte del proceso de implementación de Windows. Estos procesos se de abordan a lo largo de este artículo. Para obtener más información Microsoft Store para Empresas, vea [Microsoft Store para Empresas](/microsoft-store/). 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a>Agregar aplicación Surface a una cuenta Microsoft Store para Empresas usuario 

Para que los usuarios puedan instalar o implementar una aplicación desde la cuenta de Microsoft Store para Empresas de una empresa, las aplicaciones deseadas primero deben estar disponibles y con licencia para los usuarios de una empresa. 

1. Si aún no lo ha hecho, cree una [cuenta Microsoft Store para Empresas .](https://www.microsoft.com/business-store) 

2. Inicie sesión en el portal. 

3. Habilitar licencias sin **** conexión: haga clic en Administrar Configuración y, a continuación, active la casilla Mostrar aplicaciones con licencia sin conexión a las personas que compran en la tienda, como se muestra en la  >  **** figura 1. **** Para obtener más información sobre Microsoft Store para Empresas de licencias de aplicaciones, [consulta Aplicaciones en Microsoft Store para Empresas y Educación](/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Casilla Mostrar aplicaciones de licencias sin conexión.](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicaciones para uso sin conexión*

4. Agrega la aplicación Surface a tu Microsoft Store para Empresas cuenta:

    * Buscar en la tienda la **aplicación Surface** 
    
    * Después de que la aplicación Surface se presente en los resultados de la búsqueda, haz clic en el icono de la aplicación.
    
    * Se le presenta una opción (seleccione **En** línea o **sin**conexión), como se muestra en la figura 2.
    
      > [!div class="mx-imgBorder"]
      > ![Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figura 2. Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario*
    
    * Haga **clic en Sin** conexión para seleccionar el modo de licencias sin conexión.
    
    * Haz **clic en Obtener la aplicación** para agregar la aplicación a tu Microsoft Store para Empresas inventario. Como se muestra en la figura 3, verás un cuadro de diálogo que te pedirá que reconozcas que las aplicaciones sin conexión se pueden implementar con una herramienta de administración o descargarse desde la página de inventario de la compañía en su tienda privada.
    
      > [!div class="mx-imgBorder"]
      > ![Ventana de confirmación de la aplicación con licencia sin conexión. ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *Figura 3. Confirmación de la aplicación con licencia sin conexión*
      
    * Haga clic en **Aceptar**.

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a>Descargar la aplicación Surface desde una cuenta Microsoft Store para Empresas usuario
Después de agregar una aplicación a la cuenta Microsoft Store para Empresas en modo sin conexión, puedes descargar y agregar la aplicación como AppxBundle a un recurso compartido de implementación.

1. Inicie sesión en la cuenta Microsoft Store para Empresas en https://businessstore.microsoft.com .

2. Haga **clic en Administrar >aplicaciones & software**. Se muestra una lista de todas las aplicaciones de tu empresa, incluida la aplicación Surface que agregaste en la sección Agregar aplicación [Surface a](#add-surface-app-to-a-microsoft-store-for-business-account) una cuenta Microsoft Store para Empresas de este artículo.

3. En **Acciones**, haz clic en los puntos suspensivos (**...**) y, a continuación, haz clic en Descargar para usar **sin conexión** para la aplicación Surface.

4. Seleccione las opciones **de plataforma** **y arquitectura** deseadas de las selecciones disponibles para la aplicación seleccionada, como se muestra en la figura 4.

    > [!div class="mx-imgBorder"]
    > ![Ejemplo del paquete AppxBundle.](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figura 4. Descargar el paquete AppxBundle para una aplicación*
    
5. Haga clic **en Descargar**. Se descargará el paquete AppxBundle. Asegúrese de tener en cuenta la ruta de acceso del archivo descargado porque lo necesitará más adelante en este artículo.

6. Haga clic en **la opción Licencia codificada** o **Licencia sin codificar.** Use la opción De licencia codificada con herramientas de administración como Microsoft Endpoint Configuration Manager o cuando use Windows Configuration Designer para crear un paquete de aprovisionamiento. Seleccione la opción Licencia sin codificar cuando use administración y mantenimiento de imágenes de implementación (DISM) o soluciones de implementación basadas en imágenes, incluida la Toolkit de implementación de Microsoft (MDT).

7. Haz **clic en** Generar para generar y descargar la licencia de la aplicación. Asegúrese de tener en cuenta la ruta de acceso del archivo de licencia, ya que lo necesitará más adelante en este artículo.

>[!NOTE]
>Al descargar una aplicación para uso sin conexión, como la aplicación Surface, es posible que observes una sección en la parte inferior de la página con la etiqueta **Marcos obligatorios**. Los equipos de destino deben tener los marcos instalados para que se ejecute la aplicación, por lo que es posible que deba repetir el proceso de descarga para cada uno de los marcos necesarios para la arquitectura (x86 o x64) y también incluirlos como parte de la implementación de Windows que se describe más adelante en este artículo.

En la figura 5 se muestran los marcos necesarios para la aplicación Surface.

> [!div class="mx-imgBorder"]
> ![Marcos necesarios para la aplicación Surface.](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figura 5. Marcos necesarios para la aplicación Surface*

>[!NOTE]
>Los números de versión de la aplicación Surface y los marcos necesarios cambiarán a medida que se actualicen las aplicaciones. Busca la versión más reciente de la aplicación Surface y cada marco en Microsoft Store para Empresas. Usa siempre la aplicación Surface y las versiones recomendadas del marco según lo Microsoft Store para Empresas. El uso de marcos obsoletos o las versiones incorrectas puede provocar errores o bloqueos de aplicaciones.

Para descargar los marcos necesarios para la aplicación Surface, sigue estos pasos:

1. Haga clic **en** el botón **Descargar Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**. Esto descarga el Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Appx en la carpeta especificada.

2. Haga clic **en** el botón **Descargar Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**. Esto descarga el archivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx en la carpeta especificada.

>[!NOTE]
>Solo se requiere la versión de 64 bits (x64) de cada marco para dispositivos Surface. Los dispositivos Surface son dispositivos UEFI nativos de 64 bits y no son compatibles con las versiones de 32 bits (x86) de Windows que requerirían marcos de 32 bits. 

## <a name="install-surface-app-on-your-computer-with-powershell"></a>Instalar la aplicación Surface en el equipo con PowerShell
El siguiente procedimiento aprovisiona la aplicación Surface en el equipo y la hace disponible para las cuentas de usuario creadas en el equipo posteriormente.

1. Mediante el procedimiento descrito en la sección Cómo descargar la aplicación Surface desde una cuenta de [Microsoft Store para Empresas](#download-surface-app-from-a-microsoft-store-for-business-account) de este artículo, descarga la aplicación Surface AppxBundle y el archivo de licencia. 

2. Comienza una sesión de PowerShell con privilegios elevados.

    >[!NOTE]
    >Si no ejecuta PowerShell como administrador, la sesión no tendrá los permisos necesarios para instalar la aplicación.
    
3. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Dónde `<DownloadPath>` es la carpeta en la que descargó el archivo appxBundle y la licencia de la Microsoft Store para Empresas cuenta.

    Por ejemplo, si descargó los archivos a c:\Temp, el comando que ejecuta es:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. La aplicación Surface ahora estará disponible en tu equipo Windows actual. 

   Antes de que la aplicación Surface sea funcional en el equipo donde se ha aprovisionado, también debes aprovisionar los marcos descritos anteriormente en este artículo. Para aprovisionar estos marcos, use el siguiente procedimiento en la sesión de PowerShell con privilegios elevados que usó para aprovisionar la aplicación Surface.

5. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a>Instalar la aplicación Surface con MDT
El siguiente procedimiento usa MDT para automatizar la instalación de la aplicación Surface en el momento de la implementación. MDT aprovisiona la aplicación automáticamente durante la implementación y, por lo tanto, puedes usar este proceso con las imágenes existentes. Este es el proceso recomendado para implementar la aplicación Surface como parte de una implementación de Windows en dispositivos Surface porque no reduce la compatibilidad entre plataformas de la Windows imagen.

1. Mediante el procedimiento descrito [anteriormente en este artículo,](#download-surface-app-from-a-microsoft-store-for-business-account)descarga la aplicación Surface AppxBundle y el archivo de licencia. 

2. Con el Asistente para nueva aplicación en MDT Deployment Workbench, importe los archivos descargados como una **nueva aplicación con archivos de origen.**

3. En la **página Detalles del** comando del **** Asistente para nueva aplicación, especifique el directorio de trabajo predeterminado y, para el **comando,** especifique el nombre de archivo de AppxBundle de la siguiente manera:

   * Comando:
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Directorio de trabajo: %DEPLOYROOT%\Applications\SurfaceApp

Para que la aplicación Surface funcione en el equipo de destino, también necesitará los marcos descritos anteriormente en este artículo. Usa el siguiente procedimiento para importar los marcos necesarios para la aplicación Surface en MDT y configurarlos como dependencias.

1. Mediante el procedimiento descrito anteriormente en este artículo, descargue los archivos de marco. Almacene cada marco en una carpeta independiente.

2. Con el Asistente para nueva aplicación en MDT Deployment Workbench, importe los archivos descargados como una **nueva aplicación con archivos de origen.**

3. En la **página Detalles del** comando, escriba el nombre de archivo de cada aplicación que descargó en el campo **Comando** y el directorio de trabajo predeterminado.

Para configurar los marcos como dependencias de la aplicación Surface, usa este proceso:

1. Abre las propiedades de la aplicación Surface en MDT Deployment Workbench.

2. Haga clic en **la pestaña** Dependencias y, a continuación, haga clic **en Agregar**.

3. Active la casilla para cada marco con el nombre que proporcionó en el Asistente para nueva aplicación.

Después de importar, la aplicación Surface **** estará disponible para su selección en el paso Aplicaciones del Asistente para Windows implementación. Para instalar la aplicación automáticamente, también puedes especificar la aplicación en la secuencia de tareas de implementación siguiendo este proceso:

1. Abre la secuencia de tareas de implementación en Deployment Workbench de MDT.

2. Agrega una nueva tarea **Instalar aplicación** en la sección **Restaurar estado** de la implementación.

3. Selecciona **Instalar una sola aplicación y** especifica Surface **App** como la aplicación que se va **a instalar.**

Para obtener más información acerca de cómo incluir aplicaciones en Windows implementaciones, vea [Prepare for deployment with MDT](/windows/deployment/deploy-windows-mdt/prepare-for-windows-deployment-with-mdt).

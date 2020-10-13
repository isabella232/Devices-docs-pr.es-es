---
title: Implementar Surface App con Microsoft Store para empresas o Microsoft Store para el ámbito educativo (Surface)
description: Descubra cómo agregar y descargar Surface App con Microsoft Store para empresas o Microsoft Store para el ámbito educativo, así como instalar Surface App con PowerShell y MDT.
keywords: aplicación Surface, aplicación, implementación, personalizar
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
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114718"
---
# Implementar la aplicación Surface con Microsoft Store para empresas y educación

**Se aplica a**

- Portátil Surface Go
- Surface Pro 7
- Portátil Surface 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Ir a la superficie con LTE
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


La aplicación Surface es una aplicación de Microsoft Store ligera que ofrece control de muchas opciones y configuraciones específicas, entre las que se incluyen: 

* Habilitar o deshabilitar el botón Windows en el dispositivo Surface 
 

* Ajustar la sensibilidad de un Lápiz para Surface 
 

* Personalizar las acciones del botón de Lápiz para Surface 
 

* Habilitar o deshabilitar las mejoras de audio de Surface 
 

* Acceso rápido a la documentación de soporte técnico y a la información del dispositivo

Los clientes que usen Windows Update recibirán la aplicación Surface normalmente como parte de las actualizaciones automáticas. Pero si su organización está preparando imágenes para su implementación en sus dispositivos Surface, es posible que desee incluir la aplicación Surface (anteriormente denominada Surface hub) en el proceso de creación de imágenes y de implementación en lugar de requerir que los usuarios de cada dispositivo descarguen e instalen la aplicación de Microsoft Store o de Microsoft Store para empresas. 

> [!NOTE]
> Este artículo no se aplica a Surface Pro X. Para obtener más información, consulte [implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md)

## Información general de Surface App

La aplicación Surface está disponible como una descarga gratuita de [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P). Los usuarios pueden descargarlo e instalarlo desde Microsoft Store, pero si su organización usa Microsoft Store for Business en su lugar, tendrá que agregarlo al inventario de su tienda y posiblemente incluir la aplicación como parte del proceso de implementación de Windows. Estos procesos se tratan en este artículo. Para obtener más información acerca de Microsoft Store para empresas, consulte [Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/) en Windows TechCenter. 

## Agregar una aplicación de Surface a una cuenta de Microsoft Store para empresas 

Antes de que los usuarios puedan instalar o implementar una aplicación de una cuenta de Microsoft Store para empresas, primero debe estar disponible y conceder la licencia a los usuarios de una empresa. 

1. Si aún no lo ha hecho, cree una [cuenta de Microsoft Store para empresas](https://www.microsoft.com/business-store). 

2. Inicie sesión en el portal. 

3. Habilitar licencias sin conexión: haga clic en **administrar->configuración**de la tienda y, a continuación, seleccione la casilla **Mostrar aplicaciones con licencias sin conexión a personas que se van a comprar en la tienda** , como se muestra en la ilustración 1. Para obtener más información sobre los modelos de licencias de aplicaciones de Microsoft Store para empresas, consulte [aplicaciones en Microsoft Store para empresas y educación](https://docs.microsoft.com/microsoft-store/).

   > [!div class="mx-imgBorder"]
   > ![Casilla Mostrar aplicaciones de licencias sin conexión](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *Figura 1. Habilitar aplicaciones para su uso sin conexión*

4. Agregue la aplicación Surface a su cuenta de Microsoft Store para empresas siguiendo este procedimiento:

    * Haga clic en el menú de **tienda** .
    
    * En el cuadro de búsqueda, escriba **Surface App**y, a continuación, haga clic en el icono de búsqueda.
    
    * Una vez que se presente la aplicación Surface en los resultados de la búsqueda, haga clic en el icono de la aplicación.
    
    * Se le presenta una opción (seleccione **en línea** o **sin conexión**), como se muestra en la figura 2.
    
      > [!div class="mx-imgBorder"]
      > ![Seleccione el modo de licencia sin conexión y agregue la aplicación al inventario.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *Figura 2. Seleccione el modo de licencia sin conexión y agregue la aplicación al inventario.*
    
    * Haga clic en **sin conexión** para seleccionar el modo de licencias sin conexión.
    
    * Haga clic en **obtener la aplicación** para agregar la aplicación a su inventario de Microsoft Store para empresas. Como se muestra en la figura 3, verá un cuadro de diálogo que le pide que confirme que las aplicaciones sin conexión se pueden implementar con una herramienta de administración o se descargan desde la página de inventario de la empresa en su tienda privada.
    
      > [!div class="mx-imgBorder"]
      > ![Ventana de confirmación de aplicación con licencia sin conexión, ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *ilustración 3. Confirmación de aplicación con licencia sin conexión*
      
    * Haga clic en **Aceptar**.

## Descargar Surface App desde una cuenta de Microsoft Store para empresas
Después de agregar una aplicación a la cuenta de Microsoft Store para empresas en el modo sin conexión, puede descargar y agregar la aplicación como un AppxBundle a un recurso compartido de implementación.

1. Inicie sesión en la cuenta de Microsoft Store para empresas en https://businessstore.microsoft.com .

2. Haga clic en **administrar->aplicaciones & software**. Se muestra una lista de todas las aplicaciones de su empresa, incluida la aplicación Surface que agregó en la [aplicación agregar Surface a una cuenta de Microsoft Store para empresas](#add-surface-app-to-a-microsoft-store-for-business-account) en este artículo.

3. En **acciones**, haga clic en los puntos suspensivos (**...**) y, a continuación, haga clic en **descargar para usar sin conexión** en la aplicación Surface.

4. Seleccione las opciones de **plataforma** y **arquitectura** que desee de las selecciones disponibles para la aplicación seleccionada, como se muestra en la ilustración 4.

    > [!div class="mx-imgBorder"]
    > ![Ejemplo del paquete AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *Figura 4. Descargar el paquete AppxBundle de una aplicación*
    
5. Haga clic en **Descargar**. El paquete AppxBundle se descargará. Asegúrese de que anota la ruta de acceso del archivo descargado porque lo necesitará más adelante en este artículo.

6. Haga clic en la opción **licencia codificada** o en **licencia sin codificar** . Use la opción de licencia codificada con herramientas de administración como Microsoft Endpoint Configuration Manager o cuando use el diseñador de configuración de Windows para crear un paquete de aprovisionamiento. Seleccione la opción de licencia sin codificar al usar administración y mantenimiento de imágenes de implementación (DISM) o soluciones de implementación basadas en Imaging, incluido Microsoft Deployment Toolkit (MDT).

7. Haga clic en **generar** para generar y descargar la licencia de la aplicación. Asegúrese de que anota la ruta de acceso del archivo de licencia porque lo necesitará más adelante en este artículo.

>[!NOTE]
>Al descargar una aplicación para su uso sin conexión, como la aplicación Surface, es posible que observe una sección en la parte inferior de la página denominada **frameworks requerido**. Los equipos de destino deben tener instalados los marcos de trabajo de la aplicación, por lo que es posible que tenga que repetir el proceso de descarga para cada uno de los marcos de trabajo necesarios para su arquitectura (x86 o x64) e incluirlos como parte de la implementación de Windows que se trata más adelante en este artículo.

La figura 5 muestra los marcos de trabajo necesarios para Surface app.

> [!div class="mx-imgBorder"]
> ![Marcos necesarios para la aplicación Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*Figura 5. Marcos necesarios para la aplicación Surface*

>[!NOTE]
>Los números de versión de la aplicación Surface y los marcos obligatorios cambiarán a medida que se actualicen las aplicaciones. Busque la última versión de Surface App y de cada marco en Microsoft Store para empresas. Use siempre la aplicación de Surface y las versiones de marco recomendadas proporcionadas por Microsoft Store para empresas. El uso de Marcos anticuados o de versiones incorrectas puede producir errores o bloqueos de la aplicación.

Para descargar los marcos necesarios para la aplicación Surface, siga estos pasos:

1. Haga clic en el botón **Descargar** en **Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe**. Esto descarga el Microsoft. VCLibs. 140.00 _14.0.23816.0 _x64__8wekyb3d8bbwe. Appx a la carpeta especificada.

2. Haga clic en el botón **Descargar** en **Microsoft. net. Native. Runtime. 1.1 _ 1.23406 _x64__8wekyb3d8bbwe**. Esto descarga el archivo Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0 _x64__8wekyb3d8bbwe. appx en la carpeta especificada.

>[!NOTE]
>Para los dispositivos Surface, solo se necesita la versión de 64 bits (x64) de cada marco. Los dispositivos Surface son dispositivos UEFI nativos de 64 bits y no son compatibles con las versiones de Windows de 32 bits (x86) que requerirían marcos de trabajo de 32. 

## Instalar la aplicación Surface en el equipo con PowerShell
El procedimiento siguiente indica la aplicación Surface en el equipo y la pone a disposición de todas las cuentas de usuario creadas en el equipo después.

1. Con el procedimiento descrito en la sección [Cómo descargar la aplicación de Surface desde una cuenta de Microsoft Store para empresas](#download-surface-app-from-a-microsoft-store-for-business-account) de este artículo, descarga el archivo AppxBundle de la aplicación de Surface y el archivo de licencia. 

2. Comienza una sesión de PowerShell con privilegios elevados.

    >[!NOTE]
    >Si no ejecuta PowerShell como administrador, la sesión no tendrá los permisos necesarios para instalar la aplicación.
    
3. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    Donde `<DownloadPath>` es la carpeta donde descargó el archivo AppxBundle y el archivo de licencia de la cuenta de Microsoft Store para empresas.

    Por ejemplo, si ha descargado los archivos en c:\Temp, el comando que ejecuta es el siguiente:
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. La aplicación Surface ahora estará disponible en tu equipo Windows actual. 

   Antes de que la aplicación Surface sea funcional en el equipo donde se ha aprovisionado, también debe aprovisionar los marcos descritos anteriormente en este artículo. Para aprovisionar estos marcos, use el procedimiento siguiente en la sesión de PowerShell con privilegios elevados que usó para aprovisionar la aplicación Surface.

5. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: 

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Instalar la aplicación Surface con MDT
El siguiente procedimiento usa MDT para automatizar la instalación de Surface app en el momento de la implementación. MDT aprovisiona la aplicación automáticamente durante la implementación y, por lo tanto, puedes usar este proceso con las imágenes existentes. Este es el proceso recomendado para implementar la aplicación Surface como parte de una implementación de Windows para Surface Devices porque no reduce la compatibilidad entre plataformas de la imagen de Windows.

1. Con el procedimiento descrito [anteriormente en este artículo](#download-surface-app-from-a-microsoft-store-for-business-account), descargue el archivo AppxBundle de la aplicación superficial y el archivo de licencia. 

2. Con el Asistente para nueva aplicación de MDT Deployment Workbench, importe los archivos descargados como una nueva **aplicación con archivos de origen**.

3. En la página **detalles del comando** del Asistente para crear nueva aplicación, especifique el directorio de **trabajo** predeterminado y, para el **comando** , especifique el nombre de archivo AppxBundle de la siguiente manera:

   * Mando
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * Directorio de trabajo:%DEPLOYROOT%\Applications\SurfaceApp

Para que la aplicación Surface funcione en el equipo de destino, también necesitará los marcos descritos anteriormente en este artículo. Use el siguiente procedimiento para importar los marcos necesarios para la aplicación de Surface en MDT y para configurarlos como dependencias.

1. Con el procedimiento descrito anteriormente en este artículo, descargue los archivos de Framework. Almacene cada marco en una carpeta diferente.

2. Con el Asistente para nueva aplicación de MDT Deployment Workbench, importe los archivos descargados como una nueva **aplicación con archivos de origen**.

3. En la página **detalles del comando** , escriba el nombre de archivo de cada aplicación que haya descargado en el campo **comando** y el directorio de trabajo predeterminado.

Para configurar los marcos como dependencias de la aplicación Surface, use este proceso:

1. Abra las propiedades de la aplicación de Surface en el MDT Deployment Workbench.

2. Haga clic en la pestaña **dependencias** y, a continuación, en **Agregar**.

3. Active la casilla de verificación de cada marco de trabajo con el nombre que proporcionó en el Asistente para nueva aplicación.

Después de la importación, la aplicación Surface estará disponible para su selección en el paso **aplicaciones** del Asistente para la implementación de Windows. Para instalar la aplicación automáticamente, también puedes especificar la aplicación en la secuencia de tareas de implementación siguiendo este proceso:

1. Abre la secuencia de tareas de implementación en Deployment Workbench de MDT.

2. Agrega una nueva tarea **Instalar aplicación** en la sección **Restaurar estado** de la implementación.

3. Seleccione **instalar una sola aplicación** y especifique la aplicación **Surface** como la **aplicación que se instalará**.

Para obtener más información sobre cómo incluir aplicaciones en sus implementaciones de Windows, consulte [implementar Windows 10 con Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).

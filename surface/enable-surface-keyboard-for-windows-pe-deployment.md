---
title: Cómo habilitar el teclado para portátiles Surface durante la implementación de MDT
description: Cuando usa MDT para implementar Windows 10 en Surface laptops, necesita importar los drivers de teclado para usarlos en el entorno de Windows PE.
keywords: Windows 10 Surface, automatizar, personalizar, MDT
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834714"
---
# Cómo habilitar el teclado para portátiles Surface durante la implementación de MDT

En este artículo se trata un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT). También puede aplicar esta información a otras metodologías de implementación. En la mayoría de los tipos de dispositivos de superficie, el teclado debe funcionar durante la instalación con Lite Touch (LTI). Sin embargo, Surface Laptop necesita algunos drivers adicionales para habilitar el teclado. Para los dispositivos Surface Laptop (1º gen) y Surface Laptop 2, debe preparar los perfiles de selección y estructura de carpetas que le permiten especificar los drivers de teclado para usarlos durante la fase de entorno de preinstalación de Windows (Windows PE) de LTI. Para obtener más información sobre esta estructura de carpetas, consulte [implementar una imagen de Windows 10 con MDT: paso 5: preparar el repositorio de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!NOTE]
> Por el momento, no se admite agregar controladores de teclado de Surface Laptop 2 y Surface Laptop 3 en la misma instancia de inicio de Windows PE debido a un conflicto de drivers; Use instancias independientes en su lugar.

> [!IMPORTANT]
> Si va a implementar una imagen de Windows 10 en un portátil Surface con Windows 10 en modo S preinstalado, consulte KB [4032347, problemas al implementar Windows en dispositivos Surface con el modo preinstalado de Windows 10](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

Para agregar los drivers de teclado al perfil de selección, siga estos pasos:

1. Descargue el archivo MSI Surface portátil más reciente de las ubicaciones apropiadas:
    - [Drivers y firmware Surface Laptop (1ª generación)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Drivers y firmware Surface del portátil 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Portátil Surface 3 con el firmware y los drivers de procesador Intel](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extraiga el contenido del archivo MSI de Surface portátil en una carpeta que pueda localizar fácilmente (por ejemplo, c:\ surface_laptop_drivers). Para extraer el contenido, abra una ventana de símbolo del sistema con privilegios elevados y ejecute el comando del siguiente ejemplo:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra Deployment Workbench y expanda el nodo **recursos compartidos de implementación** y el recurso compartido de implementación y, a continuación, vaya a la carpeta **WindowsPEX64** .

   ![Imagen que muestra la ubicación de la carpeta WindowsPEX64 en Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Haga clic con el botón derecho en la carpeta **WindowsPEX64** y seleccione **importar drivers**.
5. Siga las instrucciones del Asistente para importar Controladores para importar las carpetas de controladores a la carpeta WindowsPEX64.  

> [!NOTE]
>  Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI. 

Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

Para admitir Surface Laptop 2, importe las siguientes carpetas:

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

La importación de las siguientes carpetas habilitará la funcionalidad completa del teclado, el panel táctil y el toque en PE para Surface Laptop 3.

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI. 

    Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para admitir Surface Laptop 2, importe las siguientes carpetas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3. Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

6. Compruebe que la carpeta WindowsPEX64 ahora contiene los drivers importados. La carpeta debería tener un aspecto similar al siguiente:  

   ![Imagen que muestra los drivers recién importados en la carpeta WindowsPEX64 de Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configure un perfil de selección que use la carpeta WindowsPEX64. El perfil de selección debería tener un aspecto similar al siguiente:  

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección](./images/surface-laptop-keyboard-3.png)

8. Configure las propiedades de Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección de la siguiente manera:  

   - Para **plataforma**, seleccione **x64**.
   - En **Perfil de selección**, seleccione el nuevo perfil.
   - Seleccione **incluir todos los drivers del perfil de selección**.
   
   ![Imagen que muestra las propiedades de Windows PE del recurso compartido de implementación de MDT](./images/surface-laptop-keyboard-4.png)

9. Verifique que haya configurado el resto de los drivers de equipos portátiles con un perfil de selección o una variable **DriverGroup001** .  
   - Para portátiles Surface (primer gen), el modelo es un **portátil Surface**. Los drivers de equipos portátiles de superficie restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, tal como se muestra en la figura que sigue a esta lista.
   - Para el portátil Surface 2, el modelo es el **portátil Surface 2**. Los drivers de equipos portátiles restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2. 
   - Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3. Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

   ![Imagen que muestra los drivers de la superficie normal (1º gen) en la carpeta Surface Laptop de Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y la configuración relacionada, continúe el proceso de implementación tal como se describe en [implementar una imagen de Windows 10 con MDT: paso 6: crear la secuencia de tareas de implementación](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).

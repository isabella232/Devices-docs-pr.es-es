---
title: Cómo habilitar el teclado de Surface Laptop durante la implementación de MDT
description: Cuando usas MDT para implementar Windows 10 en portátiles Surface, debes importar controladores de teclado para usarlos en el entorno de Windows PE.
keywords: windows 10 surface, automatizar, personalizar, mdt
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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312066"
---
# Cómo habilitar el teclado de Surface Laptop durante la implementación de MDT

En este artículo se trata un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT). También puede aplicar esta información a otras metodologías de implementación. En la mayoría de los tipos de dispositivos Surface, el teclado debe funcionar durante lite touch Installation (LTI). Sin embargo, Surface Laptop requiere algunos controladores adicionales para habilitar el teclado. Para dispositivos Surface Laptop (1.ª generación) y Surface Laptop 2, debes preparar la estructura de carpetas y los perfiles de selección que te permiten especificar controladores de teclado para usarlos durante la fase del Entorno de preinstalación de Windows (Windows PE) de LTI. Para obtener más información sobre esta estructura de carpetas, consulta Implementar una imagen de [Windows 10 con MDT: Paso 5: Preparar el repositorio de controladores.](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)

> [!TIP]    
> Al usar controladores de teclado para Surface Laptop 2 y Surface Laptop 3 en la misma instancia de arranque de Windows PE, es posible que deba restablecer manualmente el firmware si el teclado o el panel táctil no funcionan en Windows PE:
>
> - Mantén presionado el botón de encendido durante 30 segundos. Si estás conectado a una unidad de alimentación (PSU), mantén presionado el botón de encendido hasta que veas la luz al final del cable PSU brevemente antes de volver a activarlo.

> [!IMPORTANT]
> Si vas a implementar una imagen de Windows 10 en un Surface Laptop que tenga Windows 10 en modo S preinstalado, consulta KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problemas al implementar Windows en dispositivos Surface con Windows 10 preinstalado en modo S.

Para agregar los controladores de teclado al perfil de selección, sigue estos pasos:

1. Descarga el archivo MSI más reciente de Surface Laptop desde las ubicaciones adecuadas:
    - [Controladores y firmware de Surface Laptop (1.ª generación)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Controladores y firmware de Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 con controladores de procesador Intel y firmware](https://www.microsoft.com/download/details.aspx?id=100429)

2. Extrae el contenido del archivo MSI de Surface Laptop en una carpeta que puedas encontrar fácilmente (por ejemplo, c:\surface_laptop_drivers). Para extraer el contenido, abra una ventana del símbolo del sistema con privilegios elevados y ejecute el comando en el siguiente ejemplo:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abre Deployment Workbench, expande el nodo **Recursos compartidos** de implementación y el recurso compartido de implementación y, a continuación, navega a la **carpeta WindowsPEX64.**

   ![Imagen que muestra la ubicación de la carpeta WindowsPEX64 en Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. Haga clic con el botón secundario **en la carpeta WindowsPEX64** y seleccione **Importar controladores.**

5. Sigue las instrucciones del Asistente para importar controladores para importar las carpetas de controladores en la carpeta WindowsPEX64.  

    > [!NOTE]
    >  Comprueba el paquete MSI descargado para determinar el formato y la estructura del directorio.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI más antiguos) o SurfaceUpdate (archivos MSI más recientes), en función de cuándo se publicó el MSI. 

    Para admitir Surface Laptop (1.ª generación), importa las siguientes carpetas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para admitir Surface Laptop 2, importa las siguientes carpetas:

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\serialioi2c
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

     
    Para admitir Surface Laptop 3 con procesador Intel, importa las siguientes carpetas:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    La importación de las siguientes carpetas habilitará la funcionalidad de teclado completo, panel táctil y táctil en PE para Surface Laptop 3.

    - SerialIOGPIO
    - SerialIOI2C
    - SerialIOSPI
    - SerialIOUART
    - itouch
    - Conjunto de chips
    - ChipsetLPSS
    - ChipsetNorthpeak
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
     >  Comprueba el paquete MSI descargado para determinar el formato y la estructura del directorio.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI más antiguos) o SurfaceUpdate (archivos MSI más recientes), en función de cuándo se publicó el MSI. 

     Para admitir Surface Laptop (1.ª generación), importa las siguientes carpetas:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    Para admitir Surface Laptop 2, importa las siguientes carpetas:

    - SurfacePlatformInstaller\Drivers\System\GPIO
    - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
    - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
    - SurfacePlatformInstaller\Drivers\System\I2C
    - SurfacePlatformInstaller\Drivers\System\SPI
    - SurfacePlatformInstaller\Drivers\System\UART
    - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    Para admitir Surface Laptop 3 con procesador Intel, importa las siguientes carpetas:

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SerialIOI2C
    - SurfaceUpdate\SerialIOSPI
    - SurfaceUpdate\SerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3. Los controladores restantes de Surface Laptop se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

6. Comprueba que la carpeta WindowsPEX64 ahora contiene los controladores importados. La carpeta debe ser similar a la siguiente:  

   ![Imagen que muestra los controladores recién importados en la carpeta WindowsPEX64 de Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. Configurar un perfil de selección que use la carpeta WindowsPEX64. El perfil de selección debe ser similar al siguiente:  

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección](./images/surface-laptop-keyboard-3.png)

8. Configura las propiedades de Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección, como se muestra a continuación:  

   - Para **Plataforma,** seleccione **x64**.
   - En **Perfil de selección,** seleccione el nuevo perfil.
   - Selecciona **Incluir todos los controladores del perfil de selección.**
   
   ![Imagen que muestra las propiedades de Windows PE del recurso compartido de implementación de MDT](./images/surface-laptop-keyboard-4.png)

9. Comprueba que has configurado los controladores restantes de Surface Laptop mediante un perfil de selección o una variable **DriverGroup001.**  
   - Para Surface Laptop (1.ª generación), el modelo es **Surface Laptop.** Los controladores restantes de Surface Laptop deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, como se muestra en la figura que sigue a esta lista.
   - Para Surface Laptop 2, el modelo es **Surface Laptop 2**. Los controladores restantes de Surface Laptop deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2. 
   - Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3. Los controladores restantes de Surface Laptop se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

   ![Imagen que muestra los controladores normales de Surface Laptop (1.ª generación) en la carpeta Surface Laptop de Deployment Workbench](./images/surface-laptop-keyboard-5.png)

Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y las opciones relacionadas, continúa el proceso de implementación como se describe en Implementar una imagen de [Windows 10 con MDT: Paso 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Crear la secuencia de tareas de implementación.

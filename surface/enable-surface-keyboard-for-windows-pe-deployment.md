---
title: Cómo habilitar el teclado Surface Laptop durante la implementación de MDT
description: Cuando usas MDT para implementar Windows 10 en portátiles Surface, debes importar controladores de teclado para usarlos en el Windows PE.
keywords: windows 10 surface, automatizar, personalizar, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: 8707d022ae5e3d3f34c59fab88328b5720896898
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449193"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Cómo habilitar el teclado Surface Laptop durante la implementación de MDT

En este artículo se aborda un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT). También puede aplicar esta información a otras metodologías de implementación. En la mayoría de los tipos de dispositivos Surface, el teclado debe funcionar durante la instalación de Lite Touch (LTI). Sin embargo, Surface Laptop requiere algunos controladores adicionales para habilitar el teclado. Para dispositivo Windows s Surface Laptop (1ª generación) y Surface Laptop 2, debe preparar la estructura de carpetas y los perfiles de selección que le permiten especificar controladores de teclado para su uso durante la fase de entorno de preinstalación (Windows PE) de LTI. Para obtener más información acerca de esta estructura de carpetas, [vea Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> Al usar controladores de teclado para Surface Laptop 2 y Surface Laptop 3 en la misma instancia de arranque de Windows PE, es posible que deba restablecer manualmente el firmware si el teclado o el panel táctil no funcionan en Windows PE:
>
> - Mantenga presionado el botón De encendido durante 30 segundos. Si está conectado a una unidad de fuente de alimentación (PSU), presione y mantenga presionado el botón De encendido hasta que vea la luz al final del cable PSU que se apague brevemente antes de volver a activarse.

> [!IMPORTANT]
> Si vas a implementar una imagen de Windows 10 en un Surface Laptop que tiene Windows 10 en modo S preinstalado, consulta KB 4032347, Problemas al implementar Windows en dispositivos Surface con Windows 10 [preinstalado en modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Agregar controladores de teclado al perfil de selección

1. Descargue el archivo de Surface Laptop .msi más reciente de las ubicaciones adecuadas:
    - [Surface Laptop (1ª generación) de controladores y firmware](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 controladores y firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 con controladores de procesador Intel y firmware](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 con controladores de procesador Intel y firmware](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 con controladores de procesador AMD y firmware](https://www.microsoft.com/download/102923)
    - [Surface Laptop controladores y firmware de Studio](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 controladores y firmware](https://www.microsoft.com/download/details.aspx?id=103503)

2. Extraiga el contenido del archivo Surface Laptop .msi a una carpeta que pueda localizar fácilmente (por ejemplo, c:\surface_laptop_drivers). Para extraer el contenido, abra una ventana del símbolo del sistema con privilegios elevados y ejecute el comando en el siguiente ejemplo:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra Deployment Workbench y expanda el nodo **Recursos compartidos** de implementación y el recurso compartido de implementación y, a continuación, vaya a la **carpeta WindowsPEX64** .
4. Haz clic con el botón secundario **en la carpeta WindowsPEX64** y selecciona **Importar controladores**.
5. Siga las instrucciones del Asistente para importar controladores para importar las carpetas de controladores en la carpeta WindowsPEX64.

 > [!NOTE]
 > Compruebe el paquete .msi descargado para determinar el formato y la estructura del directorio.  La estructura de directorios empezará con SurfacePlatformInstaller (archivos .msi antiguos) o SurfaceUpdate (archivos .msi más recientes), en función del momento en que se publicó el archivo .msi.

## <a name="import-drivers-for-surface-devices"></a>Importar controladores para dispositivos Surface

Importe las siguientes carpetas según corresponda para su Surface Laptop dispositivo.  

| Dispositivo                                | Importar carpetas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Más información                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SurfaceLaptopStudio                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | n/d |
| SurfacePro8                         | heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollerhsacomponent<br> |n/d |
| Surface Laptop 4 con procesador Intel | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |n/d                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 con procesador AMD   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |n/d                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 con procesador Intel | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | La importación de las siguientes carpetas habilitará la funcionalidad completa de teclado, trackpad y táctil en PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>Conjunto de chips<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Para los archivos .msi más recientes a partir de "SurfaceUpdate", usa:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop (1ª generación)              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Para los archivos .msi más recientes a partir de "SurfaceUpdate", usa:<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > Compruebe el paquete .msi descargado para determinar el formato y la estructura del directorio.  La estructura de directorios empezará con SurfacePlatformInstaller (archivos .msi antiguos) o SurfaceUpdate (archivos .msi más recientes) en función del momento en que se publicó el .msi.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Comprobar los controladores importados & configurar las Windows PE

1. Compruebe que la carpeta WindowsPEX64 ahora contiene los controladores importados, como se muestra en la siguiente figura:

   ![Imagen que muestra los controladores recién importados en la carpeta WindowsPEX64 de Deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Configure un perfil de selección que use la carpeta WindowsPEX64, como se muestra en la siguiente figura:

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección.](./images/surface-laptop-keyboard-3.png)
1. Configure las Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección, de la siguiente manera:
    - Para **Plataforma**, seleccione **x64**.
    - Para **Perfil de selección**, seleccione el nuevo perfil.
    - Seleccione **Incluir todos los controladores del perfil de selección**.

    ![Imagen que muestra las propiedades Windows PE del recurso compartido de implementación de MDT.](./images/surface-laptop-keyboard-4.png)
4. Compruebe que ha configurado los controladores de Surface Laptop utilizando un perfil de selección o una variable **DriverGroup001**.
    - Para Surface Laptop (1ª generación), el modelo **es Surface Laptop**. Los controladores de Surface Laptop restantes deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, como se muestra en la figura siguiente.
    - Para Surface Laptop 2, el modelo **Surface Laptop 2**. El resto Surface Laptop controladores deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3. El resto Surface Laptop controladores se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Imagen que muestra los controladores Surface Laptop (1ª generación) de la carpeta Surface Laptop de Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y la configuración relacionada, continúe con el proceso de implementación tal como se describe en [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).

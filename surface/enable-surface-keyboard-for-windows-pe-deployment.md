---
title: Habilitación del teclado Surface Laptop durante la implementación de MDT
description: Cuando usas MDT para implementar Windows 10 en portátiles Surface, debes importar controladores de teclado para usarlos en el entorno Windows PE.
keywords: windows 10 surface, automate, customize, mdt
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
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497923"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>Habilitación del teclado Surface Laptop durante la implementación de MDT

En este artículo se aborda un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT). También puede aplicar esta información a otras metodologías de implementación. En la mayoría de los tipos de dispositivos Surface, el teclado debe funcionar durante la instalación de Lite Touch (LTI). Sin embargo, Surface Laptop requiere algunos controladores adicionales para habilitar el teclado. Para Surface Laptop (1.ª generación) y Surface Laptop 2 dispositivos, debe preparar la estructura de carpetas y los perfiles de selección que le permiten especificar controladores de teclado para su uso durante la fase de entorno de preinstalación Windows (Windows PE) de LTI. Para obtener más información sobre esta estructura de carpetas, consulte [Implementación de una imagen de Windows 10 mediante MDT: Paso 5: Preparación del repositorio de controladores](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> Al usar controladores de teclado para Surface Laptop 2 y Surface Laptop 3 en la misma instancia de arranque Windows PE, es posible que tenga que restablecer manualmente el firmware si el teclado o el panel táctil no funcionan en Windows PE:
>
> - Mantenga presionado el botón de encendido durante 30 segundos. Si está conectado a una unidad de alimentación (PSU), mantenga presionado el botón de encendido hasta que vea la luz al final del cable PSU apagar brevemente antes de volver a encender.

> [!IMPORTANT]
> Si va a implementar una imagen de Windows 10 en un Surface Laptop que tiene Windows 10 en modo S preinstalado, consulte [KB 4032347, Problemas al implementar Windows en dispositivos Surface con Windows 10 preinstaladas en modo S](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>Adición de controladores de teclado al perfil de selección

1. Descargue el archivo de Surface Laptop .msi más reciente de las ubicaciones adecuadas:
    - [controladores y firmware de Surface Laptop (1.ª generación)](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 controladores y firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 con controladores y firmware del procesador Intel](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 con controladores y firmware del procesador Intel](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 con controladores y firmware del procesador AMD](https://www.microsoft.com/download/102923)
    - [Controladores y firmware de Surface Laptop Studio](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 controladores y firmware](https://www.microsoft.com/download/details.aspx?id=103503)

2. Extraiga el contenido del archivo Surface Laptop .msi en una carpeta que pueda localizar fácilmente (por ejemplo, c:\surface_laptop_drivers). Para extraer el contenido, abra una ventana del símbolo del sistema con privilegios elevados y ejecute el comando en el ejemplo siguiente:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Abra Deployment Workbench y expanda el nodo **Recursos compartidos de implementación** y el recurso compartido de implementación y, a continuación, vaya a la carpeta **WindowsPEX64** .
4. Haga clic con el botón derecho en la carpeta **WindowsPEX64** y seleccione **Importar controladores**.
5. Siga las instrucciones del Asistente para importar controladores para importar las carpetas de controladores en la carpeta WindowsPEX64.

 > [!NOTE]
 > Compruebe el paquete de .msi descargado para determinar el formato y la estructura de directorios.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos .msi anteriores) o SurfaceUpdate (archivos de .msi más recientes) en función de cuándo se haya publicado el archivo .msi.

## <a name="import-drivers-for-surface-devices"></a>Importar controladores para dispositivos Surface

Importe las siguientes carpetas según corresponda para el dispositivo Surface Laptop.

| Dispositivo                                    | Importar carpetas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Más información                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **SurfaceLaptopStudio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **SurfacePro8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 con procesador Intel** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 con procesador AMD**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | n/d                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 3 con procesador Intel** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | La importación de las siguientes carpetas habilitará la funcionalidad completa de teclado, panel de seguimiento y toque en PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>Itouch<br>Chipset<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | Para los archivos de .msi más recientes a partir de "SurfaceUpdate", use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (1.ª generación)**              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | Para los archivos de .msi más recientes a partir de **"SurfaceUpdate"**, use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > Compruebe el paquete de .msi descargado para determinar el formato y la estructura de directorios.  La estructura de directorios comenzará con SurfacePlatformInstaller (archivos .msi anteriores) o SurfaceUpdate (archivos de .msi más recientes) en función de cuándo se haya publicado el .msi.

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>Comprobación de los controladores importados & configurar Windows propiedades de PE

1. Compruebe que la carpeta WindowsPEX64 contiene ahora los controladores importados, como se muestra en la ilustración siguiente:

   ![Imagen que muestra los controladores recién importados en la carpeta WindowsPEX64 de Deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Configure un perfil de selección que use la carpeta WindowsPEX64, como se muestra en la ilustración siguiente:

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección.](./images/surface-laptop-keyboard-3.png)
1. Configure las propiedades Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección, como se indica a continuación:
    - En **Plataforma**, seleccione **x64**.
    - En **Perfil de selección**, seleccione el nuevo perfil.
    - Seleccione **Incluir todos los controladores del perfil de selección**.

    ![Imagen que muestra las propiedades Windows PE del recurso compartido de implementación de MDT.](./images/surface-laptop-keyboard-4.png)
4. Compruebe que ha configurado los controladores de Surface Laptop restantes mediante un perfil de selección o una variable **DriverGroup001**.
    - Para Surface Laptop (1.ª generación), el modelo se **Surface Laptop**. Los controladores de Surface Laptop restantes deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, como se muestra en la ilustración siguiente.
    - Para Surface Laptop 2, el modelo es **Surface Laptop 2**. Los controladores de Surface Laptop restantes deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.
    - Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3. Los controladores de Surface Laptop restantes se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.

    ![Imagen que muestra los controladores de Surface Laptop normales (1.ª generación) en la carpeta Surface Laptop de Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y la configuración relacionada, continúe con el proceso de implementación como se describe en [Implementación de una imagen de Windows 10 mediante MDT: Paso 6: Crear la secuencia de tareas de implementación](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).

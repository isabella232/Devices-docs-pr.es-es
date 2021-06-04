---
title: Acelerador de implementaciones de Microsoft Surface (Surface)
description: Gracias al Acelerador de implementaciones de Microsoft Surface, las empresas que quieran restablecer la imagen inicial de sus dispositivos Surface podrán usar este mecanismo de implementación de forma rápida y sencilla.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: implementar, instalar, herramienta
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016561"
---
# Acelerador de implementaciones de Microsoft Surface

El acelerador de implementación de Microsoft Surface (SDA) automatiza la creación y la configuración de una experiencia de implementación recomendada de Microsoft mediante las herramientas de implementación gratuitas de Microsoft.

Rediseñado en abril de 2020 para simplificar y automatizar la implementación de imágenes de Surface en un entorno corporativo, la herramienta SDA le permite crear una imagen de Windows "de fábrica" que puede personalizar según los requisitos de su organización.

La herramienta de código empaquetado abierto basado en scripts aprovecha el Windows Assessment and Deployment Kit (ADK) para Windows 10, lo que facilita la creación de imágenes de Windows (WIM) en entornos de prueba o producción. Si la última versión de ADK aún no está instalada, se descargará e instalará al ejecutar la herramienta SDA.

La imagen resultante se ajusta estrechamente a la configuración de las imágenes de recuperación de equipos integrados (BMR), sin necesidad de aplicaciones preinstaladas, como Microsoft Office o la aplicación Surface para UWP.

##  <a name="requirements"></a>Requisitos

1. Una unidad USB con un tamaño mínimo de 16 GB. El disco USB tendrá el formato.
2. Un archivo. ISO con Windows 10 Pro o Windows 10 Enterprise. La herramienta de creación de medios se puede usar para descargar Windows 10 y crear un archivo. ISO. Para obtener más información, consulta [Descargar Windows 10](https://www.microsoft.com/software-download/windows10).
3. Un dispositivo con Windows 10, versión 2004 o posterior, con acceso a Internet.

Consulte la sección [requisitos previos](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) del documento Léame para obtener una lista detallada de los requisitos.

##  <a name="how-to-run-the-sda"></a>Cómo ejecutar el SDA

**Para ejecutar SDA:**

1. Vaya a [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) en github. 
2. Revise la documentación del [Léame](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .
3. En la página [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , haga clic en el botón **código** y, a continuación, seleccione **Descargar zip** para guardar los archivos de forma local en el equipo.
4. Haga clic con el botón secundario en el archivo. zip y después haga clic en **propiedades**.
5. En la pestaña **General** , seleccione la casilla **desbloquear** y, a continuación, haga clic en **Aceptar**.
6. Extraiga el archivo. zip en una ubicación de la unidad de disco duro (por ejemplo: C:\SDA).
7. Abra un símbolo del sistema de Windows PowerShell con privilegios elevados y establezca ExecutionPolicy para la sesión actual en no restringido.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Ejecute la secuencia de comandos SDA que especifica los parámetros de su entorno. El script se puede usar para crear imágenes con el fin de instalar Windows 10 en una gran variedad de dispositivos Surface. Para obtener una lista completa de los dispositivos compatibles, consulte la descripción de los [parámetros del dispositivo](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) en el artículo Léame de SDA. 

    Por ejemplo, el siguiente comando creará una unidad USB de arranque que se puede usar para [instalar Windows 10 en Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    La salida de script de ejemplo se muestra a continuación.

   ![Herramienta ejecutar el acelerador de despliegue de Surface](images/sda1.png)

    El script requerirá unos 45 minutos para ejecutarse, pero podría tardar más tiempo en función de la CPU y los recursos de disco disponibles. 

    Después de crear una imagen de Windows, la secuencia de comandos le pedirá que inserte y confirme la letra de unidad de su unidad USB. A continuación, se formateará la unidad USB, se configurará como arrancable y los archivos se copiarán para habilitar la instalación de la imagen personalizada de Windows 10 para dispositivos de Surface.

9. Inserte la unidad USB en el dispositivo donde quiera instalar Windows 10 y reinicie para empezar a instalar Windows 10. El arranque USB debe estar habilitado en el BIOS, lo cual puede requerir la desactivación temporal del arranque seguro.

> [!IMPORTANT]
> Iniciar desde la unidad USB iniciará inmediatamente la instalación de Windows 10. Asegúrese de que el dispositivo está listo antes de insertar el USB y reiniciar. 

##  <a name="related-links"></a>Vínculos relacionados

 - [Herramienta de implementación de imagen de Open Source Publicada en GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

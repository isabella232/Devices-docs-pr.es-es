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
ms.openlocfilehash: 48f89e8929bdb9d075bea988558fea234da5bbd2
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911425"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Acelerador de implementaciones de Microsoft Surface

Microsoft Surface Deployment Accelerator (SDA) automatiza la creación y configuración de una experiencia de implementación recomendada por Microsoft mediante el uso de herramientas de implementación gratuitas de Microsoft.

Rediseñada en abril de 2020 para simplificar y automatizar la implementación de imágenes de Surface en un entorno corporativo, la herramienta SDA te permite crear una imagen Windows "de fábrica" que puedas personalizar según los requisitos de la organización.

La herramienta SDA basada en scripts de código abierto aprovecha el kit de evaluación e implementación (ADK) de Windows para Windows 10, lo que facilita la creación de imágenes de Windows (WIM) en entornos de prueba o producción. Si el ADK más reciente aún no está instalado, se descargará e instalará al ejecutar la herramienta SDA.

La imagen resultante coincide estrechamente con la configuración de las imágenes de recuperación de bare metal (BMR), sin ninguna aplicación preinstalada, como Microsoft Office o la aplicación para UWP de Surface.

## <a name="requirements"></a>Requisitos

1. Una unidad usb con un tamaño mínimo de 16 GB. Se dará formato a la unidad USB.
2. Un archivo .iso con Windows 10 Pro o Windows 10 Enterprise. La herramienta de creación de medios se puede usar para descargar Windows 10 crear un archivo .iso. Para obtener más información, vea [Descargar Windows 10](https://www.microsoft.com/software-download/windows10).
3. Un dispositivo que se Windows 10, versión 2004 o posterior con acceso a Internet.

Consulte la [sección Requisitos previos](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) del documento README para obtener una lista detallada de requisitos.

## <a name="how-to-run-the-sda"></a>Cómo ejecutar el SDA

**Para ejecutar SDA:**

1. Ve a [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) en GitHub. 
2. Revise la [documentación de README.](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md)
3. En la [página SurfaceDeploymentAccelerator,](https://github.com/microsoft/SurfaceDeploymentAccelerator) haz clic en el botón Código y, a continuación, selecciona **Descargar ZIP** para guardar los archivos localmente en el equipo. ****
4. Haga clic con el botón secundario en .zip archivo y, a continuación, haga clic en **Propiedades**.
5. En la **ficha General,** active la casilla **Desbloquear y,** a continuación, haga clic en **Aceptar**.
6. Extraiga el .zip en una ubicación de la unidad de disco duro (por ejemplo, C:\SDA).
7. Abra un mensaje de Windows PowerShell y establezca ExecutionPolicy para la sesión actual en Unrestricted.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. Ejecute el script SDA que especifica parámetros para el entorno. El script se puede usar para crear imágenes para instalar Windows 10 en una variedad de dispositivos Surface. Para obtener una lista completa de dispositivos compatibles, consulta [la descripción del parámetro Device](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) en el artículo README de SDA. 

    Por ejemplo, el siguiente comando creará una unidad USB de arranque que se puede usar para instalar Windows 10 [en Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    A continuación se muestra el resultado del script de ejemplo.

   ![Ejecutar la herramienta Acelerador de implementación de Surface.](images/sda1.png)

    El script requerirá unos 45 minutos para ejecutarse, pero podría tardar más en función de los recursos de disco y CPU disponibles. 

    Después de crear una Windows, el script le pedirá que inserte y confirme la letra de unidad de la unidad USB. A continuación, se dará formato a la unidad USB, se configurará como de arranque y se copiarán archivos para habilitar la instalación de la imagen Windows 10 para dispositivos Surface.

9. Inserta la unidad USB en el dispositivo donde quieres instalar Windows 10 y reinicia para empezar a instalar Windows 10. El arranque USB debe estar habilitado en el BIOS, lo que puede requerir que deshabilite temporalmente el arranque seguro.

> [!IMPORTANT]
> El arranque desde la unidad USB empezará inmediatamente a instalar Windows 10. Asegúrate de que el dispositivo esté listo antes de insertar el USB y reiniciarlo. 

## <a name="related-links"></a>Vínculos relacionados

 - [Herramienta de implementación de imágenes de código abierto publicada en GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [Descargar e instalar el Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

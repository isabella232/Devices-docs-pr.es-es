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
# <span data-ttu-id="3a7bd-104">Acelerador de implementaciones de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="3a7bd-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="3a7bd-105">El acelerador de implementación de Microsoft Surface (SDA) automatiza la creación y la configuración de una experiencia de implementación recomendada de Microsoft mediante las herramientas de implementación gratuitas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="3a7bd-106">Rediseñado en abril de 2020 para simplificar y automatizar la implementación de imágenes de Surface en un entorno corporativo, la herramienta SDA le permite crear una imagen de Windows "de fábrica" que puede personalizar según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="3a7bd-107">La herramienta de código empaquetado abierto basado en scripts aprovecha el Windows Assessment and Deployment Kit (ADK) para Windows 10, lo que facilita la creación de imágenes de Windows (WIM) en entornos de prueba o producción.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="3a7bd-108">Si la última versión de ADK aún no está instalada, se descargará e instalará al ejecutar la herramienta SDA.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="3a7bd-109">La imagen resultante se ajusta estrechamente a la configuración de las imágenes de recuperación de equipos integrados (BMR), sin necesidad de aplicaciones preinstaladas, como Microsoft Office o la aplicación Surface para UWP.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="3a7bd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a7bd-110">Requirements</span></span>

1. <span data-ttu-id="3a7bd-111">Una unidad USB con un tamaño mínimo de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="3a7bd-112">El disco USB tendrá el formato.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="3a7bd-113">Un archivo. ISO con Windows 10 Pro o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="3a7bd-114">La herramienta de creación de medios se puede usar para descargar Windows 10 y crear un archivo. ISO.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="3a7bd-115">Para obtener más información, consulta [Descargar Windows 10](https://www.microsoft.com/software-download/windows10).</span><span class="sxs-lookup"><span data-stu-id="3a7bd-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="3a7bd-116">Un dispositivo con Windows 10, versión 2004 o posterior, con acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="3a7bd-117">Consulte la sección [requisitos previos](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) del documento Léame para obtener una lista detallada de los requisitos.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="3a7bd-118">Cómo ejecutar el SDA</span><span class="sxs-lookup"><span data-stu-id="3a7bd-118">How to run the SDA</span></span>

**<span data-ttu-id="3a7bd-119">Para ejecutar SDA:</span><span class="sxs-lookup"><span data-stu-id="3a7bd-119">To run SDA:</span></span>**

1. <span data-ttu-id="3a7bd-120">Vaya a [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) en github.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="3a7bd-121">Revise la documentación del [Léame](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) .</span><span class="sxs-lookup"><span data-stu-id="3a7bd-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="3a7bd-122">En la página [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) , haga clic en el botón **código** y, a continuación, seleccione **Descargar zip** para guardar los archivos de forma local en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="3a7bd-123">Haga clic con el botón secundario en el archivo. zip y después haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="3a7bd-124">En la pestaña **General** , seleccione la casilla **desbloquear** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="3a7bd-125">Extraiga el archivo. zip en una ubicación de la unidad de disco duro (por ejemplo: C:\SDA).</span><span class="sxs-lookup"><span data-stu-id="3a7bd-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="3a7bd-126">Abra un símbolo del sistema de Windows PowerShell con privilegios elevados y establezca ExecutionPolicy para la sesión actual en no restringido.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="3a7bd-127">Ejecute la secuencia de comandos SDA que especifica los parámetros de su entorno.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="3a7bd-128">El script se puede usar para crear imágenes con el fin de instalar Windows 10 en una gran variedad de dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="3a7bd-129">Para obtener una lista completa de los dispositivos compatibles, consulte la descripción de los [parámetros del dispositivo](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) en el artículo Léame de SDA.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="3a7bd-130">Por ejemplo, el siguiente comando creará una unidad USB de arranque que se puede usar para [instalar Windows 10 en Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span><span class="sxs-lookup"><span data-stu-id="3a7bd-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="3a7bd-131">La salida de script de ejemplo se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-131">Sample script output is below.</span></span>

   ![Herramienta ejecutar el acelerador de despliegue de Surface](images/sda1.png)

    <span data-ttu-id="3a7bd-133">El script requerirá unos 45 minutos para ejecutarse, pero podría tardar más tiempo en función de la CPU y los recursos de disco disponibles.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="3a7bd-134">Después de crear una imagen de Windows, la secuencia de comandos le pedirá que inserte y confirme la letra de unidad de su unidad USB.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="3a7bd-135">A continuación, se formateará la unidad USB, se configurará como arrancable y los archivos se copiarán para habilitar la instalación de la imagen personalizada de Windows 10 para dispositivos de Surface.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="3a7bd-136">Inserte la unidad USB en el dispositivo donde quiera instalar Windows 10 y reinicie para empezar a instalar Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="3a7bd-137">El arranque USB debe estar habilitado en el BIOS, lo cual puede requerir la desactivación temporal del arranque seguro.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a7bd-138">Iniciar desde la unidad USB iniciará inmediatamente la instalación de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="3a7bd-139">Asegúrese de que el dispositivo está listo antes de insertar el USB y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="3a7bd-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="3a7bd-140">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="3a7bd-140">Related links</span></span>

 - [<span data-ttu-id="3a7bd-141">Herramienta de implementación de imagen de Open Source Publicada en GitHub</span><span class="sxs-lookup"><span data-stu-id="3a7bd-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="3a7bd-142">Descargar e instalar Windows ADK</span><span class="sxs-lookup"><span data-stu-id="3a7bd-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

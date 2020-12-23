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
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247312"
---
# <span data-ttu-id="cf019-104">Cómo habilitar el teclado para portátiles Surface durante la implementación de MDT</span><span class="sxs-lookup"><span data-stu-id="cf019-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="cf019-105">En este artículo se trata un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="cf019-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="cf019-106">También puede aplicar esta información a otras metodologías de implementación.</span><span class="sxs-lookup"><span data-stu-id="cf019-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="cf019-107">En la mayoría de los tipos de dispositivos de superficie, el teclado debe funcionar durante la instalación con Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="cf019-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="cf019-108">Sin embargo, Surface Laptop necesita algunos drivers adicionales para habilitar el teclado.</span><span class="sxs-lookup"><span data-stu-id="cf019-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="cf019-109">Para los dispositivos Surface Laptop (1º gen) y Surface Laptop 2, debe preparar los perfiles de selección y estructura de carpetas que le permiten especificar los drivers de teclado para usarlos durante la fase de entorno de preinstalación de Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="cf019-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="cf019-110">Para obtener más información sobre esta estructura de carpetas, consulte [implementar una imagen de Windows 10 con MDT: paso 5: preparar el repositorio de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="cf019-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="cf019-111">Si va a implementar una imagen de Windows 10 en un portátil Surface con Windows 10 en modo S preinstalado, consulte KB [4032347, problemas al implementar Windows en dispositivos Surface con el modo preinstalado de Windows 10](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="cf019-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="cf019-112">Para agregar los drivers de teclado al perfil de selección, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cf019-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="cf019-113">Descargue el archivo MSI Surface portátil más reciente de las ubicaciones apropiadas:</span><span class="sxs-lookup"><span data-stu-id="cf019-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="cf019-114">Drivers y firmware Surface Laptop (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="cf019-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="cf019-115">Drivers y firmware Surface del portátil 2</span><span class="sxs-lookup"><span data-stu-id="cf019-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="cf019-116">Portátil Surface 3 con el firmware y los drivers de procesador Intel</span><span class="sxs-lookup"><span data-stu-id="cf019-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="cf019-117">Extraiga el contenido del archivo MSI de Surface portátil en una carpeta que pueda localizar fácilmente (por ejemplo, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="cf019-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="cf019-118">Para extraer el contenido, abra una ventana de símbolo del sistema con privilegios elevados y ejecute el comando del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf019-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="cf019-119">Abra Deployment Workbench y expanda el nodo **recursos compartidos de implementación** y el recurso compartido de implementación y, a continuación, vaya a la carpeta **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="cf019-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagen que muestra la ubicación de la carpeta WindowsPEX64 en Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="cf019-121">Haga clic con el botón derecho en la carpeta **WindowsPEX64** y seleccione **importar drivers**.</span><span class="sxs-lookup"><span data-stu-id="cf019-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="cf019-122">Siga las instrucciones del Asistente para importar Controladores para importar las carpetas de controladores a la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="cf019-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="cf019-123">Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="cf019-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="cf019-124">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI.</span><span class="sxs-lookup"><span data-stu-id="cf019-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="cf019-125">Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="cf019-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="cf019-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="cf019-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="cf019-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cf019-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="cf019-130">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cf019-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="cf019-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="cf019-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="cf019-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="cf019-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="cf019-135">Para admitir Surface Laptop 2, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="cf019-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="cf019-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="cf019-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="cf019-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="cf019-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="cf019-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="cf019-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="cf019-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="cf019-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="cf019-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cf019-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="cf019-143">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cf019-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="cf019-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="cf019-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cf019-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="cf019-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cf019-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="cf019-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cf019-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="cf019-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cf019-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="cf019-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cf019-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="cf019-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="cf019-151">Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="cf019-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="cf019-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cf019-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="cf019-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cf019-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="cf019-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cf019-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="cf019-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cf019-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="cf019-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cf019-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="cf019-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cf019-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="cf019-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="cf019-160">La importación de las siguientes carpetas habilitará la funcionalidad completa del teclado, el panel táctil y el toque en PE para Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cf019-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="cf019-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="cf019-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cf019-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="cf019-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cf019-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="cf019-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cf019-164">IclSerialIOUART</span></span>
- <span data-ttu-id="cf019-165">itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-165">itouch</span></span>
- <span data-ttu-id="cf019-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="cf019-166">IclChipset</span></span>
- <span data-ttu-id="cf019-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="cf019-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="cf019-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="cf019-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="cf019-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="cf019-169">ManagementEngine</span></span>
- <span data-ttu-id="cf019-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="cf019-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="cf019-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="cf019-171">SurfaceBattery</span></span>
- <span data-ttu-id="cf019-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="cf019-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="cf019-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cf019-173">SurfaceHidMini</span></span>
- <span data-ttu-id="cf019-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cf019-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="cf019-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="cf019-175">SurfaceIntegration</span></span>
- <span data-ttu-id="cf019-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cf019-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="cf019-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="cf019-177">SurfaceService</span></span>
- <span data-ttu-id="cf019-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="cf019-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="cf019-179">Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="cf019-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="cf019-180">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI.</span><span class="sxs-lookup"><span data-stu-id="cf019-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="cf019-181">Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="cf019-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="cf019-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="cf019-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="cf019-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cf019-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="cf019-186">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cf019-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="cf019-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="cf019-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="cf019-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="cf019-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="cf019-191">Para admitir Surface Laptop 2, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="cf019-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="cf019-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="cf019-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cf019-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="cf019-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="cf019-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="cf019-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="cf019-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="cf019-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="cf019-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="cf019-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cf019-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="cf019-199">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cf019-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="cf019-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="cf019-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cf019-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="cf019-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cf019-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="cf019-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cf019-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="cf019-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cf019-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="cf019-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cf019-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="cf019-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="cf019-207">Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cf019-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="cf019-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cf019-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="cf019-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cf019-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="cf019-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cf019-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="cf019-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cf019-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="cf019-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cf019-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="cf019-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cf019-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="cf019-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cf019-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="cf019-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cf019-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf019-216">Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3.</span><span class="sxs-lookup"><span data-stu-id="cf019-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="cf019-217">Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cf019-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="cf019-218">Compruebe que la carpeta WindowsPEX64 ahora contiene los drivers importados.</span><span class="sxs-lookup"><span data-stu-id="cf019-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="cf019-219">La carpeta debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf019-219">The folder should resemble the following:</span></span>  

   ![Imagen que muestra los drivers recién importados en la carpeta WindowsPEX64 de Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="cf019-221">Configure un perfil de selección que use la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="cf019-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="cf019-222">El perfil de selección debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf019-222">The selection profile should resemble the following:</span></span>  

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="cf019-224">Configure las propiedades de Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cf019-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="cf019-225">Para **plataforma**, seleccione **x64**.</span><span class="sxs-lookup"><span data-stu-id="cf019-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="cf019-226">En **Perfil de selección**, seleccione el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="cf019-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="cf019-227">Seleccione **incluir todos los drivers del perfil de selección**.</span><span class="sxs-lookup"><span data-stu-id="cf019-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagen que muestra las propiedades de Windows PE del recurso compartido de implementación de MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="cf019-229">Verifique que haya configurado el resto de los drivers de equipos portátiles con un perfil de selección o una variable **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="cf019-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="cf019-230">Para portátiles Surface (primer gen), el modelo es un **portátil Surface**.</span><span class="sxs-lookup"><span data-stu-id="cf019-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="cf019-231">Los drivers de equipos portátiles de superficie restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, tal como se muestra en la figura que sigue a esta lista.</span><span class="sxs-lookup"><span data-stu-id="cf019-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="cf019-232">Para el portátil Surface 2, el modelo es el **portátil Surface 2**.</span><span class="sxs-lookup"><span data-stu-id="cf019-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="cf019-233">Los drivers de equipos portátiles restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="cf019-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="cf019-234">Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3.</span><span class="sxs-lookup"><span data-stu-id="cf019-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="cf019-235">Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cf019-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagen que muestra los drivers de la superficie normal (1º gen) en la carpeta Surface Laptop de Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="cf019-237">Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y la configuración relacionada, continúe el proceso de implementación tal como se describe en [implementar una imagen de Windows 10 con MDT: paso 6: crear la secuencia de tareas de implementación](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="cf019-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

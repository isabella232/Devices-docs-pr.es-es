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
# <span data-ttu-id="cff9e-104">Cómo habilitar el teclado para portátiles Surface durante la implementación de MDT</span><span class="sxs-lookup"><span data-stu-id="cff9e-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="cff9e-105">En este artículo se trata un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="cff9e-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="cff9e-106">También puede aplicar esta información a otras metodologías de implementación.</span><span class="sxs-lookup"><span data-stu-id="cff9e-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="cff9e-107">En la mayoría de los tipos de dispositivos de superficie, el teclado debe funcionar durante la instalación con Lite Touch (LTI).</span><span class="sxs-lookup"><span data-stu-id="cff9e-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="cff9e-108">Sin embargo, Surface Laptop necesita algunos drivers adicionales para habilitar el teclado.</span><span class="sxs-lookup"><span data-stu-id="cff9e-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="cff9e-109">Para los dispositivos Surface Laptop (1º gen) y Surface Laptop 2, debe preparar los perfiles de selección y estructura de carpetas que le permiten especificar los drivers de teclado para usarlos durante la fase de entorno de preinstalación de Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="cff9e-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="cff9e-110">Para obtener más información sobre esta estructura de carpetas, consulte [implementar una imagen de Windows 10 con MDT: paso 5: preparar el repositorio de drivers](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span><span class="sxs-lookup"><span data-stu-id="cff9e-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="cff9e-111">Por el momento, no se admite agregar controladores de teclado de Surface Laptop 2 y Surface Laptop 3 en la misma instancia de inicio de Windows PE debido a un conflicto de drivers; Use instancias independientes en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cff9e-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cff9e-112">Si va a implementar una imagen de Windows 10 en un portátil Surface con Windows 10 en modo S preinstalado, consulte KB [4032347, problemas al implementar Windows en dispositivos Surface con el modo preinstalado de Windows 10](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span><span class="sxs-lookup"><span data-stu-id="cff9e-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="cff9e-113">Para agregar los drivers de teclado al perfil de selección, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cff9e-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="cff9e-114">Descargue el archivo MSI Surface portátil más reciente de las ubicaciones apropiadas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="cff9e-115">Drivers y firmware Surface Laptop (1ª generación)</span><span class="sxs-lookup"><span data-stu-id="cff9e-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="cff9e-116">Drivers y firmware Surface del portátil 2</span><span class="sxs-lookup"><span data-stu-id="cff9e-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="cff9e-117">Portátil Surface 3 con el firmware y los drivers de procesador Intel</span><span class="sxs-lookup"><span data-stu-id="cff9e-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="cff9e-118">Extraiga el contenido del archivo MSI de Surface portátil en una carpeta que pueda localizar fácilmente (por ejemplo, c:\ surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="cff9e-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="cff9e-119">Para extraer el contenido, abra una ventana de símbolo del sistema con privilegios elevados y ejecute el comando del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cff9e-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="cff9e-120">Abra Deployment Workbench y expanda el nodo **recursos compartidos de implementación** y el recurso compartido de implementación y, a continuación, vaya a la carpeta **WindowsPEX64** .</span><span class="sxs-lookup"><span data-stu-id="cff9e-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagen que muestra la ubicación de la carpeta WindowsPEX64 en Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="cff9e-122">Haga clic con el botón derecho en la carpeta **WindowsPEX64** y seleccione **importar drivers**.</span><span class="sxs-lookup"><span data-stu-id="cff9e-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="cff9e-123">Siga las instrucciones del Asistente para importar Controladores para importar las carpetas de controladores a la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="cff9e-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="cff9e-124">Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="cff9e-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="cff9e-125">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI.</span><span class="sxs-lookup"><span data-stu-id="cff9e-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="cff9e-126">Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="cff9e-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="cff9e-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="cff9e-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="cff9e-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="cff9e-131">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cff9e-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="cff9e-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="cff9e-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="cff9e-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="cff9e-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="cff9e-136">Para admitir Surface Laptop 2, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="cff9e-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="cff9e-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="cff9e-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="cff9e-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="cff9e-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="cff9e-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="cff9e-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="cff9e-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="cff9e-144">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cff9e-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="cff9e-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="cff9e-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="cff9e-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="cff9e-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cff9e-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="cff9e-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cff9e-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="cff9e-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cff9e-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="cff9e-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="cff9e-152">Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="cff9e-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="cff9e-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="cff9e-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="cff9e-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cff9e-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="cff9e-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cff9e-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="cff9e-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cff9e-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="cff9e-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cff9e-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="cff9e-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="cff9e-161">La importación de las siguientes carpetas habilitará la funcionalidad completa del teclado, el panel táctil y el toque en PE para Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cff9e-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="cff9e-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="cff9e-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="cff9e-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="cff9e-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cff9e-165">IclSerialIOUART</span></span>
- <span data-ttu-id="cff9e-166">itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-166">itouch</span></span>
- <span data-ttu-id="cff9e-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="cff9e-167">IclChipset</span></span>
- <span data-ttu-id="cff9e-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="cff9e-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="cff9e-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="cff9e-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="cff9e-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="cff9e-170">ManagementEngine</span></span>
- <span data-ttu-id="cff9e-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="cff9e-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="cff9e-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="cff9e-172">SurfaceBattery</span></span>
- <span data-ttu-id="cff9e-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="cff9e-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="cff9e-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cff9e-174">SurfaceHidMini</span></span>
- <span data-ttu-id="cff9e-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cff9e-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="cff9e-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="cff9e-176">SurfaceIntegration</span></span>
- <span data-ttu-id="cff9e-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cff9e-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="cff9e-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="cff9e-178">SurfaceService</span></span>
- <span data-ttu-id="cff9e-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="cff9e-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="cff9e-180">Compruebe el paquete MSI descargado para determinar el formato y la estructura de directorios.</span><span class="sxs-lookup"><span data-stu-id="cff9e-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="cff9e-181">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI anteriores) o SurfaceUpdate (archivos MSI más recientes) según el momento en que se lanzó el MSI.</span><span class="sxs-lookup"><span data-stu-id="cff9e-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="cff9e-182">Para dar soporte a un portátil Surface (1ª generación), importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="cff9e-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="cff9e-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="cff9e-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="cff9e-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="cff9e-187">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cff9e-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="cff9e-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="cff9e-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="cff9e-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="cff9e-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="cff9e-192">Para admitir Surface Laptop 2, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="cff9e-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="cff9e-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="cff9e-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="cff9e-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="cff9e-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="cff9e-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="cff9e-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="cff9e-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="cff9e-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="cff9e-200">O para los archivos MSI más recientes que comiencen con "SurfaceUpdate", use:</span><span class="sxs-lookup"><span data-stu-id="cff9e-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="cff9e-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="cff9e-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="cff9e-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="cff9e-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cff9e-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="cff9e-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cff9e-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="cff9e-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cff9e-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="cff9e-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="cff9e-208">Para admitir Surface Laptop 3 con procesador Intel, importe las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="cff9e-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="cff9e-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="cff9e-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="cff9e-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="cff9e-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="cff9e-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="cff9e-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="cff9e-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="cff9e-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="cff9e-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="cff9e-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="cff9e-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="cff9e-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="cff9e-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="cff9e-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="cff9e-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="cff9e-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="cff9e-217">Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3.</span><span class="sxs-lookup"><span data-stu-id="cff9e-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="cff9e-218">Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cff9e-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="cff9e-219">Compruebe que la carpeta WindowsPEX64 ahora contiene los drivers importados.</span><span class="sxs-lookup"><span data-stu-id="cff9e-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="cff9e-220">La carpeta debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cff9e-220">The folder should resemble the following:</span></span>  

   ![Imagen que muestra los drivers recién importados en la carpeta WindowsPEX64 de Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="cff9e-222">Configure un perfil de selección que use la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="cff9e-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="cff9e-223">El perfil de selección debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="cff9e-223">The selection profile should resemble the following:</span></span>  

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="cff9e-225">Configure las propiedades de Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cff9e-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="cff9e-226">Para **plataforma**, seleccione **x64**.</span><span class="sxs-lookup"><span data-stu-id="cff9e-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="cff9e-227">En **Perfil de selección**, seleccione el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="cff9e-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="cff9e-228">Seleccione **incluir todos los drivers del perfil de selección**.</span><span class="sxs-lookup"><span data-stu-id="cff9e-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagen que muestra las propiedades de Windows PE del recurso compartido de implementación de MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="cff9e-230">Verifique que haya configurado el resto de los drivers de equipos portátiles con un perfil de selección o una variable **DriverGroup001** .</span><span class="sxs-lookup"><span data-stu-id="cff9e-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="cff9e-231">Para portátiles Surface (primer gen), el modelo es un **portátil Surface**.</span><span class="sxs-lookup"><span data-stu-id="cff9e-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="cff9e-232">Los drivers de equipos portátiles de superficie restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, tal como se muestra en la figura que sigue a esta lista.</span><span class="sxs-lookup"><span data-stu-id="cff9e-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="cff9e-233">Para el portátil Surface 2, el modelo es el **portátil Surface 2**.</span><span class="sxs-lookup"><span data-stu-id="cff9e-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="cff9e-234">Los drivers de equipos portátiles restantes deberían residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="cff9e-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="cff9e-235">Para Surface Laptop 3 con procesador Intel, el modelo es el portátil Surface 3.</span><span class="sxs-lookup"><span data-stu-id="cff9e-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="cff9e-236">Los drivers de equipos portátiles de superficie restante se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="cff9e-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagen que muestra los drivers de la superficie normal (1º gen) en la carpeta Surface Laptop de Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="cff9e-238">Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y la configuración relacionada, continúe el proceso de implementación tal como se describe en [implementar una imagen de Windows 10 con MDT: paso 6: crear la secuencia de tareas de implementación](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span><span class="sxs-lookup"><span data-stu-id="cff9e-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

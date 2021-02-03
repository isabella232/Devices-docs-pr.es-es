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
# <span data-ttu-id="5a1a0-104">Cómo habilitar el teclado de Surface Laptop durante la implementación de MDT</span><span class="sxs-lookup"><span data-stu-id="5a1a0-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="5a1a0-105">En este artículo se trata un enfoque de implementación que usa Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="5a1a0-106">También puede aplicar esta información a otras metodologías de implementación.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="5a1a0-107">En la mayoría de los tipos de dispositivos Surface, el teclado debe funcionar durante lite touch Installation (LTI).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="5a1a0-108">Sin embargo, Surface Laptop requiere algunos controladores adicionales para habilitar el teclado.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="5a1a0-109">Para dispositivos Surface Laptop (1.ª generación) y Surface Laptop 2, debes preparar la estructura de carpetas y los perfiles de selección que te permiten especificar controladores de teclado para usarlos durante la fase del Entorno de preinstalación de Windows (Windows PE) de LTI.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="5a1a0-110">Para obtener más información sobre esta estructura de carpetas, consulta Implementar una imagen de [Windows 10 con MDT: Paso 5: Preparar el repositorio de controladores.](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)</span><span class="sxs-lookup"><span data-stu-id="5a1a0-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="5a1a0-111">Al usar controladores de teclado para Surface Laptop 2 y Surface Laptop 3 en la misma instancia de arranque de Windows PE, es posible que deba restablecer manualmente el firmware si el teclado o el panel táctil no funcionan en Windows PE:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="5a1a0-112">Mantén presionado el botón de encendido durante 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="5a1a0-113">Si estás conectado a una unidad de alimentación (PSU), mantén presionado el botón de encendido hasta que veas la luz al final del cable PSU brevemente antes de volver a activarlo.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a1a0-114">Si vas a implementar una imagen de Windows 10 en un Surface Laptop que tenga Windows 10 en modo S preinstalado, consulta KB [4032347,](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)Problemas al implementar Windows en dispositivos Surface con Windows 10 preinstalado en modo S.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="5a1a0-115">Para agregar los controladores de teclado al perfil de selección, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="5a1a0-116">Descarga el archivo MSI más reciente de Surface Laptop desde las ubicaciones adecuadas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="5a1a0-117">Controladores y firmware de Surface Laptop (1.ª generación)</span><span class="sxs-lookup"><span data-stu-id="5a1a0-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="5a1a0-118">Controladores y firmware de Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="5a1a0-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="5a1a0-119">Surface Laptop 3 con controladores de procesador Intel y firmware</span><span class="sxs-lookup"><span data-stu-id="5a1a0-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="5a1a0-120">Extrae el contenido del archivo MSI de Surface Laptop en una carpeta que puedas encontrar fácilmente (por ejemplo, c:\surface_laptop_drivers).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="5a1a0-121">Para extraer el contenido, abra una ventana del símbolo del sistema con privilegios elevados y ejecute el comando en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="5a1a0-122">Abre Deployment Workbench, expande el nodo **Recursos compartidos** de implementación y el recurso compartido de implementación y, a continuación, navega a la **carpeta WindowsPEX64.**</span><span class="sxs-lookup"><span data-stu-id="5a1a0-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![Imagen que muestra la ubicación de la carpeta WindowsPEX64 en Deployment Workbench](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="5a1a0-124">Haga clic con el botón secundario **en la carpeta WindowsPEX64** y seleccione **Importar controladores.**</span><span class="sxs-lookup"><span data-stu-id="5a1a0-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="5a1a0-125">Sigue las instrucciones del Asistente para importar controladores para importar las carpetas de controladores en la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="5a1a0-126">Comprueba el paquete MSI descargado para determinar el formato y la estructura del directorio.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="5a1a0-127">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI más antiguos) o SurfaceUpdate (archivos MSI más recientes), en función de cuándo se publicó el MSI.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="5a1a0-128">Para admitir Surface Laptop (1.ª generación), importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="5a1a0-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="5a1a0-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="5a1a0-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="5a1a0-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5a1a0-133">O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5a1a0-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="5a1a0-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="5a1a0-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5a1a0-138">Para admitir Surface Laptop 2, importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="5a1a0-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="5a1a0-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="5a1a0-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="5a1a0-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="5a1a0-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="5a1a0-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="5a1a0-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5a1a0-146">O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5a1a0-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="5a1a0-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="5a1a0-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="5a1a0-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="5a1a0-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5a1a0-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5a1a0-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5a1a0-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5a1a0-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="5a1a0-154">Para admitir Surface Laptop 3 con procesador Intel, importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="5a1a0-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="5a1a0-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="5a1a0-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="5a1a0-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5a1a0-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5a1a0-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5a1a0-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5a1a0-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5a1a0-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="5a1a0-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5a1a0-163">La importación de las siguientes carpetas habilitará la funcionalidad de teclado completo, panel táctil y táctil en PE para Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="5a1a0-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-165">SerialIOI2C</span></span>
    - <span data-ttu-id="5a1a0-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-166">SerialIOSPI</span></span>
    - <span data-ttu-id="5a1a0-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-167">SerialIOUART</span></span>
    - <span data-ttu-id="5a1a0-168">itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-168">itouch</span></span>
    - <span data-ttu-id="5a1a0-169">Conjunto de chips</span><span class="sxs-lookup"><span data-stu-id="5a1a0-169">Chipset</span></span>
    - <span data-ttu-id="5a1a0-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="5a1a0-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="5a1a0-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="5a1a0-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="5a1a0-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="5a1a0-172">ManagementEngine</span></span>
    - <span data-ttu-id="5a1a0-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="5a1a0-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="5a1a0-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="5a1a0-174">SurfaceBattery</span></span>
    - <span data-ttu-id="5a1a0-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="5a1a0-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="5a1a0-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5a1a0-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="5a1a0-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5a1a0-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="5a1a0-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="5a1a0-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="5a1a0-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5a1a0-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="5a1a0-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="5a1a0-180">SurfaceService</span></span>
    - <span data-ttu-id="5a1a0-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="5a1a0-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="5a1a0-182">Comprueba el paquete MSI descargado para determinar el formato y la estructura del directorio.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="5a1a0-183">La estructura de directorios comenzará con SurfacePlatformInstaller (archivos MSI más antiguos) o SurfaceUpdate (archivos MSI más recientes), en función de cuándo se publicó el MSI.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="5a1a0-184">Para admitir Surface Laptop (1.ª generación), importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="5a1a0-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="5a1a0-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="5a1a0-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="5a1a0-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5a1a0-189">O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5a1a0-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="5a1a0-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="5a1a0-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5a1a0-194">Para admitir Surface Laptop 2, importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="5a1a0-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="5a1a0-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="5a1a0-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="5a1a0-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="5a1a0-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="5a1a0-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="5a1a0-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="5a1a0-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="5a1a0-202">O para los archivos MSI más recientes que comienzan con "SurfaceUpdate", usa:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="5a1a0-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="5a1a0-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="5a1a0-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="5a1a0-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5a1a0-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5a1a0-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5a1a0-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5a1a0-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="5a1a0-210">Para admitir Surface Laptop 3 con procesador Intel, importa las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="5a1a0-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="5a1a0-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="5a1a0-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="5a1a0-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="5a1a0-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="5a1a0-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="5a1a0-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="5a1a0-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="5a1a0-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="5a1a0-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="5a1a0-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="5a1a0-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="5a1a0-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="5a1a0-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="5a1a0-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="5a1a0-219">Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="5a1a0-220">Los controladores restantes de Surface Laptop se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="5a1a0-221">Comprueba que la carpeta WindowsPEX64 ahora contiene los controladores importados.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="5a1a0-222">La carpeta debe ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-222">The folder should resemble the following:</span></span>  

   ![Imagen que muestra los controladores recién importados en la carpeta WindowsPEX64 de Deployment Workbench](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="5a1a0-224">Configurar un perfil de selección que use la carpeta WindowsPEX64.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="5a1a0-225">El perfil de selección debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-225">The selection profile should resemble the following:</span></span>  

   ![Imagen que muestra la carpeta WindowsPEX64 seleccionada como parte de un perfil de selección](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="5a1a0-227">Configura las propiedades de Windows PE del recurso compartido de implementación de MDT para usar el nuevo perfil de selección, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="5a1a0-228">Para **Plataforma,** seleccione **x64**.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="5a1a0-229">En **Perfil de selección,** seleccione el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="5a1a0-230">Selecciona **Incluir todos los controladores del perfil de selección.**</span><span class="sxs-lookup"><span data-stu-id="5a1a0-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![Imagen que muestra las propiedades de Windows PE del recurso compartido de implementación de MDT](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="5a1a0-232">Comprueba que has configurado los controladores restantes de Surface Laptop mediante un perfil de selección o una variable **DriverGroup001.**</span><span class="sxs-lookup"><span data-stu-id="5a1a0-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="5a1a0-233">Para Surface Laptop (1.ª generación), el modelo es **Surface Laptop.**</span><span class="sxs-lookup"><span data-stu-id="5a1a0-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="5a1a0-234">Los controladores restantes de Surface Laptop deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop, como se muestra en la figura que sigue a esta lista.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="5a1a0-235">Para Surface Laptop 2, el modelo es **Surface Laptop 2**.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="5a1a0-236">Los controladores restantes de Surface Laptop deben residir en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="5a1a0-237">Para Surface Laptop 3 con procesador Intel, el modelo es Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="5a1a0-238">Los controladores restantes de Surface Laptop se encuentran en la carpeta \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![Imagen que muestra los controladores normales de Surface Laptop (1.ª generación) en la carpeta Surface Laptop de Deployment Workbench](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="5a1a0-240">Después de configurar el recurso compartido de implementación de MDT para usar el nuevo perfil de selección y las opciones relacionadas, continúa el proceso de implementación como se describe en Implementar una imagen de [Windows 10 con MDT: Paso 6:](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)Crear la secuencia de tareas de implementación.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>

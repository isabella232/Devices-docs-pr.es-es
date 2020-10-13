---
title: Implementar el Kit de herramientas de diagnóstico de Surface para empresas
description: En este tema se explica cómo usar el kit de herramientas de diagnóstico de Surface para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 1f2661811516507abd432dba602cf8ce81e6dbb3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114668"
---
# <span data-ttu-id="8eae9-103">Implementar el Kit de herramientas de diagnóstico de Surface para empresas</span><span class="sxs-lookup"><span data-stu-id="8eae9-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="8eae9-104">El kit de herramientas de diagnóstico de Microsoft Surface para empresas (SDT) permite a los administradores de ti investigar, solucionar y resolver problemas de hardware, software y firmware rápidamente con dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="8eae9-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="8eae9-105">Puede ejecutar una variedad de pruebas de diagnóstico y reparaciones de software además de obtener información y consejos sobre el estado del dispositivo para resolver los problemas.</span><span class="sxs-lookup"><span data-stu-id="8eae9-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="8eae9-106">En concreto, SDT para empresas le permite:</span><span class="sxs-lookup"><span data-stu-id="8eae9-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="8eae9-107">Personalizar el paquete.</span><span class="sxs-lookup"><span data-stu-id="8eae9-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="8eae9-108">Ejecute la aplicación con comandos.</span><span class="sxs-lookup"><span data-stu-id="8eae9-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="8eae9-109">Ejecute varias pruebas de hardware para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="8eae9-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="8eae9-110">Generar registros para analizar problemas.</span><span class="sxs-lookup"><span data-stu-id="8eae9-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="8eae9-111">Obtener información detallada sobre la comparación de dispositivos y la configuración óptima.</span><span class="sxs-lookup"><span data-stu-id="8eae9-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="8eae9-112">Escenarios principales y recursos de descarga</span><span class="sxs-lookup"><span data-stu-id="8eae9-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="8eae9-113">Para ejecutar SDT para empresas, descargue los componentes enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="8eae9-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="8eae9-114">Modo</span><span class="sxs-lookup"><span data-stu-id="8eae9-114">Mode</span></span> |  <span data-ttu-id="8eae9-115">Escenarios principales</span><span class="sxs-lookup"><span data-stu-id="8eae9-115">Primary scenarios</span></span> | <span data-ttu-id="8eae9-116">Descargar</span><span class="sxs-lookup"><span data-stu-id="8eae9-116">Download</span></span> | <span data-ttu-id="8eae9-117">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="8eae9-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="8eae9-118">Modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="8eae9-118">Desktop mode</span></span> |  <span data-ttu-id="8eae9-119">Ayudar a los usuarios a ejecutar SDT en sus dispositivos Surface para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="8eae9-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="8eae9-120">Cree un paquete personalizado para implementarlo en uno o más dispositivos de superficie que permitan a los usuarios seleccionar registros específicos para recopilar y analizar.</span><span class="sxs-lookup"><span data-stu-id="8eae9-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="8eae9-121">Paquete MSI distribuible distribuible:</span><span class="sxs-lookup"><span data-stu-id="8eae9-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="8eae9-122">Kit de herramientas de diagnóstico de Microsoft Surface para Business Installer</span><span class="sxs-lookup"><span data-stu-id="8eae9-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="8eae9-123">Herramientas de Surface para TI</span><span class="sxs-lookup"><span data-stu-id="8eae9-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="8eae9-124">Usar el kit de herramientas de diagnóstico de Surface en el modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="8eae9-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="8eae9-125">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8eae9-125">Command line</span></span> |  <span data-ttu-id="8eae9-126">Solucione directamente los dispositivos de superficie sin interacción del usuario con herramientas estándar, como Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8eae9-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="8eae9-127">Incluye los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="8eae9-128">Recopila todos los archivos de registro</span><span class="sxs-lookup"><span data-stu-id="8eae9-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="8eae9-129">ejecuta los diagnósticos de estado mediante el analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="8eae9-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="8eae9-130">comprueba si faltan actualizaciones del firmware o el controlador en Windows Update.</span><span class="sxs-lookup"><span data-stu-id="8eae9-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="8eae9-131">verifica la información de garantía.</span><span class="sxs-lookup"><span data-stu-id="8eae9-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="8eae9-132">Aplicación de consola SDT:</span><span class="sxs-lookup"><span data-stu-id="8eae9-132">SDT console app:</span></span><br><span data-ttu-id="8eae9-133">Consola de la aplicación Microsoft Surface Diagnostics</span><span class="sxs-lookup"><span data-stu-id="8eae9-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="8eae9-134">Herramientas de Surface para TI</span><span class="sxs-lookup"><span data-stu-id="8eae9-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="8eae9-135">Ejecutar el kit de herramientas de diagnóstico de superficie con comandos</span><span class="sxs-lookup"><span data-stu-id="8eae9-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="8eae9-136">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="8eae9-136">Supported devices</span></span> 

<span data-ttu-id="8eae9-137">SDT para empresas es compatible con los dispositivos Surface 3 y versiones posteriores, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="8eae9-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="8eae9-138">Portátil Surface Go</span><span class="sxs-lookup"><span data-stu-id="8eae9-138">Surface Laptop Go</span></span>
- <span data-ttu-id="8eae9-139">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-139">Surface Book 3</span></span>
- <span data-ttu-id="8eae9-140">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="8eae9-140">Surface Go 2</span></span>
- <span data-ttu-id="8eae9-141">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="8eae9-141">Surface Pro X</span></span>
- <span data-ttu-id="8eae9-142">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8eae9-142">Surface Pro 7</span></span>
- <span data-ttu-id="8eae9-143">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-143">Surface Laptop 3</span></span>
- <span data-ttu-id="8eae9-144">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="8eae9-144">Surface Pro 6</span></span>
- <span data-ttu-id="8eae9-145">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="8eae9-145">Surface Laptop 2</span></span>
- <span data-ttu-id="8eae9-146">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8eae9-146">Surface Go</span></span>
- <span data-ttu-id="8eae9-147">Ir a la superficie con LTE</span><span class="sxs-lookup"><span data-stu-id="8eae9-147">Surface Go with LTE</span></span>
- <span data-ttu-id="8eae9-148">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="8eae9-148">Surface Book 2</span></span>
- <span data-ttu-id="8eae9-149">Surface Pro con LTE avanzada (modelo 1807)</span><span class="sxs-lookup"><span data-stu-id="8eae9-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="8eae9-150">Surface Pro (modelo 1796)</span><span class="sxs-lookup"><span data-stu-id="8eae9-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="8eae9-151">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="8eae9-151">Surface Laptop</span></span>
- <span data-ttu-id="8eae9-152">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="8eae9-152">Surface Studio</span></span>
- <span data-ttu-id="8eae9-153">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="8eae9-153">Surface Studio 2</span></span>
- <span data-ttu-id="8eae9-154">Surface Book</span><span class="sxs-lookup"><span data-stu-id="8eae9-154">Surface Book</span></span>
- <span data-ttu-id="8eae9-155">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="8eae9-155">Surface Pro 4</span></span>
- <span data-ttu-id="8eae9-156">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="8eae9-156">Surface 3 LTE</span></span>
- <span data-ttu-id="8eae9-157">Surface 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-157">Surface 3</span></span>
- <span data-ttu-id="8eae9-158">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-158">Surface Pro 3</span></span>

## <span data-ttu-id="8eae9-159">Instalación de Surface Diagnostic Toolkit for Business</span><span class="sxs-lookup"><span data-stu-id="8eae9-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="8eae9-160">Para crear un paquete SDT que puede distribuir a los usuarios de su organización:</span><span class="sxs-lookup"><span data-stu-id="8eae9-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="8eae9-161">Inicia sesión en tu dispositivo Surface con la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="8eae9-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="8eae9-162">Descargue el paquete de Windows Installer (. msi) SDT desde la [Página de descarga herramientas para ti](https://www.microsoft.com/download/details.aspx?id=46703) y cópielo en una ubicación preferida del dispositivo Surface, como el escritorio.</span><span class="sxs-lookup"><span data-stu-id="8eae9-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="8eae9-163">Aparece el Asistente de configuración SDT, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="8eae9-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="8eae9-164">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8eae9-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="8eae9-165">Si el Asistente de configuración no aparece, asegúrese de que ha iniciado sesión en la cuenta de administrador del equipo.</span><span class="sxs-lookup"><span data-stu-id="8eae9-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Bienvenido al asistente de configuración del kit de herramientas de diagnóstico de Surface](images/sdt-1.png)

    *<span data-ttu-id="8eae9-167">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="8eae9-167">Figure 1.</span></span> <span data-ttu-id="8eae9-168">Asistente de configuración del kit de herramientas de diagnóstico de Surface</span><span class="sxs-lookup"><span data-stu-id="8eae9-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="8eae9-169">Cuando aparezca el Asistente de configuración SDT, haga clic en **siguiente**y acepte el contrato de licencia para el usuario final (CLUF).</span><span class="sxs-lookup"><span data-stu-id="8eae9-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="8eae9-170">En la pantalla de opciones de instalación, cambie la ubicación de instalación predeterminada, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8eae9-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="8eae9-171">En tipo de configuración, seleccione **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="8eae9-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="8eae9-172">La opción estándar permite a los usuarios ejecutar la herramienta de diagnóstico directamente en su dispositivo Surface, siempre y cuando hayan iniciado sesión en su dispositivo con una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="8eae9-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Opciones de instalación: avanzadas](images/sdt-install.png)

7. <span data-ttu-id="8eae9-174">Haga clic en **siguiente** y, después, en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="8eae9-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="8eae9-175">Instalar con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8eae9-175">Installing using the command line</span></span>
<span data-ttu-id="8eae9-176">Si lo desea, puede instalar SDT en un símbolo del sistema y establecer una marca personalizada para instalar la herramienta en el modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="8eae9-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="8eae9-177">SDT contiene las siguientes marcas de opción de instalación:</span><span class="sxs-lookup"><span data-stu-id="8eae9-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="8eae9-178">envía datos de telemetría a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8eae9-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="8eae9-179">La marca acepta `0` deshabilitado o `1` habilitado.</span><span class="sxs-lookup"><span data-stu-id="8eae9-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="8eae9-180">El valor predeterminado es `1` Enviar telemetría.</span><span class="sxs-lookup"><span data-stu-id="8eae9-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="8eae9-181">configura la herramienta para que se instale en el modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="8eae9-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="8eae9-182">La marca acepta el `0` modo de cliente o el `1` modo de administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="8eae9-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="8eae9-183">El valor predeterminado es `0`.</span><span class="sxs-lookup"><span data-stu-id="8eae9-183">The default value is `0`.</span></span>

### <span data-ttu-id="8eae9-184">Para instalar SDT desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="8eae9-185">Abra un símbolo del sistema y escriba:</span><span class="sxs-lookup"><span data-stu-id="8eae9-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="8eae9-186">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8eae9-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="8eae9-187">Ubicación de SDT en el dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="8eae9-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="8eae9-188">Tanto SDT como la consola de la aplicación SDT están instaladas en `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="8eae9-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="8eae9-189">Además del archivo. exe, SDT instala un archivo JSON y un archivo admin.dll (modules\admin.dll), como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="8eae9-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![lista de archivos instalados de SDT en el explorador de archivos](images/sdt-2.png)

*<span data-ttu-id="8eae9-191">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="8eae9-191">Figure 2.</span></span> <span data-ttu-id="8eae9-192">Archivos instalados por SDT</span><span class="sxs-lookup"><span data-stu-id="8eae9-192">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="8eae9-193">Preparar el paquete SDT para la distribución</span><span class="sxs-lookup"><span data-stu-id="8eae9-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="8eae9-194">Crear un paquete personalizado le permite dirigir la herramienta a problemas conocidos específicos.</span><span class="sxs-lookup"><span data-stu-id="8eae9-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="8eae9-195">Haga clic en **inicio > ejecutar**, escriba **Surface** y luego haga clic en **Surface Diagnostic Toolkit para empresas**.</span><span class="sxs-lookup"><span data-stu-id="8eae9-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="8eae9-196">Cuando se abra la herramienta, haga clic en **crear paquete personalizado**, como se muestra en la ilustración 3.</span><span class="sxs-lookup"><span data-stu-id="8eae9-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Crear una opción de paquete personalizado](images/sdt-3.png)

    *<span data-ttu-id="8eae9-198">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="8eae9-198">Figure 3.</span></span> <span data-ttu-id="8eae9-199">Crear paquete personalizado</span><span class="sxs-lookup"><span data-stu-id="8eae9-199">Create custom package</span></span>*

### <span data-ttu-id="8eae9-200">Configuración de idioma y telemetría</span><span class="sxs-lookup"><span data-stu-id="8eae9-200">Language and telemetry settings</span></span>

  <span data-ttu-id="8eae9-201">Al crear un paquete, puede seleccionar la configuración de idioma o dejar de enviar la información de telemetría a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8eae9-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="8eae9-202">De forma predeterminada, SDT envía telemetría a Microsoft que se usa para mejorar la aplicación de acuerdo con la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="8eae9-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="8eae9-203">Si desea rechazar, desactive la casilla al crear un paquete personalizado, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="8eae9-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="8eae9-204">O desactive la casilla de verificación **Enviar telemetría a Microsoft** en la página de **Opciones de instalación** durante SDT Setup.</span><span class="sxs-lookup"><span data-stu-id="8eae9-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="8eae9-205">Esta configuración no afecta a la telemetría mínima almacenada automáticamente en los servidores de Microsoft cuando se ejecutan pruebas y reparaciones que requieren una conexión a Internet, como Windows Update y la reparación de software, o proporcionan comentarios con los botones de sonrisa o enfadado de la barra de herramientas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8eae9-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Seleccionar configuración de idioma y telemetría](images/sdt-4.png)

*<span data-ttu-id="8eae9-207">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="8eae9-207">Figure 4.</span></span> <span data-ttu-id="8eae9-208">Seleccionar configuración de idioma y telemetría</span><span class="sxs-lookup"><span data-stu-id="8eae9-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="8eae9-209">Página de Windows Update</span><span class="sxs-lookup"><span data-stu-id="8eae9-209">Windows Update page</span></span>

<span data-ttu-id="8eae9-210">Seleccione la opción adecuada para su organización.</span><span class="sxs-lookup"><span data-stu-id="8eae9-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="8eae9-211">Normalmente, la mayoría de las organizaciones con varios usuarios seleccionarán recibir actualizaciones a través de Windows Server Update Services (WSUS), como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="8eae9-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="8eae9-212">Si usa paquetes de Windows Update locales o WSUS, escriba la ruta de acceso según corresponda.</span><span class="sxs-lookup"><span data-stu-id="8eae9-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Seleccione la opción Windows Update](images/sdt-5.png)

*<span data-ttu-id="8eae9-214">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="8eae9-214">Figure 5.</span></span> <span data-ttu-id="8eae9-215">Opción Windows Update</span><span class="sxs-lookup"><span data-stu-id="8eae9-215">Windows Update option</span></span>*

### <span data-ttu-id="8eae9-216">Página de reparación de software</span><span class="sxs-lookup"><span data-stu-id="8eae9-216">Software repair page</span></span>

<span data-ttu-id="8eae9-217">Esto le permite seleccionar o quitar la opción de ejecutar actualizaciones de reparación de software.</span><span class="sxs-lookup"><span data-stu-id="8eae9-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![Seleccione la opción de reparación de software](images/sdt-6.png)

*<span data-ttu-id="8eae9-219">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="8eae9-219">Figure 6.</span></span> <span data-ttu-id="8eae9-220">Opción de reparación de software</span><span class="sxs-lookup"><span data-stu-id="8eae9-220">Software repair option</span></span>*

### <span data-ttu-id="8eae9-221">Recopilar registros y guardar la página del paquete</span><span class="sxs-lookup"><span data-stu-id="8eae9-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="8eae9-222">Puede seleccionar ejecutar una amplia variedad de registros entre las aplicaciones, los drivers, el hardware y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8eae9-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="8eae9-223">Haga clic en el área correspondiente y seleccione en el menú de registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="8eae9-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="8eae9-224">Después, puede guardar el paquete en un punto de distribución de software o en una ubicación equivalente a la que los usuarios puedan tener acceso.</span><span class="sxs-lookup"><span data-stu-id="8eae9-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Seleccionar opciones de registro](images/sdt-7.png)

*<span data-ttu-id="8eae9-226">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="8eae9-226">Figure 7.</span></span> <span data-ttu-id="8eae9-227">Opción log y guardar paquete</span><span class="sxs-lookup"><span data-stu-id="8eae9-227">Log option and save package</span></span>*

## <span data-ttu-id="8eae9-228">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8eae9-228">Next steps</span></span>

- [<span data-ttu-id="8eae9-229">Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="8eae9-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="8eae9-230">Usar el kit de herramientas de diagnóstico de Surface para empresas con comandos</span><span class="sxs-lookup"><span data-stu-id="8eae9-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="8eae9-231">Cambios y actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8eae9-231">Changes and updates</span></span>

### <span data-ttu-id="8eae9-232">Versión 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-232">Version 2.124.139.0</span></span>

<span data-ttu-id="8eae9-233">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8eae9-234">Soporte integrado y transparente</span><span class="sxs-lookup"><span data-stu-id="8eae9-234">Seamless integrated support</span></span>
- <span data-ttu-id="8eae9-235">Guardar todos los resultados de pruebas</span><span class="sxs-lookup"><span data-stu-id="8eae9-235">Save all test results</span></span>
- <span data-ttu-id="8eae9-236">Comprobar si la imagen se ha creado de forma personalizada</span><span class="sxs-lookup"><span data-stu-id="8eae9-236">Check if the image is custom created</span></span>
- <span data-ttu-id="8eae9-237">Incluir advertencias desde el administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8eae9-237">Include warnings from device manager</span></span>
- <span data-ttu-id="8eae9-238">Versión del firmware del Dock</span><span class="sxs-lookup"><span data-stu-id="8eae9-238">Dock firmware version</span></span>
- <span data-ttu-id="8eae9-239">Marcar unidades como posibles errores en la prueba de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="8eae9-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="8eae9-240">Quitar vínculo de tienda</span><span class="sxs-lookup"><span data-stu-id="8eae9-240">Remove store link</span></span> 

### <span data-ttu-id="8eae9-241">Versión 2.121.139</span><span class="sxs-lookup"><span data-stu-id="8eae9-241">Version 2.121.139</span></span>
*<span data-ttu-id="8eae9-242">Fecha de lanzamiento: 31 2020 de julio</span><span class="sxs-lookup"><span data-stu-id="8eae9-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="8eae9-243">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8eae9-244">Experiencia de soporte técnico perfecta</span><span class="sxs-lookup"><span data-stu-id="8eae9-244">Seamless support experience</span></span>
- <span data-ttu-id="8eae9-245">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="8eae9-245">Bug fixes</span></span>

### <span data-ttu-id="8eae9-246">Versión 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="8eae9-247">Fecha de lanzamiento: 11 de mayo de 2020</span><span class="sxs-lookup"><span data-stu-id="8eae9-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="8eae9-248">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8eae9-249">Posibilidad de omitir Windows Update para realizar la comprobación de hardware.</span><span class="sxs-lookup"><span data-stu-id="8eae9-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="8eae9-250">Posibilidad de recibir notificaciones sobre la actualización de la versión más reciente</span><span class="sxs-lookup"><span data-stu-id="8eae9-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="8eae9-251">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="8eae9-251">Surface Go 2</span></span>
- <span data-ttu-id="8eae9-252">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-252">Surface Book 3</span></span>
- <span data-ttu-id="8eae9-253">Mostrar indicador de progreso</span><span class="sxs-lookup"><span data-stu-id="8eae9-253">Show progress indicator</span></span>


### <span data-ttu-id="8eae9-254">Versión 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="8eae9-255">Fecha de lanzamiento: 21 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="8eae9-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="8eae9-256">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="8eae9-257">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="8eae9-257">Surface Pro 7</span></span>
- <span data-ttu-id="8eae9-258">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="8eae9-258">Surface Laptop 3</span></span>

### <span data-ttu-id="8eae9-259">Versión 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="8eae9-260">Fecha de lanzamiento: 24 de septiembre de 2019</span><span class="sxs-lookup"><span data-stu-id="8eae9-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="8eae9-261">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8eae9-262">Posibilidad de descargar informes de hardware.</span><span class="sxs-lookup"><span data-stu-id="8eae9-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="8eae9-263">Posibilidad de ponerse en contacto con el soporte técnico de Microsoft directamente desde la herramienta.</span><span class="sxs-lookup"><span data-stu-id="8eae9-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="8eae9-264">Versión 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="8eae9-265">Fecha de lanzamiento: 24 de junio de 2019</span><span class="sxs-lookup"><span data-stu-id="8eae9-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="8eae9-266">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8eae9-267">Información de versión del controlador incluida en los registros y en el informe.</span><span class="sxs-lookup"><span data-stu-id="8eae9-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="8eae9-268">Capacidad para proporcionar comentarios sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8eae9-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="8eae9-269">Versión 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="8eae9-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="8eae9-270">Fecha de lanzamiento: 26 de abril de 2019</span><span class="sxs-lookup"><span data-stu-id="8eae9-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="8eae9-271">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="8eae9-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="8eae9-272">Opción de configuración avanzada para desbloquear las capacidades de administrador a través de la interfaz de usuario del instalador, sin necesidad de configuración de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="8eae9-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="8eae9-273">Mejoras de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="8eae9-273">Accessibility improvements.</span></span>
- <span data-ttu-id="8eae9-274">Configuración de control de brillo de la superficie incluida en los registros.</span><span class="sxs-lookup"><span data-stu-id="8eae9-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="8eae9-275">Vínculo de compatibilidad con monitor externo en el generador de informes.</span><span class="sxs-lookup"><span data-stu-id="8eae9-275">External monitor compatibility support link in report generator.</span></span>

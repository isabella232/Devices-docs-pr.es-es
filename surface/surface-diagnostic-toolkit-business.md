---
title: Implementar el Kit de herramientas de diagnóstico de Surface para empresas
description: En este tema se explica cómo usar Surface Diagnostic Toolkit para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271584"
---
# <span data-ttu-id="45ad9-103">Implementar el Kit de herramientas de diagnóstico de Surface para empresas</span><span class="sxs-lookup"><span data-stu-id="45ad9-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="45ad9-104">Microsoft Surface Diagnostic Toolkit para empresas (SDT) permite a los administradores de TI investigar, solucionar problemas y resolver problemas de hardware, software y firmware rápidamente con dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="45ad9-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="45ad9-105">Puedes ejecutar una serie de pruebas de diagnóstico y reparaciones de software, además de obtener información sobre el estado del dispositivo y instrucciones para resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="45ad9-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="45ad9-106">En concreto, SDT para empresas te permite:</span><span class="sxs-lookup"><span data-stu-id="45ad9-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="45ad9-107">Personaliza el paquete.</span><span class="sxs-lookup"><span data-stu-id="45ad9-107">Customize the package.</span></span>](#preparing-the-sdt-package-for-distribution)
- [<span data-ttu-id="45ad9-108">Ejecuta la aplicación mediante comandos.</span><span class="sxs-lookup"><span data-stu-id="45ad9-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="45ad9-109">Ejecute varias pruebas de hardware para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="45ad9-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="45ad9-110">Generar registros para analizar problemas.</span><span class="sxs-lookup"><span data-stu-id="45ad9-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="45ad9-111">Obtenga un informe detallado que compare el dispositivo con la configuración óptima.</span><span class="sxs-lookup"><span data-stu-id="45ad9-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="45ad9-112">Escenarios principales y recursos de descarga</span><span class="sxs-lookup"><span data-stu-id="45ad9-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="45ad9-113">Para ejecutar SDT para empresas, descarga los componentes enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="45ad9-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="45ad9-114">Modo</span><span class="sxs-lookup"><span data-stu-id="45ad9-114">Mode</span></span> |  <span data-ttu-id="45ad9-115">Escenarios principales</span><span class="sxs-lookup"><span data-stu-id="45ad9-115">Primary scenarios</span></span> | <span data-ttu-id="45ad9-116">Descargar</span><span class="sxs-lookup"><span data-stu-id="45ad9-116">Download</span></span> | <span data-ttu-id="45ad9-117">Más información</span><span class="sxs-lookup"><span data-stu-id="45ad9-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="45ad9-118">Modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="45ad9-118">Desktop mode</span></span> |  <span data-ttu-id="45ad9-119">Ayudar a los usuarios a ejecutar SDT en sus dispositivos Surface para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="45ad9-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="45ad9-120">Crea un paquete personalizado para implementarlo en uno o varios dispositivos Surface, lo que permite a los usuarios seleccionar registros específicos para recopilar y analizar.</span><span class="sxs-lookup"><span data-stu-id="45ad9-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="45ad9-121">Paquete MSI distribuible de SDT:</span><span class="sxs-lookup"><span data-stu-id="45ad9-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="45ad9-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span><span class="sxs-lookup"><span data-stu-id="45ad9-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="45ad9-123">Herramientas de Surface para TI</span><span class="sxs-lookup"><span data-stu-id="45ad9-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="45ad9-124">Usar Surface Diagnostic Toolkit en modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="45ad9-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="45ad9-125">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="45ad9-125">Command line</span></span> |  <span data-ttu-id="45ad9-126">Solucionar directamente problemas de dispositivos Surface de forma remota sin la interacción del usuario, con herramientas estándar como Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="45ad9-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="45ad9-127">Incluye los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="45ad9-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="45ad9-128">recopila todos los archivos de registro</span><span class="sxs-lookup"><span data-stu-id="45ad9-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="45ad9-129">ejecuta diagnósticos de estado mediante el Analizador de procedimientos recomendados.</span><span class="sxs-lookup"><span data-stu-id="45ad9-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="45ad9-130">comprueba windows Update si faltan actualizaciones de controladores o firmware.</span><span class="sxs-lookup"><span data-stu-id="45ad9-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="45ad9-131">comprueba la información de garantía.</span><span class="sxs-lookup"><span data-stu-id="45ad9-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="45ad9-132">Aplicación de consola de SDT:</span><span class="sxs-lookup"><span data-stu-id="45ad9-132">SDT console app:</span></span><br><span data-ttu-id="45ad9-133">Microsoft Surface Diagnostics App Console</span><span class="sxs-lookup"><span data-stu-id="45ad9-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="45ad9-134">Herramientas de Surface para TI</span><span class="sxs-lookup"><span data-stu-id="45ad9-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="45ad9-135">Ejecutar Surface Diagnostic Toolkit con comandos</span><span class="sxs-lookup"><span data-stu-id="45ad9-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="45ad9-136">Dispositivos compatibles</span><span class="sxs-lookup"><span data-stu-id="45ad9-136">Supported devices</span></span> 

<span data-ttu-id="45ad9-137">SDT para empresas es compatible con Dispositivos Surface 3 y posteriores, incluidos:</span><span class="sxs-lookup"><span data-stu-id="45ad9-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="45ad9-138">Surface Book: todas las generaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-138">Surface Book - all generations</span></span>
- <span data-ttu-id="45ad9-139">Surface Go: todas las generaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-139">Surface Go - all generations</span></span>
- <span data-ttu-id="45ad9-140">Surface Laptop: todas las generaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-140">Surface Laptop - all generations</span></span>
- <span data-ttu-id="45ad9-141">Surface Pro 3 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="45ad9-141">Surface Pro 3 and later</span></span>
- <span data-ttu-id="45ad9-142">Surface Pro X: todas las generaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-142">Surface Pro X - all generations</span></span>
- <span data-ttu-id="45ad9-143">Surface Studio: todas las generaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-143">Surface Studio - all generations</span></span>
- <span data-ttu-id="45ad9-144">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="45ad9-144">Surface 3 LTE</span></span>
- <span data-ttu-id="45ad9-145">Surface 3</span><span class="sxs-lookup"><span data-stu-id="45ad9-145">Surface 3</span></span>


## <span data-ttu-id="45ad9-146">Instalación de Surface Diagnostic Toolkit para empresas</span><span class="sxs-lookup"><span data-stu-id="45ad9-146">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="45ad9-147">Para crear un paquete de SDT que puedes distribuir a los usuarios de tu organización:</span><span class="sxs-lookup"><span data-stu-id="45ad9-147">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="45ad9-148">Inicia sesión en el dispositivo Surface con la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="45ad9-148">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="45ad9-149">Descarga el paquete de Windows Installer de SDT (.msi) desde la página de descarga de Herramientas de [Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI y cópielo en una ubicación preferida del dispositivo Surface, como Escritorio.</span><span class="sxs-lookup"><span data-stu-id="45ad9-149">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="45ad9-150">Aparece el asistente para la configuración de SDT, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="45ad9-150">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="45ad9-151">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="45ad9-151">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="45ad9-152">Si no aparece el asistente para la instalación, asegúrese de que ha iniciado sesión en la cuenta de administrador en el equipo.</span><span class="sxs-lookup"><span data-stu-id="45ad9-152">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![Asistente para la configuración del Kit de herramientas de diagnóstico de Surface](images/sdt-1.png)

    *<span data-ttu-id="45ad9-154">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="45ad9-154">Figure 1.</span></span> <span data-ttu-id="45ad9-155">Asistente para la configuración del Kit de herramientas de diagnóstico de Surface</span><span class="sxs-lookup"><span data-stu-id="45ad9-155">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="45ad9-156">Cuando aparezca el Asistente para la instalación de SDT, haz clic en **Siguiente,** acepta el Contrato de licencia para el usuario final (CLUF)</span><span class="sxs-lookup"><span data-stu-id="45ad9-156">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="45ad9-157">En la pantalla Opciones de instalación, cambie la ubicación de instalación predeterminada si lo desea.</span><span class="sxs-lookup"><span data-stu-id="45ad9-157">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="45ad9-158">En Tipo de instalación, seleccione **Opciones avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="45ad9-158">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="45ad9-159">La opción estándar permite a los usuarios ejecutar la herramienta de diagnóstico directamente en su dispositivo Surface siempre que se haya iniciado sesión en el dispositivo con una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="45ad9-159">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![Opciones de instalación: Opciones avanzadas](images/sdt-install.png)

7. <span data-ttu-id="45ad9-161">Haga **clic en Siguiente** y, a continuación, haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="45ad9-161">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="45ad9-162">Instalación mediante la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="45ad9-162">Installing using the command line</span></span>
<span data-ttu-id="45ad9-163">Si lo deseas, puedes instalar SDT en un símbolo del sistema y establecer una marca personalizada para instalar la herramienta en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="45ad9-163">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="45ad9-164">SDT contiene las siguientes marcas de opción de instalación:</span><span class="sxs-lookup"><span data-stu-id="45ad9-164">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="45ad9-165">envía datos de telemetría a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45ad9-165">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="45ad9-166">La marca acepta `0` para deshabilitado o para `1` habilitado.</span><span class="sxs-lookup"><span data-stu-id="45ad9-166">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="45ad9-167">El valor predeterminado es `1` enviar telemetría.</span><span class="sxs-lookup"><span data-stu-id="45ad9-167">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="45ad9-168">configura la herramienta para que se instale en modo de administrador.</span><span class="sxs-lookup"><span data-stu-id="45ad9-168">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="45ad9-169">La marca acepta para `0` el modo de cliente o para el modo de administrador de `1` TI.</span><span class="sxs-lookup"><span data-stu-id="45ad9-169">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="45ad9-170">El valor predeterminado es `0`.</span><span class="sxs-lookup"><span data-stu-id="45ad9-170">The default value is `0`.</span></span>

### <span data-ttu-id="45ad9-171">Para instalar SDT desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="45ad9-171">To install SDT from the command line:</span></span>

1. <span data-ttu-id="45ad9-172">Abra un símbolo del sistema y escriba:</span><span class="sxs-lookup"><span data-stu-id="45ad9-172">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="45ad9-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="45ad9-173">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="45ad9-174">Buscar SDT en el dispositivo Surface</span><span class="sxs-lookup"><span data-stu-id="45ad9-174">Locating SDT on your Surface device</span></span>

<span data-ttu-id="45ad9-175">Tanto SDT como la consola de la aplicación de SDT se instalan en `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .</span><span class="sxs-lookup"><span data-stu-id="45ad9-175">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="45ad9-176">Además del archivo .exe, SDT instala un archivo JSON y un archivo admin.dll (modules\admin.dll), como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="45ad9-176">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![lista de archivos instalados de SDT en el Explorador de archivos](images/sdt-2.png)

*<span data-ttu-id="45ad9-178">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="45ad9-178">Figure 2.</span></span> <span data-ttu-id="45ad9-179">Archivos instalados por SDT</span><span class="sxs-lookup"><span data-stu-id="45ad9-179">Files installed by SDT</span></span>*

## <span data-ttu-id="45ad9-180">Preparar el paquete de SDT para su distribución</span><span class="sxs-lookup"><span data-stu-id="45ad9-180">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="45ad9-181">La creación de un paquete personalizado te permite dirigir la herramienta a problemas conocidos específicos.</span><span class="sxs-lookup"><span data-stu-id="45ad9-181">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="45ad9-182">Haz **clic en > ejecutar,** escribe **Surface** y, a continuación, haz clic en Surface Diagnostic Toolkit **para empresas.**</span><span class="sxs-lookup"><span data-stu-id="45ad9-182">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="45ad9-183">Cuando se abra la herramienta, haga **clic en Crear paquete personalizado,** como se muestra en la figura 3.</span><span class="sxs-lookup"><span data-stu-id="45ad9-183">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![Opción crear paquete personalizado](images/sdt-3.png)

    *<span data-ttu-id="45ad9-185">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="45ad9-185">Figure 3.</span></span> <span data-ttu-id="45ad9-186">Crear paquete personalizado</span><span class="sxs-lookup"><span data-stu-id="45ad9-186">Create custom package</span></span>*

### <span data-ttu-id="45ad9-187">Configuración de idioma y telemetría</span><span class="sxs-lookup"><span data-stu-id="45ad9-187">Language and telemetry settings</span></span>

  <span data-ttu-id="45ad9-188">Al crear un paquete, puedes seleccionar la configuración de idioma o no enviar información de telemetría a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45ad9-188">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="45ad9-189">De forma predeterminada, SDT envía telemetría a Microsoft que se usa para mejorar la aplicación de acuerdo con la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="45ad9-189">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="45ad9-190">Si desea rechazar, desactive la casilla al crear un paquete personalizado, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="45ad9-190">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="45ad9-191">O bien, desactive **la casilla Enviar telemetría a Microsoft** en la página Opciones de **instalación** durante la instalación de SDT.</span><span class="sxs-lookup"><span data-stu-id="45ad9-191">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="45ad9-192">Esta configuración no afecta a la telemetría mínima almacenada automáticamente en los servidores De Microsoft cuando se ejecutan pruebas y reparaciones que requieren una conexión a Internet, como la reparación de Windows Update y software, o al proporcionar comentarios con los botones Sonriente o Desaprobado en la barra de herramientas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ad9-192">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![Seleccionar la configuración de idioma y telemetría](images/sdt-4.png)

*<span data-ttu-id="45ad9-194">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="45ad9-194">Figure 4.</span></span> <span data-ttu-id="45ad9-195">Seleccionar la configuración de idioma y telemetría</span><span class="sxs-lookup"><span data-stu-id="45ad9-195">Select language and telemetry settings</span></span>*


### <span data-ttu-id="45ad9-196">Página de Windows Update</span><span class="sxs-lookup"><span data-stu-id="45ad9-196">Windows Update page</span></span>

<span data-ttu-id="45ad9-197">Seleccione la opción adecuada para su organización.</span><span class="sxs-lookup"><span data-stu-id="45ad9-197">Select the option appropriate for your organization.</span></span> <span data-ttu-id="45ad9-198">La mayoría de las organizaciones con varios usuarios normalmente seleccionarán recibir actualizaciones a través de Windows Server Update Services (WSUS), como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="45ad9-198">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="45ad9-199">Si usas paquetes locales de Windows Update o WSUS, escribe la ruta de acceso según corresponda.</span><span class="sxs-lookup"><span data-stu-id="45ad9-199">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![Opción Seleccionar Windows Update](images/sdt-5.png)

*<span data-ttu-id="45ad9-201">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="45ad9-201">Figure 5.</span></span> <span data-ttu-id="45ad9-202">Opción de Windows Update</span><span class="sxs-lookup"><span data-stu-id="45ad9-202">Windows Update option</span></span>*

### <span data-ttu-id="45ad9-203">Página de reparación de software</span><span class="sxs-lookup"><span data-stu-id="45ad9-203">Software repair page</span></span>

<span data-ttu-id="45ad9-204">Esto le permite seleccionar o quitar la opción para ejecutar actualizaciones de reparación de software.</span><span class="sxs-lookup"><span data-stu-id="45ad9-204">This allows you to select or remove the option to run software repair updates.</span></span> 

![Seleccionar la opción de reparación de software](images/sdt-6.png)

*<span data-ttu-id="45ad9-206">Figura 6.</span><span class="sxs-lookup"><span data-stu-id="45ad9-206">Figure 6.</span></span> <span data-ttu-id="45ad9-207">Opción de reparación de software</span><span class="sxs-lookup"><span data-stu-id="45ad9-207">Software repair option</span></span>*

### <span data-ttu-id="45ad9-208">Recopilar registros y guardar la página del paquete</span><span class="sxs-lookup"><span data-stu-id="45ad9-208">Collecting logs and saving package page</span></span>

<span data-ttu-id="45ad9-209">Puedes seleccionar ejecutar una amplia variedad de registros en aplicaciones, controladores, hardware y el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="45ad9-209">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="45ad9-210">Haga clic en el área adecuada y seleccione en el menú de registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="45ad9-210">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="45ad9-211">A continuación, puedes guardar el paquete en un punto de distribución de software o una ubicación equivalente a la que los usuarios puedan tener acceso.</span><span class="sxs-lookup"><span data-stu-id="45ad9-211">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![Seleccionar opciones de registro](images/sdt-7.png)

*<span data-ttu-id="45ad9-213">Figura 7.</span><span class="sxs-lookup"><span data-stu-id="45ad9-213">Figure 7.</span></span> <span data-ttu-id="45ad9-214">Opción de registro y guardar paquete</span><span class="sxs-lookup"><span data-stu-id="45ad9-214">Log option and save package</span></span>*

## <span data-ttu-id="45ad9-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="45ad9-215">Next steps</span></span>

- [<span data-ttu-id="45ad9-216">Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="45ad9-216">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="45ad9-217">Usar Surface Diagnostic Toolkit para empresas mediante comandos</span><span class="sxs-lookup"><span data-stu-id="45ad9-217">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="45ad9-218">Cambios y actualizaciones</span><span class="sxs-lookup"><span data-stu-id="45ad9-218">Changes and updates</span></span>

### <span data-ttu-id="45ad9-219">Versión 2.131.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-219">Version 2.131.139.0</span></span>

<span data-ttu-id="45ad9-220">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-220">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45ad9-221">Compatibilidad con Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="45ad9-221">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="45ad9-222">Experiencia de compatibilidad sin problemas en Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="45ad9-222">Seamless support experience on Surface Pro X</span></span>
- <span data-ttu-id="45ad9-223">Mejoras de seguridad</span><span class="sxs-lookup"><span data-stu-id="45ad9-223">Security improvements</span></span>
- <span data-ttu-id="45ad9-224">Mejoras en la experiencia del usuario inclusiva</span><span class="sxs-lookup"><span data-stu-id="45ad9-224">Inclusive user experience improvements</span></span>

### <span data-ttu-id="45ad9-225">Versión 2.124.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-225">Version 2.124.139.0</span></span>

<span data-ttu-id="45ad9-226">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-226">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45ad9-227">Compatibilidad integrada sin problemas</span><span class="sxs-lookup"><span data-stu-id="45ad9-227">Seamless integrated support</span></span>
- <span data-ttu-id="45ad9-228">Guardar todos los resultados de las pruebas</span><span class="sxs-lookup"><span data-stu-id="45ad9-228">Save all test results</span></span>
- <span data-ttu-id="45ad9-229">Comprobar si la imagen está creada de forma personalizada</span><span class="sxs-lookup"><span data-stu-id="45ad9-229">Check if the image is custom created</span></span>
- <span data-ttu-id="45ad9-230">Incluir advertencias del administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="45ad9-230">Include warnings from device manager</span></span>
- <span data-ttu-id="45ad9-231">Versión de firmware de dock</span><span class="sxs-lookup"><span data-stu-id="45ad9-231">Dock firmware version</span></span>
- <span data-ttu-id="45ad9-232">Marcar las unidades como posibles errores en la prueba de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="45ad9-232">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="45ad9-233">Quitar vínculo de almacén</span><span class="sxs-lookup"><span data-stu-id="45ad9-233">Remove store link</span></span> 

### <span data-ttu-id="45ad9-234">Versión 2.121.139</span><span class="sxs-lookup"><span data-stu-id="45ad9-234">Version 2.121.139</span></span>
*<span data-ttu-id="45ad9-235">Fecha de lanzamiento: 31 de julio de 2020</span><span class="sxs-lookup"><span data-stu-id="45ad9-235">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="45ad9-236">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-236">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45ad9-237">Experiencia de soporte sin problemas</span><span class="sxs-lookup"><span data-stu-id="45ad9-237">Seamless support experience</span></span>
- <span data-ttu-id="45ad9-238">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="45ad9-238">Bug fixes</span></span>

### <span data-ttu-id="45ad9-239">Versión 2.94.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-239">Version 2.94.139.0</span></span>
*<span data-ttu-id="45ad9-240">Fecha de lanzamiento: 11 de mayo de 2020</span><span class="sxs-lookup"><span data-stu-id="45ad9-240">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="45ad9-241">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-241">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45ad9-242">Capacidad de omitir Windows Update para realizar la comprobación de hardware.</span><span class="sxs-lookup"><span data-stu-id="45ad9-242">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="45ad9-243">Capacidad de recibir notificaciones sobre la actualización de la versión más reciente</span><span class="sxs-lookup"><span data-stu-id="45ad9-243">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="45ad9-244">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="45ad9-244">Surface Go 2</span></span>
- <span data-ttu-id="45ad9-245">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="45ad9-245">Surface Book 3</span></span>
- <span data-ttu-id="45ad9-246">Mostrar indicador de progreso</span><span class="sxs-lookup"><span data-stu-id="45ad9-246">Show progress indicator</span></span>


### <span data-ttu-id="45ad9-247">Versión 2.43.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-247">Version 2.43.139.0</span></span>
*<span data-ttu-id="45ad9-248">Fecha de lanzamiento: 21 de octubre de 2019</span><span class="sxs-lookup"><span data-stu-id="45ad9-248">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="45ad9-249">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-249">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="45ad9-250">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="45ad9-250">Surface Pro 7</span></span>
- <span data-ttu-id="45ad9-251">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="45ad9-251">Surface Laptop 3</span></span>

### <span data-ttu-id="45ad9-252">Versión 2.42.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-252">Version 2.42.139.0</span></span>
*<span data-ttu-id="45ad9-253">Fecha de lanzamiento: 24 de septiembre de 2019</span><span class="sxs-lookup"><span data-stu-id="45ad9-253">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="45ad9-254">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-254">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45ad9-255">Capacidad de descargar informes de hardware.</span><span class="sxs-lookup"><span data-stu-id="45ad9-255">Ability to download hardware reports.</span></span>
- <span data-ttu-id="45ad9-256">Capacidad de ponerse en contacto con el soporte técnico de Microsoft directamente desde la herramienta.</span><span class="sxs-lookup"><span data-stu-id="45ad9-256">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="45ad9-257">Versión 2.41.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-257">Version 2.41.139.0</span></span>
*<span data-ttu-id="45ad9-258">Fecha de lanzamiento: 24 de junio de 2019</span><span class="sxs-lookup"><span data-stu-id="45ad9-258">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="45ad9-259">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-259">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45ad9-260">Información de la versión del controlador incluida en los registros y el informe.</span><span class="sxs-lookup"><span data-stu-id="45ad9-260">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="45ad9-261">Capacidad de proporcionar comentarios sobre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45ad9-261">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="45ad9-262">Versión 2.36.139.0</span><span class="sxs-lookup"><span data-stu-id="45ad9-262">Version 2.36.139.0</span></span>
*<span data-ttu-id="45ad9-263">Fecha de lanzamiento: 26 de abril de 2019</span><span class="sxs-lookup"><span data-stu-id="45ad9-263">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="45ad9-264">Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="45ad9-264">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="45ad9-265">Opción de configuración avanzada para desbloquear las capacidades de administración a través de la interfaz de usuario del instalador, sin necesidad de configurar la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="45ad9-265">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="45ad9-266">Mejoras de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="45ad9-266">Accessibility improvements.</span></span>
- <span data-ttu-id="45ad9-267">Configuración de control de brillo de surface incluida en los registros.</span><span class="sxs-lookup"><span data-stu-id="45ad9-267">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="45ad9-268">Vínculo de compatibilidad de monitor externo en el generador de informes.</span><span class="sxs-lookup"><span data-stu-id="45ad9-268">External monitor compatibility support link in report generator.</span></span>

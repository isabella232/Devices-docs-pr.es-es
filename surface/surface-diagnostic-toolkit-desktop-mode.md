---
title: Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio
description: Cómo usar SDT para ayudar a los usuarios de su organización a ejecutar la herramienta para identificar y diagnosticar problemas con el dispositivo Surface, así como enviar solicitudes de asistencia directamente desde la herramienta.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 7/31/2020
ms.openlocfilehash: ec4a90d0d72956eaa4f98e928d128dca70d49c59
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902978"
---
# <span data-ttu-id="b533e-103">Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio</span><span class="sxs-lookup"><span data-stu-id="b533e-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="b533e-104">En este tema se explica cómo usar el kit de herramientas de diagnóstico de Surface (SDT) para ayudar a los usuarios de su organización a ejecutar la herramienta para identificar y diagnosticar problemas con su dispositivo Surface, así como enviar solicitudes de asistencia directamente desde la herramienta.</span><span class="sxs-lookup"><span data-stu-id="b533e-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with their Surface device as well as submit Support requests directly from the tool.</span></span> 

<span data-ttu-id="b533e-105">La ejecución correcta de SDT puede determinar rápidamente si un problema notificado se debe a un error de hardware o de usuario.</span><span class="sxs-lookup"><span data-stu-id="b533e-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="b533e-106">Para obtener una lista de los dispositivos Surface admitidos en SDT, consulte [deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span><span class="sxs-lookup"><span data-stu-id="b533e-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="b533e-107">Indique al usuario que instale [el paquete SDT](surface-diagnostic-toolkit-business.md#create-custom-sdt) desde un punto de distribución de software o un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="b533e-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="b533e-108">Una vez instalado, estará listo para guiar al usuario a través de una serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b533e-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="b533e-109">Comience en la Página principal, lo que permite a los usuarios introducir una descripción del problema y haga clic en **continuar**, como se muestra en la ilustración 1.</span><span class="sxs-lookup"><span data-stu-id="b533e-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="b533e-110">Inicie SDT en la figura 1 del modo de escritorio ](images/sdt-desk-1.png)
 *. SDT en modo de escritorio*</span><span class="sxs-lookup"><span data-stu-id="b533e-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="b533e-111">Cuando SDT indica que el dispositivo tiene las actualizaciones más recientes, haga clic en **continuar** para avanzar hasta el catálogo de pruebas disponibles, como se muestra en la ilustración 2.</span><span class="sxs-lookup"><span data-stu-id="b533e-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="b533e-112">Seleccione la figura 2 de opciones de SDT ](images/sdt1.png)
 *. Seleccionar de las opciones de SDT*</span><span class="sxs-lookup"><span data-stu-id="b533e-112">Select from SDT options](images/sdt1.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="b533e-113">Puede elegir ejecutar todas las pruebas de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="b533e-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="b533e-114">O bien, si ya sospecha un problema determinado, como una pantalla defectuosa o un problema de fuente de alimentación, haga clic en **seleccionar** para elegir entre las pruebas disponibles y haga clic en **Ejecutar seleccionado**, como se muestra en la ilustración 3.</span><span class="sxs-lookup"><span data-stu-id="b533e-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="b533e-115">Para obtener detalles de cada prueba, consulte la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b533e-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="b533e-116">Seleccione pruebas de hardware, ](images/sdt2.png)
 *ilustración 3. Seleccionar pruebas de hardware*</span><span class="sxs-lookup"><span data-stu-id="b533e-116">Select hardware tests](images/sdt2.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="b533e-117">Prueba de hardware</span><span class="sxs-lookup"><span data-stu-id="b533e-117">Hardware test</span></span> | <span data-ttu-id="b533e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b533e-118">Description</span></span>
    --- | ---
    <span data-ttu-id="b533e-119">Fuente de alimentación y batería</span><span class="sxs-lookup"><span data-stu-id="b533e-119">Power Supply and Battery</span></span> |  <span data-ttu-id="b533e-120">Comprueba que la fuente de alimentación funcione de manera óptima</span><span class="sxs-lookup"><span data-stu-id="b533e-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="b533e-121">Pantalla y sonido</span><span class="sxs-lookup"><span data-stu-id="b533e-121">Display and Sound</span></span>   | <span data-ttu-id="b533e-122">Comprueba el brillo, el brillo o los píxeles muertos, el altavoz y el micrófono.</span><span class="sxs-lookup"><span data-stu-id="b533e-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="b533e-123">Puertos y accesorios</span><span class="sxs-lookup"><span data-stu-id="b533e-123">Ports and Accessories</span></span>   | <span data-ttu-id="b533e-124">Comprueba los accesorios, la conexión en pantalla y el funcionamiento con USB</span><span class="sxs-lookup"><span data-stu-id="b533e-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="b533e-125">Conectividad</span><span class="sxs-lookup"><span data-stu-id="b533e-125">Connectivity</span></span> |  <span data-ttu-id="b533e-126">Verifica la conectividad de Bluetooth, inalámbrico y LTE</span><span class="sxs-lookup"><span data-stu-id="b533e-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="b533e-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b533e-127">Security</span></span>    | <span data-ttu-id="b533e-128">Comprueba los problemas relacionados con la seguridad</span><span class="sxs-lookup"><span data-stu-id="b533e-128">Checks security related issues</span></span>
    <span data-ttu-id="b533e-129">Función táctil</span><span class="sxs-lookup"><span data-stu-id="b533e-129">Touch</span></span>   | <span data-ttu-id="b533e-130">Comprueba los problemas relacionados con el tacto</span><span class="sxs-lookup"><span data-stu-id="b533e-130">Checks touch related issues</span></span>
    <span data-ttu-id="b533e-131">Teclado y toque</span><span class="sxs-lookup"><span data-stu-id="b533e-131">Keyboard and touch</span></span> |    <span data-ttu-id="b533e-132">Comprueba la conexión de teclado y la cubierta de tipo integrada</span><span class="sxs-lookup"><span data-stu-id="b533e-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="b533e-133">Sensores</span><span class="sxs-lookup"><span data-stu-id="b533e-133">Sensors</span></span> | <span data-ttu-id="b533e-134">Comprueba el funcionamiento de los distintos sensores en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="b533e-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="b533e-135">Hardware</span><span class="sxs-lookup"><span data-stu-id="b533e-135">Hardware</span></span> |  <span data-ttu-id="b533e-136">Comprueba los problemas con diferentes componentes de hardware, como la tarjeta gráfica y la cámara.</span><span class="sxs-lookup"><span data-stu-id="b533e-136">Checks issues with different hardware components such as graphics card and camera</span></span>

5. <span data-ttu-id="b533e-137">Cuando haya finalizado todas las pruebas, la herramienta le pedirá que confirme si el problema se ha corregido.</span><span class="sxs-lookup"><span data-stu-id="b533e-137">When all tests have finished, the tool asks you to confirm if your issue is fixed.</span></span> 

 ![<span data-ttu-id="b533e-138">¿Se ha solucionado el problema? ](images/sdt3.png)
 *Ilustración 3A. ¿Se ha solucionado el problema?*</span><span class="sxs-lookup"><span data-stu-id="b533e-138">Has your problem been resolved?](images/sdt3.png)
*Figure 3a. Has your problem been resolved?*</span></span>

6. <span data-ttu-id="b533e-139">Si el problema no se resuelve o no sabe, puede enviar un vale de soporte técnico seleccionando **ponerse en contacto con nosotros** para **obtener ayuda ahora.**</span><span class="sxs-lookup"><span data-stu-id="b533e-139">If the issue isn't resolved or you don't know, you can submit a Support ticket by selecting **Contact us** to **Get help now.**</span></span>
 
 ![<span data-ttu-id="b533e-140">Enviar una incidencia de soporte técnico ](images/sdt4.png)
 *3B: Enviar una incidencia de soporte técnico*</span><span class="sxs-lookup"><span data-stu-id="b533e-140">Submit a Support ticket](images/sdt4.png)
*Figure 3b. Submit a Support ticket*</span></span>

<span id="multiple" />

## <span data-ttu-id="b533e-141">Ejecución de varias pruebas de hardware para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="b533e-141">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="b533e-142">SDT está diseñado como una herramienta interactiva que ejecuta una serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b533e-142">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="b533e-143">Para cada prueba, SDT proporciona instrucciones que resumen la naturaleza de la prueba y qué usuarios deberían esperar o buscar para que la prueba se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="b533e-143">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="b533e-144">Por ejemplo, para diagnosticar si el brillo de la pantalla funciona correctamente, SDT comienza por cero y aumenta el brillo al 100 por ciento, lo que pide a los usuarios que lo confirmen, respondiendo **sí** o **no** , que el brillo funciona como se muestra en la ilustración 4.</span><span class="sxs-lookup"><span data-stu-id="b533e-144">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="b533e-145">Para cada prueba, si la funcionalidad no funciona como se espera y el usuario hace clic en **no**, SDT genera un informe de las posibles causas y las formas de solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="b533e-145">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="b533e-146">Ejecución de los diagnósticos de hardware, ](images/sdt-desk-4.png)
 *ilustración 4. Ejecución de diagnósticos de hardware*</span><span class="sxs-lookup"><span data-stu-id="b533e-146">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="b533e-147">Si el brillo se ajusta correctamente de 0-100 por ciento como se espera, indique al usuario que haga clic en **sí** y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="b533e-147">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="b533e-148">Si el brillo no se ajusta al 0-100 por ciento según lo esperado, indique al usuario que haga clic en **no** y, a continuación, haga clic en **continuar**.</span><span class="sxs-lookup"><span data-stu-id="b533e-148">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="b533e-149">Guiar a los usuarios por las pruebas restantes según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b533e-149">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="b533e-150">Cuando haya terminado, SDT proporcionará automáticamente un resumen de alto nivel del informe, incluidas las posibles causas de los problemas de hardware junto con las instrucciones de resolución.</span><span class="sxs-lookup"><span data-stu-id="b533e-150">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="b533e-151">Reparar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b533e-151">Repairing applications</span></span>

<span data-ttu-id="b533e-152">SDT le permite diagnosticar y reparar aplicaciones que pueden estar causando problemas, como se muestra en la figura 5.</span><span class="sxs-lookup"><span data-stu-id="b533e-152">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="b533e-153">Ejecutando reparación, ](images/sdt-desk-5.png)
 *ilustración 5. Ejecución de reparaciones*</span><span class="sxs-lookup"><span data-stu-id="b533e-153">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="b533e-154">Generando registros para analizar problemas</span><span class="sxs-lookup"><span data-stu-id="b533e-154">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="b533e-155">SDT proporciona una amplia compatibilidad de diagnósticos compatibles con el registro en todas las aplicaciones, drivers, hardware y problemas del sistema operativo, como se muestra en la figura 6.</span><span class="sxs-lookup"><span data-stu-id="b533e-155">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="b533e-156">Generando registros, ](images/sdt-desk-6.png)
 *Ilustración 6. Generando registros*</span><span class="sxs-lookup"><span data-stu-id="b533e-156">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="b533e-157">Generando informe detallado comparando el dispositivo y la configuración óptima</span><span class="sxs-lookup"><span data-stu-id="b533e-157">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="b533e-158">Según los registros, SDT genera un informe de problemas basados en el software y el firmware que puede guardar en una ubicación preferida.</span><span class="sxs-lookup"><span data-stu-id="b533e-158">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="b533e-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b533e-159">Related topics</span></span>

- [<span data-ttu-id="b533e-160">Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos</span><span class="sxs-lookup"><span data-stu-id="b533e-160">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)


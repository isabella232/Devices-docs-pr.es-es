---
title: Habilitar PEAP, EAP-FAST y Cisco LEAP en dispositivos Surface (Surface)
description: Averigua cómo habilitar la compatibilidad con los protocolos PEAP, EAP-FAST o Cisco LEAP en tu dispositivo Surface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: red, inalámbrica, dispositivo, implementar, autenticación, protocolo
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835970"
---
# <span data-ttu-id="a8923-104">Habilitar PEAP, EAP-FAST y Cisco LEAP en dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="a8923-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="a8923-105">Averigua cómo habilitar la compatibilidad con los protocolos PEAP, EAP-FAST o Cisco LEAP en tu dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="a8923-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="a8923-106">Si usas PEAP, EAP-FAST o Cisco LEAP en tu red de empresa, probablemente ya sabes que estos tres protocolos de autenticación inalámbrica no son compatibles con dispositivos Surface de fábrica.</span><span class="sxs-lookup"><span data-stu-id="a8923-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="a8923-107">Algunos usuarios pueden descubrir esto cuando intenten conectarse a la red inalámbrica; otros pueden descubrirlo cuando no puedes obtener acceso a recursos de red, como recursos compartidos de archivos y sitios internos.</span><span class="sxs-lookup"><span data-stu-id="a8923-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="a8923-108">Para obtener más información, consulta [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147) (Protocolo de autenticación extensible).</span><span class="sxs-lookup"><span data-stu-id="a8923-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="a8923-109">Para agregar compatibilidad para cada uno de los protocolos, puedes ejecutar un pequeño paquete MSI desde un stick USB o desde un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="a8923-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="a8923-110">Para las organizaciones que desean habilitar la compatibilidad de EAP en sus dispositivos Surface, el formato de paquete MSI admite la implementación con muchas herramientas de administración e implementación, como Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a8923-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="a8923-111">Descargar archivos de instalación de PEAP, EAP-FAST o Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="a8923-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="a8923-112">Puedes descargar los archivos de instalación de MSI para PEAP, EAP-FAST o Cisco LEAP en un único archivo zip desde el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8923-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="a8923-113">Para descargar este archivo, ve a la página [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) en el Centro de descarga de Microsoft, haz clic en **Download** (Descargar) y luego selecciona el archivo **Cisco EAP-Supplicant Installer.zip**.</span><span class="sxs-lookup"><span data-stu-id="a8923-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="a8923-114">Implementar PEAP, EAP-FAST o Cisco LEAP con MDT</span><span class="sxs-lookup"><span data-stu-id="a8923-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="a8923-115">Si ya estás realizando una implementación de Windows en dispositivos Surface en tu organización, es rápido y fácil agregar los archivos de instalación para cada protocolo en el recurso compartido de implementación y configurar la instalación automática durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="a8923-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="a8923-116">Incluso puedes configurar una secuencia de tareas que actualice los dispositivos Surface implementados anteriormente para proporcionar compatibilidad con estos protocolos mediante el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="a8923-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="a8923-117">Para habilitar la compatibilidad con PEAP, EAP-FAST o Cisco LEAP en dispositivos Surface recientemente implementados, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a8923-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="a8923-118">Descarga y extrae los archivos de instalación para cada protocolo en carpetas independientes en una ubicación de fácil acceso.</span><span class="sxs-lookup"><span data-stu-id="a8923-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="a8923-119">Abre Deployment Workbench de MDT y expande el recurso compartido de implementación en la **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a8923-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="a8923-120">Selecciona **Nueva aplicación** desde el panel **Acción**.</span><span class="sxs-lookup"><span data-stu-id="a8923-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="a8923-121">Elige **Aplicación con archivos de origen** para copiar los archivos MSI en el recurso compartido de implementación.</span><span class="sxs-lookup"><span data-stu-id="a8923-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="a8923-122">Selecciona la carpeta que creaste en el paso 1 del protocolo deseado.</span><span class="sxs-lookup"><span data-stu-id="a8923-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="a8923-123">Asigna un nombre a la carpeta en el recurso compartido de implementación donde se almacenarán los archivos de instalación.</span><span class="sxs-lookup"><span data-stu-id="a8923-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="a8923-124">Especifica la línea de comandos para implementar la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a8923-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="a8923-125">Para PEAP, usa **EAP-PEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="a8923-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="a8923-126">Para LEAP, usa **EAP-LEAP.msi /qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="a8923-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="a8923-127">Para EAP-FAST, usa **FAST.msi EAP/qn /norestart**.</span><span class="sxs-lookup"><span data-stu-id="a8923-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="a8923-128">Usa las opciones predeterminadas para completar el Asistente para nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8923-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="a8923-129">Repite los pasos 3 a 8 para cada protocolo deseado.</span><span class="sxs-lookup"><span data-stu-id="a8923-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="a8923-130">Una vez que hayas realizado estos pasos para importar los tres paquetes MSI como aplicaciones en MDT, estarán disponibles para la selección en la página Aplicaciones del Asistente para la implementación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a8923-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="a8923-131">Aunque en algunos escenarios de implementación sencillos puede ser suficiente que los técnicos seleccionen cada paquete en el momento de la implementación, no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="a8923-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="a8923-132">Este procedimiento introduce la posibilidad de que un técnico intentara aplicar estos paquetes en equipos que no sean dispositivos Surface o que se implemente en un dispositivo Surface sin compatibilidad EAP debido a errores humanos.</span><span class="sxs-lookup"><span data-stu-id="a8923-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="a8923-133">Para ocultar estas aplicaciones desde la página Instalar aplicaciones, selecciona la casilla \*\*Ocultar esta aplicación en el Asistente para la implementación \*\* en las propiedades de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8923-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="a8923-134">Después de ocultar las aplicaciones, no aparecerán como aplicaciones opcionales durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="a8923-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="a8923-135">Para implementarlas en la secuencia de tareas de implementación de Surface, deben definirse explícitamente para la instalación a través de un paso independiente en la secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="a8923-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="a8923-136">Para especificar los protocolos de forma explícita, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a8923-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="a8923-137">Abre las propiedades de la secuencia de tareas de implementación de Surface desde Deployment Workbench de MDT.</span><span class="sxs-lookup"><span data-stu-id="a8923-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="a8923-138">En la pestaña **Secuencia de tareas**, selecciona el paso **Instalar aplicaciones** en **Restaurar estado**.</span><span class="sxs-lookup"><span data-stu-id="a8923-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="a8923-139">Normalmente se encuentra entre los pasos previos y posteriores a la aplicación de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a8923-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="a8923-140">Usa el botón **Agregar** para crear un nuevo paso **Instalar aplicación** desde la categoría **General**.</span><span class="sxs-lookup"><span data-stu-id="a8923-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="a8923-141">Selecciona **Instalar una sola aplicación** en la pestaña **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a8923-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="a8923-142">Selecciona el protocolo EAP deseado de la lista.</span><span class="sxs-lookup"><span data-stu-id="a8923-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="a8923-143">Repite los pasos 2 a 5 para cada protocolo deseado.</span><span class="sxs-lookup"><span data-stu-id="a8923-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="a8923-144">Implementar PEAP, EAP-FAST o Cisco LEAP con Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a8923-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="a8923-145">Para las organizaciones que administran dispositivos Surface con Configuration Manager, es incluso más fácil implementar la compatibilidad de PEAP, EAP-FAST o Cisco LEAP en dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="a8923-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="a8923-146">Simplemente importa cada archivo MSI como una aplicación desde la biblioteca de software y configura una implementación en tu colección de dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="a8923-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="a8923-147">Para obtener más información sobre cómo implementar aplicaciones con Configuration Manager, consulta [Cómo crear aplicaciones en Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) y [Cómo implementar aplicaciones en Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span><span class="sxs-lookup"><span data-stu-id="a8923-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 






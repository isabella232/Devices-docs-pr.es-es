---
title: Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM (Surface)
description: Aprenda a administrar el modo de administración de Microsoft Surface Enterprise (SEMM) con el administrador de configuración de extremo.
keywords: inscribir, actualizar, scripts, configuración
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: bba99d202d5d0dc5085c454202ae9a95df56109c
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835522"
---
# <span data-ttu-id="17d73-104">Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM</span><span class="sxs-lookup"><span data-stu-id="17d73-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="17d73-105">La característica del modo de administración de Microsoft Surface (SEMM) de Surface UEFI permite a los administradores administrar y ayudar a proteger la configuración de la configuración de Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="17d73-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="17d73-106">Para la mayoría de las organizaciones, este proceso se consigue creando paquetes de Windows Installer (. msi) con la herramienta de configurador Microsoft Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="17d73-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="17d73-107">A continuación, estos paquetes se ejecutan o se implementan en los dispositivos Surface del cliente para inscribir los dispositivos en SEMM y para actualizar la configuración de la configuración de Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="17d73-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="17d73-108">Para las organizaciones con Microsoft Endpoint Configuration Manager, existe una alternativa al uso del proceso configurador Microsoft Surface UEFI. msi para implementar y administrar SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="17d73-109">Microsoft Surface UEFI Manager es un instalador ligero que hace que los ensamblados necesarios para la administración de SEMM estén disponibles en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="17d73-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="17d73-110">Al instalar estos ensamblados con Microsoft Surface UEFI Manager en un cliente administrado, SEMM puede ser administrado por Configuration Manager con scripts de PowerShell, implementado como aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="17d73-111">Con este proceso, la administración de SEMM se realiza en Configuration Manager, que elimina la necesidad de la herramienta externa del configurador Microsoft Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="17d73-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="17d73-112">Aunque el proceso descrito en este artículo puede funcionar con versiones anteriores de Endpoint Configuration Manager o con otras soluciones de administración de terceros, la administración de SEMM con Microsoft Surface UEFI Manager y PowerShell solo se admite en la rama actual del administrador de configuración de extremo.</span><span class="sxs-lookup"><span data-stu-id="17d73-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="17d73-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="17d73-113">Prerequisites</span></span>

<span data-ttu-id="17d73-114">Antes de comenzar el proceso descrito en este artículo, familiarícese con las siguientes tecnologías y herramientas:</span><span class="sxs-lookup"><span data-stu-id="17d73-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="17d73-115">Superficie UEFI</span><span class="sxs-lookup"><span data-stu-id="17d73-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="17d73-116">Modo de administración de empresa de Surface (SEMM)</span><span class="sxs-lookup"><span data-stu-id="17d73-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="17d73-117">Scripting de PowerShell</span><span class="sxs-lookup"><span data-stu-id="17d73-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="17d73-118">Implementación de aplicaciones de System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="17d73-119">Administración de certificados</span><span class="sxs-lookup"><span data-stu-id="17d73-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="17d73-120">También necesitará acceso al certificado que pretende usar para proteger el SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="17d73-121">Para obtener más información sobre los requisitos para este certificado, consulte [requisitos de certificados del modo de administración de Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span><span class="sxs-lookup"><span data-stu-id="17d73-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="17d73-122">Es muy importante que este certificado se mantenga en un lugar seguro y se haga una copia de seguridad de él correctamente.</span><span class="sxs-lookup"><span data-stu-id="17d73-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="17d73-123">Si este certificado se pierde o no se puede usar, no es posible restablecer Surface UEFI, cambiar la configuración de la superficie administrada UEFI o quitar SEMM de un dispositivo Surface inscrito.</span><span class="sxs-lookup"><span data-stu-id="17d73-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="17d73-124">Descargar Microsoft Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="17d73-125">La administración de SEMM con Configuration Manager requiere la instalación de Microsoft Surface UEFI Manager en cada dispositivo Surface del cliente.</span><span class="sxs-lookup"><span data-stu-id="17d73-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="17d73-126">Puede descargar Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) desde la página [Surface Tools para ti](https://www.microsoft.com/download/details.aspx?id=46703) en el centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="17d73-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="17d73-127">Descargar scripts SEMM para Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="17d73-128">Después de instalar Microsoft Surface UEFI Manager en el dispositivo Surface del cliente, SEMM se implementa y administra con scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17d73-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="17d73-129">Puede descargar muestras de las [secuencias de comandos de administración de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) desde el centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="17d73-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="17d73-130">Implementar Microsoft Surface UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="17d73-131">La implementación de Microsoft Surface UEFI Manager es una implementación de aplicaciones típica.</span><span class="sxs-lookup"><span data-stu-id="17d73-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="17d73-132">El archivo instalador de Microsoft Surface UEFI Manager es un archivo de Windows Installer estándar que puede instalar con la [opción silencio estándar](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span><span class="sxs-lookup"><span data-stu-id="17d73-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="17d73-133">El comando para instalar Microsoft Surface UEFI Manager es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="17d73-134">El comando para desinstalar Microsoft Surface UEFI Manager es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="17d73-135">Para crear una nueva aplicación e implementarla en una colección que contiene los dispositivos de Surface, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="17d73-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="17d73-136">Abra la consola de Configuration Manager desde la pantalla **Inicio** o desde el menú **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="17d73-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="17d73-137">Seleccione **biblioteca de software** en la esquina inferior izquierda de la ventana.</span><span class="sxs-lookup"><span data-stu-id="17d73-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="17d73-138">Expanda el nodo **Administración de aplicaciones** de la biblioteca de software y, a continuación, seleccione **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="17d73-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="17d73-139">Seleccione el botón **crear aplicación** en la pestaña **Inicio** , en la parte superior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="17d73-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="17d73-140">Esto inicia el Asistente para crear aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="17d73-141">El Asistente para crear aplicaciones presenta una serie de pasos:</span><span class="sxs-lookup"><span data-stu-id="17d73-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="17d73-142">**General** : la opción **detectar automáticamente la información sobre esta aplicación desde los archivos de instalación** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="17d73-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="17d73-143">En el campo **tipo** , **Windows Installer (archivo. msi)** también está seleccionado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="17d73-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="17d73-144">Seleccione **examinar** para ir a y seleccione **SurfaceUEFIManagerSetup.msi**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17d73-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="17d73-145">La ubicación de SurfaceUEFIManagerSetup.msi debe estar en un recurso compartido de red y encontrarse en una carpeta que no contenga otros archivos.</span><span class="sxs-lookup"><span data-stu-id="17d73-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="17d73-146">No se puede usar una ubicación de archivo local.</span><span class="sxs-lookup"><span data-stu-id="17d73-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="17d73-147">**Importar información** : el Asistente para crear aplicaciones analizará el archivo. msi y leerá el nombre de la **aplicación** y el **código de producto**.</span><span class="sxs-lookup"><span data-stu-id="17d73-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="17d73-148">SurfaceUEFIManagerSetup.msi debe aparecer como el único archivo que está debajo de los **archivos de contenido**de línea, como se muestra en la ilustración 1.</span><span class="sxs-lookup"><span data-stu-id="17d73-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="17d73-149">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-149">Select **Next** to proceed.</span></span>

      ![Se analiza automáticamente la información de la configuración de Surface UEFI Manager.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="17d73-151">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="17d73-151">Figure 1.</span></span> <span data-ttu-id="17d73-152">La información de la configuración de Microsoft Surface UEFI Manager se analiza de forma automática</span><span class="sxs-lookup"><span data-stu-id="17d73-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="17d73-153">**Información general** : puede modificar el nombre de la aplicación e información sobre el editor y la versión, o agregar comentarios en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="17d73-154">El comando de instalación de Microsoft Surface UEFI Manager se muestra en el campo del programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="17d73-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="17d73-155">El comportamiento de instalación predeterminada de instalar para el sistema permite que Microsoft Surface UEFI Manager Instale los ensamblados necesarios para SEMM incluso si un usuario no ha iniciado sesión en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="17d73-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="17d73-156">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="17d73-157">**Resumen** : la información que se analizó en el paso **Importar información** y las selecciones del paso **información general** se muestra en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="17d73-158">Seleccione **siguiente** para confirmar las selecciones y crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17d73-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="17d73-159">**Progreso** : muestra una barra de progreso y un estado a medida que se importa la aplicación y se agrega a la biblioteca de software.</span><span class="sxs-lookup"><span data-stu-id="17d73-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="17d73-160">**Finalización** : se muestra una confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17d73-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="17d73-161">Seleccione **cerrar** para finalizar el Asistente para crear aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="17d73-162">Después de crear la aplicación en Configuration Manager, puede distribuirla a los puntos de distribución e implementarla en las colecciones, incluidos los dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="17d73-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="17d73-163">Esta aplicación no instalará ni habilitará SEMM en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="17d73-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="17d73-164">Solo proporciona los ensamblados necesarios para que SEMM se habilite con el script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17d73-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="17d73-165">Si no desea instalar los ensamblados de Microsoft Surface UEFI Manager en dispositivos que no se administrarán con SEMM, puede configurar Microsoft Surface UEFI Manager como una dependencia de los scripts de SEMM Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="17d73-166">Este escenario se trata en la sección [implementar SEMM de scripts de Configuration Manager](#deploy-semm-configuration-manager-scripts) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="17d73-167">Crear o modificar los scripts de SEMM Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="17d73-168">Una vez instalados los ensamblados necesarios en los dispositivos, el proceso de inscribir los dispositivos en SEMM y configurar Surface UEFI se realiza con scripts de PowerShell y se implementa como una aplicación de scripts con Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="17d73-169">Estas secuencias de comandos se pueden modificar para satisfacer las necesidades de la organización y el entorno.</span><span class="sxs-lookup"><span data-stu-id="17d73-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="17d73-170">Por ejemplo, puede crear varias configuraciones para dispositivos de Surface administrados en diferentes departamentos o roles.</span><span class="sxs-lookup"><span data-stu-id="17d73-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="17d73-171">Puede descargar ejemplos de las secuencias de comandos para SEMM y Configuration Manager desde el vínculo de la sección [requisitos previos](#prerequisites) al principio de este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="17d73-172">Hay dos scripts principales que necesitará para realizar una implementación de SEMM con Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="17d73-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="17d73-173">**ConfigureSEMM.ps1** : Use este script para crear paquetes de configuración para los dispositivos Surface con la configuración de Surface UEFI deseada para aplicar la configuración especificada a un dispositivo Surface, para inscribir el dispositivo en SEMM y para establecer una clave del registro usada para identificar la inscripción del dispositivo en SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="17d73-174">**ResetSEMM.ps1** : Use este script para restablecer SEMM en un dispositivo Surface, que anula su inscripción de semm y quita el control de la configuración de Surface UEFI.</span><span class="sxs-lookup"><span data-stu-id="17d73-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="17d73-175">Los scripts de ejemplo incluyen ejemplos de cómo establecer la configuración de Surface UEFI y cómo controlar los permisos de esa configuración.</span><span class="sxs-lookup"><span data-stu-id="17d73-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="17d73-176">Esta configuración se puede modificar para la superficie segura UEFI y establecer la configuración de Surface UEFI según las necesidades de su entorno.</span><span class="sxs-lookup"><span data-stu-id="17d73-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="17d73-177">En las siguientes secciones de este artículo, se explica el script de ConfigureSEMM.ps1 y se exploran las modificaciones que es necesario realizar en la secuencia de comandos para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="17d73-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="17d73-178">Los scripts de SEMM Configuration Manager y el archivo de certificado SEMM exportado (. pfx) deben ubicarse en la misma carpeta sin otros archivos antes de que se agreguen a Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="17d73-179">Especificar nombres de paquetes y certificados</span><span class="sxs-lookup"><span data-stu-id="17d73-179">Specify certificate and package names</span></span>

<span data-ttu-id="17d73-180">La primera región de la secuencia de comandos que necesita modificar es la parte que especifica y carga el certificado SEMM, además de indicar SurfaceUEFIManager versión y los nombres del paquete de configuración de SEMM y SEMM restablecer paquete.</span><span class="sxs-lookup"><span data-stu-id="17d73-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="17d73-181">El nombre del certificado y la versión de SurfaceUEFIManager se especifican en las líneas 56 a 73 en el script de ConfigureSEMM.ps1.</span><span class="sxs-lookup"><span data-stu-id="17d73-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="17d73-182">Reemplace el valor **FabrikamSEMMSample. pfx** de la variable **$certName** por el nombre del archivo de certificado SEMM en la línea 58.</span><span class="sxs-lookup"><span data-stu-id="17d73-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="17d73-183">El script creará un directorio de trabajo (denominado configuración) en la carpeta en la que se encuentran los scripts y, a continuación, copiará el archivo de certificado en este directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="17d73-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="17d73-184">El paquete de propietario y el paquete de restablecimiento también se crearán en el directorio config y conservarán la configuración de los permisos y la configuración de Surface UEFI generados por el script.</span><span class="sxs-lookup"><span data-stu-id="17d73-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="17d73-185">En la línea 73, reemplace el valor de la variable **$password** , de **1234** a la contraseña del archivo de certificado.</span><span class="sxs-lookup"><span data-stu-id="17d73-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="17d73-186">Si no es necesaria una contraseña, elimine el texto de **1234** .</span><span class="sxs-lookup"><span data-stu-id="17d73-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="17d73-187">Los últimos dos caracteres de la huella digital del certificado son necesarios para inscribir un dispositivo en SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="17d73-188">Esta secuencia de comandos mostrará estos dígitos al usuario, lo que permite al usuario o al técnico grabar estos dígitos antes de que el sistema se reinicie para inscribir el dispositivo en SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="17d73-189">La secuencia de comandos usa el código siguiente, que se encuentra en las líneas 150-155, para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="17d73-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Los administradores con acceso al archivo de certificados (. pfx) pueden leer la huella digital en cualquier momento abriendo el archivo. pfx en CertMgr. <span data-ttu-id="17d73-191">Para ver la huella digital con CertMgr, siga este proceso:</span><span class="sxs-lookup"><span data-stu-id="17d73-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="17d73-192">Haga clic con el botón derecho en el archivo. pfx y, después, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="17d73-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="17d73-193">Expanda la carpeta en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="17d73-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="17d73-194">Seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="17d73-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="17d73-195">Haga clic con el botón derecho en el certificado en el panel principal y, a continuación, seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="17d73-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="17d73-196">Seleccione la pestaña **detalles** .</span><span class="sxs-lookup"><span data-stu-id="17d73-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="17d73-197">Solo se deben seleccionar **todas** **las propiedades** o en el menú desplegable **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="17d73-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="17d73-198">Seleccione la **huella digital**del campo.</span><span class="sxs-lookup"><span data-stu-id="17d73-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="17d73-199">El nombre de certificado y la contraseña de SEMM también deben escribirse en esta sección del script de ResetSEMM.ps1 para habilitar Configuration Manager para quitar SEMM del dispositivo con la acción de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="17d73-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="17d73-200">Configurar permisos</span><span class="sxs-lookup"><span data-stu-id="17d73-200">Configure permissions</span></span>

<span data-ttu-id="17d73-201">La primera región de la secuencia de comandos en la que especificará la configuración de Surface UEFI es la región de **permisos de configuración** .</span><span class="sxs-lookup"><span data-stu-id="17d73-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="17d73-202">Esta región comienza en la línea 210 de la secuencia de comandos de ejemplo con el comentario **# configurar permisos** y continúa en la línea 247.</span><span class="sxs-lookup"><span data-stu-id="17d73-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="17d73-203">El siguiente fragmento de código establece primero permisos para todos los ajustes de la superficie UEFI para que solo los pueda modificar SEMM, después agrega permisos explícitos que permiten al usuario local modificar la superficie UEFI contraseña, TPM, y cámaras frontal y trasera.</span><span class="sxs-lookup"><span data-stu-id="17d73-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="17d73-204">Cada variable **$uefiV 2** identifica una configuración de Surface UEFI mediante el establecimiento de nombre o identificador, y luego configura los permisos en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="17d73-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="17d73-205">**$ownerOnly** : el permiso para modificar esta configuración solo se concede a SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="17d73-206">**$ownerAndLocalUser** : el permiso para modificar esta configuración se concede a un usuario local que arranca con Surface UEFI, así como a SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="17d73-207">Puede encontrar información sobre los nombres e identificadores de configuración disponibles para Surface UEFI en la sección [nombres e identificadores de configuración](#settings-names-and-ids) de este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="17d73-208">Configurar opciones</span><span class="sxs-lookup"><span data-stu-id="17d73-208">Configure settings</span></span>

<span data-ttu-id="17d73-209">La segunda región de la secuencia de comandos en la que especificará la configuración de Surface UEFI es el área **configurar opciones** del script de ConfigureSEMM.ps1, que establece si cada opción está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="17d73-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="17d73-210">El script de ejemplo incluye instrucciones para establecer toda la configuración en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="17d73-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="17d73-211">La secuencia de comandos proporciona instrucciones explícitas para deshabilitar IPv6 para el arranque PXE y para dejar la contraseña de administrador de Surface UEFI sin cambios.</span><span class="sxs-lookup"><span data-stu-id="17d73-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="17d73-212">Puede encontrar esta región empezando con el comentario de **Configuración # Configurar** en la línea 291 a la 335 en la secuencia de comandos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17d73-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="17d73-213">La región aparece de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="17d73-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="17d73-214">Al igual que los permisos establecidos en la sección de configuración de **permisos** del script, la configuración de cada configuración de Surface UEFI se realiza definiendo la variable **$uefiV 2** .</span><span class="sxs-lookup"><span data-stu-id="17d73-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="17d73-215">Para cada línea que define la variable **$uefiV 2** , se identifica la configuración de Surface UEFI mediante el nombre o el identificador de configuración, y el valor configurado se establece en **habilitado** o **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="17d73-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="17d73-216">Si no desea alterar la configuración de una superficie UEFI, por ejemplo, asegúrese de que la contraseña de administrador de Surface UEFI no se limpie con la acción de restablecer la configuración de Surface UEFI a su valor predeterminado, puede usar **ClearConfiguredValue ()** para exigir que no se modifique esta configuración.</span><span class="sxs-lookup"><span data-stu-id="17d73-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="17d73-217">En el script de ejemplo, se usa en la línea 323 para evitar que se borre la contraseña de administrador de Surface UEFI, identificada en el script de ejemplo según su identificador de configuración, **501**.</span><span class="sxs-lookup"><span data-stu-id="17d73-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="17d73-218">Puede encontrar información sobre los nombres e identificadores de configuración disponibles para Surface UEFI en la sección [nombres e identificadores de configuración,](#settings-names-and-ids) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="17d73-219">Configuración clave del registro</span><span class="sxs-lookup"><span data-stu-id="17d73-219">Settings registry key</span></span>

<span data-ttu-id="17d73-220">Para identificar sistemas inscritos para Configuration Manager, el script de ConfigureSEMM.ps1 graba las claves del registro que se pueden usar para identificar sistemas inscritos como instalados con el script de configuración SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="17d73-221">Estas claves se pueden encontrar en la siguiente ubicación.</span><span class="sxs-lookup"><span data-stu-id="17d73-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="17d73-222">El siguiente fragmento de código, que se encuentra en las líneas 380-477, se usa para escribir estas claves de registro.</span><span class="sxs-lookup"><span data-stu-id="17d73-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="17d73-223">Nombres e identificadores de configuración</span><span class="sxs-lookup"><span data-stu-id="17d73-223">Settings names and IDs</span></span>

<span data-ttu-id="17d73-224">Para configurar la configuración de Surface UEFI o permisos para la configuración de Surface UEFI, debe hacer referencia a cada configuración mediante su nombre de configuración o el identificador de configuración.</span><span class="sxs-lookup"><span data-stu-id="17d73-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="17d73-225">Con cada nueva actualización de Surface UEFI, se puede Agregar una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="17d73-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="17d73-226">La mejor manera de obtener una lista completa de la configuración disponible en un dispositivo Surface, junto con el nombre de configuración y los identificadores de configuración, es usar la ShowSettingsOptions.ps1 script de SEMM_Powershell.zip en [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="17d73-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="17d73-227">El equipo en el que se ejecuta ShowSettingsOptions.ps1 debe tener instalado Microsoft Surface UEFI Manager, pero el script no requiere un dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="17d73-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>

<span data-ttu-id="17d73-228">La mejor manera de ver los nombres e identificadores de configuración más actuales para los dispositivos es usar el script de ConfigureSEMM.ps1 o el ConfigureSEMM- <device name> . PS1 de la SEMM_Powershell.zip en [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="17d73-228">The best way to view the most current Setting names and IDs for devices is to use the ConfigureSEMM.ps1 script or the ConfigureSEMM - <device name>.ps1 from the SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>

<span data-ttu-id="17d73-229">En el script ConfigureSEMM.ps1 se pueden ver los nombres e identificadores de todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="17d73-229">Setting names and IDs for all devices can be seen in the ConfigureSEMM.ps1 script.</span></span>

<span data-ttu-id="17d73-230">La configuración de nombres e identificadores para dispositivos específicos se puede ver en los <device name> scripts ConfigureSEMM-. ps1.</span><span class="sxs-lookup"><span data-stu-id="17d73-230">Setting names and IDs for specific devices can be seen in the ConfigureSEMM - <device name>.ps1 scripts.</span></span> <span data-ttu-id="17d73-231">Por ejemplo, los nombres e identificadores de configuración de Surface Pro X pueden encontrarse en el script ConfigureSEMM – ProX.ps1.</span><span class="sxs-lookup"><span data-stu-id="17d73-231">For example, setting names and IDs for Surface Pro X can be found in the ConfigureSEMM – ProX.ps1 script.</span></span>

## <span data-ttu-id="17d73-232">Implementar SEMM scripts de Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="17d73-232">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="17d73-233">Una vez que los scripts estén preparados para configurar y habilitar SEMM en el dispositivo cliente, el siguiente paso es agregar estos scripts como una aplicación en Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-233">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="17d73-234">Antes de abrir el administrador de configuración, asegúrese de que los siguientes archivos están en una carpeta compartida que no incluye otros archivos:</span><span class="sxs-lookup"><span data-stu-id="17d73-234">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="17d73-235">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="17d73-235">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="17d73-236">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="17d73-236">ResetSEMM.ps1</span></span>
* <span data-ttu-id="17d73-237">El certificado de SEMM (por ejemplo, SEMMCertificate. pfx)</span><span class="sxs-lookup"><span data-stu-id="17d73-237">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="17d73-238">Los scripts de Configuration Manager de SEMM se agregarán a Configuration Manager como una aplicación de script.</span><span class="sxs-lookup"><span data-stu-id="17d73-238">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="17d73-239">El comando para instalar SEMM con ConfigureSEMM.ps1 es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-239">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="17d73-240">El comando para desinstalar SEMM con ResetSEMM.ps1 es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-240">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="17d73-241">Para agregar los scripts del administrador de configuración de SEMM a Configuration Manager como una aplicación, use el siguiente proceso:</span><span class="sxs-lookup"><span data-stu-id="17d73-241">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="17d73-242">Inicie el Asistente para crear aplicaciones usando los pasos 1 a 5 de la sección [implementar Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-242">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="17d73-243">Continúe con el Asistente para crear aplicaciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="17d73-243">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="17d73-244">**General** : seleccione **especificar manualmente la información de la aplicación**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17d73-244">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="17d73-245">**Información general** : escriba un nombre para la aplicación (por ejemplo, SEMM) y cualquier otra información que desee, como editor, versión o comentarios, en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-245">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="17d73-246">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-246">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="17d73-247">**Catálogo de aplicaciones** : los campos de esta página se pueden dejar con los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="17d73-247">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="17d73-248">Selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17d73-248">Select **Next**.</span></span>

   - <span data-ttu-id="17d73-249">**Tipos de implementación** : seleccione **Agregar** para iniciar el Asistente para crear tipos de implementación.</span><span class="sxs-lookup"><span data-stu-id="17d73-249">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="17d73-250">Siga los pasos del Asistente para crear tipos de implementación, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="17d73-250">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="17d73-251">**General** : seleccione **instalador de script** en el menú desplegable **tipo** .</span><span class="sxs-lookup"><span data-stu-id="17d73-251">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="17d73-252">La opción **especificar manualmente la información de tipo de implementación** se seleccionará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="17d73-252">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="17d73-253">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-253">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="17d73-254">**Información general** : escriba un nombre para el tipo de implementación (por ejemplo, scripts de configuración de SEMM) y, a continuación, seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-254">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="17d73-255">**Contenido** : seleccione **examinar** junto al campo **Ubicación de contenido** y, a continuación, seleccione la carpeta donde se encuentran los scripts de Configuration Manager de semm.</span><span class="sxs-lookup"><span data-stu-id="17d73-255">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="17d73-256">En el campo **programa de instalación** , escriba el comando de [instalación](#deploy-semm-configuration-manager-scripts) que se encontró anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-256">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="17d73-257">En el campo **desinstalar programa** , escriba el [comando de desinstalación](#deploy-semm-configuration-manager-scripts) que se encuentra anteriormente en este artículo (que se muestra en la ilustración 2).</span><span class="sxs-lookup"><span data-stu-id="17d73-257">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="17d73-258">Seleccione **siguiente** para ir a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-258">Select **Next** to move to the next page.</span></span>
    
     ![Establecer los scripts de Configuration Manager de SEMM como comandos de instalación y desinstalación](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="17d73-260">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="17d73-260">Figure 2.</span></span> <span data-ttu-id="17d73-261">Establecer los scripts de Configuration Manager de SEMM como comandos de instalación y desinstalación</span><span class="sxs-lookup"><span data-stu-id="17d73-261">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="17d73-262">**Método de detección** : seleccione la **cláusula Add** para agregar la regla de detección de la clave de registro SEMM de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-262">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="17d73-263">Aparece la ventana **regla de detección** , como se muestra en la ilustración 3.</span><span class="sxs-lookup"><span data-stu-id="17d73-263">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="17d73-264">Usa la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="17d73-264">Use the following settings:</span></span>

       - <span data-ttu-id="17d73-265">Seleccione **registro** en el menú desplegable **tipo de configuración** .</span><span class="sxs-lookup"><span data-stu-id="17d73-265">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="17d73-266">Seleccione **HKEY_LOCAL_MACHINE** en el menú desplegable **Hive (Hive** ).</span><span class="sxs-lookup"><span data-stu-id="17d73-266">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="17d73-267">Escriba **SOFTWARE\Microsoft\Surface\SEMM** en el campo **clave** .</span><span class="sxs-lookup"><span data-stu-id="17d73-267">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="17d73-268">Escriba **CertName** en el campo de **valor** .</span><span class="sxs-lookup"><span data-stu-id="17d73-268">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="17d73-269">Seleccione **cadena** en el menú desplegable **tipo de datos** .</span><span class="sxs-lookup"><span data-stu-id="17d73-269">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="17d73-270">Seleccione la **opción este registro debe cumplir con los siguientes pasos para indicar la presencia de esta aplicación** .</span><span class="sxs-lookup"><span data-stu-id="17d73-270">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="17d73-271">Escriba el nombre del certificado que ha introducido en la línea 58 del script en el campo de **valor** .</span><span class="sxs-lookup"><span data-stu-id="17d73-271">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="17d73-272">Seleccione **Aceptar** para cerrar la ventana de **regla de detección** .</span><span class="sxs-lookup"><span data-stu-id="17d73-272">Select **OK** to close the **Detection Rule** window.</span></span>

     ![Usar una clave del registro para identificar los dispositivos inscritos en SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="17d73-274">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="17d73-274">Figure 3.</span></span> <span data-ttu-id="17d73-275">Usar una clave del registro para identificar los dispositivos inscritos en SEMM</span><span class="sxs-lookup"><span data-stu-id="17d73-275">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="17d73-276">Seleccione **siguiente** para pasar a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="17d73-276">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="17d73-277">**Experiencia de usuario** : seleccione **instalar para el sistema** en el menú desplegable de **instalación** .</span><span class="sxs-lookup"><span data-stu-id="17d73-277">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="17d73-278">Si quiere que los usuarios registren y escriban la huella digital del certificado, deje el requisito de inicio de sesión establecido en **solo cuando un usuario ha iniciado sesión**.</span><span class="sxs-lookup"><span data-stu-id="17d73-278">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="17d73-279">Si desea que los administradores introduzcan la huella digital para los usuarios y los usuarios no necesiten ver la huella digital, seleccione **si un usuario ha iniciado sesión en** el menú desplegable de **requisitos de inicio de sesión** .</span><span class="sxs-lookup"><span data-stu-id="17d73-279">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="17d73-280">**Requisitos** : el script de ConfigureSEMM.ps1 comprueba automáticamente que el dispositivo es un dispositivo Surface antes de intentar habilitar SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-280">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="17d73-281">Sin embargo, si tiene previsto implementar esta aplicación de script en una colección con dispositivos distintos de los que se administrarán con SEMM, puede agregar requisitos aquí para asegurarse de que esta aplicación se ejecute solo en dispositivos Surface o dispositivos que desee administrar con SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-281">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="17d73-282">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-282">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="17d73-283">**Dependencias** : seleccione **Agregar** para abrir la ventana **Agregar dependencia** .</span><span class="sxs-lookup"><span data-stu-id="17d73-283">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="17d73-284">Seleccione **Agregar** para abrir la ventana **especificar aplicación requerida** .</span><span class="sxs-lookup"><span data-stu-id="17d73-284">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="17d73-285">Escriba un nombre para las dependencias SEMM en el campo de **nombre del grupo de dependencias** (por ejemplo, *SEMM ensamblados*).</span><span class="sxs-lookup"><span data-stu-id="17d73-285">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="17d73-286">Seleccione **Microsoft Surface UEFI Manager** en la lista de **aplicaciones disponibles** y el tipo de implementación MSI y, a continuación, seleccione **Aceptar** para cerrar la ventana **especificar aplicación requerida** .</span><span class="sxs-lookup"><span data-stu-id="17d73-286">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="17d73-287">Mantenga activada la casilla de verificación **instalación automática** si quiere que Microsoft Surface UEFI Manager se instale automáticamente en los dispositivos cuando intente habilitar SEMM con los scripts de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-287">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="17d73-288">Seleccione **Aceptar** para cerrar la ventana **Agregar dependencia** .</span><span class="sxs-lookup"><span data-stu-id="17d73-288">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="17d73-289">Seleccione **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="17d73-289">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="17d73-290">**Resumen** : la información que ha introducido en el Asistente para crear tipos de implementación se muestra en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-290">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="17d73-291">Seleccione **siguiente** para confirmar las selecciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-291">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="17d73-292">**Progreso** : se muestra una barra de progreso y un estado como tipo de implementación para la aplicación de script SEMM en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-292">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="17d73-293">**Finalización** : la confirmación de la creación del tipo de implementación se muestra cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="17d73-293">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="17d73-294">Seleccione **cerrar** para finalizar el Asistente para crear tipos de implementación.</span><span class="sxs-lookup"><span data-stu-id="17d73-294">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="17d73-295">**Resumen** : se muestra la información introducida en el Asistente para crear aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-295">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="17d73-296">Seleccione **siguiente** para crear la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17d73-296">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="17d73-297">**Progreso** : se muestra una barra de progreso y el estado como la aplicación en la biblioteca de software en esta página.</span><span class="sxs-lookup"><span data-stu-id="17d73-297">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="17d73-298">**Finalización** : se muestra una confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17d73-298">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="17d73-299">Seleccione **cerrar** para finalizar el Asistente para crear aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-299">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="17d73-300">Una vez que la aplicación de scripts esté disponible en la biblioteca de software de Configuration Manager, puede distribuir e implementar SEMM con los scripts que preparó para dispositivos o colecciones.</span><span class="sxs-lookup"><span data-stu-id="17d73-300">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="17d73-301">Si ha configurado los ensamblados de Microsoft Surface UEFI Manager como una dependencia que se instalará de forma automática, puede implementar SEMM en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="17d73-301">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="17d73-302">Si no ha configurado los ensamblados como dependencia, debe instalarlos en los dispositivos que desea administrar antes de habilitar SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-302">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="17d73-303">Al implementar SEMM con esta aplicación de scripts y con una configuración visible para el usuario final, el script de PowerShell se iniciará y la ventana de PowerShell mostrará la huella digital para el certificado.</span><span class="sxs-lookup"><span data-stu-id="17d73-303">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="17d73-304">Puede hacer que los usuarios registren esta huella digital y escribirla cuando se lo solicite la Surface UEFI después de que el dispositivo se reinicie.</span><span class="sxs-lookup"><span data-stu-id="17d73-304">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="17d73-305">Como alternativa, puede configurar la instalación de la aplicación para que se reinicie automáticamente y, de forma invisible para el usuario.</span><span class="sxs-lookup"><span data-stu-id="17d73-305">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="17d73-306">En este caso, se requerirá que un técnico Introduzca la huella digital en cada dispositivo a medida que se reinicie.</span><span class="sxs-lookup"><span data-stu-id="17d73-306">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="17d73-307">Cualquier técnico con acceso al archivo de certificado puede leer la huella digital viendo el certificado con CertMgr.</span><span class="sxs-lookup"><span data-stu-id="17d73-307">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="17d73-308">Las instrucciones para ver la huella digital con CertMgr se encuentran en la sección [crear o modificar la Semm de las secuencias de comandos de Configuration Manager](#create-or-modify-the-semm-configuration-manager-scripts) de este artículo.</span><span class="sxs-lookup"><span data-stu-id="17d73-308">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="17d73-309">La eliminación de SEMM de un dispositivo implementado con Configuration Manager con estas secuencias de comandos es tan fácil como desinstalar la aplicación con Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="17d73-309">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="17d73-310">Esta acción inicia el script de ResetSEMM.ps1 y anula la inscripción del dispositivo correctamente con el mismo archivo de certificado que se usó durante la implementación de SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-310">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="17d73-311">Microsoft Surface recomienda que cree paquetes de restablecimiento solo cuando necesite anular la inscripción de un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="17d73-311">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="17d73-312">Normalmente, estos paquetes de restablecimiento son válidos para un solo dispositivo, identificados por su número de serie.</span><span class="sxs-lookup"><span data-stu-id="17d73-312">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="17d73-313">Sin embargo, puede crear un paquete de restablecimiento universal que funcione para cualquier dispositivo inscrito en SEMM con este certificado.</span><span class="sxs-lookup"><span data-stu-id="17d73-313">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="17d73-314">Le recomendamos encarecidamente que proteja su paquete de restablecimiento universal tan detenidamente como el certificado que usó para inscribir dispositivos en SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-314">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="17d73-315">Recuerde que, al igual que el propio certificado, este paquete de restablecimiento universal se puede usar para anular la inscripción de cualquiera de los dispositivos Surface de su organización desde SEMM.</span><span class="sxs-lookup"><span data-stu-id="17d73-315">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="17d73-316">Al instalar un paquete de restablecimiento, el valor más bajo admitido (LSV) se restablece en el valor 1.</span><span class="sxs-lookup"><span data-stu-id="17d73-316">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="17d73-317">Puede volver a inscribir un dispositivo con un paquete de configuración existente.</span><span class="sxs-lookup"><span data-stu-id="17d73-317">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="17d73-318">El dispositivo solicitará la huella digital del certificado antes de que se realice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="17d73-318">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="17d73-319">Por esta razón, la reinscripción de un dispositivo en SEMM requeriría la creación y la instalación de un nuevo paquete en ese dispositivo.</span><span class="sxs-lookup"><span data-stu-id="17d73-319">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="17d73-320">Como esta acción es una inscripción nueva y no un cambio en la configuración en un dispositivo ya inscrito en SEMM, el dispositivo solicitará la huella digital del certificado antes de que se realice la propiedad.</span><span class="sxs-lookup"><span data-stu-id="17d73-320">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>

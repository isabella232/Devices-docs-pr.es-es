---
title: Implementar Surface App con Microsoft Store para empresas o Microsoft Store para el ámbito educativo (Surface)
description: Descubra cómo agregar y descargar Surface App con Microsoft Store para empresas o Microsoft Store para el ámbito educativo, así como instalar Surface App con PowerShell y MDT.
keywords: aplicación Surface, aplicación, implementación, personalizar
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835122"
---
# <span data-ttu-id="02dc3-104">Implementar la aplicación Surface con Microsoft Store para empresas y educación</span><span class="sxs-lookup"><span data-stu-id="02dc3-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="02dc3-105">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="02dc3-105">Applies to</span></span>**

- <span data-ttu-id="02dc3-106">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="02dc3-106">Surface Pro 7</span></span>
- <span data-ttu-id="02dc3-107">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="02dc3-107">Surface Laptop 3</span></span>
- <span data-ttu-id="02dc3-108">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="02dc3-108">Surface Pro 6</span></span>
- <span data-ttu-id="02dc3-109">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="02dc3-109">Surface Laptop 2</span></span>
- <span data-ttu-id="02dc3-110">Surface Go</span><span class="sxs-lookup"><span data-stu-id="02dc3-110">Surface Go</span></span>
- <span data-ttu-id="02dc3-111">Ir a la superficie con LTE</span><span class="sxs-lookup"><span data-stu-id="02dc3-111">Surface Go with LTE</span></span>
- <span data-ttu-id="02dc3-112">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="02dc3-112">Surface Book 2</span></span>
- <span data-ttu-id="02dc3-113">Surface Pro con LTE avanzada (modelo 1807)</span><span class="sxs-lookup"><span data-stu-id="02dc3-113">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="02dc3-114">Surface Pro (modelo 1796)</span><span class="sxs-lookup"><span data-stu-id="02dc3-114">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="02dc3-115">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="02dc3-115">Surface Laptop</span></span>
- <span data-ttu-id="02dc3-116">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="02dc3-116">Surface Studio</span></span>
- <span data-ttu-id="02dc3-117">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="02dc3-117">Surface Studio 2</span></span>
- <span data-ttu-id="02dc3-118">Surface Book</span><span class="sxs-lookup"><span data-stu-id="02dc3-118">Surface Book</span></span>
- <span data-ttu-id="02dc3-119">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="02dc3-119">Surface Pro 4</span></span>
- <span data-ttu-id="02dc3-120">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="02dc3-120">Surface 3 LTE</span></span>
- <span data-ttu-id="02dc3-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="02dc3-121">Surface 3</span></span>
- <span data-ttu-id="02dc3-122">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="02dc3-122">Surface Pro 3</span></span>


<span data-ttu-id="02dc3-123">La aplicación Surface es una aplicación de Microsoft Store ligera que ofrece control de muchas opciones y configuraciones específicas, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="02dc3-123">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="02dc3-124">Habilitar o deshabilitar el botón Windows en el dispositivo Surface 
</span><span class="sxs-lookup"><span data-stu-id="02dc3-124">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="02dc3-125">Ajustar la sensibilidad de un Lápiz para Surface 
</span><span class="sxs-lookup"><span data-stu-id="02dc3-125">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="02dc3-126">Personalizar las acciones del botón de Lápiz para Surface 
</span><span class="sxs-lookup"><span data-stu-id="02dc3-126">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="02dc3-127">Habilitar o deshabilitar las mejoras de audio de Surface 
</span><span class="sxs-lookup"><span data-stu-id="02dc3-127">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="02dc3-128">Acceso rápido a la documentación de soporte técnico y a la información del dispositivo</span><span class="sxs-lookup"><span data-stu-id="02dc3-128">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="02dc3-129">Los clientes que usen Windows Update recibirán la aplicación Surface normalmente como parte de las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-129">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="02dc3-130">Pero si su organización está preparando imágenes para su implementación en sus dispositivos Surface, es posible que desee incluir la aplicación Surface (anteriormente denominada Surface hub) en el proceso de creación de imágenes y de implementación en lugar de requerir que los usuarios de cada dispositivo descarguen e instalen la aplicación de Microsoft Store o de Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-130">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="02dc3-131">Este artículo no se aplica a Surface Pro X. Para obtener más información, consulte [implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="02dc3-131">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="02dc3-132">Información general de Surface App</span><span class="sxs-lookup"><span data-stu-id="02dc3-132">Surface app overview</span></span>

<span data-ttu-id="02dc3-133">La aplicación Surface está disponible como una descarga gratuita de [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span><span class="sxs-lookup"><span data-stu-id="02dc3-133">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="02dc3-134">Los usuarios pueden descargarlo e instalarlo desde Microsoft Store, pero si su organización usa Microsoft Store for Business en su lugar, tendrá que agregarlo al inventario de su tienda y posiblemente incluir la aplicación como parte del proceso de implementación de Windows.</span><span class="sxs-lookup"><span data-stu-id="02dc3-134">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="02dc3-135">Estos procesos se tratan en este artículo.</span><span class="sxs-lookup"><span data-stu-id="02dc3-135">These processes are discussed throughout this article.</span></span> <span data-ttu-id="02dc3-136">Para obtener más información acerca de Microsoft Store para empresas, consulte [Microsoft Store para empresas](https://docs.microsoft.com/microsoft-store/) en Windows TechCenter.</span><span class="sxs-lookup"><span data-stu-id="02dc3-136">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="02dc3-137">Agregar una aplicación de Surface a una cuenta de Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="02dc3-137">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="02dc3-138">Antes de que los usuarios puedan instalar o implementar una aplicación de una cuenta de Microsoft Store para empresas, primero debe estar disponible y conceder la licencia a los usuarios de una empresa.</span><span class="sxs-lookup"><span data-stu-id="02dc3-138">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="02dc3-139">Si aún no lo ha hecho, cree una [cuenta de Microsoft Store para empresas](https://www.microsoft.com/business-store).</span><span class="sxs-lookup"><span data-stu-id="02dc3-139">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="02dc3-140">Inicie sesión en el portal.</span><span class="sxs-lookup"><span data-stu-id="02dc3-140">Log on to the portal.</span></span> 

3. <span data-ttu-id="02dc3-141">Habilitar licencias sin conexión: haga clic en **administrar->configuración**de la tienda y, a continuación, seleccione la casilla **Mostrar aplicaciones con licencias sin conexión a personas que se van a comprar en la tienda** , como se muestra en la ilustración 1.</span><span class="sxs-lookup"><span data-stu-id="02dc3-141">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="02dc3-142">Para obtener más información sobre los modelos de licencias de aplicaciones de Microsoft Store para empresas, consulte [aplicaciones en Microsoft Store para empresas y educación](https://docs.microsoft.com/microsoft-store/).</span><span class="sxs-lookup"><span data-stu-id="02dc3-142">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span><br/> <br/>
   ![Casilla Mostrar aplicaciones de licencias sin conexión](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="02dc3-144">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="02dc3-144">Figure 1.</span></span> <span data-ttu-id="02dc3-145">Habilitar aplicaciones para su uso sin conexión</span><span class="sxs-lookup"><span data-stu-id="02dc3-145">Enable apps for offline use</span></span>*

4. <span data-ttu-id="02dc3-146">Agregue la aplicación Surface a su cuenta de Microsoft Store para empresas siguiendo este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="02dc3-146">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>
    * <span data-ttu-id="02dc3-147">Haga clic en el menú de **tienda** .</span><span class="sxs-lookup"><span data-stu-id="02dc3-147">Click the **Shop** menu.</span></span>
    * <span data-ttu-id="02dc3-148">En el cuadro de búsqueda, escriba **Surface App**y, a continuación, haga clic en el icono de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02dc3-148">In the search box, type **Surface app**, and then click the search icon.</span></span>
    * <span data-ttu-id="02dc3-149">Una vez que se presente la aplicación Surface en los resultados de la búsqueda, haga clic en el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02dc3-149">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    * <span data-ttu-id="02dc3-150">Se le presenta una opción (seleccione **en línea** o **sin conexión**), como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="02dc3-150">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span><br/><br/>
    
    ![Seleccione el modo de licencia sin conexión y agregue la aplicación al inventario.](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *<span data-ttu-id="02dc3-152">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="02dc3-152">Figure 2.</span></span> <span data-ttu-id="02dc3-153">Seleccione el modo de licencia sin conexión y agregue la aplicación al inventario.</span><span class="sxs-lookup"><span data-stu-id="02dc3-153">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="02dc3-154">Haga clic en **sin conexión** para seleccionar el modo de licencias sin conexión.</span><span class="sxs-lookup"><span data-stu-id="02dc3-154">Click **Offline** to select the Offline licensing mode.</span></span>
    * <span data-ttu-id="02dc3-155">Haga clic en **obtener la aplicación** para agregar la aplicación a su inventario de Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-155">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="02dc3-156">Como se muestra en la figura 3, verá un cuadro de diálogo que le pide que confirme que las aplicaciones sin conexión se pueden implementar con una herramienta de administración o se descargan desde la página de inventario de la empresa en su tienda privada.</span><span class="sxs-lookup"><span data-stu-id="02dc3-156">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
    ![Ventana de confirmación de aplicación con licencia sin conexión](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *<span data-ttu-id="02dc3-158">Figura 3.</span><span class="sxs-lookup"><span data-stu-id="02dc3-158">Figure 3.</span></span> <span data-ttu-id="02dc3-159">Confirmación de aplicación con licencia sin conexión</span><span class="sxs-lookup"><span data-stu-id="02dc3-159">Offline-licensed app acknowledgement</span></span>*
    * <span data-ttu-id="02dc3-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-160">Click **OK**.</span></span>

## <span data-ttu-id="02dc3-161">Descargar Surface App desde una cuenta de Microsoft Store para empresas</span><span class="sxs-lookup"><span data-stu-id="02dc3-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="02dc3-162">Después de agregar una aplicación a la cuenta de Microsoft Store para empresas en el modo sin conexión, puede descargar y agregar la aplicación como un AppxBundle a un recurso compartido de implementación.</span><span class="sxs-lookup"><span data-stu-id="02dc3-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>
1. <span data-ttu-id="02dc3-163">Inicie sesión en la cuenta de Microsoft Store para empresas en https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="02dc3-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>
2. <span data-ttu-id="02dc3-164">Haga clic en **administrar->aplicaciones & software**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="02dc3-165">Se muestra una lista de todas las aplicaciones de su empresa, incluida la aplicación Surface que agregó en la [aplicación agregar Surface a una cuenta de Microsoft Store para empresas](#add-surface-app-to-a-microsoft-store-for-business-account) en este artículo.</span><span class="sxs-lookup"><span data-stu-id="02dc3-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>
3. <span data-ttu-id="02dc3-166">En **acciones**, haga clic en los puntos suspensivos (**...**) y, a continuación, haga clic en **descargar para usar sin conexión** en la aplicación Surface.</span><span class="sxs-lookup"><span data-stu-id="02dc3-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>
4. <span data-ttu-id="02dc3-167">Seleccione las opciones de **plataforma** y **arquitectura** que desee de las selecciones disponibles para la aplicación seleccionada, como se muestra en la ilustración 4.</span><span class="sxs-lookup"><span data-stu-id="02dc3-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    ![Ejemplo del paquete AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *<span data-ttu-id="02dc3-169">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="02dc3-169">Figure 4.</span></span> <span data-ttu-id="02dc3-170">Descargar el paquete AppxBundle de una aplicación</span><span class="sxs-lookup"><span data-stu-id="02dc3-170">Download the AppxBundle package for an app</span></span>*
5. <span data-ttu-id="02dc3-171">Haga clic en **Descargar**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-171">Click **Download**.</span></span> <span data-ttu-id="02dc3-172">El paquete AppxBundle se descargará.</span><span class="sxs-lookup"><span data-stu-id="02dc3-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="02dc3-173">Asegúrese de que anota la ruta de acceso del archivo descargado porque lo necesitará más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="02dc3-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>
6. <span data-ttu-id="02dc3-174">Haga clic en la opción **licencia codificada** o en **licencia sin codificar** .</span><span class="sxs-lookup"><span data-stu-id="02dc3-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="02dc3-175">Use la opción de licencia codificada con herramientas de administración como Microsoft Endpoint Configuration Manager o cuando use el diseñador de configuración de Windows para crear un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="02dc3-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="02dc3-176">Seleccione la opción de licencia sin codificar al usar administración y mantenimiento de imágenes de implementación (DISM) o soluciones de implementación basadas en Imaging, incluido Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="02dc3-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>
7. <span data-ttu-id="02dc3-177">Haga clic en **generar** para generar y descargar la licencia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02dc3-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="02dc3-178">Asegúrese de que anota la ruta de acceso del archivo de licencia porque lo necesitará más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="02dc3-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="02dc3-179">Al descargar una aplicación para su uso sin conexión, como la aplicación Surface, es posible que observe una sección en la parte inferior de la página denominada **frameworks requerido**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="02dc3-180">Los equipos de destino deben tener instalados los marcos de trabajo de la aplicación, por lo que es posible que tenga que repetir el proceso de descarga para cada uno de los marcos de trabajo necesarios para su arquitectura (x86 o x64) e incluirlos como parte de la implementación de Windows que se trata más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="02dc3-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="02dc3-181">La figura 5 muestra los marcos de trabajo necesarios para Surface app.</span><span class="sxs-lookup"><span data-stu-id="02dc3-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

![Marcos necesarios para la aplicación Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*<span data-ttu-id="02dc3-183">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="02dc3-183">Figure 5.</span></span> <span data-ttu-id="02dc3-184">Marcos necesarios para la aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="02dc3-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="02dc3-185">Los números de versión de la aplicación Surface y los marcos obligatorios cambiarán a medida que se actualicen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="02dc3-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="02dc3-186">Busque la última versión de Surface App y de cada marco en Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="02dc3-187">Use siempre la aplicación de Surface y las versiones de marco recomendadas proporcionadas por Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="02dc3-188">El uso de Marcos anticuados o de versiones incorrectas puede producir errores o bloqueos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02dc3-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="02dc3-189">Para descargar los marcos necesarios para la aplicación Surface, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="02dc3-189">To download the required frameworks for the Surface app, follow these steps:</span></span>
1. <span data-ttu-id="02dc3-190">Haga clic en el botón **Descargar** en **Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="02dc3-191">Esto descarga el Microsoft. VCLibs. 140.00 _ 14.0.23816.0_x64__8wekyb3d8bbwe. Appx a la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="02dc3-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>
2. <span data-ttu-id="02dc3-192">Haga clic en el botón **Descargar** en **Microsoft. net. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="02dc3-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="02dc3-193">Esto descarga el archivo Microsoft. NET. Native. Runtime. 1.1 _ 1.1.23406.0_x64__8wekyb3d8bbwe. appx en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="02dc3-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="02dc3-194">Para los dispositivos Surface, solo se necesita la versión de 64 bits (x64) de cada marco.</span><span class="sxs-lookup"><span data-stu-id="02dc3-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="02dc3-195">Los dispositivos Surface son dispositivos UEFI nativos de 64 bits y no son compatibles con las versiones de Windows de 32 bits (x86) que requerirían marcos de trabajo de 32.</span><span class="sxs-lookup"><span data-stu-id="02dc3-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="02dc3-196">Instalar la aplicación Surface en el equipo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="02dc3-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="02dc3-197">El procedimiento siguiente indica la aplicación Surface en el equipo y la pone a disposición de todas las cuentas de usuario creadas en el equipo después.</span><span class="sxs-lookup"><span data-stu-id="02dc3-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>
1. <span data-ttu-id="02dc3-198">Con el procedimiento descrito en la sección [Cómo descargar la aplicación de Surface desde una cuenta de Microsoft Store para empresas](#download-surface-app-from-a-microsoft-store-for-business-account) de este artículo, descarga el archivo AppxBundle de la aplicación de Surface y el archivo de licencia.</span><span class="sxs-lookup"><span data-stu-id="02dc3-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 
2. <span data-ttu-id="02dc3-199">Comienza una sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="02dc3-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="02dc3-200">Si no ejecuta PowerShell como administrador, la sesión no tendrá los permisos necesarios para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02dc3-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="02dc3-201">En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: </span><span class="sxs-lookup"><span data-stu-id="02dc3-201">In the elevated PowerShell session, copy and paste the following command:</span></span>
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="02dc3-202">Donde `<DownloadPath>` es la carpeta donde descargó el archivo AppxBundle y el archivo de licencia de la cuenta de Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="02dc3-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="02dc3-203">Por ejemplo, si ha descargado los archivos en c:\Temp, el comando que ejecuta es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02dc3-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).

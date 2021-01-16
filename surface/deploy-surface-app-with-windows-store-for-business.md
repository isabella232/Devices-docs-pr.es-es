---
title: Implementar la aplicación Surface con la Microsoft Store para Empresas o la Microsoft Store para Educación (Surface)
description: Descubre cómo agregar y descargar la aplicación Surface con la Microsoft Store para Empresas o la Microsoft Store para Educación, así como instalar la aplicación Surface con PowerShell y MDT.
keywords: aplicación surface, aplicación, implementación, personalizar
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271077"
---
# <span data-ttu-id="4940a-104">Implementar la aplicación Surface con la Microsoft Store para Empresas y Educación</span><span class="sxs-lookup"><span data-stu-id="4940a-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="4940a-105">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="4940a-105">Applies to</span></span>**

- <span data-ttu-id="4940a-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="4940a-106">Surface Pro 7+</span></span>
- <span data-ttu-id="4940a-107">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="4940a-107">Surface Laptop Go</span></span>
- <span data-ttu-id="4940a-108">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="4940a-108">Surface Pro 7</span></span>
- <span data-ttu-id="4940a-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="4940a-109">Surface Laptop 3</span></span>
- <span data-ttu-id="4940a-110">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="4940a-110">Surface Pro 6</span></span>
- <span data-ttu-id="4940a-111">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="4940a-111">Surface Laptop 2</span></span>
- <span data-ttu-id="4940a-112">Surface Go</span><span class="sxs-lookup"><span data-stu-id="4940a-112">Surface Go</span></span>
- <span data-ttu-id="4940a-113">Surface Go con LTE</span><span class="sxs-lookup"><span data-stu-id="4940a-113">Surface Go with LTE</span></span>
- <span data-ttu-id="4940a-114">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="4940a-114">Surface Book 2</span></span>
- <span data-ttu-id="4940a-115">Surface Pro con LTE avanzada (modelo 1807)</span><span class="sxs-lookup"><span data-stu-id="4940a-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="4940a-116">Surface Pro (modelo 1796)</span><span class="sxs-lookup"><span data-stu-id="4940a-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="4940a-117">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="4940a-117">Surface Laptop</span></span>
- <span data-ttu-id="4940a-118">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="4940a-118">Surface Studio</span></span>
- <span data-ttu-id="4940a-119">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="4940a-119">Surface Studio 2</span></span>
- <span data-ttu-id="4940a-120">Surface Book</span><span class="sxs-lookup"><span data-stu-id="4940a-120">Surface Book</span></span>
- <span data-ttu-id="4940a-121">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4940a-121">Surface Pro 4</span></span>
- <span data-ttu-id="4940a-122">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="4940a-122">Surface 3 LTE</span></span>
- <span data-ttu-id="4940a-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="4940a-123">Surface 3</span></span>
- <span data-ttu-id="4940a-124">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="4940a-124">Surface Pro 3</span></span>


<span data-ttu-id="4940a-125">La aplicación Surface es una aplicación ligera de Microsoft Store que proporciona control de muchas opciones y configuraciones específicas de Surface, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="4940a-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="4940a-126">Habilitar o deshabilitar el botón Windows en el dispositivo Surface 
</span><span class="sxs-lookup"><span data-stu-id="4940a-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="4940a-127">Ajustar la sensibilidad de un Lápiz para Surface 
</span><span class="sxs-lookup"><span data-stu-id="4940a-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="4940a-128">Personalizar las acciones del botón de Lápiz para Surface 
</span><span class="sxs-lookup"><span data-stu-id="4940a-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="4940a-129">Habilitar o deshabilitar las mejoras de audio de Surface 
</span><span class="sxs-lookup"><span data-stu-id="4940a-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="4940a-130">Acceso rápido a la documentación de soporte técnico e información para el dispositivo</span><span class="sxs-lookup"><span data-stu-id="4940a-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="4940a-131">Normalmente, los clientes que usan Windows Update recibirán la aplicación Surface como parte de las actualizaciones automáticas.</span><span class="sxs-lookup"><span data-stu-id="4940a-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="4940a-132">Pero si tu organización está preparando imágenes para su implementación en los dispositivos Surface, es posible que quieras incluir la aplicación Surface (anteriormente denominada Surface Hub) en el proceso de creación de imágenes e implementación en lugar de requerir que los usuarios de cada dispositivo individual descarguen e instalen la aplicación desde Microsoft Store o la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4940a-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="4940a-133">Este artículo no se aplica a Surface Pro X. Para obtener más información, consulta [Implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="4940a-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="4940a-134">Introducción a la aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="4940a-134">Surface app overview</span></span>

<span data-ttu-id="4940a-135">La aplicación Surface está disponible como descarga gratuita desde [Microsoft Store.](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)</span><span class="sxs-lookup"><span data-stu-id="4940a-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="4940a-136">Los usuarios pueden descargarla e instalarla desde Microsoft Store, pero si tu organización usa la Microsoft Store para Empresas en su lugar, deberás agregarla al inventario de la tienda y posiblemente incluir la aplicación como parte del proceso de implementación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4940a-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="4940a-137">Estos procesos se de abordan a lo largo de este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="4940a-138">Para obtener más información sobre la Microsoft Store para Empresas, consulta [Microsoft Store para Empresas](https://docs.microsoft.com/microsoft-store/) en el TechCenter de Windows.</span><span class="sxs-lookup"><span data-stu-id="4940a-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="4940a-139">Agregar una aplicación Surface a una cuenta de la Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="4940a-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="4940a-140">Antes de que los usuarios puedan instalar o implementar una aplicación desde la cuenta de la Microsoft Store para Empresas de una empresa, las aplicaciones deseadas deben estar disponibles y tener una licencia para los usuarios de una empresa.</span><span class="sxs-lookup"><span data-stu-id="4940a-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="4940a-141">Si aún no lo has hecho, crea una [cuenta de la Microsoft Store para Empresas.](https://www.microsoft.com/business-store)</span><span class="sxs-lookup"><span data-stu-id="4940a-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="4940a-142">Inicie sesión en el portal.</span><span class="sxs-lookup"><span data-stu-id="4940a-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="4940a-143">Habilita las licencias sin conexión: haz clic en \*\*\*\* Administrar **>** Configuración de la Tienda y, a continuación, selecciona la casilla Mostrar aplicaciones con licencia sin conexión a las personas que compran en la tienda, como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="4940a-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="4940a-144">Para obtener más información sobre los modelos de licencias de aplicaciones de la Microsoft Store para Empresas, consulta Aplicaciones de [la Microsoft Store para Empresas y Educación.](https://docs.microsoft.com/microsoft-store/)</span><span class="sxs-lookup"><span data-stu-id="4940a-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![Casilla Mostrar aplicaciones de licencias sin conexión](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="4940a-146">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="4940a-146">Figure 1.</span></span> <span data-ttu-id="4940a-147">Habilitar aplicaciones para su uso sin conexión</span><span class="sxs-lookup"><span data-stu-id="4940a-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="4940a-148">Agrega la aplicación Surface a tu cuenta de la Microsoft Store para Empresas siguiendo este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="4940a-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="4940a-149">Haz clic en **el menú** Tienda.</span><span class="sxs-lookup"><span data-stu-id="4940a-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="4940a-150">En el cuadro de búsqueda, escribe **la aplicación Surface**y, a continuación, haz clic en el icono de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4940a-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="4940a-151">Después de que la aplicación Surface se presente en los resultados de búsqueda, haz clic en el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4940a-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="4940a-152">Se le presenta una opción (seleccione **En** línea o **sin**conexión), como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="4940a-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="4940a-154">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="4940a-154">Figure 2.</span></span> <span data-ttu-id="4940a-155">Selecciona el modo de licencias sin conexión y agrega la aplicación al inventario</span><span class="sxs-lookup"><span data-stu-id="4940a-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="4940a-156">Haga clic **en Sin** conexión para seleccionar el modo de licencias sin conexión.</span><span class="sxs-lookup"><span data-stu-id="4940a-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="4940a-157">Haz **clic en Obtener la** aplicación para agregarla al inventario de la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4940a-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="4940a-158">Como se muestra en la figura 3, verás un cuadro de diálogo que te pide que reconozcas que las aplicaciones sin conexión se pueden implementar mediante una herramienta de administración o descargar desde la página de inventario de la empresa en su tienda privada.</span><span class="sxs-lookup"><span data-stu-id="4940a-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="4940a-159">Ventana de confirmación de aplicaciones con licencia sin conexión ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *figura 3. Confirmación de la aplicación con licencia sin conexión*</span><span class="sxs-lookup"><span data-stu-id="4940a-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="4940a-160">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4940a-160">Click **OK**.</span></span>

## <span data-ttu-id="4940a-161">Descargar la aplicación Surface desde una cuenta de la Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="4940a-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="4940a-162">Después de agregar una aplicación a la cuenta de la Microsoft Store para Empresas en modo sin conexión, puedes descargarla y agregarla como appxBundle a un recurso compartido de implementación.</span><span class="sxs-lookup"><span data-stu-id="4940a-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="4940a-163">Inicie sesión en la cuenta de la Microsoft Store para Empresas en https://businessstore.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="4940a-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="4940a-164">Haga **clic en Administrar >aplicaciones & software.**</span><span class="sxs-lookup"><span data-stu-id="4940a-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="4940a-165">Se muestra una lista de todas las aplicaciones de tu empresa, incluida la aplicación Surface que agregaste en la sección Agregar aplicación Surface a una cuenta de la [Microsoft Store](#add-surface-app-to-a-microsoft-store-for-business-account) para Empresas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="4940a-166">En **Acciones,** haz clic en los puntos suspensivos (**...**) y, a continuación, haz clic en Descargar para su uso **sin conexión** para la aplicación Surface.</span><span class="sxs-lookup"><span data-stu-id="4940a-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="4940a-167">Seleccione las opciones **de plataforma** **y arquitectura** deseadas de las selecciones disponibles para la aplicación seleccionada, como se muestra en la figura 4.</span><span class="sxs-lookup"><span data-stu-id="4940a-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Ejemplo del paquete AppxBundle](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="4940a-169">Figura 4.</span><span class="sxs-lookup"><span data-stu-id="4940a-169">Figure 4.</span></span> <span data-ttu-id="4940a-170">Descargar el paquete AppxBundle para una aplicación</span><span class="sxs-lookup"><span data-stu-id="4940a-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="4940a-171">Haga **clic en Descargar**.</span><span class="sxs-lookup"><span data-stu-id="4940a-171">Click **Download**.</span></span> <span data-ttu-id="4940a-172">Se descargará el paquete AppxBundle.</span><span class="sxs-lookup"><span data-stu-id="4940a-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="4940a-173">Asegúrese de tomar nota de la ruta de acceso del archivo descargado porque lo necesitará más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="4940a-174">Haga clic en **la opción de licencia codificada** o **sin** codificar.</span><span class="sxs-lookup"><span data-stu-id="4940a-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="4940a-175">Usa la opción de licencia codificada con herramientas de administración como Microsoft Endpoint Configuration Manager o cuando usas el Diseñador de configuraciones de Windows para crear un paquete de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="4940a-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="4940a-176">Selecciona la opción de licencia sin codificar cuando usas administración y mantenimiento de imágenes de implementación (DISM) o soluciones de implementación basadas en imágenes, incluido Microsoft Deployment Toolkit (MDT).</span><span class="sxs-lookup"><span data-stu-id="4940a-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="4940a-177">Haz **clic en** Generar para generar y descargar la licencia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4940a-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="4940a-178">Asegúrese de tomar nota de la ruta de acceso del archivo de licencia, ya que lo necesitará más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="4940a-179">Al descargar una aplicación para su uso sin conexión, como la aplicación Surface, es posible que observes una sección en la parte inferior de la página con la etiqueta **Marcos necesarios.**</span><span class="sxs-lookup"><span data-stu-id="4940a-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="4940a-180">Los equipos de destino deben tener los marcos instalados para que se ejecute la aplicación, por lo que es posible que deba repetir el proceso de descarga para cada uno de los marcos necesarios para la arquitectura (x86 o x64) e incluirlos también como parte de la implementación de Windows que se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="4940a-181">La figura 5 muestra los marcos necesarios para la aplicación Surface.</span><span class="sxs-lookup"><span data-stu-id="4940a-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Marcos necesarios para la aplicación Surface](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="4940a-183">Figura 5.</span><span class="sxs-lookup"><span data-stu-id="4940a-183">Figure 5.</span></span> <span data-ttu-id="4940a-184">Marcos necesarios para la aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="4940a-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="4940a-185">Los números de versión de la aplicación Surface y los marcos necesarios cambiarán a medida que se actualicen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4940a-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="4940a-186">Busca la versión más reciente de la aplicación Surface y cada marco de la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4940a-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="4940a-187">Usa siempre la aplicación Surface y las versiones de marco recomendadas según lo proporcionado por la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4940a-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="4940a-188">El uso de marcos obsoletos o las versiones incorrectas puede provocar errores o bloqueos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4940a-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="4940a-189">Para descargar los marcos necesarios para la aplicación Surface, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4940a-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="4940a-190">Haga clic **en** el botón Descargar **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="4940a-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4940a-191">Esto descarga la Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe. Archivo Appx en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="4940a-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="4940a-192">Haga clic **en** el botón **Descargar Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span><span class="sxs-lookup"><span data-stu-id="4940a-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4940a-193">Esto descarga el archivo Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx en la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="4940a-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="4940a-194">Solo se requiere la versión de 64 bits (x64) de cada marco para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="4940a-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="4940a-195">Los dispositivos Surface son dispositivos UEFI nativos de 64 bits y no son compatibles con versiones de 32 bits (x86) de Windows que requerirían marcos de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4940a-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="4940a-196">Instalar la aplicación Surface en el equipo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4940a-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="4940a-197">El siguiente procedimiento aprovisiona la aplicación Surface en el equipo y la pone a disposición de las cuentas de usuario creadas en el equipo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4940a-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="4940a-198">Mediante el procedimiento descrito en la sección Cómo descargar la aplicación Surface desde una cuenta de la [Microsoft Store](#download-surface-app-from-a-microsoft-store-for-business-account) para Empresas de este artículo, descarga la aplicación Surface AppxBundle y el archivo de licencia.</span><span class="sxs-lookup"><span data-stu-id="4940a-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4940a-199">Comienza una sesión de PowerShell con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="4940a-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="4940a-200">Si no ejecuta PowerShell como administrador, la sesión no tendrá los permisos necesarios para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4940a-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="4940a-201">En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: </span><span class="sxs-lookup"><span data-stu-id="4940a-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="4940a-202">Dónde `<DownloadPath>` está la carpeta en la que descargaste el appxBundle y el archivo de licencia de la cuenta de la Microsoft Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="4940a-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="4940a-203">Por ejemplo, si descargó los archivos en c:\Temp, el comando que ejecuta es:</span><span class="sxs-lookup"><span data-stu-id="4940a-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="4940a-204">La aplicación Surface ahora estará disponible en tu equipo Windows actual.</span><span class="sxs-lookup"><span data-stu-id="4940a-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="4940a-205">Antes de que la aplicación Surface sea funcional en el equipo donde se ha aprovisionado, también debes aprovisionar los marcos descritos anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="4940a-206">Para aprovisionar estos marcos, usa el siguiente procedimiento en la sesión de PowerShell con privilegios elevados que usste para aprovisionar la aplicación Surface.</span><span class="sxs-lookup"><span data-stu-id="4940a-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="4940a-207">En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: </span><span class="sxs-lookup"><span data-stu-id="4940a-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="4940a-208">En la sesión de PowerShell con privilegios elevados, copia y pega el siguiente comando: </span><span class="sxs-lookup"><span data-stu-id="4940a-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="4940a-209">Instalar la aplicación Surface con MDT</span><span class="sxs-lookup"><span data-stu-id="4940a-209">Install Surface app with MDT</span></span>
<span data-ttu-id="4940a-210">El siguiente procedimiento usa MDT para automatizar la instalación de la aplicación Surface en el momento de la implementación.</span><span class="sxs-lookup"><span data-stu-id="4940a-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="4940a-211">MDT aprovisiona la aplicación automáticamente durante la implementación y, por lo tanto, puedes usar este proceso con las imágenes existentes.</span><span class="sxs-lookup"><span data-stu-id="4940a-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="4940a-212">Este es el proceso recomendado para implementar la aplicación Surface como parte de una implementación de Windows en dispositivos Surface porque no reduce la compatibilidad entre plataformas de la imagen de Windows.</span><span class="sxs-lookup"><span data-stu-id="4940a-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="4940a-213">Mediante el procedimiento descrito [anteriormente en este artículo,](#download-surface-app-from-a-microsoft-store-for-business-account)descarga la aplicación Surface AppxBundle y el archivo de licencia.</span><span class="sxs-lookup"><span data-stu-id="4940a-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4940a-214">Con el Asistente para nueva aplicación en MDT Deployment Workbench, importa los archivos descargados como una nueva **aplicación con archivos de origen.**</span><span class="sxs-lookup"><span data-stu-id="4940a-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4940a-215">En la **página Detalles del** comando del \*\*\*\* Asistente para nueva \*\*\*\* aplicación, especifique el directorio de trabajo predeterminado y, para el comando, especifique el nombre de archivo de AppxBundle, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="4940a-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="4940a-216">Comando:</span><span class="sxs-lookup"><span data-stu-id="4940a-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="4940a-217">Directorio de trabajo: %DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="4940a-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="4940a-218">Para que la aplicación Surface funcione en el equipo de destino, también requerirá los marcos descritos anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4940a-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="4940a-219">Usa el siguiente procedimiento para importar los marcos necesarios para la aplicación Surface en MDT y configurarlos como dependencias.</span><span class="sxs-lookup"><span data-stu-id="4940a-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="4940a-220">Mediante el procedimiento descrito anteriormente en este artículo, descargue los archivos de marco.</span><span class="sxs-lookup"><span data-stu-id="4940a-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="4940a-221">Almacena cada marco en una carpeta independiente.</span><span class="sxs-lookup"><span data-stu-id="4940a-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="4940a-222">Con el Asistente para nueva aplicación en MDT Deployment Workbench, importa los archivos descargados como una nueva **aplicación con archivos de origen.**</span><span class="sxs-lookup"><span data-stu-id="4940a-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4940a-223">En la **página Detalles del** comando, escriba el nombre \*\*\*\* de archivo de cada aplicación que descargó en el campo Comando y en el directorio de trabajo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4940a-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="4940a-224">Para configurar los marcos como dependencias de la aplicación Surface, usa este proceso:</span><span class="sxs-lookup"><span data-stu-id="4940a-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="4940a-225">Abre las propiedades de la aplicación Surface en MDT Deployment Workbench.</span><span class="sxs-lookup"><span data-stu-id="4940a-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4940a-226">Haga clic en **la pestaña** Dependencias y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4940a-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="4940a-227">Active la casilla de cada marco con el nombre que proporcionó en el Asistente para nuevas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4940a-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="4940a-228">Después de la importación, la aplicación Surface estará disponible para su selección en el paso **Aplicaciones** del Asistente para la implementación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4940a-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="4940a-229">Para instalar la aplicación automáticamente, también puedes especificar la aplicación en la secuencia de tareas de implementación siguiendo este proceso:</span><span class="sxs-lookup"><span data-stu-id="4940a-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="4940a-230">Abre la secuencia de tareas de implementación en Deployment Workbench de MDT.</span><span class="sxs-lookup"><span data-stu-id="4940a-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4940a-231">Agrega una nueva tarea **Instalar aplicación** en la sección **Restaurar estado** de la implementación.</span><span class="sxs-lookup"><span data-stu-id="4940a-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="4940a-232">Selecciona **Instalar una sola aplicación y** especifica la aplicación **Surface** como la aplicación que **se instalará.**</span><span class="sxs-lookup"><span data-stu-id="4940a-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="4940a-233">Para obtener más información sobre cómo incluir aplicaciones en las implementaciones de Windows, consulta [Implementar Windows 10 con Microsoft Deployment Toolkit.](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)</span><span class="sxs-lookup"><span data-stu-id="4940a-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

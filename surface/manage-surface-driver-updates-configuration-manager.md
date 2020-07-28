---
title: Administrar actualizaciones de controladores de Surface en Configuration Manager
description: En este artículo, se describen las opciones disponibles para administrar e implementar actualizaciones de firmware y controladores para dispositivos Surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, actualización, dispositivo, administrar, implementar, controlador, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: be32309b26ff6a873c36927cc39595022c4dbb90
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897078"
---
# <span data-ttu-id="6edb9-104">Administrar actualizaciones de controladores de Surface en Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6edb9-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="6edb9-105">Resumen</span><span class="sxs-lookup"><span data-stu-id="6edb9-105">Summary</span></span>

<span data-ttu-id="6edb9-106">A partir de [Microsoft System Center Configuration Manager versión 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), puede sincronizar e implementar actualizaciones de controladores y firmware de Microsoft Surface directamente a través del cliente de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6edb9-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="6edb9-107">El proceso es similar al de implementar actualizaciones regulares.</span><span class="sxs-lookup"><span data-stu-id="6edb9-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="6edb9-108">Sin embargo, para obtener las actualizaciones de los drivers de Surface en tu catálogo, necesitarás otras configuraciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="6edb9-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="6edb9-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6edb9-109">Prerequisites</span></span>

<span data-ttu-id="6edb9-110">Para administrar las actualizaciones de los controladores de Surface, se deben cumplir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="6edb9-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6edb9-111">Debe usar Configuration Manager versión 1710 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6edb9-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="6edb9-112">Todos los puntos de actualización de software (SUPs) deben ejecutar Windows Server 2016 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6edb9-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="6edb9-113">De lo contrario, el administrador de configuración ignora esta configuración y los controladores de superficie no se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="6edb9-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="6edb9-114">Si su entorno no cumple con los requisitos previos, consulte los [métodos alternativos](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) para implementar el controlador de superficie y las actualizaciones de firmware en la sección [preguntas más frecuentes](#frequently-asked-questions-faq) .</span><span class="sxs-lookup"><span data-stu-id="6edb9-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="6edb9-115">Archivos de registro útiles</span><span class="sxs-lookup"><span data-stu-id="6edb9-115">Useful log files</span></span>

<span data-ttu-id="6edb9-116">Los siguientes registros son especialmente útiles cuando se administran las actualizaciones de los controladores de Surface.</span><span class="sxs-lookup"><span data-stu-id="6edb9-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="6edb9-117">Nombre de registro</span><span class="sxs-lookup"><span data-stu-id="6edb9-117">Log name</span></span>|<span data-ttu-id="6edb9-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="6edb9-118">Description</span></span>|
|---|---|
|<span data-ttu-id="6edb9-119">WCM. log</span><span class="sxs-lookup"><span data-stu-id="6edb9-119">WCM.log</span></span>|<span data-ttu-id="6edb9-120">Registra detalles sobre la configuración del punto de actualización de software y las conexiones con el servidor WSUS para las categorías, clasificaciones e idiomas de las actualizaciones suscritas.</span><span class="sxs-lookup"><span data-stu-id="6edb9-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="6edb9-121">WsyncMgr. log</span><span class="sxs-lookup"><span data-stu-id="6edb9-121">WsyncMgr.log</span></span>|<span data-ttu-id="6edb9-122">Registra detalles sobre el proceso de sincronización de las actualizaciones de software.</span><span class="sxs-lookup"><span data-stu-id="6edb9-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="6edb9-123">Estos registros se encuentran en el servidor del sitio que administra el SUP o en el SUP si se instala directamente en un servidor de sitio.</span><span class="sxs-lookup"><span data-stu-id="6edb9-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="6edb9-124">Para obtener una lista completa de los registros de Configuration Manager, consulte [archivos de registro en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span><span class="sxs-lookup"><span data-stu-id="6edb9-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="6edb9-125">Habilitar la administración de actualizaciones del controlador de Surface</span><span class="sxs-lookup"><span data-stu-id="6edb9-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="6edb9-126">Para habilitar la administración de las actualizaciones del controlador de Surface en Configuration Manager, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6edb9-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="6edb9-127">En la consola del administrador de configuración, **Administration**vaya a la  >  **información general**de administración sitios de  >  **configuración del sitio**  >  **Sites**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="6edb9-128">Seleccione el sitio que contiene el servidor SUP de nivel superior de su entorno.</span><span class="sxs-lookup"><span data-stu-id="6edb9-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="6edb9-129">En la cinta de opciones, seleccione **Configurar componentes del sitio**y, a continuación, seleccione **punto de actualización de software**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="6edb9-130">O bien, haga clic con el botón secundario en el sitio y seleccione **Configurar componentes de sitio**  >  **punto de actualización de software**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="6edb9-131">En la pestaña **clasificaciones** , active la casilla **incluir actualizaciones de firmware y controladores de Surface de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="6edb9-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![Propiedades de componente de punto de actualización de software](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="6edb9-133">Cuando se le solicite en el siguiente mensaje de advertencia, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="6edb9-135">En la pestaña productos, seleccione los productos que desea actualizar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="6edb9-136">La mayoría de los drivers pertenecen a los siguientes grupos de productos:</span><span class="sxs-lookup"><span data-stu-id="6edb9-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="6edb9-137">Controladores de la versión de Windows 10 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6edb9-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="6edb9-138">Windows 10 y actualización posterior & controladores de servicio</span><span class="sxs-lookup"><span data-stu-id="6edb9-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-139">Actualización de aniversario de Windows 10 y drivers de mantenimiento posterior</span><span class="sxs-lookup"><span data-stu-id="6edb9-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-140">Actualización de aniversario de Windows 10 y actualización posterior & controladores de servicio</span><span class="sxs-lookup"><span data-stu-id="6edb9-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-141">Windows 10 Creators Update y versiones posteriores de servicios de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="6edb9-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-142">Windows 10 Creators Update y posterior actualiza & controladores de servicio</span><span class="sxs-lookup"><span data-stu-id="6edb9-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-143">Controladores de mantenimiento de Windows 10 Fall Creators Update y posteriores</span><span class="sxs-lookup"><span data-stu-id="6edb9-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-144">Windows 10 Fall Creators Update y actualización posterior & drivers de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="6edb9-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-145">Controladores de mantenimiento de Windows 10 S y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6edb9-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="6edb9-146">Windows 10 S versión 1709 y posteriores que atienden los drivers para pruebas</span><span class="sxs-lookup"><span data-stu-id="6edb9-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="6edb9-147">Windows 10 S versión 1709 y posteriores actualizar & de mantenimiento de controladores para pruebas</span><span class="sxs-lookup"><span data-stu-id="6edb9-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="6edb9-148">La mayoría de los drivers de Surface pertenecen a varios grupos de producto de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6edb9-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="6edb9-149">Es posible que no tenga que seleccionar todos los productos que se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="6edb9-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="6edb9-150">Para ayudar a reducir el número de productos que rellenan el catálogo de actualizaciones, le recomendamos que seleccione solo los productos que necesita su entorno para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="6edb9-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="6edb9-151">Comprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="6edb9-151">Verifying the configuration</span></span>

<span data-ttu-id="6edb9-152">Para comprobar que el SUP está configurado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6edb9-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="6edb9-153">Abra WsyncMgr. log y busque la siguiente entrada:</span><span class="sxs-lookup"><span data-stu-id="6edb9-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="6edb9-154">Si se ha registrado una de las siguientes entradas en WsyncMgr. log, volver a comprobar el paso 4 de la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="6edb9-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="6edb9-155">Abra WCM. log y busque una entrada similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6edb9-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![Configuración de WCM. log](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="6edb9-157">Esta entrada es un elemento XML en el que se muestra una lista de todos los grupos de productos y la clasificación sincronizada actualmente por el servidor SUP.</span><span class="sxs-lookup"><span data-stu-id="6edb9-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="6edb9-158">Por ejemplo, es posible que vea una entrada similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6edb9-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="6edb9-159">Si no encuentra los productos que seleccionó en el paso 6 de la sección anterior, verifique si la configuración de SUP está guardada.</span><span class="sxs-lookup"><span data-stu-id="6edb9-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="6edb9-160">También puede esperar hasta que finalice la sincronización siguiente y, después, comprobar si las actualizaciones del controlador de superficie y del firmware se enumeran en actualizaciones de software en la consola de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6edb9-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="6edb9-161">Por ejemplo, la consola podría mostrar la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="6edb9-161">For example, the console might display the following information.</span></span>

   ![Todos los resultados de búsqueda de actualizaciones de software](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="6edb9-163">Sincronización manual</span><span class="sxs-lookup"><span data-stu-id="6edb9-163">Manual synchronization</span></span>

<span data-ttu-id="6edb9-164">Si no desea esperar hasta la siguiente sincronización, siga estos pasos para iniciar una sincronización:</span><span class="sxs-lookup"><span data-stu-id="6edb9-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="6edb9-165">En la consola del administrador de configuración, vaya al software de Descripción general de la **biblioteca de software**para  >  **Overview**  >  **Actualizar**  >  **todas las actualizaciones de software**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="6edb9-166">En la cinta de opciones, seleccione **sincronizar actualizaciones de software**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="6edb9-167">O bien, haga clic con el botón secundario en **todas las actualizaciones de software**y seleccione **sincronizar actualización de software**.</span><span class="sxs-lookup"><span data-stu-id="6edb9-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="6edb9-168">Busque las siguientes entradas en WsyncMgr. log para supervisar el progreso de la sincronización:</span><span class="sxs-lookup"><span data-stu-id="6edb9-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <span data-ttu-id="6edb9-169">Implementación de actualizaciones de controladores y firmware de superficie</span><span class="sxs-lookup"><span data-stu-id="6edb9-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="6edb9-170">Puede implementar el firmware de superficie y las actualizaciones de drivers de la misma manera en que implementa otras actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="6edb9-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="6edb9-171">Para obtener más información sobre la implementación, consulte [System Center 2012 Configuration Manager-Part7: actualizaciones de software (implementación)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span><span class="sxs-lookup"><span data-stu-id="6edb9-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="6edb9-172">Preguntas frecuentes (FAQ)</span><span class="sxs-lookup"><span data-stu-id="6edb9-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="6edb9-173">Después de seguir los pasos descritos en este artículo, los drivers de Surface aún no se sincronizan.</span><span class="sxs-lookup"><span data-stu-id="6edb9-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="6edb9-174">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="6edb9-174">Why?</span></span>**

<span data-ttu-id="6edb9-175">Si sincroniza desde un servidor Windows Server Update Services (WSUS) que precede en la cadena, en lugar de Microsoft Update, asegúrese de que el servidor WSUS que precede en la cadena está configurado para admitir y sincronizar las actualizaciones del controlador de la superficie.</span><span class="sxs-lookup"><span data-stu-id="6edb9-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="6edb9-176">Todos los servidores descendentes se limitan a las actualizaciones que están presentes en la base de datos del servidor WSUS que precede en la cadena.</span><span class="sxs-lookup"><span data-stu-id="6edb9-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="6edb9-177">Hay más de 68.000 actualizaciones que se clasifican como controladores en WSUS.</span><span class="sxs-lookup"><span data-stu-id="6edb9-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="6edb9-178">Para evitar que los controladores no relacionados con la superficie se sincronicen con Configuration Manager, Microsoft filtra la sincronización de controlador contra una lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="6edb9-179">Después de publicar e incorporar la nueva lista de permitidos en Configuration Manager, los nuevos drivers se agregarán a la consola después de la siguiente sincronización.</span><span class="sxs-lookup"><span data-stu-id="6edb9-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="6edb9-180">Microsoft tiene como objetivo obtener los impulsores de superficie agregados a la lista de permitidos cada mes de forma alineada con los lanzamientos de actualizaciones mensuales para que estén disponibles para la sincronización con Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6edb9-180">Microsoft aims to get the Surface drivers added to the allow list each month in alignment with monthly update releases to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="6edb9-181">Si su entorno de Configuration Manager está desconectado, se importará una nueva lista de permitidos cada vez que importe [actualizaciones de servicio](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) a Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6edb9-181">If your Configuration Manager environment is offline, a new allow list is imported every time that you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="6edb9-182">También tendrá que importar un [nuevo catálogo de WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contenga los drivers antes de que se muestren las actualizaciones en la consola de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="6edb9-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="6edb9-183">Como un entorno WSUS independiente contiene más drivers que un SUP de Configuration Manager, le recomendamos que establezca un entorno de Configuration Manager que tenga capacidades en línea y que lo configure para sincronizar los impulsores de la superficie.</span><span class="sxs-lookup"><span data-stu-id="6edb9-183">Because a standalone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="6edb9-184">Esto proporciona una exportación de WSUS más pequeña, muy similar al entorno sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6edb9-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="6edb9-185">Si su entorno de Configuration Manager está en línea y puede detectar nuevas actualizaciones, recibirá actualizaciones en la lista automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6edb9-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="6edb9-186">Si no ve los drivers esperados, revise los archivos WCM. log y WsyncMgr. log en busca de errores de sincronización.</span><span class="sxs-lookup"><span data-stu-id="6edb9-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log files for any synchronization failures.</span></span>

**<span data-ttu-id="6edb9-187">Mi entorno de Configuration Manager está desconectado.</span><span class="sxs-lookup"><span data-stu-id="6edb9-187">My Configuration Manager environment is offline.</span></span> <span data-ttu-id="6edb9-188">¿Puedo importar manualmente los drivers de Surface en WSUS?</span><span class="sxs-lookup"><span data-stu-id="6edb9-188">Can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="6edb9-189">No.</span><span class="sxs-lookup"><span data-stu-id="6edb9-189">No.</span></span> <span data-ttu-id="6edb9-190">Incluso si la actualización se importa a WSUS, la actualización no se importará a la consola de Configuration Manager para su implementación si no aparece en la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-190">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="6edb9-191">Debe usar la [herramienta de conexión de servicio](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para importar las actualizaciones de servicio a Configuration Manager para actualizar la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="6edb9-191">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="6edb9-192">¿Qué métodos alternativos tengo para implementar actualizaciones de drivers y firmware de Surface?</span><span class="sxs-lookup"><span data-stu-id="6edb9-192">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="6edb9-193">Para obtener información sobre cómo implementar actualizaciones de drivers y firmware de Surface a través de canales alternativos, consulte [Manage Surface Driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span><span class="sxs-lookup"><span data-stu-id="6edb9-193">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="6edb9-194">Si desea descargar el archivo. msi o. exe y, a continuación, implementar a través de los canales de implementación de software tradicionales, consulte [mantener actualizado el firmware de la superficie con Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="6edb9-194">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="6edb9-195">Información adicional</span><span class="sxs-lookup"><span data-stu-id="6edb9-195">Additional Information</span></span>

<span data-ttu-id="6edb9-196">Para obtener más información sobre el controlador de superficie y las actualizaciones de firmware, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6edb9-196">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="6edb9-197">Administrar las actualizaciones de controladores y firmware de Surface</span><span class="sxs-lookup"><span data-stu-id="6edb9-197">Manage Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)
- [<span data-ttu-id="6edb9-198">Consideraciones para Surface y System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6edb9-198">Considerations for Surface and System Center Configuration Manager</span></span>](considerations-for-surface-and-system-center-configuration-manager.md)

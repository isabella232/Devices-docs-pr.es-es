---
title: Implementar la calidad de servicio en Surface Hub
ms.reviewer: ''
manager: laurawi
description: Más información sobre cómo configurar QoS en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835193"
---
# <span data-ttu-id="48ee2-103">Implementar calidad de servicio (QoS) en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="48ee2-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="48ee2-104">Calidad de servicio (QoS) es una combinación de tecnologías de red que permite a los administradores optimizar la experiencia de las comunicaciones de audio, vídeo y uso compartido de aplicaciones en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="48ee2-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="48ee2-105">La configuración [de QoS para Skype empresarial](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) en Surface Hub se puede realizar con el [proveedor de administración de dispositivos móviles (MDM)](manage-settings-with-mdm-for-surface-hub.md) o a través de un [paquete de aprovisionamiento](provisioning-packages-for-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="48ee2-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="48ee2-106">Este procedimiento explica cómo configurar QoS para Surface Hub con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="48ee2-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="48ee2-107">En Intune, [cree una directiva personalizada](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="48ee2-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Captura de pantalla del cuadro de diálogo de creación de directiva personalizada en Intune](images/qos-create.png)

2. <span data-ttu-id="48ee2-109">En **Configuración personalizada de OMA-URI**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="48ee2-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="48ee2-110">Para cada configuración que agregue, tendrá que escribir un nombre, una descripción (opcional), un tipo de datos, OMA-URI y valor.</span><span class="sxs-lookup"><span data-stu-id="48ee2-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![Captura de pantalla de un cuadro de diálogo Configuración OMA-URI en blanco](images/qos-setting.png)

3. <span data-ttu-id="48ee2-112">Agregue la siguiente configuración personalizada de OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="48ee2-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="48ee2-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="48ee2-113">Name</span></span> | <span data-ttu-id="48ee2-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="48ee2-114">Data type</span></span> | <span data-ttu-id="48ee2-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="48ee2-115">OMA-URI</span></span><br><span data-ttu-id="48ee2-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="48ee2-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="48ee2-117">Valor</span><span class="sxs-lookup"><span data-stu-id="48ee2-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="48ee2-118">Puerto de origen de audio</span><span class="sxs-lookup"><span data-stu-id="48ee2-118">Audio Source Port</span></span> | <span data-ttu-id="48ee2-119">Cadena</span><span class="sxs-lookup"><span data-stu-id="48ee2-119">String</span></span> |  <span data-ttu-id="48ee2-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="48ee2-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="48ee2-121">Obtén los valores de tu Administrador de Skype</span><span class="sxs-lookup"><span data-stu-id="48ee2-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="48ee2-122">DSCP de audio</span><span class="sxs-lookup"><span data-stu-id="48ee2-122">Audio DSCP</span></span> | <span data-ttu-id="48ee2-123">Integer</span><span class="sxs-lookup"><span data-stu-id="48ee2-123">Integer</span></span> |  <span data-ttu-id="48ee2-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="48ee2-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="48ee2-125">46</span><span class="sxs-lookup"><span data-stu-id="48ee2-125">46</span></span>
    <span data-ttu-id="48ee2-126">Puerto de origen de video</span><span class="sxs-lookup"><span data-stu-id="48ee2-126">Video Source Port</span></span> | <span data-ttu-id="48ee2-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="48ee2-127">String</span></span> |  <span data-ttu-id="48ee2-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="48ee2-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="48ee2-129">Obtén los valores de tu Administrador de Skype</span><span class="sxs-lookup"><span data-stu-id="48ee2-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="48ee2-130">DSCP de vídeo</span><span class="sxs-lookup"><span data-stu-id="48ee2-130">Video DSCP</span></span> | <span data-ttu-id="48ee2-131">Integer</span><span class="sxs-lookup"><span data-stu-id="48ee2-131">Integer</span></span> |  <span data-ttu-id="48ee2-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="48ee2-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="48ee2-133">34</span><span class="sxs-lookup"><span data-stu-id="48ee2-133">34</span></span>
    <span data-ttu-id="48ee2-134">Nombre del proceso de audio</span><span class="sxs-lookup"><span data-stu-id="48ee2-134">Audio Process Name</span></span> | <span data-ttu-id="48ee2-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="48ee2-135">String</span></span> |  <span data-ttu-id="48ee2-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="48ee2-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="48ee2-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="48ee2-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="48ee2-138">Nombre del proceso de vídeo</span><span class="sxs-lookup"><span data-stu-id="48ee2-138">Video Process Name</span></span> | <span data-ttu-id="48ee2-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="48ee2-139">String</span></span> |  <span data-ttu-id="48ee2-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="48ee2-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="48ee2-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="48ee2-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="48ee2-142">Cada ruta **OMA-URI** comienza por `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="48ee2-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="48ee2-143">La ruta de acceso completa de la configuración del puerto de origen de audio, por ejemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="48ee2-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="48ee2-144">Cuando se haya creado la Directiva, [impleméntela en Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="48ee2-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="48ee2-145">Por el momento, no puede configurar la opción de configuración **IPProtocolMatchCondition** en el [CSP de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="48ee2-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="48ee2-146">Si esta configuración está configurada, la Directiva no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="48ee2-146">If this setting is configured, the policy will fail to apply.</span></span>
 

---
title: Implementar la calidad de servicio en Surface Hub
ms.reviewer: ''
manager: laurawi
description: Aprende a configurar QoS en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470488"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="2ad9c-103">Implementar calidad de servicio (QoS) en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2ad9c-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="2ad9c-104">Calidad de servicio (QoS) es una combinación de tecnologías de red que permite a los administradores optimizar la experiencia de comunicaciones de uso compartido de aplicaciones y audio en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="2ad9c-105">La configuración [de QoS para Skype Empresarial](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) en Surface Hub se puede realizar con el proveedor de administración de dispositivos móviles [(MDM)](manage-settings-with-mdm-for-surface-hub.md) o a través de un paquete [de aprovisionamiento.](provisioning-packages-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="2ad9c-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="2ad9c-106">En este procedimiento se explica cómo configurar QoS para Surface Hub con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="2ad9c-107">En Intune, [cree una directiva personalizada](https://docs.microsoft.com/intune/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="2ad9c-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla del cuadro de diálogo de creación de directivas personalizadas en Intune](images/qos-create.png)

2. <span data-ttu-id="2ad9c-109">En **Configuración personalizada de OMA-URI,** seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="2ad9c-110">Para cada configuración que agregue, escribirá un nombre, una descripción (opcional), un tipo de datos, OMA-URI y un valor.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de un cuadro de diálogo de configuración de OMA-URI en blanco](images/qos-setting.png)

3. <span data-ttu-id="2ad9c-112">Agregue la siguiente configuración de OMA-URI personalizada:</span><span class="sxs-lookup"><span data-stu-id="2ad9c-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="2ad9c-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="2ad9c-113">Name</span></span> | <span data-ttu-id="2ad9c-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2ad9c-114">Data type</span></span> | <span data-ttu-id="2ad9c-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="2ad9c-115">OMA-URI</span></span><br><span data-ttu-id="2ad9c-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="2ad9c-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="2ad9c-117">Valor</span><span class="sxs-lookup"><span data-stu-id="2ad9c-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="2ad9c-118">Puerto de origen de audio</span><span class="sxs-lookup"><span data-stu-id="2ad9c-118">Audio Source Port</span></span> | <span data-ttu-id="2ad9c-119">Cadena</span><span class="sxs-lookup"><span data-stu-id="2ad9c-119">String</span></span> |  <span data-ttu-id="2ad9c-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="2ad9c-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="2ad9c-121">Obtener los valores del administrador de Skype</span><span class="sxs-lookup"><span data-stu-id="2ad9c-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="2ad9c-122">DSCP de audio</span><span class="sxs-lookup"><span data-stu-id="2ad9c-122">Audio DSCP</span></span> | <span data-ttu-id="2ad9c-123">Integer</span><span class="sxs-lookup"><span data-stu-id="2ad9c-123">Integer</span></span> |  <span data-ttu-id="2ad9c-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="2ad9c-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="2ad9c-125">46</span><span class="sxs-lookup"><span data-stu-id="2ad9c-125">46</span></span>
    <span data-ttu-id="2ad9c-126">Puerto de origen de vídeo</span><span class="sxs-lookup"><span data-stu-id="2ad9c-126">Video Source Port</span></span> | <span data-ttu-id="2ad9c-127">Cadena</span><span class="sxs-lookup"><span data-stu-id="2ad9c-127">String</span></span> |  <span data-ttu-id="2ad9c-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="2ad9c-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="2ad9c-129">Obtener los valores del administrador de Skype</span><span class="sxs-lookup"><span data-stu-id="2ad9c-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="2ad9c-130">DSCP de vídeo</span><span class="sxs-lookup"><span data-stu-id="2ad9c-130">Video DSCP</span></span> | <span data-ttu-id="2ad9c-131">Integer</span><span class="sxs-lookup"><span data-stu-id="2ad9c-131">Integer</span></span> |  <span data-ttu-id="2ad9c-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="2ad9c-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="2ad9c-133">34</span><span class="sxs-lookup"><span data-stu-id="2ad9c-133">34</span></span>
    <span data-ttu-id="2ad9c-134">Nombre del proceso de audio</span><span class="sxs-lookup"><span data-stu-id="2ad9c-134">Audio Process Name</span></span> | <span data-ttu-id="2ad9c-135">Cadena</span><span class="sxs-lookup"><span data-stu-id="2ad9c-135">String</span></span> |  <span data-ttu-id="2ad9c-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="2ad9c-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="2ad9c-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="2ad9c-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="2ad9c-138">Nombre del proceso de vídeo</span><span class="sxs-lookup"><span data-stu-id="2ad9c-138">Video Process Name</span></span> | <span data-ttu-id="2ad9c-139">Cadena</span><span class="sxs-lookup"><span data-stu-id="2ad9c-139">String</span></span> |  <span data-ttu-id="2ad9c-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="2ad9c-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="2ad9c-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="2ad9c-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="2ad9c-142">Cada **ruta de acceso de OMA-URI** comienza por `./Device/Vendor/MSFT/NetworkQoSPolicy` .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="2ad9c-143">La ruta de acceso completa para la configuración del puerto de origen de audio, por ejemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .</span><span class="sxs-lookup"><span data-stu-id="2ad9c-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="2ad9c-144">Cuando se haya creado la directiva, impleméntela en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="2ad9c-145">Actualmente, no puede configurar la **configuración IPProtocolMatchCondition** en [networkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span><span class="sxs-lookup"><span data-stu-id="2ad9c-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="2ad9c-146">Si esta configuración está configurada, la directiva no se aplicará.</span><span class="sxs-lookup"><span data-stu-id="2ad9c-146">If this setting is configured, the policy will fail to apply.</span></span>
 

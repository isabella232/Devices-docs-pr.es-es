---
title: Novedades en Windows 10, versión 1703 para Surface Hub
description: Windows 10, versión 1703 (Creators Update) ofrece nuevas características a Microsoft Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: bdc6e384839606fe6138c75e190d68a84679f5b4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834897"
---
# <span data-ttu-id="ea834-103">¿Qué novedades hay en Windows 10, versión 1703 para Microsoft Surface Hub?</span><span class="sxs-lookup"><span data-stu-id="ea834-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="ea834-104">Mira al ingeniero de Surface Hub, Jordan Marchese, presentar las actualizaciones de Microsoft Surface Hub con Windows 10, versión 1703 (Windows 10 Creators Update).</span><span class="sxs-lookup"><span data-stu-id="ea834-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="ea834-105">Windows 10, versión 1703 (también denominada Creators Update), presenta los siguientes cambios para Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ea834-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="ea834-106">Nueva configuración</span><span class="sxs-lookup"><span data-stu-id="ea834-106">New settings</span></span>

<span data-ttu-id="ea834-107">Se ha agregado configuración para la administración de dispositivos móviles (MDM) y los proveedores de servicios de configuración (CSP) para ampliar las capacidades de administración de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ea834-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="ea834-108">[La configuración incluye](manage-settings-with-mdm-for-surface-hub.md):</span><span class="sxs-lookup"><span data-stu-id="ea834-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="ea834-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="ea834-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="ea834-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="ea834-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="ea834-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="ea834-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="ea834-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="ea834-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="ea834-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="ea834-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="ea834-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="ea834-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="ea834-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="ea834-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="ea834-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="ea834-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="ea834-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="ea834-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="ea834-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="ea834-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="ea834-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="ea834-119">System/AllowStorageCard</span></span>

<span data-ttu-id="ea834-120">Además de la configuración basada en el nuevo [CSP de NetworkQoSPolicy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) y [CSP de NetworkProxy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span><span class="sxs-lookup"><span data-stu-id="ea834-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="ea834-121">Asistente de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="ea834-121">Provisioning wizard</span></span>

<span data-ttu-id="ea834-122">Un asistente fácil de usar que ayuda a crear rápidamente paquetes de aprovisionamiento que se pueden aplicar a varios dispositivos Surface Hub e incluye la unión en bloque a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ea834-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="ea834-123">Obtén información sobre cómo crear un paquete de aprovisionamiento para Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="ea834-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![pasos del asistente para aprovisionamiento de dispositivos Surface Hub](images/wcd-wizard.png)
    
## <span data-ttu-id="ea834-125">Miracast en la red inalámbrica o LAN existente</span><span class="sxs-lookup"><span data-stu-id="ea834-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="ea834-126">Microsoft ha ampliado la capacidad de [enviar una emisión de Miracast a través de una red local](miracast-over-infrastructure.md), en lugar de a través de un vínculo directo inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="ea834-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="ea834-127">Recuperación en la nube</span><span class="sxs-lookup"><span data-stu-id="ea834-127">Cloud recovery</span></span>

<span data-ttu-id="ea834-128">Cuando se restablece un dispositivo Surface Hub, ahora tienes la capacidad de descargar de la nube una compilación de fábrica del sistema operativo e instalarla.</span><span class="sxs-lookup"><span data-stu-id="ea834-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="ea834-129">Más información sobre la recuperación en la nube.</span><span class="sxs-lookup"><span data-stu-id="ea834-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="ea834-130">La recuperación en la nube no funciona si usas servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="ea834-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![Reinstalar](images/reinstall.png)
    
## <span data-ttu-id="ea834-132">Finalizar sesión</span><span class="sxs-lookup"><span data-stu-id="ea834-132">End session</span></span>

<span data-ttu-id="ea834-133">**He terminado** es ahora **Finalizar sesión**.</span><span class="sxs-lookup"><span data-stu-id="ea834-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="ea834-134">Aprende a usar Finalizar sesión.</span><span class="sxs-lookup"><span data-stu-id="ea834-134">Learn how to use End session.</span></span>](i-am-done-finishing-your-surface-hub-meeting.md) 

![finalizar sesión](images/end-session.png)



 

 

---
title: Cómo usar la recuperación en la nube para BitLocker en un Surface Hub
description: Cómo usar la recuperación en la nube para BitLocker en un Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Configuración de accesibilidad, aplicación Configuración, Accesibilidad
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834873"
---
# <span data-ttu-id="a2ee0-104">Resumen</span><span class="sxs-lookup"><span data-stu-id="a2ee0-104">Summary</span></span>

<span data-ttu-id="a2ee0-105">En este artículo se describe cómo usar la función de recuperación de la nube si se lo solicita inesperadamente mediante BitLocker en un dispositivo Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="a2ee0-106">Debe seguir estos pasos solo si no está disponible una clave de recuperación de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="a2ee0-107">Este proceso de recuperación elimina el contenido de la unidad interna.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="a2ee0-108">Si se produce un error en el proceso, la unidad interna quedará totalmente inutilizable.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="a2ee0-109">Si esto sucede, tendrá que registrar una solicitud de servicio con Microsoft para obtener una solución.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="a2ee0-110">Una vez completado el proceso de recuperación, el dispositivo se restablecerá a la configuración de fábrica y se devolverá al estado de la misma.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="a2ee0-111">Después de la recuperación, el Surface Hub debe reconfigurarse por completo.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2ee0-112">Este proceso requiere una conexión a Internet abierta que no use un proxy u otro método de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="a2ee0-113">Proceso de recuperación en la nube</span><span class="sxs-lookup"><span data-stu-id="a2ee0-113">Cloud recovery process</span></span>

<span data-ttu-id="a2ee0-114">Para realizar una recuperación en la nube, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a2ee0-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="a2ee0-115">Seleccione **ESC para ver más opciones de recuperación**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-115">Select **Press Esc for more recovery options**.</span></span>

   ![Captura de pantalla de escape](images/01-escape.png)

1. <span data-ttu-id="a2ee0-117">Seleccione **omitir esta unidad**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-117">Select **Skip this drive**.</span></span>

   ![Captura de pantalla de omitir esta unidad](images/02-skip-this-drive.png)

1. <span data-ttu-id="a2ee0-119">Seleccione **recuperar en la nube**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-119">Select **Recover from the cloud**.</span></span>

   ![Captura de pantalla de la recuperación desde la nube](images/03-recover-from-cloud.png)

1. <span data-ttu-id="a2ee0-121">Seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-121">Select **Yes**.</span></span>

   ![Captura de pantalla de sí](images/04-yes.png)

1. <span data-ttu-id="a2ee0-123">Seleccione **reinstalar**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-123">Select **Reinstall**.</span></span>

   ![Captura de pantalla de reinstalar](images/05a-reinstall.png)

   ![Captura de pantalla de la descarga](images/05b-downloading.png)

1. <span data-ttu-id="a2ee0-126">Una vez completado el proceso **de recuperación de**la nube, inicie la reconfiguración con la configuración rápida.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![Captura de pantalla de fuera del cuadro](images/06-out-of-box.png)

## <span data-ttu-id="a2ee0-128">Mensaje de error "se ha encontrado un error"</span><span class="sxs-lookup"><span data-stu-id="a2ee0-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="a2ee0-129">Este error suele deberse a problemas de red que se producen durante la descarga de la recuperación.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="a2ee0-130">Cuando se produzca este problema, no desactive el concentrador porque no podrá reiniciarlo.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="a2ee0-131">Si recibe este mensaje de error, vuelva al paso "recuperar desde la nube" y, a continuación, reinicie el proceso de recuperación.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="a2ee0-132">Seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-132">Select **Cancel**.</span></span>

   ![Captura de pantalla de cancelar](images/07-cancel.png)

1. <span data-ttu-id="a2ee0-134">Seleccione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-134">Select **Troubleshoot**.</span></span>

   ![Captura de pantalla de solución de problemas](images/08-troubleshoot.png)

1. <span data-ttu-id="a2ee0-136">Seleccione **recuperar en la nube**.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-136">Select **Recover from the cloud**.</span></span>

   ![Captura de pantalla de la recuperación desde la nube](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="a2ee0-138">Si se produce un error de **no se encontró la red cableada** , seleccione **Cancelar**y, a continuación, deje que Surface Hub vuelva a descubrir la red cableada.</span><span class="sxs-lookup"><span data-stu-id="a2ee0-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![Captura de pantalla de red cableada no encontrada](images/10-cancel.png)
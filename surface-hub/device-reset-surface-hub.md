---
title: Restablecer o recuperar Surface Hub
description: Describe los procesos de restablecimiento y recuperación para Surface Hub, y proporciona instrucciones.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: restablecer Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104822"
---
# <span data-ttu-id="fa618-104">Restablecer o recuperar Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa618-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="fa618-105">En este artículo se describe cómo restablecer o recuperar Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="fa618-106">Al [restablecer Surface Hub](#reset-a-surface-hub) , se devuelve su sistema operativo a la última actualización acumulativa de Windows Update y se quitan todos los archivos de usuarios locales y la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="fa618-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="fa618-107">La información que se elimina incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa618-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="fa618-108">La cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fa618-108">The device account</span></span>
- <span data-ttu-id="fa618-109">Información de la cuenta para los administradores locales del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fa618-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="fa618-110">Información de unión de dominios o de Azure AD-join</span><span class="sxs-lookup"><span data-stu-id="fa618-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="fa618-111">Información de inscripción de la administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="fa618-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="fa618-112">Información de configuración que se estableció con MDM o la aplicación configuración</span><span class="sxs-lookup"><span data-stu-id="fa618-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="fa618-113">[La recuperación de Surface Hub desde la nube](#recover-a-surface-hub-from-the-cloud) también elimina esta información.</span><span class="sxs-lookup"><span data-stu-id="fa618-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="fa618-114">Además, Surface Hub descarga una nueva imagen de sistema operativo y la instala.</span><span class="sxs-lookup"><span data-stu-id="fa618-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="fa618-115">Puede especificar si el proceso de recuperación conserva otra información almacenada en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span>

## <span data-ttu-id="fa618-116">Restablecer un Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa618-116">Reset a Surface Hub</span></span>

<span data-ttu-id="fa618-117">Es posible que tenga que restablecer su Surface Hub por razones como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fa618-117">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="fa618-118">Va a cambiar el propósito del dispositivo para un nuevo espacio de reunión y quiere reconfigurarlo.</span><span class="sxs-lookup"><span data-stu-id="fa618-118">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="fa618-119">Quieres cambiar el modo en que se administra el dispositivo de forma local.</span><span class="sxs-lookup"><span data-stu-id="fa618-119">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="fa618-120">Se perdió el nombre de usuario o la contraseña de la cuenta del dispositivo o de la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="fa618-120">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="fa618-121">Después de instalar una actualización, el rendimiento del dispositivo disminuye.</span><span class="sxs-lookup"><span data-stu-id="fa618-121">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="fa618-122">Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="fa618-122">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="fa618-123">El proceso de restablecimiento del dispositivo puede demorar hasta seis horas.</span><span class="sxs-lookup"><span data-stu-id="fa618-123">The device reset process may take up to six hours.</span></span> <span data-ttu-id="fa618-124">No apague ni desconecte Surface Hub hasta que el proceso haya terminado.</span><span class="sxs-lookup"><span data-stu-id="fa618-124">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="fa618-125">Si interrumpe el proceso, el dispositivo deja de funcionar.</span><span class="sxs-lookup"><span data-stu-id="fa618-125">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="fa618-126">El dispositivo requiere servicio de garantía para volver a funcionar.</span><span class="sxs-lookup"><span data-stu-id="fa618-126">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="fa618-127">En tu Surface Hub, abre **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="fa618-127">On your Surface Hub, open **Settings**.</span></span>

   ![Imagen que muestra la aplicación configuración para Surface Hub.](images/sh-settings.png)

1. <span data-ttu-id="fa618-129">Seleccione **actualizar & seguridad**.</span><span class="sxs-lookup"><span data-stu-id="fa618-129">Select **Update & Security**.</span></span>

   ![Imagen que muestra la actualización & grupo de seguridad en la aplicación configuración de Surface Hub.](images/sh-settings-update-security.png)

1. <span data-ttu-id="fa618-131">Seleccione **recuperación**y, a continuación, en **restablecer dispositivo**, seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="fa618-131">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   ![Imagen que muestra la opción restablecer dispositivo en la aplicación de configuración de Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="fa618-133">Una vez finalizado el proceso de restablecimiento, Surface Hub inicia de nuevo el [programa de ejecución inicial](first-run-program-surface-hub.md) .</span><span class="sxs-lookup"><span data-stu-id="fa618-133">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="fa618-134">Si el proceso de restablecimiento encuentra un problema, revierte la superficie del sistema operativo existente y, después, muestra la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="fa618-134">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="fa618-135">Recuperar un Surface Hub desde la nube</span><span class="sxs-lookup"><span data-stu-id="fa618-135">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="fa618-136">Si, por algún motivo, Surface Hub se vuelve inutilizable, aún puede recuperarlo desde la nube sin la ayuda de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fa618-136">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="fa618-137">Surface Hub puede descargar una nueva imagen de sistema operativo de la nube y usar esa imagen para reinstalar su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fa618-137">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="fa618-138">Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="fa618-138">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="fa618-139">El Surface Hub o sus cuentas relacionadas han introducido un estado inestable</span><span class="sxs-lookup"><span data-stu-id="fa618-139">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="fa618-140">Surface Hub está bloqueado</span><span class="sxs-lookup"><span data-stu-id="fa618-140">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="fa618-141">La **recuperación del proceso en la nube** requiere una conexión cableada que proporciona conectividad abierta a Internet (sin solicitudes de proxy u otras solicitudes de autenticación).</span><span class="sxs-lookup"><span data-stu-id="fa618-141">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="fa618-142">Recuperar un Surface Hub de un estado defectuoso</span><span class="sxs-lookup"><span data-stu-id="fa618-142">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="fa618-143">Si la cuenta del dispositivo se encuentra en un estado inestable o si la cuenta del administrador tiene problemas, puede usar la aplicación configuración para iniciar el proceso de recuperación de la nube.</span><span class="sxs-lookup"><span data-stu-id="fa618-143">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="fa618-144">Solo debe usar el proceso de recuperación de la nube cuando el proceso de [restablecimiento del dispositivo](#reset-a-surface-hub) no soluciona el problema.</span><span class="sxs-lookup"><span data-stu-id="fa618-144">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="fa618-145">En su Surface Hub, seleccione **configuración** &gt; **& seguridad** &gt; **recuperación**.</span><span class="sxs-lookup"><span data-stu-id="fa618-145">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

1. <span data-ttu-id="fa618-146">En **recuperar de la nube**, seleccione **reiniciar ahora**.</span><span class="sxs-lookup"><span data-stu-id="fa618-146">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![recuperar desde la nube](images/recover-from-the-cloud.png)

### <span data-ttu-id="fa618-148">Recuperar un Surface Hub bloqueado</span><span class="sxs-lookup"><span data-stu-id="fa618-148">Recover a locked Surface Hub</span></span>

<span data-ttu-id="fa618-149">En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión.</span><span class="sxs-lookup"><span data-stu-id="fa618-149">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="fa618-150">Cuando esto suceda, el dispositivo se reiniciará automáticamente y volverá a intentar la operación.</span><span class="sxs-lookup"><span data-stu-id="fa618-150">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="fa618-151">Pero si esta operación falla varias veces, el dispositivo se bloqueará automáticamente para proteger los datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="fa618-151">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="fa618-152">Para desbloquearlo, debe [restablecer el dispositivo](#reset-a-surface-hub) o, si no funciona, recuperarlo de la nube.</span><span class="sxs-lookup"><span data-stu-id="fa618-152">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="fa618-153">Ubique el interruptor de encendido en la parte inferior de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-153">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="fa618-154">El interruptor de alimentación está junto a la conexión del cable de alimentación.</span><span class="sxs-lookup"><span data-stu-id="fa618-154">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="fa618-155">Para obtener más información sobre el cambio de alimentación, consulte la [Guía de preparación del sitio de Surface Hub (pdf)](surface-hub-site-readiness-guide.md).</span><span class="sxs-lookup"><span data-stu-id="fa618-155">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

1. <span data-ttu-id="fa618-156">Mientras el Surface Hub muestra la pantalla de bienvenida, use el interruptor de encendido para desactivar Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-156">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

1. <span data-ttu-id="fa618-157">Use el interruptor de alimentación para activar de nuevo la Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-157">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="fa618-158">El dispositivo se inicia y muestra la pantalla del logotipo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa618-158">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="fa618-159">Cuando veas puntos giratorias debajo del logotipo de Surface Hub, usa el interruptor de alimentación para desactivar de nuevo la Hub de Surface.</span><span class="sxs-lookup"><span data-stu-id="fa618-159">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

1. <span data-ttu-id="fa618-160">Repita el paso 3 3 horas, o hasta que el Surface Hub muestre el mensaje "preparando la reparación automática".</span><span class="sxs-lookup"><span data-stu-id="fa618-160">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="fa618-161">Después de mostrar este mensaje, el Surface Hub muestra la pantalla de Windows RE.</span><span class="sxs-lookup"><span data-stu-id="fa618-161">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

1. <span data-ttu-id="fa618-162">Seleccione **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="fa618-162">Select **Advanced Options**.</span></span>

1. <span data-ttu-id="fa618-163">Seleccione **recuperar en la nube**.</span><span class="sxs-lookup"><span data-stu-id="fa618-163">Select **Recover from the cloud**.</span></span> <span data-ttu-id="fa618-164">(Opcionalmente, puede seleccionar **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="fa618-164">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="fa618-165">Sin embargo, la opción **de recuperación de la nube** es el método recomendado).</span><span class="sxs-lookup"><span data-stu-id="fa618-165">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![Recuperar desde la nube](images/recover-from-cloud.png)
1. <span data-ttu-id="fa618-167">Si se le pide que escriba la clave de BitLocker, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fa618-167">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="fa618-168">Para conservar la información que BitLocker protege en el Surface Hub, escriba la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="fa618-168">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="fa618-169">Para descartar la información protegida, seleccione **omitir esta unidad**</span><span class="sxs-lookup"><span data-stu-id="fa618-169">To discard the protected information, select **Skip this drive**</span></span>  

1. <span data-ttu-id="fa618-170">Cuando se le solicite, seleccione **reinstalar**.</span><span class="sxs-lookup"><span data-stu-id="fa618-170">When you are prompted, select **Reinstall**.</span></span>

    ![Reinstalar](images/reinstall.png)

1. <span data-ttu-id="fa618-172">Para volver a particionar el disco, seleccione **sí**.</span><span class="sxs-lookup"><span data-stu-id="fa618-172">To repartition the disk, select **Yes**.</span></span>

   ![Volver a particionar](images/repartition.png)

   <span data-ttu-id="fa618-174">En primer lugar, el proceso de recuperación descarga la imagen del sistema operativo de la nube.</span><span class="sxs-lookup"><span data-stu-id="fa618-174">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![descargando 97&](images/recover-progress.png)

   <span data-ttu-id="fa618-176">Cuando termine la descarga, el proceso de recuperación restaurará Surface Hub de acuerdo con las opciones que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="fa618-176">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="fa618-177">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="fa618-177">Contact Support</span></span>

<span data-ttu-id="fa618-178">Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="fa618-178">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="fa618-179">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fa618-179">Related topics</span></span>

[<span data-ttu-id="fa618-180">Administrar Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa618-180">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="fa618-181">Guía del administrador de Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa618-181">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

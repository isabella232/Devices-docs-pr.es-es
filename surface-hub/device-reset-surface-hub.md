---
title: Restablecer o recuperar un Surface Hub
description: Describe los procesos de restablecimiento y recuperación de Surface Hub y proporciona instrucciones.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: restablecer Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406658"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="5900a-104">Restablecer o recuperar un Surface Hub</span><span class="sxs-lookup"><span data-stu-id="5900a-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="5900a-105">En este artículo se describe cómo restablecer o recuperar un Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="5900a-106">[Restablecer Surface Hub devuelve](#reset-a-surface-hub) su sistema operativo a la última actualización acumulativa de Windows y quita todos los archivos de usuario locales y la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="5900a-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="5900a-107">La información que se quita incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5900a-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="5900a-108">La cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5900a-108">The device account</span></span>
- <span data-ttu-id="5900a-109">Información de cuenta para los administradores locales del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5900a-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="5900a-110">Información de unión a dominio o unión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="5900a-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="5900a-111">Información de inscripción de Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="5900a-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="5900a-112">Información de configuración que se estableció mediante MDM o la aplicación Configuración</span><span class="sxs-lookup"><span data-stu-id="5900a-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="5900a-113">[Recuperar un Surface Hub de la nube](#recover-a-surface-hub-from-the-cloud) también quita esta información.</span><span class="sxs-lookup"><span data-stu-id="5900a-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="5900a-114">Además, Surface Hub descarga una nueva imagen del sistema operativo e la instala.</span><span class="sxs-lookup"><span data-stu-id="5900a-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="5900a-115">Puedes especificar si el proceso de recuperación conserva otra información almacenada en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="5900a-116">La herramienta de recuperación de [Surface Hub](surface-hub-recovery-tool.md) usa la misma imagen del sistema operativo si necesitas recuperar un Surface Hub para el que no se pueda usar ninguna de estas opciones.</span><span class="sxs-lookup"><span data-stu-id="5900a-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="5900a-117">Restablecer un Surface Hub</span><span class="sxs-lookup"><span data-stu-id="5900a-117">Reset a Surface Hub</span></span>

<span data-ttu-id="5900a-118">Es posible que deba restablecer Surface Hub por motivos como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5900a-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="5900a-119">Estás reconfigurando el dispositivo para un nuevo espacio de reuniones y quieres volver a configurarlo.</span><span class="sxs-lookup"><span data-stu-id="5900a-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="5900a-120">Quieres cambiar el modo en que se administra el dispositivo de forma local.</span><span class="sxs-lookup"><span data-stu-id="5900a-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="5900a-121">Se ha perdido el nombre de usuario o la contraseña de la cuenta del dispositivo o la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="5900a-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="5900a-122">Después de instalar una actualización, el rendimiento del dispositivo disminuye.</span><span class="sxs-lookup"><span data-stu-id="5900a-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="5900a-123">Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5900a-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="5900a-124">El proceso de restablecimiento del dispositivo puede tardar hasta seis horas.</span><span class="sxs-lookup"><span data-stu-id="5900a-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="5900a-125">No desactives ni desenchufes Surface Hub hasta que el proceso haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="5900a-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="5900a-126">Si interrumpes el proceso, el dispositivo se vuelve inoperable.</span><span class="sxs-lookup"><span data-stu-id="5900a-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="5900a-127">El dispositivo requiere el servicio de garantía para volver a funcionar.</span><span class="sxs-lookup"><span data-stu-id="5900a-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="5900a-128">En tu Surface Hub, abre **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="5900a-128">On your Surface Hub, open **Settings**.</span></span>

   ![Imagen que muestra la aplicación Configuración de Surface Hub.](images/sh-settings.png)

2. <span data-ttu-id="5900a-130">Seleccione **Actualizar & seguridad**.</span><span class="sxs-lookup"><span data-stu-id="5900a-130">Select **Update & Security**.</span></span>

   ![Imagen que muestra Actualizar & seguridad en la aplicación Configuración de Surface Hub.](images/sh-settings-update-security.png)

3. <span data-ttu-id="5900a-132">Selecciona **Recuperación**y, a continuación, en **Restablecer dispositivo,** selecciona **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="5900a-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5900a-133">Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, como se te pedirá más adelante.</span><span class="sxs-lookup"><span data-stu-id="5900a-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="5900a-134">Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="5900a-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="5900a-135">Cuando el concentrador se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="5900a-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="5900a-136">Si se omite ese mensaje, se producirá un error en el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="5900a-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![Imagen que muestra la opción Restablecer dispositivo en la aplicación Configuración de Surface Hub.](images/sh-settings-reset-device.png)

   <span data-ttu-id="5900a-138">Una vez terminado el proceso de restablecimiento, Surface Hub vuelve a [iniciar el primer programa de ejecución.](first-run-program-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="5900a-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="5900a-139">Si el proceso de restablecimiento encuentra un problema, revierte Surface Hub a la imagen del sistema operativo existente anteriormente y, a continuación, muestra la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="5900a-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="5900a-140">Recuperar un Surface Hub desde la nube</span><span class="sxs-lookup"><span data-stu-id="5900a-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="5900a-141">Si, por algún motivo, Surface Hub se vuelve inutilizable, puedes recuperarlo de la nube sin la ayuda del soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5900a-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="5900a-142">Surface Hub puede descargar una imagen del sistema operativo nueva de la nube y usar esa imagen para reinstalar su sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5900a-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="5900a-143">Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="5900a-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="5900a-144">Surface Hub o sus cuentas relacionadas han entrado en un estado inestable</span><span class="sxs-lookup"><span data-stu-id="5900a-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="5900a-145">Surface Hub está bloqueado</span><span class="sxs-lookup"><span data-stu-id="5900a-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="5900a-146">El **proceso Recuperar desde la nube** requiere una conexión por cable que proporciona conectividad a Internet abierta (sin proxy u otros mensajes de autenticación).</span><span class="sxs-lookup"><span data-stu-id="5900a-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="5900a-147">Recuperar un Surface Hub de un estado defectuoso</span><span class="sxs-lookup"><span data-stu-id="5900a-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="5900a-148">Si la cuenta del dispositivo entra en un estado inestable o si la cuenta de administrador tiene problemas, puedes usar la aplicación Configuración para iniciar el proceso de recuperación en la nube.</span><span class="sxs-lookup"><span data-stu-id="5900a-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="5900a-149">Solo debes usar el proceso de recuperación en la nube cuando [el](#reset-a-surface-hub) proceso de restablecimiento del dispositivo no solucione el problema.</span><span class="sxs-lookup"><span data-stu-id="5900a-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="5900a-150">En Surface Hub, selecciona **Configuración** &gt; **Actualizar & recuperación de** &gt; **seguridad.**</span><span class="sxs-lookup"><span data-stu-id="5900a-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="5900a-151">En **Recuperar desde la nube,** seleccione Reiniciar **ahora**.</span><span class="sxs-lookup"><span data-stu-id="5900a-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![recuperar desde la nube](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="5900a-153">Recuperar un Surface Hub bloqueado</span><span class="sxs-lookup"><span data-stu-id="5900a-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="5900a-154">En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión.</span><span class="sxs-lookup"><span data-stu-id="5900a-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="5900a-155">Cuando esto sucede, el dispositivo se reinicia automáticamente e intenta de nuevo la operación.</span><span class="sxs-lookup"><span data-stu-id="5900a-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="5900a-156">Pero si esta operación falla repetidamente, el dispositivo se bloquea automáticamente para proteger los datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="5900a-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="5900a-157">Para desbloquearlo, debes [restablecer el](#reset-a-surface-hub) dispositivo o, si no funciona, recuperarlo de la nube.</span><span class="sxs-lookup"><span data-stu-id="5900a-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="5900a-158">Localiza el conmutador de energía en la parte inferior de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="5900a-159">El conmutador de alimentación está junto a la conexión del cable de alimentación.</span><span class="sxs-lookup"><span data-stu-id="5900a-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="5900a-160">Para obtener más información acerca del conmutador de alimentación, consulta la Guía de preparación del sitio de [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="5900a-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="5900a-161">Mientras surface hub muestra la pantalla de bienvenida, usa el botón de encendido para desactivar Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="5900a-162">Usa el conmutador de energía para volver a activar Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="5900a-163">El dispositivo se inicia y muestra la pantalla logotipo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="5900a-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="5900a-164">Cuando veas puntos giratorios debajo del logotipo de Surface Hub, usa el conmutador de energía para desactivar el Surface Hub de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5900a-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="5900a-165">Repita el paso 3 tres veces o hasta que Surface Hub muestre el mensaje "Preparar reparación automática".</span><span class="sxs-lookup"><span data-stu-id="5900a-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="5900a-166">Después de mostrar este mensaje, Surface Hub muestra la pantalla Windows RE.</span><span class="sxs-lookup"><span data-stu-id="5900a-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="5900a-167">Selecciona **Restablecer para volver a instalar Windows**.</span><span class="sxs-lookup"><span data-stu-id="5900a-167">Select **Reset to re-install Windows**.</span></span> 
![restablecer para volver a instalar](images/recover-from-cloud.png)

8. <span data-ttu-id="5900a-169">Seleccione **Descarga en la nube.**</span><span class="sxs-lookup"><span data-stu-id="5900a-169">Select **Cloud download.**</span></span> 

   ![Descarga en la nube](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="5900a-171">Si recibe un mensaje de error que indica **No se puede descargar,** seleccione **Cancelar** e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5900a-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="5900a-172">Seleccione **Limpiar completamente la unidad.**  
![ recuperar y limpiar completamente la unidad</span><span class="sxs-lookup"><span data-stu-id="5900a-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="5900a-173">Se te **preguntará ¿Estás listo para restablecer este dispositivo?**.</span><span class="sxs-lookup"><span data-stu-id="5900a-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="5900a-174">Selecciona **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="5900a-174">Select **Reset**.</span></span> 
![recuperar y confirmar el restablecimiento](images/recover-confirm-reset.png)

11. <span data-ttu-id="5900a-176">La descarga comienza y el proceso de recuperación indica **restablecer este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5900a-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![recuperación que se muestra en curso](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="5900a-178">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="5900a-178">Contact Support</span></span>

<span data-ttu-id="5900a-179">Si tiene preguntas o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="5900a-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5900a-180">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5900a-180">Related topics</span></span>

[<span data-ttu-id="5900a-181">Administrar Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="5900a-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="5900a-182">Guía del administrador de Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="5900a-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

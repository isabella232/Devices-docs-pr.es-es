---
title: Restablecimiento y recuperación de Surface Hub 2S
description: Aprende a recuperar y restablecer Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342980"
---
# <span data-ttu-id="6fe15-104">Restablecimiento y recuperación de Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="6fe15-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="6fe15-105">Si tienes problemas con Surface Hub 2S, puedes restablecer la configuración de fábrica del dispositivo o restaurarlo mediante una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="6fe15-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="6fe15-106">Para empezar, inicia sesión en Surface Hub 2S con credenciales de administrador, abre la aplicación Configuración, selecciona Actualizar & seguridad y, **a**continuación, selecciona **Recuperación.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6fe15-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="6fe15-107">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="6fe15-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6fe15-108">Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, ya que se te pedirá más adelante.</span><span class="sxs-lookup"><span data-stu-id="6fe15-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="6fe15-109">Para obtener más información, consulta [Guardar la clave de BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="6fe15-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="6fe15-110">Para restablecer el dispositivo, seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="6fe15-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="6fe15-111">Cuando aparezca **la ventana Listo para restablecer este** dispositivo, seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="6fe15-112">Cuando el hub se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="6fe15-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="6fe15-113">Si se omite ese mensaje, se producirá un error en el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="6fe15-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="6fe15-114">Una vez que escribes la clave de BitLocker, el concentrador vuelve a instalar el sistema operativo desde la partición de recuperación.</span><span class="sxs-lookup"><span data-stu-id="6fe15-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="6fe15-115">Esto puede tardar hasta una hora en completarse.</span><span class="sxs-lookup"><span data-stu-id="6fe15-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="6fe15-116">Para volver a configurar el dispositivo, ejecuta el programa de instalación por primera vez.</span><span class="sxs-lookup"><span data-stu-id="6fe15-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="6fe15-117">Si administra el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retire y elimine el registro anterior y vuelva a inscribir el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6fe15-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="6fe15-118">Para obtener más información, consulta Quitar dispositivos mediante el borrado, la retirada o la [eliminación manual de la inscripción del dispositivo.](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="6fe15-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Restablecer y recuperar Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="6fe15-120">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="6fe15-120">Figure 1.</span></span> <span data-ttu-id="6fe15-121">Restablecimiento y recuperación de Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="6fe15-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="6fe15-122">Recuperar Surface Hub 2S mediante una unidad de recuperación USB</span><span class="sxs-lookup"><span data-stu-id="6fe15-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="6fe15-123">Nuevo en Surface Hub 2S, ahora puedes reinstalar el dispositivo mediante una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="6fe15-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="6fe15-124">Recuperación desde una unidad USB</span><span class="sxs-lookup"><span data-stu-id="6fe15-124">Recovery from a USB drive</span></span>

<span data-ttu-id="6fe15-125">Con Surface Hub 2S, puedes reinstalar el dispositivo mediante una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="6fe15-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="6fe15-126">Al hacerlo, puedes reinstalar el dispositivo en la configuración de fábrica si has perdido la clave de BitLocker o si ya no tienes credenciales de administrador en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="6fe15-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="6fe15-127">Usa una unidad USB 3.0 con 8 GB o 16 GB de almacenamiento, con el formato FAT32.</span><span class="sxs-lookup"><span data-stu-id="6fe15-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="6fe15-128">Desde un equipo independiente, descarga la imagen de recuperación del archivo .zip desde el sitio web de [Recuperación](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) de Surface y, a continuación, vuelve a estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6fe15-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="6fe15-129">En el cuadro de búsqueda de la barra de tareas, **escriba**la unidad de recuperación y, a continuación, seleccione Crear una unidad de **recuperación** o unidad **de** recuperación a partir de los resultados.</span><span class="sxs-lookup"><span data-stu-id="6fe15-129">In the search box on the taskbar, enter **recovery drive**, and then select **Create a recovery drive** or **Recovery Drive** from the results.</span></span> <span data-ttu-id="6fe15-130">Es posible que tenga que escribir una contraseña de administrador o confirmar su elección.</span><span class="sxs-lookup"><span data-stu-id="6fe15-130">You may need to enter an admin password or confirm your choice.</span></span>

1. <span data-ttu-id="6fe15-131">En el **cuadro Control de cuentas** de usuario, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-131">In the **User Account Control** box, select **Yes**.</span></span>

1. <span data-ttu-id="6fe15-132">Asegúrese de borrar la casilla De copia de seguridad de **los archivos del sistema en** la unidad de recuperación y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-132">Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.</span></span>

1. <span data-ttu-id="6fe15-133">Selecciona la unidad USB y, a continuación, selecciona **> Crear**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-133">Select your USB drive, and then select **Next > Create**.</span></span>  <span data-ttu-id="6fe15-134">Algunas utilidades deben copiarse en la unidad de recuperación, por lo que esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="6fe15-134">Some utilities need to be copied to the recovery drive, so this might take a few minutes.</span></span>

1. <span data-ttu-id="6fe15-135">Cuando la unidad de recuperación esté lista, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-135">When the recovery drive is ready, select **Finish**.</span></span>

1. <span data-ttu-id="6fe15-136">Haz doble clic en el archivo .zip de imagen de recuperación que descargaste anteriormente para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="6fe15-136">Double-click the recovery image .zip file that you previously downloaded to open it.</span></span>

1. <span data-ttu-id="6fe15-137">Seleccione todos los archivos de la carpeta de imagen de recuperación, cópielos en la raíz de la unidad USB y, a continuación, seleccione Elegir para reemplazar los **archivos en el destino.**</span><span class="sxs-lookup"><span data-stu-id="6fe15-137">Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.</span></span>

1. <span data-ttu-id="6fe15-138">Una vez que los archivos han terminado de copiarse, selecciona el icono Quitar **hardware** y medios de expulsar de forma segura en la barra de tareas y quita la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="6fe15-138">Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar, and remove your USB drive.</span></span>

1. <span data-ttu-id="6fe15-139">Conecta la unidad USB a cualquier puerto USB-C o USB-A en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="6fe15-139">Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S.</span></span>

1. <span data-ttu-id="6fe15-140">Desactiva el hub y, a continuación, toma estos pasos para arrancar desde la unidad USB:</span><span class="sxs-lookup"><span data-stu-id="6fe15-140">Turn off the Hub and then take these steps to boot from the USB drive:</span></span>

   1. <span data-ttu-id="6fe15-141">Al presionar el botón Bajar volumen, presione el botón De encendido.</span><span class="sxs-lookup"><span data-stu-id="6fe15-141">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="6fe15-142">Mantén presionado ambos botones hasta que veas el logotipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="6fe15-142">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="6fe15-143">Suelta el botón de inicio/apagado, pero mantén presionado el botón Bajar volumen hasta que comience la interfaz de usuario de instalación.</span><span class="sxs-lookup"><span data-stu-id="6fe15-143">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Usar los botones bajar volumen y encendido para iniciar la recuperación*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="6fe15-145">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="6fe15-145">Figure 2.</span></span> <span data-ttu-id="6fe15-146">Botones de volumen y energía</span><span class="sxs-lookup"><span data-stu-id="6fe15-146">Volume and Power buttons</span></span>*

1. <span data-ttu-id="6fe15-147">En la pantalla de selección de idioma, selecciona el idioma para mostrar de Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="6fe15-147">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="6fe15-148">Seleccione **Recuperar desde una unidad,** limpie completamente **la**unidad y, a continuación, **seleccione Recuperar**.</span><span class="sxs-lookup"><span data-stu-id="6fe15-148">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="6fe15-149">Si se te pide una clave de BitLocker, selecciona **Omitir esta unidad.**</span><span class="sxs-lookup"><span data-stu-id="6fe15-149">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="6fe15-150">Surface Hub 2S se reinicia varias veces y tarda aproximadamente 30 minutos en completar el proceso de recuperación.</span><span class="sxs-lookup"><span data-stu-id="6fe15-150">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="6fe15-151">Cuando aparezca la pantalla de configuración por primera vez, quita la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="6fe15-151">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="6fe15-152">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="6fe15-152">Contact Support</span></span>

<span data-ttu-id="6fe15-153">Si tiene preguntas o necesita ayuda, puede crear [una solicitud de soporte técnico.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="6fe15-153">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>

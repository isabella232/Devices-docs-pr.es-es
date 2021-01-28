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
ms.openlocfilehash: 88f5d912f7505aecaa5bd7ba659acab2d6c4fa1a
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304813"
---
# <span data-ttu-id="7a89b-104">Restablecimiento y recuperación de Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="7a89b-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="7a89b-105">Si tienes problemas con Surface Hub 2S, puedes restablecer el dispositivo a la configuración de fábrica o restaurarlo mediante una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="7a89b-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="7a89b-106">Para empezar, inicia sesión en Surface Hub 2S con credenciales de administrador, abre la aplicación Configuración, selecciona Actualizar & seguridad y, **a**continuación, selecciona **Recuperación.** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7a89b-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="7a89b-107">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="7a89b-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="7a89b-108">Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, ya que se te pedirá más adelante.</span><span class="sxs-lookup"><span data-stu-id="7a89b-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="7a89b-109">Para obtener más información, consulta [Guardar la clave de BitLocker.](save-bitlocker-key-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="7a89b-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="7a89b-110">Para restablecer el dispositivo, seleccione **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="7a89b-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="7a89b-111">Cuando aparezca **la ventana Listo para restablecer este** dispositivo, seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="7a89b-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="7a89b-112">Cuando el hub se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="7a89b-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="7a89b-113">Si se omite ese mensaje, se producirá un error en el restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="7a89b-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="7a89b-114">Una vez que escribes la clave de BitLocker, el concentrador vuelve a instalar el sistema operativo desde la partición de recuperación.</span><span class="sxs-lookup"><span data-stu-id="7a89b-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="7a89b-115">Esto puede tardar hasta una hora en completarse.</span><span class="sxs-lookup"><span data-stu-id="7a89b-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="7a89b-116">Para volver a configurar el dispositivo, ejecuta el programa de instalación por primera vez.</span><span class="sxs-lookup"><span data-stu-id="7a89b-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="7a89b-117">Si administra el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retire y elimine el registro anterior y vuelva a inscribir el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a89b-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="7a89b-118">Para obtener más información, consulta Quitar dispositivos mediante borrar, retirar o deshacer manualmente [la inscripción del dispositivo.](https://docs.microsoft.com/intune/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="7a89b-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Restablecer y recuperar Surface Hub 2S*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="7a89b-120">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="7a89b-120">Figure 1.</span></span> <span data-ttu-id="7a89b-121">Restablecimiento y recuperación de Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="7a89b-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="7a89b-122">Recuperar Surface Hub 2S mediante una unidad de recuperación USB</span><span class="sxs-lookup"><span data-stu-id="7a89b-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="7a89b-123">Nuevo en Surface Hub 2S, ahora puedes reinstalar el dispositivo mediante una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="7a89b-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="7a89b-124">Recuperación desde una unidad USB</span><span class="sxs-lookup"><span data-stu-id="7a89b-124">Recovery from a USB drive</span></span>

<span data-ttu-id="7a89b-125">Con Surface Hub 2S, puedes reinstalar el dispositivo mediante una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="7a89b-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="7a89b-126">Al hacerlo, puedes reinstalar el dispositivo en la configuración de fábrica si has perdido la clave de BitLocker o si ya no tienes credenciales de administrador en la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="7a89b-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="7a89b-127">Usa una unidad USB 3.0 con 8 GB o 16 GB de almacenamiento, con el formato FAT32.</span><span class="sxs-lookup"><span data-stu-id="7a89b-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="7a89b-128">Desde un equipo independiente, descarga la imagen de recuperación del archivo .zip desde el sitio web de [Recuperación](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) de Surface y, a continuación, vuelve a estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="7a89b-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="7a89b-129">Descomprima el archivo descargado en la raíz de la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="7a89b-129">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="7a89b-130">Conecta la unidad USB a cualquier puerto USB-C o USB-A en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="7a89b-130">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="7a89b-131">Desactiva el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7a89b-131">Turn off the device:</span></span>

   1. <span data-ttu-id="7a89b-132">Al presionar el botón Bajar volumen, presione el botón De encendido.</span><span class="sxs-lookup"><span data-stu-id="7a89b-132">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="7a89b-133">Mantén presionado ambos botones hasta que veas el logotipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a89b-133">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="7a89b-134">Suelta el botón de inicio/apagado, pero mantén presionado el botón Bajar volumen hasta que comience la interfaz de usuario de instalación.</span><span class="sxs-lookup"><span data-stu-id="7a89b-134">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*Usar los botones bajar volumen y encendido para iniciar la recuperación*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="7a89b-136">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="7a89b-136">Figure 2.</span></span> <span data-ttu-id="7a89b-137">Botones de volumen y energía</span><span class="sxs-lookup"><span data-stu-id="7a89b-137">Volume and Power buttons</span></span>*

1. <span data-ttu-id="7a89b-138">En la pantalla de selección de idioma, selecciona el idioma para mostrar de Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="7a89b-138">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="7a89b-139">Seleccione **Recuperar desde una unidad,** limpie completamente **la**unidad y, a continuación, **seleccione Recuperar**.</span><span class="sxs-lookup"><span data-stu-id="7a89b-139">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="7a89b-140">Si se te pide una clave de BitLocker, selecciona **Omitir esta unidad.**</span><span class="sxs-lookup"><span data-stu-id="7a89b-140">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="7a89b-141">Surface Hub 2S se reinicia varias veces y tarda aproximadamente 30 minutos en completar el proceso de recuperación.</span><span class="sxs-lookup"><span data-stu-id="7a89b-141">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="7a89b-142">Cuando aparezca la pantalla de configuración por primera vez, quita la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="7a89b-142">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="7a89b-143">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="7a89b-143">Contact Support</span></span>

<span data-ttu-id="7a89b-144">Si tiene preguntas o necesita ayuda, puede crear [una solicitud de soporte técnico.](https://support.microsoft.com/supportforbusiness/productselection)</span><span class="sxs-lookup"><span data-stu-id="7a89b-144">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>

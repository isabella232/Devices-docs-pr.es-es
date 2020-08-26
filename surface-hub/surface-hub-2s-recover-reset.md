---
title: Restablecer y recuperar para Surface Hub 2S
description: Más información sobre cómo recuperar y restablecer Surface Hub 2S.
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
ms.openlocfilehash: e3b1e380f9776fc56e99b8d4e35f708aa952759c
ms.sourcegitcommit: e075b46f14b730464d66246b0280ef2cfa16b3fe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963576"
---
# <span data-ttu-id="4eb7d-104">Restablecer y recuperar para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4eb7d-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="4eb7d-105">Si tiene problemas con Surface Hub 2S, puede restablecer el dispositivo a la configuración de fábrica o restaurar mediante una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="4eb7d-106">Para comenzar, inicie sesión en Surface Hub 2S con credenciales de administrador, abra la aplicación **configuración** , seleccione **Actualizar & seguridad**y, a continuación, seleccione **recuperación**.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="4eb7d-107">Restablecer el dispositivo</span><span class="sxs-lookup"><span data-stu-id="4eb7d-107">Reset the device</span></span>

1. <span data-ttu-id="4eb7d-108">Para restablecer el dispositivo **, seleccione introducción**.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-108">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="4eb7d-109">Cuando aparezca la ventana **listo para restablecer este dispositivo** , seleccione **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!NOTE]
   > <span data-ttu-id="4eb7d-110">Surface Hub 2S reinstala el sistema operativo desde la partición de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="4eb7d-111">Esto puede demorar hasta una hora en completarse.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="4eb7d-112">Para volver a configurar el dispositivo, ejecute el programa de instalación por primera vez.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-112">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="4eb7d-113">Si administra el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retire y elimine el registro anterior y, a continuación, vuelva a inscribir el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="4eb7d-114">Para obtener más información, vea [quitar dispositivos mediante barrido, retirada o desafiliación manual del dispositivo](https://docs.microsoft.com/intune/devices-wipe).</span><span class="sxs-lookup"><span data-stu-id="4eb7d-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

> [!div class="mx-imgBorder"]
> ![\* Restablecer y recuperar para Surface Hub 2S \*](images/sh2-reset.png)
<br/>*<span data-ttu-id="4eb7d-116">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-116">Figure 1.</span></span> <span data-ttu-id="4eb7d-117">Restablecer y recuperar para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="4eb7d-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="4eb7d-118">Recuperar Surface Hub 2S con una unidad de recuperación USB</span><span class="sxs-lookup"><span data-stu-id="4eb7d-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="4eb7d-119">Nuevo en Surface Hub 2S, ahora puede reinstalar el dispositivo con una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="4eb7d-120">Recuperación desde una unidad USB</span><span class="sxs-lookup"><span data-stu-id="4eb7d-120">Recovery from a USB drive</span></span>

<span data-ttu-id="4eb7d-121">Con Surface Hub 2S, puede reinstalar el dispositivo con una imagen de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="4eb7d-122">Al hacerlo, puede volver a instalar el dispositivo en la configuración de fábrica si ha perdido la clave de BitLocker o si ya no tiene credenciales de administrador en la aplicación configuración.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="4eb7d-123">Use una unidad USB 3,0 con 8 GB o 16 GB de almacenamiento, con formato FAT32.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="4eb7d-124">Desde un PC independiente, descarga la imagen de recuperación de archivos. zip del [sitio web de recuperación superficial](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) y, a continuación, vuelve a estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="4eb7d-125">Descomprima el archivo descargado en la raíz de la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  

1. <span data-ttu-id="4eb7d-126">Conecta la unidad USB a cualquier puerto USB-C o USB: un puerto en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>

1. <span data-ttu-id="4eb7d-127">Apague el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4eb7d-127">Turn off the device:</span></span>

   1. <span data-ttu-id="4eb7d-128">Mientras presiona el botón bajar de volumen, presione el botón de encendido.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-128">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="4eb7d-129">Mantenga presionados los dos botones hasta que vea el logotipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-129">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="4eb7d-130">Suelta el botón de encendido, pero continúa manteniendo el botón bajar el volumen hasta que comience la interfaz de usuario de instalación.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-130">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

   ![\* Usar los botones de encendido y de apagado de volumen para iniciar la recuperación \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="4eb7d-132">Figura 2.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-132">Figure 2.</span></span> <span data-ttu-id="4eb7d-133">Botones de volumen y de encendido</span><span class="sxs-lookup"><span data-stu-id="4eb7d-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="4eb7d-134">En la pantalla de selección de idioma, seleccione el idioma de la pantalla para Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="4eb7d-135">Seleccione **recuperar desde una unidad** y **Limpie completamente la unidad**y, a continuación, seleccione **recuperar**.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="4eb7d-136">Si se le pide una clave de BitLocker, seleccione **omitir esta unidad**.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="4eb7d-137">Surface Hub 2S se reinicia varias veces y tarda aproximadamente 30 minutos en completar el proceso de recuperación.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="4eb7d-138">Cuando aparezca la pantalla de configuración del primer momento, quite la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="4eb7d-138">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="4eb7d-139">Contactar con el soporte técnico</span><span class="sxs-lookup"><span data-stu-id="4eb7d-139">Contact Support</span></span>

<span data-ttu-id="4eb7d-140">Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="4eb7d-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>

---
title: Desinstalación de SSD en dispositivos de superficie compatibles
description: Cómo transferir una SSD de un dispositivo Surface a otro.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919229"
---
# <span data-ttu-id="51156-103">Procedimientos recomendados para la eliminación de SSD de dispositivos de superficie compatibles</span><span class="sxs-lookup"><span data-stu-id="51156-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51156-104">Este artículo está pensado para el uso de técnicos de ti cualificados únicamente en una organización empresarial.</span><span class="sxs-lookup"><span data-stu-id="51156-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="51156-105">Describe los procedimientos recomendados para que los técnicos de ti cualificados lo usen al quitar y reemplazar SSDs en dispositivos Surface que tengan SSDs extraíbles.</span><span class="sxs-lookup"><span data-stu-id="51156-105">It describes the recommended best practices for use by qualified IT technicians when they remove and replace SSDs in Surface devices that have removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="51156-106">Abrir dispositivos y reemplazar componentes de dispositivos puede presentar descargas eléctricas, daños en el dispositivo, incendio y riesgos personales y otros peligros.</span><span class="sxs-lookup"><span data-stu-id="51156-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="51156-107">Siempre tenga cuidado cuando lleve a cabo dichas actividades.</span><span class="sxs-lookup"><span data-stu-id="51156-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="51156-108">Siga las precauciones de seguridad y los procedimientos que se identifican en la [Guía de eliminación de rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="51156-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="51156-109">Le recomendamos que obtenga asistencia profesional si no puede seguir las precauciones de seguridad y los procedimientos que se especifican en la "Guía de eliminación de rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="51156-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="51156-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="51156-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51156-111">En este artículo se presupone que usted comprende las precauciones Generales de seguridad y los procedimientos y directivas de seguridad que se describen en la "Guía de eliminación de rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="51156-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="51156-112">Prepararse para la eliminación de SSD</span><span class="sxs-lookup"><span data-stu-id="51156-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="51156-113">Instalar las últimas actualizaciones</span><span class="sxs-lookup"><span data-stu-id="51156-113">Install the latest updates</span></span> 

<span data-ttu-id="51156-114">Antes de empezar, asegúrese de que la versión de Windows tiene los últimos cambios:</span><span class="sxs-lookup"><span data-stu-id="51156-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="51156-115">Vaya a **iniciar**  >  **configuración**  >  **Actualizar & seguridad**y seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="51156-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="51156-116">Instalar todas las actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="51156-116">Install all available updates.</span></span> 
2. <span data-ttu-id="51156-117">Instalar todas las actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="51156-117">Install all available updates.</span></span>
3. <span data-ttu-id="51156-118">Compruebe que tiene contraseñas necesarias para tener acceso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="51156-119">Administrar BitLocker</span><span class="sxs-lookup"><span data-stu-id="51156-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="51156-120">Esta sección incluye recomendaciones para organizaciones que han habilitado el cifrado de BitLocker en discos duros.</span><span class="sxs-lookup"><span data-stu-id="51156-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="51156-121">Para obtener más información, consulte la [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="51156-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="51156-122">Si el cifrado de BitLocker se deshabilita durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="51156-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="51156-123">Si el dispositivo se puede descifrar antes de la eliminación y sustitución de SSD, siga estos pasos para desactivar BitLocker:</span><span class="sxs-lookup"><span data-stu-id="51156-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="51156-124">En **configuración**, escriba **BitLocker**y, a continuación, seleccione **Administrar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="51156-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="51156-125">Seleccione **desactivar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="51156-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="51156-126">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-126">Power down the device.</span></span> 

### <span data-ttu-id="51156-127">Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="51156-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="51156-128">Si el dispositivo está cifrado antes de la eliminación y sustitución de SSD, siga estos pasos para generar una clave de recuperación de BitLocker y guardarla en almacenamiento USB:</span><span class="sxs-lookup"><span data-stu-id="51156-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="51156-129">En **configuración**, escriba **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="51156-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="51156-130">Seleccione **administrar**  > **clave de recuperación BitLocker generando**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="51156-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="51156-131">Inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="51156-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="51156-132">Guarde la clave de recuperación en el almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="51156-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="51156-133">Quite la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="51156-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="51156-134">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-134">Power down the device.</span></span> 

## <span data-ttu-id="51156-135">Quitar y reemplazar el SSD</span><span class="sxs-lookup"><span data-stu-id="51156-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="51156-136">Quite el SSD con las instrucciones de la [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="51156-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="51156-137">Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet por cable.</span><span class="sxs-lookup"><span data-stu-id="51156-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="51156-138">Encienda el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-138">Power on the new device.</span></span> <span data-ttu-id="51156-139">El dispositivo puede pasar por una actualización de firmware durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="51156-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="51156-140">Después de la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="51156-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="51156-141">Administrar SSDs sin cifrar</span><span class="sxs-lookup"><span data-stu-id="51156-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="51156-142">Si el SSD sigue sin cifrar durante la transferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51156-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="51156-143">Vaya a la contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="51156-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="51156-144">Escriba la contraseña e inicie sesión en espera de que se complete la autenticación en dos fases (si procede).</span><span class="sxs-lookup"><span data-stu-id="51156-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="51156-145">Una vez que hayas iniciado sesión por completo, ve a **iniciar**  >  **Account**  >  **sesión**de cuenta.</span><span class="sxs-lookup"><span data-stu-id="51156-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="51156-146">Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="51156-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="51156-147">Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD, y quiere habilitar BitLocker después de la sustitución, **vaya a BitLocker**  >  **Manage BitLocker**  >  **resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="51156-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="51156-148">Ejecute el kit de herramientas de diagnóstico de Microsoft Surface para empresas (SDT) para comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="51156-149">Para comprobar la activación de Windows, navegue hasta la activación de la **configuración**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="51156-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="51156-150">Si ve algún mensaje de error, seleccione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="51156-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="51156-151">Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a cuenta de **archivo**  >  **Account** y, después, compruebe si hay algún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="51156-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="51156-152">Administrar SSDs cifradas</span><span class="sxs-lookup"><span data-stu-id="51156-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="51156-153">Deberá tener un segundo dispositivo para leer la clave de recuperación de BitLocker guardada en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="51156-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="51156-154">Si el SSD seguía cifrado durante la transferencia, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51156-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="51156-155">Inserte la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="51156-156">Abra el archivo. txt que contiene la clave de recuperación de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="51156-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="51156-157">Escriba manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.</span><span class="sxs-lookup"><span data-stu-id="51156-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="51156-158">Una vez que haya escrito correctamente la clave de recuperación de BitLocker, vaya a contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="51156-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="51156-159">Escriba la contraseña e inicie sesión, pendiente de la finalización de la autenticación en dos fases (si procede).</span><span class="sxs-lookup"><span data-stu-id="51156-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="51156-160">Una vez que hayas iniciado sesión por completo, ve a **iniciar**  >  **Account**  >  **sesión**de cuenta.</span><span class="sxs-lookup"><span data-stu-id="51156-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="51156-161">Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN.</span><span class="sxs-lookup"><span data-stu-id="51156-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="51156-162">Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD, y si quiere habilitar BitLocker después de la sustitución, vaya a **configuración**  >  **BitLocker**  >  **Manage BitLocker**  >  **Resume Bitlocker**.</span><span class="sxs-lookup"><span data-stu-id="51156-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="51156-163">Ejecute **SDT** para comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51156-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="51156-164">Para comprobar la activación de Windows, vaya a activación de **configuración**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="51156-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="51156-165">Si ve algún mensaje de error, seleccione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="51156-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="51156-166">Para comprobar el estado de la cuenta de Office, abra la **aplicación de Office**y, a continuación, vaya a cuenta de **archivo**  >  **Account** para comprobar si hay algún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="51156-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="51156-167">Más información</span><span class="sxs-lookup"><span data-stu-id="51156-167">More information</span></span> 

<span data-ttu-id="51156-168">Para obtener más información, consulta los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="51156-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="51156-169">Guía de eliminación de rSSD para Enterprise</span><span class="sxs-lookup"><span data-stu-id="51156-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="51156-170">Guía de recuperación de BitLocker</span><span class="sxs-lookup"><span data-stu-id="51156-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="51156-171">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="51156-171">Still need help?</span></span> <span data-ttu-id="51156-172">Vaya a [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="51156-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
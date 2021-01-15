---
title: Eliminación de SSD en dispositivos Surface compatibles
description: En este artículo, destinado a técnicos de TI cualificados, se describen los procedimientos recomendados para la eliminación y sustitución de los SSD en Surface Laptop 3, Surface Pro X y Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270635"
---
# <span data-ttu-id="67cee-103">Procedimientos recomendados para la eliminación de SSD desde dispositivos Surface compatibles</span><span class="sxs-lookup"><span data-stu-id="67cee-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67cee-104">Este artículo está pensado para ser usado por técnicos de TI cualificados solo en una organización empresarial.</span><span class="sxs-lookup"><span data-stu-id="67cee-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="67cee-105">Describe los procedimientos recomendados para su uso por parte de técnicos de TI cualificados en la eliminación y sustitución de los SSD en los siguientes dispositivos Surface compatibles:</span><span class="sxs-lookup"><span data-stu-id="67cee-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="67cee-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="67cee-106">Surface Pro 7+</span></span>
- <span data-ttu-id="67cee-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="67cee-107">Surface Pro X</span></span>
- <span data-ttu-id="67cee-108">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="67cee-108">Surface Laptop Go</span></span>
- <span data-ttu-id="67cee-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="67cee-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="67cee-110">La apertura de dispositivos y el reemplazo de componentes del dispositivo pueden presentar descargas eléctricas, daños en el dispositivo, incendios y daños personales, y otros riesgos.</span><span class="sxs-lookup"><span data-stu-id="67cee-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="67cee-111">Tenga cuidado siempre cuando realice dichas actividades.</span><span class="sxs-lookup"><span data-stu-id="67cee-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="67cee-112">Siga las precauciones y procedimientos de seguridad que se identifican en la Guía de [eliminación de rSSD para empresas.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="67cee-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="67cee-113">Le recomendamos que reciba asistencia profesional si no puede seguir las precauciones y procedimientos de seguridad especificados en la "Guía de eliminación de rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="67cee-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="67cee-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="67cee-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67cee-115">En este artículo se supone que comprende las directivas y procedimientos generales de seguridad y precaución que se describen en la "Guía de eliminación de rSSD para empresas".</span><span class="sxs-lookup"><span data-stu-id="67cee-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="67cee-116">Preparar la eliminación de SSD</span><span class="sxs-lookup"><span data-stu-id="67cee-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="67cee-117">Instalar las actualizaciones más recientes</span><span class="sxs-lookup"><span data-stu-id="67cee-117">Install the latest updates</span></span> 

<span data-ttu-id="67cee-118">Antes de empezar, asegúrate de que la versión de Windows tenga instaladas las actualizaciones más recientes:</span><span class="sxs-lookup"><span data-stu-id="67cee-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="67cee-119">Ve a **Iniciar**  >  **actualización de**configuración &  >  **seguridad**y selecciona **Buscar actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="67cee-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="67cee-120">Instale todas las actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="67cee-120">Install all available updates.</span></span>
3. <span data-ttu-id="67cee-121">Comprueba las contraseñas necesarias para acceder al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="67cee-122">Administrar BitLocker</span><span class="sxs-lookup"><span data-stu-id="67cee-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="67cee-123">En esta sección se incluyen recomendaciones para las organizaciones que han habilitado el cifrado de BitLocker para discos duros.</span><span class="sxs-lookup"><span data-stu-id="67cee-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="67cee-124">Para obtener más información, consulta [guía de recuperación de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)</span><span class="sxs-lookup"><span data-stu-id="67cee-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="67cee-125">Si el cifrado de BitLocker está deshabilitado durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="67cee-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="67cee-126">Si el dispositivo se puede descifrar antes de quitar y reemplazar SSD, sigue estos pasos para desactivar BitLocker:</span><span class="sxs-lookup"><span data-stu-id="67cee-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="67cee-127">En **Configuración,** escribe **BitLocker** y, a continuación, **selecciona Administrar BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="67cee-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="67cee-128">Selecciona **Desactivar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="67cee-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="67cee-129">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-129">Power down the device.</span></span> 

### <span data-ttu-id="67cee-130">Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="67cee-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="67cee-131">Si el dispositivo está cifrado antes de quitar y reemplazar SSD, sigue estos pasos para generar una clave de recuperación de BitLocker y guardarla en el almacenamiento USB:</span><span class="sxs-lookup"><span data-stu-id="67cee-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="67cee-132">En **Configuración,** escriba **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="67cee-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="67cee-133">Selecciona **Administrar BitLocker Generar**clave de  > **recuperación de BitLocker.**</span><span class="sxs-lookup"><span data-stu-id="67cee-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="67cee-134">Inserta una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="67cee-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="67cee-135">Guarda la clave de recuperación en el almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="67cee-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="67cee-136">Quita la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="67cee-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="67cee-137">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-137">Power down the device.</span></span> 

## <span data-ttu-id="67cee-138">Quitar y reemplazar SSD</span><span class="sxs-lookup"><span data-stu-id="67cee-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="67cee-139">Quita el SSD mediante las instrucciones adecuadas para el dispositivo que se incluyen en la Guía de [eliminación de rSSD para empresas.](https://www.microsoft.com/download/100440)</span><span class="sxs-lookup"><span data-stu-id="67cee-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="67cee-140">Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet cableada.</span><span class="sxs-lookup"><span data-stu-id="67cee-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="67cee-141">Encienda el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-141">Power on the new device.</span></span> <span data-ttu-id="67cee-142">El dispositivo puede pasar por una actualización de firmware durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="67cee-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="67cee-143">Después de la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="67cee-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="67cee-144">Administrar SSD sin cifrar</span><span class="sxs-lookup"><span data-stu-id="67cee-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="67cee-145">Si el SSD no se cifra durante la transferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="67cee-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="67cee-146">Vaya a **Contraseña de opciones de inicio de**sesión  >  \*\*\*\* (representada por el icono de clave del lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="67cee-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="67cee-147">Escriba la contraseña e inicie sesión pendiente de finalización de la autenticación en dos fases (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="67cee-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="67cee-148">Una vez que haya iniciado sesión por completo, vaya **a Iniciar**sesión  >  **en la**  >  **cuenta.**</span><span class="sxs-lookup"><span data-stu-id="67cee-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="67cee-149">Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="67cee-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="67cee-150">Si el dispositivo estaba deshabilitado para BitLocker para facilitar la eliminación y sustitución de SSD, y quieres habilitar BitLocker después del reemplazo, ve a **BitLocker**  >  **Administrar BitLocker**  >  **Reanudar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="67cee-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="67cee-151">Ejecuta [Microsoft Surface Diagnostic Toolkit para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="67cee-152">Busca la activación de Windows navegando a **Activación**  >  **de configuración.**</span><span class="sxs-lookup"><span data-stu-id="67cee-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="67cee-153">Si ve algún mensaje de error, seleccione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="67cee-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="67cee-154">Compruebe la cuenta de Office abriendo \*\*\*\* la aplicación **de Office,** vaya a Cuenta de archivo y, a continuación,  >  \*\*\*\* compruebe si hay mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="67cee-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="67cee-155">Administración de SSD cifrados</span><span class="sxs-lookup"><span data-stu-id="67cee-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="67cee-156">Tendrá que tener un segundo dispositivo para leer la clave de recuperación de BitLocker que se guardó en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="67cee-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="67cee-157">Si el SSD está cifrado durante la transferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="67cee-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="67cee-158">Inserta la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="67cee-159">Abre el archivo .txt que contiene la clave de recuperación de Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="67cee-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="67cee-160">Escribe manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.</span><span class="sxs-lookup"><span data-stu-id="67cee-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="67cee-161">Después de especificar correctamente la clave de \*\*\*\* recuperación de BitLocker, ve a Contraseña de opciones de inicio de sesión (representada por el icono de clave del  >  \*\*\*\* lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="67cee-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="67cee-162">Escriba la contraseña e inicie sesión, pendiente de la finalización de la autenticación en dos fases (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="67cee-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="67cee-163">Una vez que haya iniciado sesión por completo, vaya **a Iniciar**sesión  >  **en la**  >  **cuenta.**</span><span class="sxs-lookup"><span data-stu-id="67cee-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="67cee-164">Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN.</span><span class="sxs-lookup"><span data-stu-id="67cee-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="67cee-165">Si el dispositivo estaba deshabilitado para BitLocker para facilitar la eliminación y sustitución \*\*\*\* de SSD y si quieres habilitar BitLocker después del reemplazo, ve a Configuración de  >  **BitLocker**  >  **Administrar BitLocker**Reanudar  >  **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="67cee-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="67cee-166">Ejecuta **[SDT para](surface-diagnostic-toolkit-for-business-intro.md)** comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="67cee-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="67cee-167">Para comprobar la activación de Windows, seleccione **Configuración**  >  **de activación.**</span><span class="sxs-lookup"><span data-stu-id="67cee-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="67cee-168">Si ve algún mensaje de error, seleccione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="67cee-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="67cee-169">Para comprobar el estado de la cuenta de Office, abra la aplicación **de Office**y, a continuación, vaya a Cuenta de archivo para comprobar si hay \*\*\*\*  >  \*\*\*\* mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="67cee-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="67cee-170">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="67cee-170">Learn more</span></span>

- [<span data-ttu-id="67cee-171">Guía de eliminación de rSSD para empresas</span><span class="sxs-lookup"><span data-stu-id="67cee-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="67cee-172">Guía de recuperación de BitLocker</span><span class="sxs-lookup"><span data-stu-id="67cee-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="67cee-173">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="67cee-173">Still need help?</span></span> <span data-ttu-id="67cee-174">Vaya a [Microsoft Community.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="67cee-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
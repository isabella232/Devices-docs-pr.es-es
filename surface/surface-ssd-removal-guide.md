---
title: Eliminación de SSD en dispositivos Surface compatibles
description: En este artículo, destinado a técnicos de TI cualificados, se describen los procedimientos recomendados para la eliminación y sustitución de los SD en Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X y Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576910"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="33794-103">Procedimientos recomendados para la eliminación de SSD de dispositivos Surface compatibles</span><span class="sxs-lookup"><span data-stu-id="33794-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33794-104">Este artículo está pensado para su uso por técnicos de TI cualificados solo en una organización empresarial.</span><span class="sxs-lookup"><span data-stu-id="33794-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="33794-105">Describe los procedimientos recomendados para su uso por técnicos de TI cualificados en la eliminación y sustitución de los SD en los siguientes dispositivos Surface compatibles:</span><span class="sxs-lookup"><span data-stu-id="33794-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="33794-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="33794-106">Surface Pro 7+</span></span>
- <span data-ttu-id="33794-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="33794-107">Surface Pro X</span></span>
- <span data-ttu-id="33794-108">Surface Laptop Ir</span><span class="sxs-lookup"><span data-stu-id="33794-108">Surface Laptop Go</span></span>
- <span data-ttu-id="33794-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="33794-109">Surface Laptop 3</span></span>
- <span data-ttu-id="33794-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="33794-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="33794-111">Abrir dispositivos y reemplazar componentes del dispositivo puede presentar descargas eléctricas, daños en el dispositivo, riesgos de incendio y daños personales, y otros riesgos.</span><span class="sxs-lookup"><span data-stu-id="33794-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="33794-112">Tenga siempre cuidado al realizar dichas actividades.</span><span class="sxs-lookup"><span data-stu-id="33794-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="33794-113">Siga las precauciones y procedimientos de seguridad que se identifican en la Guía de eliminación [de rSSD para Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="33794-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="33794-114">Se recomienda obtener asistencia profesional si no puede seguir las precauciones y procedimientos de seguridad especificados en la "Guía de eliminación de rSSD para Enterprise".</span><span class="sxs-lookup"><span data-stu-id="33794-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="33794-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="33794-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33794-116">En este artículo se supone que comprende las directivas y procedimientos generales de seguridad y precauciones que se describen en la "Guía de eliminación de rSSD para Enterprise".</span><span class="sxs-lookup"><span data-stu-id="33794-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="33794-117">Preparar la eliminación de SSD</span><span class="sxs-lookup"><span data-stu-id="33794-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="33794-118">Instalar las actualizaciones más recientes</span><span class="sxs-lookup"><span data-stu-id="33794-118">Install the latest updates</span></span> 

<span data-ttu-id="33794-119">Antes de empezar, asegúrese de que la versión de Windows tiene instaladas las actualizaciones más recientes:</span><span class="sxs-lookup"><span data-stu-id="33794-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="33794-120">Vaya **a Inicio**  >  **Configuración**  >  **Actualizar & Seguridad**y seleccione Buscar **actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="33794-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="33794-121">Instale todas las actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="33794-121">Install all available updates.</span></span>
3. <span data-ttu-id="33794-122">Comprueba las contraseñas necesarias para acceder al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="33794-123">Administrar BitLocker</span><span class="sxs-lookup"><span data-stu-id="33794-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="33794-124">En esta sección se incluyen recomendaciones para las organizaciones que han BitLocker cifrado de discos duros.</span><span class="sxs-lookup"><span data-stu-id="33794-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="33794-125">Para obtener más información, [vea BitLocker guía de recuperación](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="33794-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="33794-126">Si BitLocker cifrado está deshabilitado durante la eliminación y reemplazo de SSD</span><span class="sxs-lookup"><span data-stu-id="33794-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="33794-127">Si el dispositivo se puede descifrar antes de la eliminación y reemplazo de SSD, siga estos pasos para desactivar BitLocker:</span><span class="sxs-lookup"><span data-stu-id="33794-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="33794-128">En **Configuración**, escriba BitLocker y, a **continuación,** seleccione **Administrar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="33794-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="33794-129">Seleccione **Desactivar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="33794-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="33794-130">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="33794-131">Si BitLocker cifrado está habilitado durante la eliminación y reemplazo de SSD</span><span class="sxs-lookup"><span data-stu-id="33794-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="33794-132">Si el dispositivo está cifrado antes de la eliminación y reemplazo de SSD, siga estos pasos para generar una clave de recuperación BitLocker y guardarlo en el almacenamiento USB:</span><span class="sxs-lookup"><span data-stu-id="33794-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="33794-133">En **Configuración**, escriba **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="33794-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="33794-134">Seleccione **Administrar BitLocker**Generar BitLocker clave de  > **recuperación**.</span><span class="sxs-lookup"><span data-stu-id="33794-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="33794-135">Inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="33794-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="33794-136">Guarde la clave de recuperación en el almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="33794-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="33794-137">Quite la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="33794-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="33794-138">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="33794-139">Quitar y reemplazar SSD</span><span class="sxs-lookup"><span data-stu-id="33794-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="33794-140">Quite el SSD mediante las instrucciones adecuadas para el dispositivo que se incluyen en la Guía de eliminación de [rSSD para Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="33794-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="33794-141">Coloca el SSD original en un nuevo dispositivo y conecta el nuevo dispositivo a una conexión a Internet por cable.</span><span class="sxs-lookup"><span data-stu-id="33794-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="33794-142">Encienda el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-142">Power on the new device.</span></span> <span data-ttu-id="33794-143">El dispositivo puede pasar por una actualización de firmware durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="33794-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="33794-144">Después de la eliminación y reemplazo de SSD</span><span class="sxs-lookup"><span data-stu-id="33794-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="33794-145">Administrar EDS sin cifrar</span><span class="sxs-lookup"><span data-stu-id="33794-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="33794-146">Si el SSD no está cifrado durante la transferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33794-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="33794-147">Ve a **Opciones de inicio de sesión**  >  **Contraseña** (representada por el icono de tecla en el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="33794-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="33794-148">Escriba la contraseña y el inicio de sesión pendientes de la finalización de la autenticación en dos fases (si procede).</span><span class="sxs-lookup"><span data-stu-id="33794-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="33794-149">Una vez que haya iniciado sesión por completo, vaya **a Inicio de**sesión  >  **de**la  >  **cuenta**.</span><span class="sxs-lookup"><span data-stu-id="33794-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="33794-150">Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="33794-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="33794-151">Si el dispositivo BitLocker deshabilitado para facilitar la eliminación y reemplazo de SSD y quieres habilitar BitLocker después del reemplazo, ve a **BitLocker**Administrar BitLocker  >  \*\*\*\*  >  **Reanudar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="33794-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="33794-152">Ejecuta la [herramienta de diagnóstico de Microsoft Surface Toolkit para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="33794-153">Compruebe si Windows activa mediante la navegación **a Configuración**  >  **activation**.</span><span class="sxs-lookup"><span data-stu-id="33794-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="33794-154">Si ve algún mensaje de error, seleccione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="33794-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="33794-155">Compruebe la Office de correo abriendo **la aplicación Office,** vaya a **Cuenta**de archivo y, a continuación, compruebe si hay mensajes  >  \*\*\*\* de error.</span><span class="sxs-lookup"><span data-stu-id="33794-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="33794-156">Administración de DS cifrados</span><span class="sxs-lookup"><span data-stu-id="33794-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="33794-157">Tendrá que tener un segundo dispositivo para leer la BitLocker de recuperación que se guardó en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="33794-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="33794-158">Si el SSD está cifrado durante la transferencia, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="33794-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="33794-159">Inserte la unidad USB que contiene la BitLocker de recuperación en el segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="33794-160">Abra el .txt que contiene la clave de recuperación de Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="33794-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="33794-161">Escribe manualmente la clave BitLocker de recuperación en el nuevo dispositivo que contiene el SSD original.</span><span class="sxs-lookup"><span data-stu-id="33794-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="33794-162">Una vez que haya escrito correctamente la clave \*\*\*\* de recuperación BitLocker, vaya a Contraseña de opciones de inicio de sesión (representada por el icono de tecla en  >  \*\*\*\* el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="33794-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="33794-163">Escriba la contraseña y el inicio de sesión, pendiente de la finalización de la autenticación en dos fases (si procede).</span><span class="sxs-lookup"><span data-stu-id="33794-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="33794-164">Una vez que haya iniciado sesión por completo, vaya **a Inicio de**sesión  >  **de**la  >  **cuenta**.</span><span class="sxs-lookup"><span data-stu-id="33794-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="33794-165">Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN.</span><span class="sxs-lookup"><span data-stu-id="33794-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="33794-166">Si el dispositivo BitLocker deshabilitado para facilitar la eliminación y reemplazo de SSD y si quieres habilitar BitLocker después del reemplazo, ve **a Configuración**  >  **BitLocker**Administrar BitLocker Resume  >  \*\*\*\*  >  **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="33794-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="33794-167">Ejecute **[SDT para](surface-diagnostic-toolkit-for-business-intro.md)** comprobar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33794-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="33794-168">Para comprobar Windows activación, **seleccione Configuración**  >  **activación**.</span><span class="sxs-lookup"><span data-stu-id="33794-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="33794-169">Si ve algún mensaje de error, seleccione **Solucionar problemas.**</span><span class="sxs-lookup"><span data-stu-id="33794-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="33794-170">Para comprobar el estado de la cuenta Office, abra **la aplicación Office**y, a continuación, vaya a Cuenta de archivo para comprobar si hay mensajes de \*\*\*\*  >  \*\*\*\* error.</span><span class="sxs-lookup"><span data-stu-id="33794-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="33794-171">Obtén más información</span><span class="sxs-lookup"><span data-stu-id="33794-171">Learn more</span></span>

- [<span data-ttu-id="33794-172">Guía de eliminación de rSSD para Enterprise</span><span class="sxs-lookup"><span data-stu-id="33794-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="33794-173">Guía de recuperación de BitLocker</span><span class="sxs-lookup"><span data-stu-id="33794-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="33794-174">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="33794-174">Still need help?</span></span> <span data-ttu-id="33794-175">Vaya a [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="33794-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
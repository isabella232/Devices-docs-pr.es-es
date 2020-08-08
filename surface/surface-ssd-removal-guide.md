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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918973"
---
# <span data-ttu-id="d97c7-103">Procedimientos recomendados para la eliminación de SSD en dispositivos de superficie compatibles</span><span class="sxs-lookup"><span data-stu-id="d97c7-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d97c7-104">Este artículo está pensado para el uso de técnicos de ti cualificados únicamente en una organización empresarial.</span><span class="sxs-lookup"><span data-stu-id="d97c7-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="d97c7-105">Describe los procedimientos recomendados para que los técnicos de ti cualificados los usen para quitar y reemplazar SSDs en dispositivos Surface con SSDs extraíbles.</span><span class="sxs-lookup"><span data-stu-id="d97c7-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="d97c7-106">Abrir dispositivos y reemplazar componentes de dispositivos puede presentar descargas eléctricas, daños en el dispositivo, incendio y riesgos personales y otros peligros.</span><span class="sxs-lookup"><span data-stu-id="d97c7-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="d97c7-107">Tenga siempre cuidado cuando realice actividades de este tipo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="d97c7-108">Siga las precauciones de seguridad y los procedimientos identificados en la guía de eliminación de rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="d97c7-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="d97c7-109">Microsoft recomienda que solicite asistencia profesional si no puede seguir las precauciones de seguridad y los procedimientos especificados en la guía de eliminación de rSSD para empresas.</span><span class="sxs-lookup"><span data-stu-id="d97c7-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="d97c7-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d97c7-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d97c7-111">Este artículo supone que usted comprende las precauciones Generales de seguridad y los procedimientos y políticas de seguridad que se describen en la [Guía de eliminación de rSSD para empresas](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="d97c7-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="d97c7-112">Prepararse para la eliminación de SSD</span><span class="sxs-lookup"><span data-stu-id="d97c7-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="d97c7-113">Instalar las últimas actualizaciones</span><span class="sxs-lookup"><span data-stu-id="d97c7-113">Install the latest updates</span></span> 

<span data-ttu-id="d97c7-114">Antes de empezar, asegúrese de que su versión de Windows tiene las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="d97c7-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="d97c7-115">Vaya a **Inicio**de  >  la actualización de**configuración**  >  **& seguridad** y seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="d97c7-116">Instalar todas las actualizaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="d97c7-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="d97c7-117">Confirme que tiene las contraseñas necesarias para acceder al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="d97c7-118">Administrar BitLocker</span><span class="sxs-lookup"><span data-stu-id="d97c7-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="d97c7-119">Esta sección incluye recomendaciones para las organizaciones que han habilitado el cifrado de BitLocker en las unidades de disco duro.</span><span class="sxs-lookup"><span data-stu-id="d97c7-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="d97c7-120">Para obtener más información, consulte la [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span><span class="sxs-lookup"><span data-stu-id="d97c7-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="d97c7-121">Si el cifrado de BitLocker se deshabilita durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="d97c7-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="d97c7-122">Si el dispositivo se puede descifrar antes de la eliminación y sustitución de SSD, siga estos pasos para desactivar BitLocker:</span><span class="sxs-lookup"><span data-stu-id="d97c7-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="d97c7-123">En **configuración**, escriba **BitLocker** y seleccione **Administrar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="d97c7-124">Seleccione **desactivar BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="d97c7-125">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-125">Power down the device.</span></span> 

### <span data-ttu-id="d97c7-126">Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="d97c7-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="d97c7-127">Si el dispositivo está cifrado antes de la eliminación y sustitución de SSD, siga estos pasos para generar una clave de recuperación de BitLocker y guardarla en almacenamiento USB:</span><span class="sxs-lookup"><span data-stu-id="d97c7-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="d97c7-128">Vaya a **configuración** y escriba **BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="d97c7-129">Seleccione **administrar**  > **clave de recuperación BitLocker generando**BitLocker.</span><span class="sxs-lookup"><span data-stu-id="d97c7-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="d97c7-130">Inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="d97c7-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="d97c7-131">Guarde la clave de recuperación en el almacenamiento USB.</span><span class="sxs-lookup"><span data-stu-id="d97c7-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="d97c7-132">Quite la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="d97c7-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="d97c7-133">Apague el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-133">Power down the device.</span></span> 

## <span data-ttu-id="d97c7-134">Quitar y reemplazar el SSD</span><span class="sxs-lookup"><span data-stu-id="d97c7-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="d97c7-135">Quite la SSD con las instrucciones de la [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440).</span><span class="sxs-lookup"><span data-stu-id="d97c7-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="d97c7-136">Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet por cable.</span><span class="sxs-lookup"><span data-stu-id="d97c7-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="d97c7-137">Encienda el nuevo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-137">Power on the new device.</span></span> <span data-ttu-id="d97c7-138">El dispositivo puede pasar por una actualización de firmware durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="d97c7-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="d97c7-139">Después de la eliminación y sustitución de SSD</span><span class="sxs-lookup"><span data-stu-id="d97c7-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="d97c7-140">Administrar SSDs sin cifrar</span><span class="sxs-lookup"><span data-stu-id="d97c7-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="d97c7-141">Si el SSD sigue sin cifrar durante la transferencia, complete los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="d97c7-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="d97c7-142">Vaya a la contraseña **de opciones de inicio de sesión**  >  **Password** (representada como el icono de llave en el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="d97c7-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="d97c7-143">Escriba la contraseña e inicie sesión pendiente de la autenticación en dos fases (si procede).</span><span class="sxs-lookup"><span data-stu-id="d97c7-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="d97c7-144">Una vez que haya iniciado sesión completamente, vaya a **iniciar**  >  **Account**  >  **sesión**de cuenta.</span><span class="sxs-lookup"><span data-stu-id="d97c7-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="d97c7-145">Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="d97c7-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="d97c7-146">Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD y quiere habilitar BitLocker después de la sustitución, **vaya a BitLocker**  >  **Manage**BitLocker  >  **resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="d97c7-147">Ejecute **SDT** para confirmar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="d97c7-148">Para comprobar la activación de Windows, navegue hasta la activación de la **configuración**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="d97c7-149">Si hay algún mensaje de error, seleccione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="d97c7-150">Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a cuenta de **archivo**  >  **Account** y compruebe si hay algún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d97c7-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="d97c7-151">Administrar SSDs cifradas</span><span class="sxs-lookup"><span data-stu-id="d97c7-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="d97c7-152">Necesitará un segundo dispositivo para leer la clave de recuperación de BitLocker guardada en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="d97c7-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="d97c7-153">Si el SSD seguía cifrado durante la transferencia, completa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d97c7-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="d97c7-154">Inserte la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="d97c7-155">Abra el archivo. txt que contiene la clave de recuperación de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="d97c7-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="d97c7-156">Escriba manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.</span><span class="sxs-lookup"><span data-stu-id="d97c7-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="d97c7-157">Una vez que haya escrito correctamente la clave de recuperación de BitLocker, vaya a contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).</span><span class="sxs-lookup"><span data-stu-id="d97c7-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="d97c7-158">Escribir la contraseña e iniciar sesión, pendiente de la finalización de la autenticación en dos fases (si procede)</span><span class="sxs-lookup"><span data-stu-id="d97c7-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="d97c7-159">Una vez que haya iniciado sesión completamente, vaya a **iniciar**  >  **Account**  >  **sesión**de cuenta.</span><span class="sxs-lookup"><span data-stu-id="d97c7-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="d97c7-160">Vuelva a iniciar sesión con la contraseña y configure Windows Hello y agregue un PIN.</span><span class="sxs-lookup"><span data-stu-id="d97c7-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="d97c7-161">Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD y quiere habilitar BitLocker después de la sustitución, vaya a **configuración**  >  **BitLocker**  >  **Manage**BitLocker  >  **resume BitLocker**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="d97c7-162">Ejecute **SDT** para confirmar la funcionalidad completa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d97c7-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="d97c7-163">Para comprobar la activación de Windows, vaya a activación de **configuración**  >  **Activation**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="d97c7-164">Si hay algún mensaje de error, seleccione **solucionar problemas**.</span><span class="sxs-lookup"><span data-stu-id="d97c7-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="d97c7-165">Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a la cuenta de **archivo**  >  **Account** y compruebe si hay algún mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d97c7-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="d97c7-166">Más información</span><span class="sxs-lookup"><span data-stu-id="d97c7-166">More information</span></span> 

<span data-ttu-id="d97c7-167">Para obtener más información, consulta los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d97c7-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="d97c7-168">Guía de eliminación de rSSD para Enterprise</span><span class="sxs-lookup"><span data-stu-id="d97c7-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="d97c7-169">Guía de recuperación de BitLocker</span><span class="sxs-lookup"><span data-stu-id="d97c7-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="d97c7-170">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="d97c7-170">Still need help?</span></span> <span data-ttu-id="d97c7-171">Vaya a [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d97c7-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
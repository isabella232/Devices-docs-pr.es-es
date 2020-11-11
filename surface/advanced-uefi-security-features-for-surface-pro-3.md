---
title: Características avanzadas de seguridad de UEFI para Surface Pro 3 (Surface)
description: En este artículo se describe cómo instalar y configurar la actualización de UEFI v3.11.760.0 para habilitar las opciones de seguridad adicionales para dispositivos Surface Pro 3.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: seguridad, características, configurar, hardware, dispositivo, personalizado, script, actualizar
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163179"
---
# <span data-ttu-id="6e0ac-104">Características avanzadas de seguridad de UEFI para Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="6e0ac-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="6e0ac-105">En este artículo se describe cómo instalar y configurar la actualización de UEFI v3.11.760.0 para habilitar las opciones de seguridad adicionales para dispositivos Surface Pro 3.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="6e0ac-106">Para abordar un control más detallado de la seguridad de dispositivos Surface, la actualización de UEFI v3.11.760.0 proporciona otras opciones de seguridad que te permiten deshabilitar dispositivos de hardware específicos o impedir el inicio desde esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="6e0ac-107">Después de instalar la actualización de UEFI en un dispositivo, puedes configurarlo automáticamente o manualmente mediante la ejecución de un script.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="6e0ac-108">Instalar manualmente la actualización de UEFI</span><span class="sxs-lookup"><span data-stu-id="6e0ac-108">Manually install the UEFI update</span></span>


<span data-ttu-id="6e0ac-109">Antes de configurar las características de seguridad avanzadas del dispositivo Surface, primero debes instalar la actualización de UEFI v3.11.760.0.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="6e0ac-110">Esta actualización se instalará automáticamente si recibes actualizaciones de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="6e0ac-111">Para obtener más información sobre cómo configurar Windows para actualizarse automáticamente mediante Windows Update, consulta [Cómo configurar y utilizar actualizaciones automáticas en Windows](https://support.microsoft.com/kb/306525).</span><span class="sxs-lookup"><span data-stu-id="6e0ac-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="6e0ac-112">Para actualizar la UEFI en Surface Pro 3, puedes descargar e instalar las actualizaciones de la UEFI de Surface como parte del firmware de Surface Pro 3 y el paquete de controladores.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="6e0ac-113">Este firmware y estos paquetes de controladores están disponibles en la [Página de Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="6e0ac-114">Puedes encontrar más información sobre el firmware y los paquetes de controladores en [Descargar el firmware y los controladores más recientes para los dispositivos de Surface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span><span class="sxs-lookup"><span data-stu-id="6e0ac-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="6e0ac-115">El firmware y los paquetes de controladores están disponibles en formatos Windows Installer (.msi) y de archivo (.zip) independientes.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="6e0ac-116">Puedes encontrar más información sobre estos dos formatos y cómo se pueden usar para actualizar los controladores en [Administrar actualizaciones de controladores y firmware de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span><span class="sxs-lookup"><span data-stu-id="6e0ac-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="6e0ac-117">Configurar manualmente las opciones de seguridad adicionales</span><span class="sxs-lookup"><span data-stu-id="6e0ac-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="6e0ac-118">Para especificar la configuración de firmware en un dispositivo Surface, comienza con el dispositivo apagado, mantén presionado el botón **Subir el volumen**, presiona el botón **inicio/apagado** y suéltalo, y, luego, suelta el botón **Subir el volumen** después de que el dispositivo haya comenzado a arrancar.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="6e0ac-119">Después de instalar la actualización de UEFI v3.11.760.0 en un dispositivo Surface, tendrás disponible un menú de UEFI adicional denominado **Seguridad avanzada del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="6e0ac-120">Si haces clic en este menú, se muestran las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6e0ac-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="6e0ac-121">Opción</span><span class="sxs-lookup"><span data-stu-id="6e0ac-121">Option</span></span>         | <span data-ttu-id="6e0ac-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e0ac-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="6e0ac-123">Opciones de configuración disponibles (las predeterminadas se indican con negrita)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="6e0ac-124">Arranque de red</span><span class="sxs-lookup"><span data-stu-id="6e0ac-124">Network Boot</span></span>   | <span data-ttu-id="6e0ac-125">Habilita o deshabilita la capacidad del dispositivo Surface de arrancar desde la red (también conocida como el arranque PXE).</span><span class="sxs-lookup"><span data-stu-id="6e0ac-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="6e0ac-126">**Habilitado**, No de arranque</span><span class="sxs-lookup"><span data-stu-id="6e0ac-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="6e0ac-127">USB lateral</span><span class="sxs-lookup"><span data-stu-id="6e0ac-127">Side USB</span></span>       | <span data-ttu-id="6e0ac-128">Habilita o deshabilita el puerto USB en el lateral del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="6e0ac-129">Además, el puerto USB se puede habilitar, pero no permite arrancar.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="6e0ac-130">**Habilitado**, No de arranque, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="6e0ac-131">Puerto de acoplamiento</span><span class="sxs-lookup"><span data-stu-id="6e0ac-131">Docking Port</span></span>   | <span data-ttu-id="6e0ac-132">Habilita o deshabilita los puertos en la base de acoplamiento de Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="6e0ac-133">Además, el puerto de acoplamiento se puede habilitar, pero bloquea el arranque desde cualquier puerto USB o Ethernet en la estación de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="6e0ac-134">**Habilitado**, No de arranque, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="6e0ac-135">Cámara frontal</span><span class="sxs-lookup"><span data-stu-id="6e0ac-135">Front Camera</span></span>   | <span data-ttu-id="6e0ac-136">Habilita o deshabilita la cámara en la parte frontal del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="6e0ac-137">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="6e0ac-138">Cámara trasera</span><span class="sxs-lookup"><span data-stu-id="6e0ac-138">Rear Camera</span></span>    | <span data-ttu-id="6e0ac-139">Habilita o deshabilita la cámara en la parte trasera del dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="6e0ac-140">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="6e0ac-141">Audio integrado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-141">On Board Audio</span></span> | <span data-ttu-id="6e0ac-142">Habilita o deshabilita el audio en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="6e0ac-143">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="6e0ac-144">microSD</span><span class="sxs-lookup"><span data-stu-id="6e0ac-144">microSD</span></span>        | <span data-ttu-id="6e0ac-145">Habilita o deshabilita la ranura microSD en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="6e0ac-146">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="6e0ac-147">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6e0ac-147">WiFi</span></span>           | <span data-ttu-id="6e0ac-148">Habilita o deshabilita el transceptor Wi-Fi integrado en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="6e0ac-149">Esto deshabilita también Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="6e0ac-150">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="6e0ac-151">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="6e0ac-151">Bluetooth</span></span>      | <span data-ttu-id="6e0ac-152">Habilita o deshabilita el transceptor Bluetooth integrado en el dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="6e0ac-153">**Habilitado**, Deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="6e0ac-154">Automatizar la configuración de seguridad adicional</span><span class="sxs-lookup"><span data-stu-id="6e0ac-154">Automate additional security settings</span></span>


<span data-ttu-id="6e0ac-155">Como profesional de TI con privilegios administrativos, puedes automatizar la configuración de las opciones de UEFI aprovechando [Surface Pro 3 Firmware Tools (KB 476)](https://go.microsoft.com/fwlink/p/?LinkID=618038) disponible desde el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="6e0ac-156">Estas herramientas instalan a un ensamblado .NET que se puede llamar desde cualquier aplicación o script personalizados.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="6e0ac-157">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6e0ac-157">Prerequisites</span></span>**

-   <span data-ttu-id="6e0ac-158">Los scripts de muestra a continuación aprovechan la extensión mencionada anteriormente y, por tanto, suponen que la herramienta se ha instalado en el dispositivo que se administra.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="6e0ac-159">Los scripts se deben ejecutar con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="6e0ac-160">Se debe llamar al comando de Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) antes de ejecutar scripts de muestra si no están firmados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="6e0ac-161">Scripts de muestra</span><span class="sxs-lookup"><span data-stu-id="6e0ac-161">Sample scripts</span></span>**

> [!NOTE]
> <span data-ttu-id="6e0ac-162">La contraseña de UEFI usada en los scripts de muestra a continuación se presenta en texto sin cifrar.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-162">The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="6e0ac-163">Te recomendamos encarecidamente guardar los scripts en un lugar protegido y los ejecutes en un entorno controlado.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="6e0ac-164">Mostrar todas las opciones configurables:</span><span class="sxs-lookup"><span data-stu-id="6e0ac-164">Show all configurable options:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

<span data-ttu-id="6e0ac-165">Establecer o cambiar la contraseña de UEFI:</span><span class="sxs-lookup"><span data-stu-id="6e0ac-165">Set or change UEFI password:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="6e0ac-166">Comprobar el estado de los cambios propuestos:</span><span class="sxs-lookup"><span data-stu-id="6e0ac-166">Check status of proposed changes:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

<span data-ttu-id="6e0ac-167">Revertir UEFI con valores predeterminados:</span><span class="sxs-lookup"><span data-stu-id="6e0ac-167">Revert UEFI to default values:</span></span>

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

<span data-ttu-id="6e0ac-168">Interpretación del código de estado</span><span class="sxs-lookup"><span data-stu-id="6e0ac-168">Status code interpretation</span></span>

-   <span data-ttu-id="6e0ac-169">00: La actualización propuesta se instaló correctamente</span><span class="sxs-lookup"><span data-stu-id="6e0ac-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="6e0ac-170">02: Uno de los valores propuestos tenía un valor no válido</span><span class="sxs-lookup"><span data-stu-id="6e0ac-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="6e0ac-171">03: Había un conjunto de valores propuesto que no se había reconocido</span><span class="sxs-lookup"><span data-stu-id="6e0ac-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="6e0ac-172">0F: La contraseña de desbloqueo no coincidió con la contraseña establecida actualmente</span><span class="sxs-lookup"><span data-stu-id="6e0ac-172">0F - The unlock password did not match currently set password</span></span>

 

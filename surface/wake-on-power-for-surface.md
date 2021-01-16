---
title: Cómo habilitar La activación en la alimentación para Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Describe cómo habilitar y deshabilitar La activación en la alimentación para dispositivos Surface.
keywords: update, deploy, implementar, driver, driver, controlador, wake-on-lan, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271564"
---
# <span data-ttu-id="f06e7-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="f06e7-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="f06e7-105">Los dispositivos Surface se pueden apagar mientras estás fuera de tu escritorio o configurarse para hibernar en modo para ahorrar batería.</span><span class="sxs-lookup"><span data-stu-id="f06e7-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="f06e7-106">Para mejorar la capacidad de administración de estos dispositivos, La activación en la alimentación permite que los dispositivos Surface compatibles se inicien automáticamente cuando se vuelvan a conectar a la alimentación.</span><span class="sxs-lookup"><span data-stu-id="f06e7-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="f06e7-107">Para configurar La activación en la alimentación, puedes usar el Modo de administración de Surface Enterprise (SEMM) a través del Configurador de UEFI de Surface o el Administrador de UEFI.</span><span class="sxs-lookup"><span data-stu-id="f06e7-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="f06e7-108">La característica Activar en energía está disponible en los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f06e7-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="f06e7-109">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="f06e7-109">Surface Pro 7+</span></span>
- <span data-ttu-id="f06e7-110">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="f06e7-110">Surface Book 3</span></span>
- <span data-ttu-id="f06e7-111">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="f06e7-111">Surface Pro 7</span></span>
- <span data-ttu-id="f06e7-112">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="f06e7-112">Surface Laptop 3</span></span>
- <span data-ttu-id="f06e7-113">Surface Laptop Go</span><span class="sxs-lookup"><span data-stu-id="f06e7-113">Surface Laptop Go</span></span>
- <span data-ttu-id="f06e7-114">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="f06e7-114">Surface Pro X</span></span> 


## <span data-ttu-id="f06e7-115">Información general y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f06e7-115">Overview and prerequisites</span></span>

<span data-ttu-id="f06e7-116">El Configurador de UEFI de Surface te permite guardar la configuración de UEFI individual en un paquete .msi de Windows Installer para su distribución en dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="f06e7-116">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="f06e7-117">En este artículo se supone que sabe cómo usar SEMM.</span><span class="sxs-lookup"><span data-stu-id="f06e7-117">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="f06e7-118">Para obtener más información, consulta la documentación del Modo [de administración de Surface Enterprise (SEMM).](surface-enterprise-management-mode.md)</span><span class="sxs-lookup"><span data-stu-id="f06e7-118">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="f06e7-119">Para habilitar La activación en la alimentación</span><span class="sxs-lookup"><span data-stu-id="f06e7-119">To enable Wake on Power</span></span>

1.  <span data-ttu-id="f06e7-120">Descarga la versión más reciente de [Surface UEFI Configurator.](https://www.microsoft.com/download/confirmation.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="f06e7-120">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="f06e7-121">Inicia sesión en el dispositivo Surface como administrador, abre el **Configurador de UEFI**de Surface, selecciona **Dispositivos Surface**y, a continuación, **selecciona Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f06e7-121">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecciona Dispositivos Surface y selecciona Siguiente.":::
3.  <span data-ttu-id="f06e7-123">Seleccione **Inicio**y, a continuación, **seleccione Crear en** Paquete de **configuración.**</span><span class="sxs-lookup"><span data-stu-id="f06e7-123">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione Crear paquete de configuración.":::
4.  <span data-ttu-id="f06e7-125">Seleccione **Protección de**certificados y agregue el archivo .pfx del certificado.</span><span class="sxs-lookup"><span data-stu-id="f06e7-125">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="f06e7-126">Escriba su contraseña, seleccione **Siguiente,** agregue **Protección con contraseña,** según corresponda y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f06e7-126">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="f06e7-127">En la **página Elegir el tipo de Surface al** que quieres dirigirte, selecciona los dispositivos de destino según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f06e7-127">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="f06e7-128">Por ejemplo, selecciona **Surface Pro 7.**</span><span class="sxs-lookup"><span data-stu-id="f06e7-128">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="f06e7-129">En la **página Características avanzadas,** seleccione **Activar al**encender , establezca la característica en **Activar**y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f06e7-129">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Activar al activar y establecer en Activar."::: 
8.  <span data-ttu-id="f06e7-131">En la **página Correcto,** seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f06e7-131">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f06e7-132">Si es la primera vez que proporcionas la configuración al dispositivo, también se te pedirá que proporciones los dos últimos caracteres de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="f06e7-132">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="f06e7-133">Guarde el paquete .msi.</span><span class="sxs-lookup"><span data-stu-id="f06e7-133">Save the .msi package.</span></span> 

## <span data-ttu-id="f06e7-134">Aplicar el paquete MSI</span><span class="sxs-lookup"><span data-stu-id="f06e7-134">Apply the MSI package</span></span> 

<span data-ttu-id="f06e7-135">Puedes aplicar el paquete MSI a dispositivos de toda la red mediante herramientas de distribución de software como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f06e7-135">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f06e7-136">Este procedimiento incluye pasos para instalar el paquete en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="f06e7-136">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="f06e7-137">En un símbolo del sistema con privilegios elevados, escriba la ruta de acceso completa del archivo .msi para ejecutar el paquete .msi.</span><span class="sxs-lookup"><span data-stu-id="f06e7-137">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="f06e7-138">En el **cuadro de** diálogo Advertencia, selecciona **Aceptar** o deshabilita BitLocker, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f06e7-138">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecciona Aceptar o deshabilita BitLocker según corresponda.":::
3.  <span data-ttu-id="f06e7-140">En la página principal, selecciona **Siguiente** para ejecutar el paquete y aplicar la configuración de UEFI recién configurada.</span><span class="sxs-lookup"><span data-stu-id="f06e7-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Una de las páginas de bienvenida, seleccione Siguiente.":::
4.  <span data-ttu-id="f06e7-142">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f06e7-142">Restart your device.</span></span> 

<span data-ttu-id="f06e7-143">La activación en la alimentación ya está configurada.</span><span class="sxs-lookup"><span data-stu-id="f06e7-143">Wake on Power is now configured.</span></span> <span data-ttu-id="f06e7-144">Para probar la configuración, apaga el dispositivo, desconecta la alimentación y, a continuación, vuelve a conectar la energía.</span><span class="sxs-lookup"><span data-stu-id="f06e7-144">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="f06e7-145">El dispositivo debe iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f06e7-145">The device should start automatically.</span></span> 

## <span data-ttu-id="f06e7-146">Referencias</span><span class="sxs-lookup"><span data-stu-id="f06e7-146">References</span></span>

<span data-ttu-id="f06e7-147">Para obtener más información, vea los artículos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f06e7-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="f06e7-148">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="f06e7-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="f06e7-149">Activar en LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="f06e7-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="f06e7-150">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="f06e7-150">Still need help?</span></span> <span data-ttu-id="f06e7-151">Vaya a [Microsoft Community.](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f06e7-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
---
title: Cómo habilitar la reactivación de energía para Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Describe cómo habilitar y deshabilitar Wake on Power para dispositivos Surface.
keywords: actualizar, implementar, controlador, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114578"
---
# <span data-ttu-id="cb717-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="cb717-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="cb717-105">Los dispositivos de Surface se pueden apagar mientras está lejos de la oficina o en modo de hibernación para ahorrar vida de la batería.</span><span class="sxs-lookup"><span data-stu-id="cb717-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="cb717-106">Para mejorar la capacidad de administración de estos dispositivos, Wake on Power permite que los dispositivos de Surface compatibles se inicien de forma automática cuando se vuelven a conectar a la alimentación.</span><span class="sxs-lookup"><span data-stu-id="cb717-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="cb717-107">Para configurar la Wake on Power, puede usar el modo de administración de la empresa de Surface (SEMM), ya sea a través del configurador Surface UEFI o el administrador UEFI.</span><span class="sxs-lookup"><span data-stu-id="cb717-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="cb717-108">La característica Wake on Power está disponible en los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="cb717-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="cb717-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="cb717-109">Surface Book 3</span></span>
- <span data-ttu-id="cb717-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cb717-110">Surface Pro 7</span></span>
- <span data-ttu-id="cb717-111">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="cb717-111">Surface Laptop 3</span></span>
- <span data-ttu-id="cb717-112">Portátil Surface Go</span><span class="sxs-lookup"><span data-stu-id="cb717-112">Surface Laptop Go</span></span>
- <span data-ttu-id="cb717-113">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="cb717-113">Surface Pro X</span></span> 


## <span data-ttu-id="cb717-114">Información general y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cb717-114">Overview and prerequisites</span></span>

<span data-ttu-id="cb717-115">El configurador de Surface UEFI le permite guardar la configuración de UEFI individual en un paquete. msi de Windows Installer para distribuirlo a los dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="cb717-115">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="cb717-116">En este artículo se da por supuesto que sabe cómo usar SEMM.</span><span class="sxs-lookup"><span data-stu-id="cb717-116">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="cb717-117">Para obtener más información, consulte la documentación del [modo de administración de Surface Enterprise (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="cb717-117">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="cb717-118">Para habilitar Wake on Power</span><span class="sxs-lookup"><span data-stu-id="cb717-118">To enable Wake on Power</span></span>

1.  <span data-ttu-id="cb717-119">Descarga la última versión del [configurador de Surface UEFI](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="cb717-119">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="cb717-120">Inicie sesión en el dispositivo Surface como administrador, Abra **Surface configurador UEFI**, seleccione **Surface Devices**y, después, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cb717-120">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
3.  <span data-ttu-id="cb717-122">Seleccione **Inicio**y, a continuación, haga clic en **crear** en **paquete de configuración**.</span><span class="sxs-lookup"><span data-stu-id="cb717-122">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
4.  <span data-ttu-id="cb717-124">Seleccione **protección de certificado**y agregue el archivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="cb717-124">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="cb717-125">Escriba la contraseña, seleccione **siguiente**, agregar **protección con contraseña**, según corresponda y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cb717-125">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="cb717-126">En la página **elegir el tipo de superficie que desea dirigir** , seleccione los dispositivos de destino según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cb717-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="cb717-127">Por ejemplo, seleccione **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="cb717-127">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="cb717-128">En la página **características avanzadas** , seleccione **Wake on Power**, establezca la característica **en activado**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="cb717-128">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Surface Devices y haga clic en siguiente."::: 
8.  <span data-ttu-id="cb717-130">En la página **correcta** , seleccione **fin**.</span><span class="sxs-lookup"><span data-stu-id="cb717-130">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb717-131">Si esta es la primera vez que proporciona la configuración a su dispositivo, se le pedirá que proporcione también los dos últimos caracteres de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="cb717-131">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="cb717-132">Guarde el paquete. msi.</span><span class="sxs-lookup"><span data-stu-id="cb717-132">Save the .msi package.</span></span> 

## <span data-ttu-id="cb717-133">Aplicar el paquete MSI</span><span class="sxs-lookup"><span data-stu-id="cb717-133">Apply the MSI package</span></span> 

<span data-ttu-id="cb717-134">Puede aplicar el paquete MSI a dispositivos en la red mediante herramientas de distribución de software como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cb717-134">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="cb717-135">Este procedimiento incluye pasos para instalar el paquete en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="cb717-135">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="cb717-136">En un símbolo del sistema con privilegios elevados, escriba la ruta de acceso completa del archivo. msi para ejecutar el paquete. msi.</span><span class="sxs-lookup"><span data-stu-id="cb717-136">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="cb717-137">En el cuadro de diálogo de **ADVERTENCIA** , seleccione **Aceptar** o deshabilitar BitLocker, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cb717-137">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
3.  <span data-ttu-id="cb717-139">En la Página principal, seleccione **siguiente** para ejecutar el paquete y aplicar la configuración UEFI recién configurado.</span><span class="sxs-lookup"><span data-stu-id="cb717-139">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
4.  <span data-ttu-id="cb717-141">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cb717-141">Restart your device.</span></span> 

<span data-ttu-id="cb717-142">La Wake on Power ya está configurada.</span><span class="sxs-lookup"><span data-stu-id="cb717-142">Wake on Power is now configured.</span></span> <span data-ttu-id="cb717-143">Para probar la configuración, apague el dispositivo, desconecte la energía y, a continuación, vuelva a conectar la energía.</span><span class="sxs-lookup"><span data-stu-id="cb717-143">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="cb717-144">El dispositivo debe iniciarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cb717-144">The device should start automatically.</span></span> 

## <span data-ttu-id="cb717-145">Referencias</span><span class="sxs-lookup"><span data-stu-id="cb717-145">References</span></span>

<span data-ttu-id="cb717-146">Para obtener más información, consulte los artículos siguientes.</span><span class="sxs-lookup"><span data-stu-id="cb717-146">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="cb717-147">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="cb717-147">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="cb717-148">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="cb717-148">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="cb717-149">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="cb717-149">Still need help?</span></span> <span data-ttu-id="cb717-150">Vaya a [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cb717-150">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
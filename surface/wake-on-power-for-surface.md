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
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903051"
---
# <span data-ttu-id="bec62-104">Wake on Power para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="bec62-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="bec62-105">Los dispositivos Surface pueden apagarse fuera del escritorio o establecerse en el modo de hibernación para ahorrar batería.</span><span class="sxs-lookup"><span data-stu-id="bec62-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="bec62-106">Para mejorar la capacidad de administración de estos dispositivos, Wake on Power permite que los dispositivos de Surface compatibles se inicien automáticamente cuando vuelvan a conectarse a la energía.</span><span class="sxs-lookup"><span data-stu-id="bec62-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="bec62-107">Para configurar Wake on Power necesita usar el modo de administración de Surface Enterprise (SEMM), ya sea mediante el configurador Surface UEFI o el administrador UEFI.</span><span class="sxs-lookup"><span data-stu-id="bec62-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="bec62-108">Wake on Power es una característica disponible en los siguientes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="bec62-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="bec62-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="bec62-109">Surface Book 3</span></span>
- <span data-ttu-id="bec62-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="bec62-110">Surface Pro 7</span></span>
- <span data-ttu-id="bec62-111">Portátil Surface 3</span><span class="sxs-lookup"><span data-stu-id="bec62-111">Surface Laptop 3</span></span>
- <span data-ttu-id="bec62-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="bec62-112">Surface Pro X</span></span> 

## <span data-ttu-id="bec62-113">Información general y requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bec62-113">Overview and prerequisites</span></span>

<span data-ttu-id="bec62-114">Puede usar el configurador de superficie UEFI para configurar las opciones de UEFI individuales que se guardan en un paquete. msi de Windows Installer para su distribución en dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="bec62-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="bec62-115">En este artículo se da por supuesto que ya está familiarizado con el uso de SEMM.</span><span class="sxs-lookup"><span data-stu-id="bec62-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="bec62-116">Para obtener más información, consulte la documentación del [modo de administración de Surface Enterprise (SEMM)](surface-enterprise-management-mode.md) .</span><span class="sxs-lookup"><span data-stu-id="bec62-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="bec62-117">Para habilitar Wake on Power</span><span class="sxs-lookup"><span data-stu-id="bec62-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="bec62-118">Descarga la última versión del [configurador de Surface UEFI](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span><span class="sxs-lookup"><span data-stu-id="bec62-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="bec62-119">Inicia sesión en el dispositivo Surface como administrador, abre el **configurador UEFI de Surface**, selecciona **Surface Devices**y, a continuación, haz clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bec62-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
3.  <span data-ttu-id="bec62-121">Seleccione **Inicio** y, a continuación, en **paquete de configuración** , seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="bec62-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione crear paquete de configuración.":::
4.  <span data-ttu-id="bec62-123">Seleccione **protección de certificado** y agregue el archivo. pfx de certificado.</span><span class="sxs-lookup"><span data-stu-id="bec62-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="bec62-124">Después de escribir la contraseña, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bec62-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="bec62-125">Agregar **protección con contraseña**, según corresponda y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bec62-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="bec62-126">En la página **elegir el tipo de superficie que desea dirigir** , seleccione los dispositivos de destino según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bec62-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="bec62-127">Por ejemplo, **Surface Pro 7**.</span><span class="sxs-lookup"><span data-stu-id="bec62-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="bec62-128">En la página **características avanzadas** , seleccione **Wake on Power** y establezca en **activado**.</span><span class="sxs-lookup"><span data-stu-id="bec62-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="bec62-129">Selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bec62-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Wake on Power y establezca la configuración en activado."::: 
7.  <span data-ttu-id="bec62-131">En la página **correcta** , seleccione **fin**.</span><span class="sxs-lookup"><span data-stu-id="bec62-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="bec62-132">Si es la primera vez que proporciona una configuración a su dispositivo, se le pedirá que proporcione los dos últimos caracteres de la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="bec62-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="bec62-133">Guarde el paquete. msi.</span><span class="sxs-lookup"><span data-stu-id="bec62-133">Save the .msi package.</span></span> 

## <span data-ttu-id="bec62-134">Aplicar el paquete MSI</span><span class="sxs-lookup"><span data-stu-id="bec62-134">Apply the MSI package</span></span> 

<span data-ttu-id="bec62-135">Puede aplicar el paquete MSI a dispositivos de la red con herramientas de distribución de software como Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bec62-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="bec62-136">Este procedimiento incluye pasos para instalar el paquete en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="bec62-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="bec62-137">Abra un símbolo del sistema con privilegios elevados y escriba la ruta de acceso completa del archivo. msi para ejecutar el paquete. msi.</span><span class="sxs-lookup"><span data-stu-id="bec62-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="bec62-138">En el cuadro de diálogo de **ADVERTENCIA** , seleccione **Aceptar** o deshabilitar BitLocker según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bec62-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Seleccione Aceptar o deshabilitar BitLocker según corresponda.":::
3.  <span data-ttu-id="bec62-140">En la Página principal, seleccione **siguiente** para ejecutar el paquete y aplicar la configuración UEFI recién configurado.</span><span class="sxs-lookup"><span data-stu-id="bec62-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="En la Página principal, seleccione siguiente.":::
4.  <span data-ttu-id="bec62-142">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bec62-142">Restart your device.</span></span> 

<span data-ttu-id="bec62-143">La Wake on Power ya está configurada.</span><span class="sxs-lookup"><span data-stu-id="bec62-143">Wake on Power is now configured.</span></span> <span data-ttu-id="bec62-144">Para probar la configuración, apague el dispositivo, desconecte la energía y, a continuación, vuelva a conectar la energía.</span><span class="sxs-lookup"><span data-stu-id="bec62-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="bec62-145">El dispositivo se iniciará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bec62-145">The device will start automatically.</span></span> 

## <span data-ttu-id="bec62-146">Más información</span><span class="sxs-lookup"><span data-stu-id="bec62-146">More information</span></span>

<span data-ttu-id="bec62-147">Para obtener más información, consulte los artículos siguientes.</span><span class="sxs-lookup"><span data-stu-id="bec62-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="bec62-148">Modo de administración de Surface Enterprise</span><span class="sxs-lookup"><span data-stu-id="bec62-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="bec62-149">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="bec62-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="bec62-150">¿Aún necesitas ayuda?</span><span class="sxs-lookup"><span data-stu-id="bec62-150">Still need help?</span></span> <span data-ttu-id="bec62-151">Vaya a [Microsoft Community](https://answers.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bec62-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>
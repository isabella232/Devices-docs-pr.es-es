---
title: Proteger y administrar Surface Hub 2S con SEMM
description: Más información sobre cómo proteger Surface Hub 2S con SEMM.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835273"
---
# <span data-ttu-id="74a43-104">Proteger y administrar Surface Hub 2S con SEMM y UEFI</span><span class="sxs-lookup"><span data-stu-id="74a43-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="74a43-105">Nuevo en Surface Hub 2S, puede usar SEMM para administrar la configuración de UEFI del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74a43-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="74a43-106">Use el configurador de Microsoft Surface UEFI para controlar los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="74a43-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="74a43-107">LAN de cable</span><span class="sxs-lookup"><span data-stu-id="74a43-107">Wired LAN</span></span>
- <span data-ttu-id="74a43-108">Cámaras</span><span class="sxs-lookup"><span data-stu-id="74a43-108">Cameras</span></span>
- <span data-ttu-id="74a43-109">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="74a43-109">Bluetooth</span></span>
- <span data-ttu-id="74a43-110">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="74a43-110">Wi-Fi</span></span>
- <span data-ttu-id="74a43-111">Sensor de ocupación</span><span class="sxs-lookup"><span data-stu-id="74a43-111">Occupancy sensor</span></span>

<span data-ttu-id="74a43-112">Use el configurador UEFI de Microsoft Surface para activar o desactivar los siguientes ajustes de UEFI:</span><span class="sxs-lookup"><span data-stu-id="74a43-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="74a43-113">Arranque</span><span class="sxs-lookup"><span data-stu-id="74a43-113">Boot</span></span>

    - <span data-ttu-id="74a43-114">IPv6 para el arranque PXE</span><span class="sxs-lookup"><span data-stu-id="74a43-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="74a43-115">Arranque alternativo</span><span class="sxs-lookup"><span data-stu-id="74a43-115">Alternate Boot</span></span>
    - <span data-ttu-id="74a43-116">Bloqueo de orden de arranque</span><span class="sxs-lookup"><span data-stu-id="74a43-116">Boot Order Lock</span></span>
    - <span data-ttu-id="74a43-117">Arranque desde USB</span><span class="sxs-lookup"><span data-stu-id="74a43-117">USB Boot</span></span>
- <span data-ttu-id="74a43-118">Página frontal de UEFI</span><span class="sxs-lookup"><span data-stu-id="74a43-118">UEFI Front Page</span></span>

    - <span data-ttu-id="74a43-119">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="74a43-119">Devices</span></span>
    - <span data-ttu-id="74a43-120">Arranque</span><span class="sxs-lookup"><span data-stu-id="74a43-120">Boot</span></span>
    - <span data-ttu-id="74a43-121">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="74a43-121">Date/Time</span></span>

## <span data-ttu-id="74a43-122">Crear imagen de configuración UEFI</span><span class="sxs-lookup"><span data-stu-id="74a43-122">Create UEFI configuration image</span></span>

<span data-ttu-id="74a43-123">A diferencia de otros dispositivos de Surface, no puede usar un archivo MSI o una imagen Win PE para aplicar esta configuración en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="74a43-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="74a43-124">En su lugar, debe crear una imagen USB para cargarla en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74a43-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="74a43-125">Para crear una imagen de configuración UEFI de Surface Hub 2S, descargue e instale la última versión del configurador Microsoft Surface UEFI desde la página [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74a43-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="74a43-126">Para obtener más información sobre el uso de UEFI y SEMM, consulte [modo de administración de Microsoft Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span><span class="sxs-lookup"><span data-stu-id="74a43-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="74a43-127">Para configurar UEFI en Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="74a43-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="74a43-128">Inicie el configurador UEFI y, en la primera pantalla, elija **paquete de configuración**.</span><span class="sxs-lookup"><span data-stu-id="74a43-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* Inicie el configurador UEFI y seleccione paquete de configuración \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="74a43-130">Para agregar el certificado a su paquete, debe tener un certificado válido con la clave privada en un formato de archivo. pfx para firmar y proteger el paquete.</span><span class="sxs-lookup"><span data-stu-id="74a43-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="74a43-131">Seleccione **protección de certificado +.**</span><span class="sxs-lookup"><span data-stu-id="74a43-131">Select **+ Certificate Protection.**</span></span> <br>
![\* Protección de certificados de selección \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="74a43-133">Escriba la contraseña de la clave privada del certificado.</span><span class="sxs-lookup"><span data-stu-id="74a43-133">Enter the certificate’s private key’s password.</span></span><br>
![\* Escriba la contraseña de la clave privada del certificado \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="74a43-135">Después de importar la clave privada, siga creando el paquete.</span><span class="sxs-lookup"><span data-stu-id="74a43-135">After importing the private key, continue creating the package.</span></span><br>
![\* Continuar con la creación del paquete \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="74a43-137">Elija **concentrador** y **Surface Hub 2** como destino para el paquete de configuración UEFI.</span><span class="sxs-lookup"><span data-stu-id="74a43-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* Elige Hub y Surface Hub 2 como destino para el paquete de configuración UEFI \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="74a43-139">Elija los componentes y la configuración que desee activar o desactivar en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="74a43-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* Elija los componentes y la configuración que desea activar o desactivar \*.](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="74a43-141">Use la opción USB para exportar el archivo.</span><span class="sxs-lookup"><span data-stu-id="74a43-141">Use the USB option to export the file.</span></span><br>
![\* Use la opción USB para exportar el archivo \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="74a43-143">Inserta y elige la unidad USB que deseas usar para este paquete.</span><span class="sxs-lookup"><span data-stu-id="74a43-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="74a43-144">La unidad USB tendrá formato y perderá la información que tenga.</span><span class="sxs-lookup"><span data-stu-id="74a43-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* Inserta y elige la unidad USB para tu paquete \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="74a43-146">Una vez que se haya creado el paquete correctamente, el configurador mostrará los dos últimos caracteres de la huella digital de su certificado.</span><span class="sxs-lookup"><span data-stu-id="74a43-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="74a43-147">Estos caracteres se necesitan al importar a la configuración a Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="74a43-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* Configuración correcta del paquete \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="74a43-149">Para arrancar en UEFI</span><span class="sxs-lookup"><span data-stu-id="74a43-149">To boot into UEFI</span></span>

<span data-ttu-id="74a43-150">Desactiva Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="74a43-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="74a43-151">Mantén pulsado el botón **subir el volumen** y pulsa el botón de **encendido** .</span><span class="sxs-lookup"><span data-stu-id="74a43-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="74a43-152">Mantenga pulsado el botón subir el volumen hasta que aparezca el menú UEFI.</span><span class="sxs-lookup"><span data-stu-id="74a43-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>

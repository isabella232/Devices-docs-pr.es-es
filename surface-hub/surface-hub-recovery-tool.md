---
title: Uso de la herramienta de recuperación de Surface Hub
description: Cómo usar la herramienta de recuperación de Surface hub para volver a crear una imagen de SSD.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: administrar Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836894"
---
# <span data-ttu-id="fa24d-104">Uso de la herramienta de recuperación de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa24d-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="fa24d-105">La [herramienta de recuperación de Surface Hub de Microsoft](https://www.microsoft.com/download/details.aspx?id=52210) le ayuda a volver a crear una imagen de la unidad de estado sólido (SSD) del concentrador de Surface con un dispositivo de escritorio Windows 10, sin llamar a soporte técnico ni reemplazar el SSD.</span><span class="sxs-lookup"><span data-stu-id="fa24d-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="fa24d-106">Con esta herramienta, puede rehacer la imagen de una SSD que tiene una contraseña de administrador desconocida, errores de inicio, que no pudo completar una recuperación de la nube o para un dispositivo que tiene una versión anterior del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fa24d-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="fa24d-107">La herramienta no solucionará la SSDs físicamente dañada.</span><span class="sxs-lookup"><span data-stu-id="fa24d-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="fa24d-108">Para volver a crear una imagen de la SSD del Surface Hub con la herramienta de recuperación, tendrá que quitar el SSD de Surface Hub, conectar la unidad al cable USB a SATA y, a continuación, conectar el cable al equipo de escritorio en el que está instalada la herramienta de recuperación.</span><span class="sxs-lookup"><span data-stu-id="fa24d-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="fa24d-109">Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, consulte [sustitución de SSD en Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="fa24d-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa24d-110">No deje que el dispositivo pase al estado de suspensión o interrumpa la descarga del archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="fa24d-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="fa24d-111">Si la herramienta no se completa correctamente, póngase en contacto [con el soporte técnico de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="fa24d-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="fa24d-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fa24d-112">Prerequisites</span></span>

### <span data-ttu-id="fa24d-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="fa24d-113">Mandatory</span></span>

- <span data-ttu-id="fa24d-114">EQUIPO host que ejecuta la versión de 64 bits de Windows 10, versión 1607 o superior.</span><span class="sxs-lookup"><span data-stu-id="fa24d-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="fa24d-115">Acceso a Internet</span><span class="sxs-lookup"><span data-stu-id="fa24d-115">Internet access</span></span>
- <span data-ttu-id="fa24d-116">Puerto USB 2,0 o superior abierto</span><span class="sxs-lookup"><span data-stu-id="fa24d-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="fa24d-117">Cable USB a SATA</span><span class="sxs-lookup"><span data-stu-id="fa24d-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="fa24d-118">10 GB de espacio libre en el disco del equipo host</span><span class="sxs-lookup"><span data-stu-id="fa24d-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="fa24d-119">SSDs se distribuyó con Surface Hub o un SSD proporcionado por el soporte técnico como reemplazo.</span><span class="sxs-lookup"><span data-stu-id="fa24d-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="fa24d-120">SSDs no suministrado por Microsoft no es compatible.</span><span class="sxs-lookup"><span data-stu-id="fa24d-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="fa24d-121">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="fa24d-121">Recommended</span></span>

- <span data-ttu-id="fa24d-122">Conexión a Internet de alta velocidad</span><span class="sxs-lookup"><span data-stu-id="fa24d-122">High-speed Internet connection</span></span>
- <span data-ttu-id="fa24d-123">Puerto USB 3,0 abierto</span><span class="sxs-lookup"><span data-stu-id="fa24d-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="fa24d-124">Cable USB 3,0 o superior USB a SATA</span><span class="sxs-lookup"><span data-stu-id="fa24d-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="fa24d-125">La herramienta de creación de imágenes se probó con la siguiente marca y modelo de cables:</span><span class="sxs-lookup"><span data-stu-id="fa24d-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="fa24d-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="fa24d-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="fa24d-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="fa24d-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="fa24d-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="fa24d-128">Ugreen 20231</span></span>

## <span data-ttu-id="fa24d-129">Descargar la herramienta de recuperación de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa24d-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="fa24d-130">La herramienta de recuperación de Surface Hub está disponible para su descarga desde las [herramientas de Surface hub para ello](https://www.microsoft.com/download/details.aspx?id=52210) bajo el nombre de archivo **SurfaceHub_Recovery_v1.14.137.0.msi**.</span><span class="sxs-lookup"><span data-stu-id="fa24d-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v1.14.137.0.msi**.</span></span>

<span data-ttu-id="fa24d-131">Para iniciar la descarga, haga clic en **Descargar**, elija **SurfaceHub_Recovery_v1.14.137.0.msi** de la lista y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fa24d-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v1.14.137.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="fa24d-132">En el menú emergente, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fa24d-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="fa24d-133">Haga clic en **Ejecutar** para iniciar la instalación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fa24d-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="fa24d-134">Haga clic en **Guardar** para copiar la descarga en el equipo para su instalación posterior.</span><span class="sxs-lookup"><span data-stu-id="fa24d-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="fa24d-135">Instale la herramienta de recuperación de Surface Hub en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="fa24d-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="fa24d-136">Ejecutar la herramienta de recuperación de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fa24d-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="fa24d-137">En el equipo host, seleccione el botón **Inicio** , desplácese por la lista alfabética de la izquierda y seleccione el método abreviado de la herramienta de recuperación.</span><span class="sxs-lookup"><span data-stu-id="fa24d-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Acceso directo a la herramienta de recuperación de Surface Hub de Microsoft](images/shrt-shortcut.png)

2. <span data-ttu-id="fa24d-139">Haz clic en **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="fa24d-139">Click **Start**.</span></span>

    ![Botón Inicio de la herramienta de recuperación](images/shrt-start.png)

3. <span data-ttu-id="fa24d-141">En la ventana de **guías** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fa24d-141">In the **Guidance** window, click **Next**.</span></span>

    ![No deje que su equipo pase a la guía de suspensión](images/shrt-guidance.png)

4. <span data-ttu-id="fa24d-143">Haga clic en **sí** para descargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="fa24d-143">click **Yes** to download the image.</span></span> <span data-ttu-id="fa24d-144">La descarga de la imagen de recuperación depende de la velocidad de conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="fa24d-144">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="fa24d-145">En una conexión corporativa media, la descarga del archivo de imagen de 8 GB puede tardar hasta una hora.</span><span class="sxs-lookup"><span data-stu-id="fa24d-145">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![¿Descargar la imagen?](images/shrt-download.png)

5. <span data-ttu-id="fa24d-147">Una vez completada la descarga, la herramienta le indica que conecte una unidad SSD.</span><span class="sxs-lookup"><span data-stu-id="fa24d-147">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="fa24d-148">Si la herramienta no puede ubicar la unidad conectada, existe la posibilidad de que el cable utilizado no informe al nombre de la SSD en Windows.</span><span class="sxs-lookup"><span data-stu-id="fa24d-148">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="fa24d-149">La herramienta de creación de imágenes debe encontrar el nombre de la unidad como "dispositivo USB LITEon L CH-128V2S" antes de que pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="fa24d-149">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="fa24d-150">Para obtener más información sobre cómo quitar la unidad existente de su Surface Hub, consulte [sustitución de SSD en Surface Hub](surface-hub-ssd-replacement.md).</span><span class="sxs-lookup"><span data-stu-id="fa24d-150">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![Conectar SSD](images/shrt-drive.png)

6. <span data-ttu-id="fa24d-152">Cuando se reconozca la unidad, haga clic en **iniciar** para comenzar el proceso de creación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="fa24d-152">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="fa24d-153">En la advertencia de que se borrarán todos los datos de la unidad, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fa24d-153">On the warning that all data on the drive will be erased, click **OK**.</span></span>

    ![Iniciar la creación de imágenes de SSD](images/shrt-drive-start.png)

    <span data-ttu-id="fa24d-155">Antes de aplicar la imagen del sistema a la unidad, se vuelve a particionar y formatear SSD.</span><span class="sxs-lookup"><span data-stu-id="fa24d-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="fa24d-156">La copia de los archivos binarios del sistema tardará aproximadamente 30 minutos, pero puede tardar más tiempo en función de la velocidad de su bus USB, el cable que se usa o el software antivirus instalado en su sistema.</span><span class="sxs-lookup"><span data-stu-id="fa24d-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>

    ![Copia finalizada](images/shrt-done.png)

    ![Recreación de imágenes completada](images/shrt-complete.png)

## <span data-ttu-id="fa24d-159">Solución de problemas y problemas comunes</span><span class="sxs-lookup"><span data-stu-id="fa24d-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="fa24d-160">Problema</span><span class="sxs-lookup"><span data-stu-id="fa24d-160">Issue</span></span> | <span data-ttu-id="fa24d-161">Notas</span><span class="sxs-lookup"><span data-stu-id="fa24d-161">Notes</span></span>
--- | ---
<span data-ttu-id="fa24d-162">La herramienta no puede hacer una imagen de la SSD</span><span class="sxs-lookup"><span data-stu-id="fa24d-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="fa24d-163">Asegúrate de estar usando un SSD suministrado por fábrica y uno de los cables probados.</span><span class="sxs-lookup"><span data-stu-id="fa24d-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="fa24d-164">El proceso de recreación de imágenes aparece detenido o inmovilizado</span><span class="sxs-lookup"><span data-stu-id="fa24d-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="fa24d-165">Es seguro cerrar y reiniciar la herramienta de recuperación de Surface Hub sin ningún efecto indebido a la SSD.</span><span class="sxs-lookup"><span data-stu-id="fa24d-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="fa24d-166">La herramienta no reconoce la unidad</span><span class="sxs-lookup"><span data-stu-id="fa24d-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="fa24d-167">Verifica que la SSD del Surface Hub se Enumere como una unidad Lite-on, "dispositivo USB LITE-CH de 128V2S".</span><span class="sxs-lookup"><span data-stu-id="fa24d-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="fa24d-168">Si la unidad se reconoce como otro dispositivo con nombre, el cable actual no es compatible.</span><span class="sxs-lookup"><span data-stu-id="fa24d-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="fa24d-169">Prueba otro cable o uno de los cables probados mencionados arriba.</span><span class="sxs-lookup"><span data-stu-id="fa24d-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="fa24d-170">Error:-2147024809</span><span class="sxs-lookup"><span data-stu-id="fa24d-170">Error: -2147024809</span></span> | <span data-ttu-id="fa24d-171">Abra Disk Manager y quite las particiones de la unidad Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="fa24d-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="fa24d-172">Desconecte y vuelva a conectar la unidad al equipo host.</span><span class="sxs-lookup"><span data-stu-id="fa24d-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="fa24d-173">Vuelva a iniciar la herramienta de creación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="fa24d-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="fa24d-174">Si la herramienta no se completa correctamente, póngase en contacto [con el soporte técnico de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span><span class="sxs-lookup"><span data-stu-id="fa24d-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

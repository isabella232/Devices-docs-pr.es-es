---
title: Actualización de firmware de Microsoft Surface Dock 1
description: En este artículo se explica cómo usar Microsoft Surface Dock Firmware Update para instalar y administrar el firmware en Surface Dock 1 original. Cuando se instale en el dispositivo Surface, actualizará los dispositivos Surface Dock 1 conectados al dispositivo Surface.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319214"
---
# <span data-ttu-id="e5f00-104">Actualización de firmware de Microsoft Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5f00-105">Este artículo contiene instrucciones técnicas para los administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="e5f00-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="e5f00-106">Si eres un usuario principal, consulta Cómo actualizar el firmware de [Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)en el sitio de soporte técnico de   Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5f00-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="e5f00-107">Las instrucciones del sitio de soporte técnico son las mismas que las que se indican a continuación, pero este artículo contiene información adicional para supervisar, comprobar e implementar la actualización en varios dispositivos de una red.</span><span class="sxs-lookup"><span data-stu-id="e5f00-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="e5f00-108">En este artículo se explica cómo usar Microsoft Surface Dock Firmware Update para instalar y administrar el firmware en Surface Dock 1 original.</span><span class="sxs-lookup"><span data-stu-id="e5f00-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="e5f00-109">Cuando se instale en el dispositivo Surface, actualizará los dispositivos Surface Dock 1 conectados al dispositivo Surface.</span><span class="sxs-lookup"><span data-stu-id="e5f00-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f00-110">Este artículo no se aplica a Surface Dock 2, que recibe actualizaciones automáticamente a través de Windows Update o mediante Microsoft Endpoint Configuration Manager u otras herramientas de implementación de MSI.</span><span class="sxs-lookup"><span data-stu-id="e5f00-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="e5f00-111">Para obtener más información, consulta [Novedades de Surface Dock.](surface-dock-whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="e5f00-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="e5f00-112">Esta herramienta reemplaza a la anterior herramienta Microsoft Surface Dock Updater, que anteriormente estaba disponible para su descarga como parte de Surface Tools para TI.</span><span class="sxs-lookup"><span data-stu-id="e5f00-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="e5f00-113">La herramienta anterior se llamaba Surface_Dock_Updater_vx.xx.xxx.x.msi (donde x indica el número de versión) y ya no está disponible para su descarga y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e5f00-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <a name="install-the-surface-dock-firmware-update"></a><span data-ttu-id="e5f00-114">Instalar la actualización de firmware de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="e5f00-115">En esta sección se describe cómo instalar manualmente la actualización de firmware.</span><span class="sxs-lookup"><span data-stu-id="e5f00-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f00-116">Microsoft publica periódicamente nuevas versiones de La actualización de firmware de Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="e5f00-117">El archivo MSI no se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e5f00-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="e5f00-118">Si has implementado msi en dispositivos Surface y se lanza una nueva versión del firmware, deberás implementar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e5f00-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="e5f00-119">Descargar e instalar [la actualización de firmware de Microsoft Surface Dock.](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="e5f00-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="e5f00-120">La actualización requiere un dispositivo Surface que ejecute Windows 10, versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e5f00-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="e5f00-121">Instalar el archivo MSI puede solicitarte que reinicies Surface.</span><span class="sxs-lookup"><span data-stu-id="e5f00-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="e5f00-122">Sin embargo, no es necesario reiniciar para realizar la actualización.</span><span class="sxs-lookup"><span data-stu-id="e5f00-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="e5f00-123">Desconecta el dispositivo Surface de Surface Dock, espera ~5 segundos y vuelve a conectarte.</span><span class="sxs-lookup"><span data-stu-id="e5f00-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="e5f00-124">La actualización de firmware de Surface Dock actualizará la base de datos silenciosamente en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e5f00-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="e5f00-125">El proceso puede tardar unos minutos en completarse y continuará incluso si se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="e5f00-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <a name="monitor-the-surface-dock-firmware-update"></a><span data-ttu-id="e5f00-126">Supervisar la actualización de firmware de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="e5f00-127">Esta sección es opcional y proporciona información general sobre cómo supervisar la instalación de la actualización de firmware.</span><span class="sxs-lookup"><span data-stu-id="e5f00-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="e5f00-128">Para supervisar la actualización:</span><span class="sxs-lookup"><span data-stu-id="e5f00-128">To monitor the update:</span></span>

1. <span data-ttu-id="e5f00-129">Abra el Visor de eventos, vaya a Registros \*\*\*\* de Windows > Aplicación y, a continuación, en \*\*\*\* Acciones en el panel derecho, haga clic en Filtrar registro actual **,** escriba **SurfaceDockFwUpdate junto** a Orígenes de eventos y, **a**continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="e5f00-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="e5f00-130">Escriba el siguiente comando en un símbolo del sistema con privilegios elevados:</span><span class="sxs-lookup"><span data-stu-id="e5f00-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="e5f00-131">Instale la actualización tal como se describe en [la siguiente sección](#install-the-surface-dock-firmware-update) de este artículo.</span><span class="sxs-lookup"><span data-stu-id="e5f00-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="e5f00-132">Evento 2007 con el siguiente texto indica una actualización correcta: La actualización de **firmware finalizó. hr=0 DriverTelementry EventCode = 2007**.</span><span class="sxs-lookup"><span data-stu-id="e5f00-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="e5f00-133">Si la actualización no se realiza correctamente, el identificador de evento 2007 se mostrará como un **evento Error** en lugar de **Como información.**</span><span class="sxs-lookup"><span data-stu-id="e5f00-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="e5f00-134">Además, la versión notificada en el Registro de Windows no será actual.</span><span class="sxs-lookup"><span data-stu-id="e5f00-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="e5f00-135">Una vez completada la actualización, los valores DWORD actualizados se mostrarán en el Registro de Windows, correspondiente a la versión actual de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="e5f00-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="e5f00-136">Vea la [sección de referencia](#versions-reference) de versiones de este artículo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e5f00-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="e5f00-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5f00-137">For example:</span></span>

    - <span data-ttu-id="e5f00-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span><span class="sxs-lookup"><span data-stu-id="e5f00-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="e5f00-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span><span class="sxs-lookup"><span data-stu-id="e5f00-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="e5f00-140">Si ves "No se puede encontrar la descripción del identificador de evento xxxx del surfaceDockFwUpdate de origen" en el texto del evento, esto se espera y se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="e5f00-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="e5f00-141">Vea también las siguientes secciones de este artículo:</span><span class="sxs-lookup"><span data-stu-id="e5f00-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="e5f00-142">Cómo comprobar la finalización de la actualización de firmware</span><span class="sxs-lookup"><span data-stu-id="e5f00-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="e5f00-143">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="e5f00-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="e5f00-144">Recomendaciones para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e5f00-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="e5f00-145">Referencia de versiones</span><span class="sxs-lookup"><span data-stu-id="e5f00-145">Versions reference</span></span>](#versions-reference)

## <a name="network-deployment"></a><span data-ttu-id="e5f00-146">Implementación de red</span><span class="sxs-lookup"><span data-stu-id="e5f00-146">Network deployment</span></span>

<span data-ttu-id="e5f00-147">Puedes usar comandos de Windows Installer (Msiexec.exe) para implementar La actualización de firmware de Surface Dock en varios dispositivos de la red.</span><span class="sxs-lookup"><span data-stu-id="e5f00-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="e5f00-148">Cuando use Microsoft Endpoint Configuration Manager u otra herramienta de implementación, escriba la siguiente sintaxis para asegurarse de que la instalación sea silenciosa:</span><span class="sxs-lookup"><span data-stu-id="e5f00-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="e5f00-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span><span class="sxs-lookup"><span data-stu-id="e5f00-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="e5f00-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5f00-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="e5f00-151">Un archivo de registro no se crea de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e5f00-151">A log file is not created by default.</span></span> <span data-ttu-id="e5f00-152">Para crear un archivo de registro, deberá anexar "/l*v [ruta de acceso]". Por ejemplo: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span><span class="sxs-lookup"><span data-stu-id="e5f00-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="e5f00-153">Para obtener más información, consulte la [documentación de opciones de la línea de](https://docs.microsoft.com/windows/win32/msi/command-line-options) comandos.</span><span class="sxs-lookup"><span data-stu-id="e5f00-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5f00-154">Si quieres mantener Surface Dock actualizado con cualquier otro método, consulta [Actualizar Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e5f00-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <a name="intune-deployment"></a><span data-ttu-id="e5f00-155">Implementación de Intune</span><span class="sxs-lookup"><span data-stu-id="e5f00-155">Intune deployment</span></span>

<span data-ttu-id="e5f00-156">Puedes usar Intune para distribuir la actualización de firmware de Surface Dock a los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e5f00-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="e5f00-157">Primero tendrá que convertir el archivo MSI al formato .intunewin, como se describe en la siguiente documentación: Intune independiente - Administración de [aplicaciones de Win32](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="e5f00-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="e5f00-158">Use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e5f00-158">Use the following command:</span></span>
  - **<span data-ttu-id="e5f00-159">msiexec /i \<path to msi file\> /quiet /q</span><span class="sxs-lookup"><span data-stu-id="e5f00-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <a name="how-to-verify-completion-of-the-firmware-update"></a><span data-ttu-id="e5f00-160">Cómo comprobar la finalización de la actualización de firmware</span><span class="sxs-lookup"><span data-stu-id="e5f00-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="e5f00-161">El firmware de Surface Dock consta de dos componentes:</span><span class="sxs-lookup"><span data-stu-id="e5f00-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="e5f00-162">**Componente 10:** Firmware de la unidad de controladora micro (MCU)</span><span class="sxs-lookup"><span data-stu-id="e5f00-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="e5f00-163">**Componente 20:** Firmware de puerto de visualización (DP).</span><span class="sxs-lookup"><span data-stu-id="e5f00-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="e5f00-164">La finalización correcta de la actualización de firmware de Surface Dock da como resultado nuevos valores de clave del Registro para estos componentes de firmware.</span><span class="sxs-lookup"><span data-stu-id="e5f00-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="e5f00-165">Para comprobar las actualizaciones:</span><span class="sxs-lookup"><span data-stu-id="e5f00-165">To verify updates:</span></span>**

1. <span data-ttu-id="e5f00-166">Abra Regedit y vaya a la siguiente ruta de acceso del Registro:</span><span class="sxs-lookup"><span data-stu-id="e5f00-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="e5f00-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="e5f00-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="e5f00-168">Busque las claves del Registro: **Component10CurrentFwVersion y Component20CurrentFwVersion**, que hacen referencia al firmware que se encuentra actualmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5f00-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Proceso de instalación de actualización de firmware de Surface Dock](images/regeditDock.png)

3. <span data-ttu-id="e5f00-170">Compruebe que los nuevos valores de clave del Registro coincidan con los valores de clave del Registro actualizados que aparecen en la referencia de versiones al final de este documento.</span><span class="sxs-lookup"><span data-stu-id="e5f00-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="e5f00-171">Si los valores coinciden, el firmware se actualizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5f00-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="e5f00-172">Si no se puede comprobar, revise el registro de eventos y las sugerencias para la solución de problemas en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="e5f00-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <a name="event-logging"></a><span data-ttu-id="e5f00-173">Registro de eventos</span><span class="sxs-lookup"><span data-stu-id="e5f00-173">Event logging</span></span>

**<span data-ttu-id="e5f00-174">Tabla 1.</span><span class="sxs-lookup"><span data-stu-id="e5f00-174">Table 1.</span></span> <span data-ttu-id="e5f00-175">Archivos de registro para la actualización de firmware de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="e5f00-176">Log</span><span class="sxs-lookup"><span data-stu-id="e5f00-176">Log</span></span>                              | <span data-ttu-id="e5f00-177">Ubicación</span><span class="sxs-lookup"><span data-stu-id="e5f00-177">Location</span></span>                               | <span data-ttu-id="e5f00-178">Notas</span><span class="sxs-lookup"><span data-stu-id="e5f00-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="e5f00-179">Registro de actualización de firmware de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="e5f00-180">Debe especificarse la ruta de acceso (vea la nota)</span><span class="sxs-lookup"><span data-stu-id="e5f00-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="e5f00-181">Las versiones anteriores de esta herramienta escribieron eventos en registros de aplicaciones y servicios\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="e5f00-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="e5f00-182">Registro de instalación de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="e5f00-182">Windows Device Install log</span></span>       | <span data-ttu-id="e5f00-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="e5f00-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="e5f00-184">Para obtener más información acerca del uso del registro de instalación de dispositivos, consulte la documentación de registro [de SetupAPI.](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)</span><span class="sxs-lookup"><span data-stu-id="e5f00-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="e5f00-185">Tabla 2.</span><span class="sxs-lookup"><span data-stu-id="e5f00-185">Table 2.</span></span> <span data-ttu-id="e5f00-186">IDs del registro de eventos para la actualización de firmware de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="e5f00-187">Los eventos se registran en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5f00-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="e5f00-188">Nota: Las versiones anteriores de esta herramienta escribieron eventos en registros de aplicaciones y servicios\Microsoft Surface Dock Updater.</span><span class="sxs-lookup"><span data-stu-id="e5f00-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="e5f00-189">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e5f00-189">Event ID</span></span> | <span data-ttu-id="e5f00-190">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="e5f00-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="e5f00-191">2001</span><span class="sxs-lookup"><span data-stu-id="e5f00-191">2001</span></span>     | <span data-ttu-id="e5f00-192">Se ha iniciado la actualización de firmware de dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="e5f00-193">2002</span><span class="sxs-lookup"><span data-stu-id="e5f00-193">2002</span></span>     | <span data-ttu-id="e5f00-194">Se omitió la actualización de firmware de dock porque se sabe que dock está actualizado.</span><span class="sxs-lookup"><span data-stu-id="e5f00-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="e5f00-195">2003</span><span class="sxs-lookup"><span data-stu-id="e5f00-195">2003</span></span>     | <span data-ttu-id="e5f00-196">No se pudo obtener la versión de firmware de la actualización de firmware de dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="e5f00-197">2004</span><span class="sxs-lookup"><span data-stu-id="e5f00-197">2004</span></span>     | <span data-ttu-id="e5f00-198">Consulta de la versión del firmware.</span><span class="sxs-lookup"><span data-stu-id="e5f00-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="e5f00-199">2005</span><span class="sxs-lookup"><span data-stu-id="e5f00-199">2005</span></span>     | <span data-ttu-id="e5f00-200">El firmware de dock no pudo iniciar la actualización.</span><span class="sxs-lookup"><span data-stu-id="e5f00-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="e5f00-201">2006</span><span class="sxs-lookup"><span data-stu-id="e5f00-201">2006</span></span>     | <span data-ttu-id="e5f00-202">No se pudieron enviar pares de oferta/carga útil.</span><span class="sxs-lookup"><span data-stu-id="e5f00-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="e5f00-203">2007</span><span class="sxs-lookup"><span data-stu-id="e5f00-203">2007</span></span>     | <span data-ttu-id="e5f00-204">La actualización de firmware finalizó.</span><span class="sxs-lookup"><span data-stu-id="e5f00-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="e5f00-205">2008</span><span class="sxs-lookup"><span data-stu-id="e5f00-205">2008</span></span>     | <span data-ttu-id="e5f00-206">Telemetría de dock BEGIN.</span><span class="sxs-lookup"><span data-stu-id="e5f00-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="e5f00-207">2011</span><span class="sxs-lookup"><span data-stu-id="e5f00-207">2011</span></span>     | <span data-ttu-id="e5f00-208">Telemetría de acoplamiento final.</span><span class="sxs-lookup"><span data-stu-id="e5f00-208">END dock telemetry.</span></span>                                                  |

## <a name="troubleshooting-tips"></a><span data-ttu-id="e5f00-209">Recomendaciones para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="e5f00-209">Troubleshooting tips</span></span>

- <span data-ttu-id="e5f00-210">Desconecta completamente la alimentación de Surface Dock de la corriente alterna para restablecer Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="e5f00-211">Desconecta todos los periféricos excepto Surface Dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="e5f00-212">Desinstala cualquier actualización de firmware actual de Surface Dock y, a continuación, instala la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="e5f00-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="e5f00-213">Asegúrate de que Surface Dock esté desconectado y, a continuación, deja tiempo suficiente para que la actualización se complete como se supervisa a través de un LED en el puerto Ethernet de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5f00-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="e5f00-214">Espera hasta que el LED deje de parpadear antes de desconectar Surface Dock de la alimentación.</span><span class="sxs-lookup"><span data-stu-id="e5f00-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="e5f00-215">Conecta Surface Dock a un dispositivo diferente para ver si es capaz de actualizar la base dock.</span><span class="sxs-lookup"><span data-stu-id="e5f00-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <a name="versions-reference"></a><span data-ttu-id="e5f00-216">Referencia de versiones</span><span class="sxs-lookup"><span data-stu-id="e5f00-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="e5f00-217">El archivo de instalación se publica con el siguiente formato de nomenclatura: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (por ejemplo, Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) y se instala de forma predeterminada en C:\Archivos de programa\SurfaceUpdate.</span><span class="sxs-lookup"><span data-stu-id="e5f00-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <a name="version-1.53.139.0"></a><span data-ttu-id="e5f00-218">Versión 1.53.139.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="e5f00-219">Fecha de lanzamiento: 4 de agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="e5f00-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="e5f00-220">Esta versión de la actualización de firmware de Surface Dock incluye correcciones de errores y compatibilidad con:</span><span class="sxs-lookup"><span data-stu-id="e5f00-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="e5f00-221">Actualizar Surface Dock 1 con Surface Pro X.</span><span class="sxs-lookup"><span data-stu-id="e5f00-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="e5f00-222">Si estás ejecutando Surface Pro X, descarga el archivo . Compilación arm64.</span><span class="sxs-lookup"><span data-stu-id="e5f00-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="e5f00-223">Para todos los demás dispositivos, usa la compilación AMD64.</span><span class="sxs-lookup"><span data-stu-id="e5f00-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="e5f00-224">Valores de clave del Registro</span><span class="sxs-lookup"><span data-stu-id="e5f00-224">Registry key values</span></span>

<span data-ttu-id="e5f00-225">Los valores del Registro que indican el estado de las actualizaciones de firmware no han cambiado con respecto a la versión anterior de esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="e5f00-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="e5f00-226">Component10CurrentFwVersion actualizado a **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="e5f00-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="e5f00-227">Component20CurrentFwVersion actualizado a **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="e5f00-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <a name="version-1.42.139"></a><span data-ttu-id="e5f00-228">Versión 1.42.139</span><span class="sxs-lookup"><span data-stu-id="e5f00-228">Version 1.42.139</span></span> 
*<span data-ttu-id="e5f00-229">Fecha de lanzamiento: 18 de septiembre de 2019</span><span class="sxs-lookup"><span data-stu-id="e5f00-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="e5f00-230">Esta versión, incluida en Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, actualiza el firmware en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="e5f00-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="e5f00-231">Valores de clave del Registro actualizados</span><span class="sxs-lookup"><span data-stu-id="e5f00-231">Updated registry key values</span></span>

- <span data-ttu-id="e5f00-232">Component10CurrentFwVersion actualizado a **4ac3970**.</span><span class="sxs-lookup"><span data-stu-id="e5f00-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="e5f00-233">Component20CurrentFwVersion actualizado a **4a1d570**.</span><span class="sxs-lookup"><span data-stu-id="e5f00-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="e5f00-234">Agrega compatibilidad con Surface Pro 7 y Surface Laptop 3.</span><span class="sxs-lookup"><span data-stu-id="e5f00-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <a name="legacy-versions"></a><span data-ttu-id="e5f00-235">Versiones heredadas</span><span class="sxs-lookup"><span data-stu-id="e5f00-235">Legacy versions</span></span>

### <a name="version-2.23.139.0"></a><span data-ttu-id="e5f00-236">Versión 2.23.139.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="e5f00-237">Fecha de lanzamiento: 10 de octubre de 2018</span><span class="sxs-lookup"><span data-stu-id="e5f00-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="e5f00-238">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="e5f00-239">Agregar compatibilidad con Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="e5f00-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="e5f00-240">Agregar compatibilidad con Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="e5f00-240">Add support for Surface Laptop 2</span></span>


### <a name="version-2.22.139.0"></a><span data-ttu-id="e5f00-241">Versión 2.22.139.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="e5f00-242">Fecha de lanzamiento: 26 de julio de 2018</span><span class="sxs-lookup"><span data-stu-id="e5f00-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="e5f00-243">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="e5f00-244">Aumentar la confiabilidad de las actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e5f00-244">Increase update reliability</span></span>
- <span data-ttu-id="e5f00-245">Agregar compatibilidad con Surface Go</span><span class="sxs-lookup"><span data-stu-id="e5f00-245">Add support for Surface Go</span></span>

### <a name="version-2.12.136.0"></a><span data-ttu-id="e5f00-246">Versión 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="e5f00-247">Fecha de lanzamiento: 29 de enero de 2018</span><span class="sxs-lookup"><span data-stu-id="e5f00-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="e5f00-248">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="e5f00-249">Actualización de firmware del conjunto de chips principal de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="e5f00-250">Actualización de firmware de DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="e5f00-251">Se ha mejorado la estabilidad de la pantalla para las pantallas externas cuando se usa con Surface Book o Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="e5f00-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="e5f00-252">Además, en la instalación de esta versión de Surface Dock Updater en dispositivos Surface Book se incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="e5f00-253">Actualización de firmware de la base de Surface Book</span><span class="sxs-lookup"><span data-stu-id="e5f00-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="e5f00-254">Se ha agregado soporte para las actualizaciones de firmware de Surface Dock con mejoras destinadas a dispositivos de Surface Book</span><span class="sxs-lookup"><span data-stu-id="e5f00-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <a name="version-2.9.136.0"></a><span data-ttu-id="e5f00-255">Versión 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="e5f00-256">Fecha de lanzamiento: 3 de noviembre de 2017</span><span class="sxs-lookup"><span data-stu-id="e5f00-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="e5f00-257">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="e5f00-258">Actualización de firmware de DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="e5f00-259">Resuelve un problema con el audio en adaptadores de puerto de pantalla pasivos</span><span class="sxs-lookup"><span data-stu-id="e5f00-259">Resolves an issue with audio over passive display port adapters</span></span>

### <a name="version-2.1.15.0"></a><span data-ttu-id="e5f00-260">Versión 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="e5f00-261">Fecha de lanzamiento: 19 de junio de 2017</span><span class="sxs-lookup"><span data-stu-id="e5f00-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="e5f00-262">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="e5f00-263">Surface Laptop</span><span class="sxs-lookup"><span data-stu-id="e5f00-263">Surface Laptop</span></span>
* <span data-ttu-id="e5f00-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="e5f00-264">Surface Pro</span></span>

### <a name="version-2.1.6.0"></a><span data-ttu-id="e5f00-265">Versión 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="e5f00-266">Fecha de lanzamiento: 7 de abril de 2017</span><span class="sxs-lookup"><span data-stu-id="e5f00-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="e5f00-267">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="e5f00-268">Actualización de firmware de DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="e5f00-269">Requiere Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5f00-269">Requires Windows 10</span></span>

### <a name="version-2.0.22.0"></a><span data-ttu-id="e5f00-270">Versión 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="e5f00-271">Fecha de lanzamiento: 21 de octubre de 2016</span><span class="sxs-lookup"><span data-stu-id="e5f00-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="e5f00-272">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="e5f00-273">Actualización de firmware de USB de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="e5f00-274">Fiabilidad mejorada de los puertos de audio, USB y Ethernet</span><span class="sxs-lookup"><span data-stu-id="e5f00-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <a name="version-1.0.8.0"></a><span data-ttu-id="e5f00-275">Versión 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="e5f00-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="e5f00-276">Fecha de lanzamiento: 26 de abril de 2016</span><span class="sxs-lookup"><span data-stu-id="e5f00-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="e5f00-277">Esta versión de Surface Dock Updater agrega compatibilidad con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5f00-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="e5f00-278">Actualización de firmware del conjunto de chips principal de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="e5f00-279">Actualización de firmware de DisplayPort de Surface Dock</span><span class="sxs-lookup"><span data-stu-id="e5f00-279">Update for Surface Dock DisplayPort firmware</span></span>


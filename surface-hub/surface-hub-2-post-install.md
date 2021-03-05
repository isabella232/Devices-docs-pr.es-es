---
title: Configurar Windows 10 Pro o Enterprise en Surface Hub 2
description: En este artículo se incluyen recomendaciones para garantizar la mejor experiencia al usar un equipo táctil y de lápiz de pantalla grande personalizado.
keywords: Surface Hub, Windows 10, escritorio, instalación, configuración
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393587"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="37a5b-104">Configurar Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="37a5b-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="37a5b-105">Después de completar el proceso de instalación de la migración a Windows 10 Pro o Enterprise, puedes realizar los siguientes pasos para configurar aplicaciones y configuraciones en Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="37a5b-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="37a5b-106">Estos pasos se recomiendan para garantizar la mejor experiencia al usar este equipo táctil y de lápiz de pantalla grande personalizado.</span><span class="sxs-lookup"><span data-stu-id="37a5b-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="37a5b-107">Al realizar estos pasos, puede resultar útil usar un teclado y un mouse con cable o inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="37a5b-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="37a5b-108">Configurar la configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="37a5b-108">Configure system settings</span></span>

1. <span data-ttu-id="37a5b-109">Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="37a5b-110">En los dispositivos unidos a Azure AD, el usuario que realiza la unión a Azure AD se agrega automáticamente al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="37a5b-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="37a5b-111">Los administradores globales de Azure AD y los dispositivos de Azure AD también <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> son administradores </a> locales.</span><span class="sxs-lookup"><span data-stu-id="37a5b-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="37a5b-112">Puede escribir **administradores de grupos locales netos** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="37a5b-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="37a5b-113">Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo: **username-SHub-Desktop**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="37a5b-114">Seleccione **Iniciar**  >  **configuración**  >  **Cuentas Sincronizar**la  >  **configuración** y desactivar la configuración **de** sincronización.</span><span class="sxs-lookup"><span data-stu-id="37a5b-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="37a5b-115">La configuración que se usa aquí está diseñada para habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no quiera sincronizar otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="37a5b-116">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="37a5b-117">Habilitar el teclado táctil y el panel táctil</span><span class="sxs-lookup"><span data-stu-id="37a5b-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="37a5b-118">Selecciona **Iniciar**  >  \*\*\*\*  >  **dispositivos de configuración**  >  **Escribiendo** y activa Mostrar **el teclado táctil** cuando no esté en modo tableta y no haya ningún teclado conectado.</span><span class="sxs-lookup"><span data-stu-id="37a5b-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="37a5b-119">Pulse y mantenga presionado o haga clic con el botón secundario en la barra de tareas y, a continuación, seleccione **Mostrar botón del teclado táctil** y Mostrar botón del panel **táctil.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="37a5b-120">El teclado táctil es útil para la entrada directa del usuario y el panel táctil virtual ayuda con selecciones precisas, sugerencias de pantalla activa o como alternativa para pulsar y mantener pulsado el botón secundario.</span><span class="sxs-lookup"><span data-stu-id="37a5b-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="37a5b-121">Consulta el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37a5b-121">See the following example.</span></span>

      ![Configuración táctil](images/touch.png)

3. <span data-ttu-id="37a5b-123">Configure el teclado táctil en QWERTY y flotante.</span><span class="sxs-lookup"><span data-stu-id="37a5b-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="37a5b-124">Seleccione el **icono Teclado** de la barra de tareas para mostrar el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="37a5b-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="37a5b-125">En el teclado táctil, selecciona el icono del teclado en la esquina superior izquierda para abrir la configuración del teclado.</span><span class="sxs-lookup"><span data-stu-id="37a5b-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="37a5b-126">Seleccione el tipo de teclado junto al último de la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar flotante, lo que resulta muy útil en esta pantalla grande.</span><span class="sxs-lookup"><span data-stu-id="37a5b-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="37a5b-127">Vea los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="37a5b-127">See the following examples.</span></span>

       ![Configuración del teclado](images/kbd.png)
 
4. <span data-ttu-id="37a5b-129">Configure las opciones de teclado suave.</span><span class="sxs-lookup"><span data-stu-id="37a5b-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="37a5b-130">Seleccione el **icono Configuración** en el teclado táctil o busque y abra La configuración **de escritura.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![configuración de teclado suave](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="37a5b-132">Habilita todas las opciones en Ortografía, Escritura y teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="37a5b-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="37a5b-133">En el ejemplo siguiente se muestra el trackpad, que resulta útil para navegar y seleccionar opciones.</span><span class="sxs-lookup"><span data-stu-id="37a5b-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="37a5b-134">El teclado en pantalla se usa para buscar en Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="37a5b-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Uso del trackpad](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="37a5b-136">Configurar Bluetooth teclado y mouse (opcional)</span><span class="sxs-lookup"><span data-stu-id="37a5b-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="37a5b-137">Conecta un teclado y un mouse si usas el dispositivo como dispositivo Windows principal o lo usas a menudo para escribir o trabajar con precisión.</span><span class="sxs-lookup"><span data-stu-id="37a5b-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="37a5b-138">Si el dispositivo Surface Hub está cerca de un equipo, puedes usar Mouse sin bordes para moverse sin problemas <a href="https://aka.ms/mm" target="_blank"> entre Surface Hub y el </a> EQUIPO.</span><span class="sxs-lookup"><span data-stu-id="37a5b-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="37a5b-139">Para obtener más información, <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> consulta Descarga de Microsoft desde El garage: Mouse sin bordes.</span><span class="sxs-lookup"><span data-stu-id="37a5b-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="37a5b-140">Ejemplo de diseño de la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="37a5b-140">Example of Taskbar layout</span></span>

<span data-ttu-id="37a5b-141">Después de completar los pasos siguientes para configurar o configurar Surface Hub 2 para Windows 10 Professional o Enterprise, te recomendamos que uses anclar las aplicaciones más usadas a la barra de tareas para un inicio rápido y táctil de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="37a5b-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="37a5b-142">A continuación se muestra un ejemplo de cómo podría ser la barra de tareas:</span><span class="sxs-lookup"><span data-stu-id="37a5b-142">Below is an example of what your taskbar could look like:</span></span>

 ![Diseño de la barra de tareas](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="37a5b-144">Actualizar aplicaciones instaladas</span><span class="sxs-lookup"><span data-stu-id="37a5b-144">Update installed apps</span></span>

<span data-ttu-id="37a5b-145">Para actualizar todas las aplicaciones de la Tienda instaladas:</span><span class="sxs-lookup"><span data-stu-id="37a5b-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="37a5b-146">Abre la aplicación de Microsoft Store y selecciona **los** puntos suspensivos Ver más en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="37a5b-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="37a5b-147">Selecciona **Descargas y actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="37a5b-148">Seleccionar **Obtener actualizaciones**</span><span class="sxs-lookup"><span data-stu-id="37a5b-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="37a5b-149">Buscar e instalar todas las actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="37a5b-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="37a5b-150">Después de migrar a Windows 10 Professional o Windows 10 Enterprise, es posible que haya actualizaciones de mantenimiento y características disponibles para instalar.</span><span class="sxs-lookup"><span data-stu-id="37a5b-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="37a5b-151">Vaya a **Configuración**Actualizar & seguridad  >  **>** y, a continuación, seleccione Comprobar si **hay actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="37a5b-152">Si hay actualizaciones, instáleslas, reinicie y repita el proceso hasta que vea la siguiente notificación:</span><span class="sxs-lookup"><span data-stu-id="37a5b-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Notificación de Windows Update "Estás actualizado"](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="37a5b-154">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="37a5b-154">OneDrive for Business</span></span>

<span data-ttu-id="37a5b-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive para la Empresa para compartir fácilmente herramientas, registros y </a> otros archivos entre todos los dispositivos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="37a5b-156">OneDrive te permite compartir los archivos de trabajo entre tus portátiles, Surface Hub Desktop y tus dispositivos móviles administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="37a5b-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="37a5b-157">Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.</span><span class="sxs-lookup"><span data-stu-id="37a5b-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="37a5b-158">Teniendo en cuenta el tamaño de la SSD de Surface Hub (128 GB), si configuras OneDrive en el dispositivo de escritorio de Surface Hub, asegúrate de que la configuración predeterminada sea mantener los archivos en línea y descargar los archivos mientras los usas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="37a5b-159">Para configurar OneDrive para descargar archivos \*\*\*\* solo cuando sea necesario, establezca la configuración Archivos a petición en Guardar espacio y descargar archivos a medida **que los use**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="37a5b-160">Para obtener más información, consulta <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Consultar y establecer estados de archivos a petición en Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Configuración de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="37a5b-162">También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de conservar el espacio en la unidad y descargar solo los archivos que necesite.</span><span class="sxs-lookup"><span data-stu-id="37a5b-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="37a5b-163">SharePoint y Teams</span><span class="sxs-lookup"><span data-stu-id="37a5b-163">SharePoint and Teams</span></span>

<span data-ttu-id="37a5b-164">Los archivos de Canal de SharePoint y Teams también pueden sincronizarse localmente con los dispositivos de escritorio, como portátiles y Surface Hubs, mediante el motor de sincronización de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="37a5b-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="37a5b-165">Para sincronizar archivos corporativos internos con la unidad local con la aplicación de sincronización de OneDrive:</span><span class="sxs-lookup"><span data-stu-id="37a5b-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="37a5b-166">Vaya a un sitio de SharePoint y vaya al directorio de documentos de nivel superior para obtener los archivos que le interesan ver o editar desde el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="37a5b-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="37a5b-167">Seleccione el botón **Sincronizar** en la parte superior de la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="37a5b-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="37a5b-168">Seleccione abrir **en** el elemento emergente **Este sitio está intentando abrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="37a5b-169">Compruebe que los archivos de SharePoint se sincronizan con la unidad local seleccionando el icono de OneDrive en la parte inferior derecha de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="37a5b-170">Compruebe que la configuración está configurada para mantener los archivos en línea y descargar los archivos solo cuando los use:</span><span class="sxs-lookup"><span data-stu-id="37a5b-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="37a5b-171">Abra el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="37a5b-172">Vaya a y haga clic con el botón secundario en el nombre de SharePoint; por ejemplo, \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="37a5b-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="37a5b-173">Seleccione **Liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="37a5b-174">La columna Estado mostrará el estado de los archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="37a5b-175">Para obtener más información, vea <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar archivos de SharePoint con el cliente de sincronización de OneDrive </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="37a5b-176">Los archivos de canal de Teams se almacenan en sitios de SharePoint, con todas las mismas funciones de documentos de SharePoint, incluido el historial de versiones y la sincronización con los dispositivos de escritorio locales.</span><span class="sxs-lookup"><span data-stu-id="37a5b-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="37a5b-177">Para sincronizar archivos de canal de Teams:</span><span class="sxs-lookup"><span data-stu-id="37a5b-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="37a5b-178">Vaya al Canal de interés de Teams y seleccione la **pestaña** Archivos en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="37a5b-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="37a5b-179">A continuación, **seleccione Sincronizar**. Los archivos comenzarán a sincronizarse y estarán visibles en el Explorador de archivos en \*\*Escritorio \ Contoso \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="37a5b-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="37a5b-180">Use el mismo procedimiento que usó para sincronizar sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, pulsando y mantén presionado o haciendo clic con el botón secundario en el Explorador de archivos en el nombre del canal de Teams y seleccionando Liberar espacio **.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="37a5b-181">Configuración del lápiz de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="37a5b-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="37a5b-182">Emparejar el lápiz Bluetooth Surface Hub</span><span class="sxs-lookup"><span data-stu-id="37a5b-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="37a5b-183">Emparejar el lápiz para mantener actualizado el firmware del lápiz, establecer los accesos directos del lápiz y obtener información de carga de batería en la página de configuración del dispositivo Bluetooth o en la aplicación Surface:</span><span class="sxs-lookup"><span data-stu-id="37a5b-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="37a5b-184">Seleccione **Iniciar**  >  **dispositivos de**  >  **configuración**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="37a5b-185">Selecciona **Agregar Bluetooth u otro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="37a5b-186">Elija **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="37a5b-187">Quite el botón de cola del lápiz y agite para desconectar la conexión de la batería.</span><span class="sxs-lookup"><span data-stu-id="37a5b-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="37a5b-188">Vuelva a colocar la tapa y mantenga presionada la tapa hasta que parpadee el LED de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="37a5b-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="37a5b-189">En la configuración de Bluetooth Surface Hub, elige **Lápiz de Surface Hub 2**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="37a5b-190">Complete la operación de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="37a5b-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="37a5b-191">Si el emparejamiento no se realiza correctamente, puede intentar emparejar el lápiz de nuevo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="37a5b-192">Si eso no funciona, puedes probar para ver si la batería se carga comprobando que el lápiz funciona en la aplicación Pizarra.</span><span class="sxs-lookup"><span data-stu-id="37a5b-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="37a5b-193">Si no es así, reemplace la batería y vuelva a emparejar el lápiz.</span><span class="sxs-lookup"><span data-stu-id="37a5b-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="37a5b-194">Si es necesario, reinicia el dispositivo y vuelve a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="37a5b-195">**Establecer métodos abreviados de lápiz** El lápiz de Surface Hub tiene un botón de acceso directo que a veces se conoce como "clic de cola".</span><span class="sxs-lookup"><span data-stu-id="37a5b-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="37a5b-196">La configuración de métodos abreviados requiere emparejar primero el lápiz, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="37a5b-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="37a5b-197">Busque Pluma y seleccione **Lápiz & configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="37a5b-198">Cerca de la parte inferior de la página, seleccione Métodos abreviados de lápiz que abre el cuadro de diálogo, que se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="37a5b-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Métodos abreviados de lápiz](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="37a5b-200">Configuración de cámara</span><span class="sxs-lookup"><span data-stu-id="37a5b-200">Camera configuration</span></span>

<span data-ttu-id="37a5b-201">Puedes montar la cámara en la parte superior o en cualquier lado del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="37a5b-202">Monta la cámara en una posición para optimizar el ángulo de la cámara si estás usando el concentrador con un soporte de escritorio en lugar de un carro, o si estás cerca del concentrador.</span><span class="sxs-lookup"><span data-stu-id="37a5b-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="37a5b-203">La cámara no gira automáticamente, por lo que debes tener una tecla hexadecimal de 2 mm para girar manualmente la cámara.</span><span class="sxs-lookup"><span data-stu-id="37a5b-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="37a5b-204">Para obtener más información sobre cómo montar de forma lateral la cámara y girar la cámara manualmente, consulta Orientación del objetivo de la cámara de <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="37a5b-205">Configuración de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="37a5b-205">Windows Hello configuration</span></span>

<span data-ttu-id="37a5b-206">Surface Hub 2S que ejecuta Windows 10 Enterprise permite el conjunto completo de aplicaciones de escritorio de Win32, así como opciones biométricas de Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="37a5b-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="37a5b-207">El accesorio lector de huellas digitales de Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="37a5b-208">Para solicitar un lector de huellas digitales de Surface Hub 2 o ver especificaciones técnicas, consulta (surface-hub-2-essential-add-ons.md" target="_blank">Complementos esenciales para Windows 10 Pro y Enterprise en Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="37a5b-209">Después de insertar el lector de huellas digitales, selecciona **Opciones**de inicio de sesión cuentas de configuración  >  \*\*\*\*  >  \*\*\*\*  >  \*\*\*\*  >  **Windows Hello Fingerprint** para inscribir la huella digital.</span><span class="sxs-lookup"><span data-stu-id="37a5b-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="37a5b-210">Usa un dispositivo certificado de Windows Hello para el reconocimiento facial.</span><span class="sxs-lookup"><span data-stu-id="37a5b-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="37a5b-211">La cámara de Surface Hub 2S no admite el reconocimiento facial de Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="37a5b-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="37a5b-212">Habilitar un icono de acceso directo de pantalla de bloqueo en la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="37a5b-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="37a5b-213">Para agregar un icono a la barra de tareas que habilita un bloqueo de pantalla táctil similar al método abreviado de teclado windows-L:</span><span class="sxs-lookup"><span data-stu-id="37a5b-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="37a5b-214">Pulsa y mantén presionado o haz clic con el botón derecho en el escritorio, selecciona **Nuevo**  >  **acceso directo**  >  **Examinar**  >  **escritorio**  >  **Aceptar**  >  **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="37a5b-215">Proporcione un nombre para el acceso directo como **Bloquear mi PC**y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="37a5b-216">Haga clic con el botón secundario o pulse y mantenga presionado el acceso directo recién creado en el escritorio y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="37a5b-217">En la **pestaña Acceso** directo, escriba lo siguiente en el **campo Destino:** **Rundll32.exe User32.dll,LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="37a5b-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="37a5b-218">Seleccione el **botón Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione un icono para usar.</span><span class="sxs-lookup"><span data-stu-id="37a5b-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="37a5b-219">Observa el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37a5b-219">See the following example:</span></span>

    ![Elegir un icono](images/lock.png)
    
1.  <span data-ttu-id="37a5b-221">Seleccione **Aceptar** para guardar el acceso directo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="37a5b-222">Haga clic con el botón secundario o pulse y mantenga presionado el acceso directo y seleccione **Anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="37a5b-223">Después de anclar el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="37a5b-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="37a5b-224">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="37a5b-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="37a5b-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="37a5b-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="37a5b-226">Para instalar la pizarra de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="37a5b-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="37a5b-227">Selecciona el **icono Área de trabajo** de Windows Ink en la parte inferior derecha de la barra de tareas y descarga **Pizarra.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Área de trabajo de lápiz](images/ink.png) 

<span data-ttu-id="37a5b-229">Como alternativa, puedes instalar whiteboard desde Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="37a5b-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="37a5b-230">Abre la aplicación de Microsoft Store y busca **Whiteboard**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="37a5b-231">Elige **No gracias para** iniciar sesión y usar en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="37a5b-232">Anclar pizarra a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="37a5b-233">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="37a5b-233">Surface app</span></span>

1. <span data-ttu-id="37a5b-234">En Microsoft Store, busque **Surface**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="37a5b-235">Establece el **filtro Disponible en** todos los **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="37a5b-236">Instala la **aplicación Surface.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-236">Install the **Surface** app.</span></span> <span data-ttu-id="37a5b-237">Esta debería ser la primera aplicación enumerada.</span><span class="sxs-lookup"><span data-stu-id="37a5b-237">This should be the first app listed.</span></span> <span data-ttu-id="37a5b-238">Es posible que deba asociar la MSA a la Tienda para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37a5b-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="37a5b-239">Anclar la **aplicación Surface** a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="37a5b-240">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="37a5b-240">Snip & Sketch</span></span>

1. <span data-ttu-id="37a5b-241">Abre la **aplicación Snip & Sketch** y anclarla a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="37a5b-242">Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, **seleccione Configuración**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="37a5b-243">En **Configuración,** activa Copia **automática en el Portapapeles**, Guardar **snips**y **Varias ventanas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="37a5b-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="37a5b-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="37a5b-244">Microsoft Office</span></span>

1. <span data-ttu-id="37a5b-245">Abra <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal </a> e instale las aplicaciones deseadas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="37a5b-246">Anclar las aplicaciones de Office deseadas a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="37a5b-247">Si Outlook está instalado, asegúrese de establecer la OST de Outlook para que solo guarde la memoria caché de las últimas dos semanas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="37a5b-248">Esto reducirá en gran medida el uso del disco y el tiempo de instalación.</span><span class="sxs-lookup"><span data-stu-id="37a5b-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="37a5b-249">Selecciona **Configuración de**la cuenta  >  **de** archivo y selecciona tu cuenta.</span><span class="sxs-lookup"><span data-stu-id="37a5b-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="37a5b-250">Seleccione **Cambiar** y establezca el control deslizante para Usar el modo **caché de Exchange** en 14 días.</span><span class="sxs-lookup"><span data-stu-id="37a5b-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="37a5b-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="37a5b-251">Microsoft Teams</span></span>

1. <span data-ttu-id="37a5b-252">Descargar e instalar <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="37a5b-253">Configure las opciones para iniciar automáticamente la aplicación (opcional).</span><span class="sxs-lookup"><span data-stu-id="37a5b-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="37a5b-254">Anclar Teams a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="37a5b-255">Considera la posibilidad de reducir las notificaciones de Teams en el dispositivo para evitar distracciones (opcional).</span><span class="sxs-lookup"><span data-stu-id="37a5b-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notificaciones de Teams](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="37a5b-257">Aplicación Connect</span><span class="sxs-lookup"><span data-stu-id="37a5b-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37a5b-258">En Windows 10, versión 2004 y versiones posteriores, la aplicación Connect para la proyección inalámbrica con Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="37a5b-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="37a5b-259">Si has instalado (o actualizado a) Windows versión 2004 o posterior, puedes ver lo siguiente en la pantalla Proyectar a este equipo en configuración:</span><span class="sxs-lookup"><span data-stu-id="37a5b-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Proyecto para este equipo](images/sh2-project.png) 


1. <span data-ttu-id="37a5b-261">Para instalar la aplicación desde la página de configuración \*\*\*\*"Proyectar a este equipo", selecciona Características opcionales Agregar una característica y,  >  **a** continuación, instala la **aplicación Pantalla** inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="37a5b-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="37a5b-262">En **Algunos dispositivos Windows y Android pueden proyectarse**a este equipo cuando diga que está bien , elija:</span><span class="sxs-lookup"><span data-stu-id="37a5b-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="37a5b-263">**Disponible en todas** partes si el dispositivo no está en una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="37a5b-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="37a5b-264">De lo contrario, **elija Disponible en todas partes en redes seguras.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="37a5b-265">En **Solicitar proyecto a este equipo,** elija Solo primera **vez**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="37a5b-266">En **Requerir PIN para el emparejamiento,** elija **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="37a5b-267">Para iniciar la aplicación y anclarla a la barra de tareas, busque **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="37a5b-268">Abre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="37a5b-268">Open the app.</span></span> <span data-ttu-id="37a5b-269">Mientras la aplicación está abierta, haz clic con el botón secundario en el icono Conectar aplicación de la barra de tareas y selecciona **Anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="37a5b-270">A continuación, cierra la aplicación Conectar.</span><span class="sxs-lookup"><span data-stu-id="37a5b-270">Then close the Connect app.</span></span> <span data-ttu-id="37a5b-271">**Es posible que el proyecto en este equipo** no funcione a menos que la aplicación se haya ejecutado al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="37a5b-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="37a5b-272">Configuración recomendada cuando no está en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="37a5b-272">Recommended configuration when not on the corporate network:</span></span>

![Configuración en casa](images/project1.png)

<span data-ttu-id="37a5b-274">Configuración recomendada en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="37a5b-274">Recommended configuration on the corporate network:</span></span>

![Configuración en el trabajo](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="37a5b-276">Tu Teléfono</span><span class="sxs-lookup"><span data-stu-id="37a5b-276">Your Phone</span></span>

<span data-ttu-id="37a5b-277">La **aplicación Tu teléfono** está instalada de forma predeterminada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="37a5b-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="37a5b-278">Si no está presente, también puedes instalarlo desde la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="37a5b-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="37a5b-279">Para obtener información sobre cómo configurar la aplicación, consulta Cómo configurar Tu teléfono en Windows 10 y sincronizar datos <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> entre el equipo y el </a> teléfono.</span><span class="sxs-lookup"><span data-stu-id="37a5b-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="37a5b-280">Consulta también <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Cómo solucionar problemas comunes con la aplicación Tu teléfono en Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="37a5b-281">Zonas de lujo</span><span class="sxs-lookup"><span data-stu-id="37a5b-281">Fancy Zones</span></span>


<span data-ttu-id="37a5b-282">**Zonas elegantes** forma parte de una colección de herramientas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> denominadas PowerToys </a> en GitHub.</span><span class="sxs-lookup"><span data-stu-id="37a5b-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="37a5b-283">Es una excelente manera de usar la pantalla en un Surface Hub 2, ya que te permite definir diseños fijos en la pantalla ("zonas") y, a continuación, seleccionar qué aplicación se ejecutará en cada zona.</span><span class="sxs-lookup"><span data-stu-id="37a5b-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="37a5b-284">El [wiki de PowerToys](https://github.com/microsoft/PowerToys/wiki) tiene instrucciones sobre cómo usar y personalizar cada herramienta, [incluidos FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="37a5b-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="37a5b-285">En un nivel alto: después de instalar PowerToys, puedes seleccionar o crear un diseño personalizado y, a continuación, mantener presionada la tecla mayús y arrastrar o usar teclas de teclado para mover una aplicación en ejecución a zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="37a5b-286">El uso Bluetooth teclado y mouse USB te ayudarán con esto, o puedes usar el teclado táctil y el panel táctil en pantalla.</span><span class="sxs-lookup"><span data-stu-id="37a5b-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="37a5b-287">Sugerencias de power toys</span><span class="sxs-lookup"><span data-stu-id="37a5b-287">Power toys tips</span></span>**
- <span data-ttu-id="37a5b-288">Para recibir notificaciones por correo electrónico de las actualizaciones de la versión de PowerToys en GitHub, haga clic en el botón "Registrarse" en la parte superior de la [página](https://github.com/microsoft/PowerToys/releases).</span><span class="sxs-lookup"><span data-stu-id="37a5b-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="37a5b-289">Una vez instalado PowerToys, puedes recibir notificaciones de Windows o descargar e instalar las actualizaciones \*\*\*\* más recientes configurando la configuración de PowerToys Descargar actualizaciones automáticamente en on.</span><span class="sxs-lookup"><span data-stu-id="37a5b-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="37a5b-290">Para llegar a la configuración de PowerToys, seleccione las aplicaciones en ejecución de quilates en la barra de tareas y, a continuación, haga clic con el botón secundario o presione y mantenga presionado el icono PowerToys hasta que aparezca el menú. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="37a5b-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="37a5b-291">Seleccione "Configuración".</span><span class="sxs-lookup"><span data-stu-id="37a5b-291">Select “Settings”.</span></span>
- <span data-ttu-id="37a5b-292">En la parte inferior de la página de configuración de PowerToys, activa **Descargar actualizaciones automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="37a5b-293">Cuando se haya publicado una actualización, aparecerá una notificación de Windows que te dará la opción de cuándo instalar la actualización.</span><span class="sxs-lookup"><span data-stu-id="37a5b-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="37a5b-294">Explorador Chromium perimetral</span><span class="sxs-lookup"><span data-stu-id="37a5b-294">Edge Chromium browser</span></span>

<span data-ttu-id="37a5b-295">Descargue e instale el nuevo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> explorador Edge Chromium </a> .</span><span class="sxs-lookup"><span data-stu-id="37a5b-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="37a5b-296">Herramienta de diagnóstico de hardware de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="37a5b-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="37a5b-297">La <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> herramienta de diagnóstico de hardware de Surface Hub disponible de forma gratuita en Microsoft </a> Store.</span><span class="sxs-lookup"><span data-stu-id="37a5b-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="37a5b-298">La herramienta está diseñada para ayudarte a asegurarte de que surface hub funciona en su mejor momento.</span><span class="sxs-lookup"><span data-stu-id="37a5b-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="37a5b-299">Contiene pruebas para determinar si el firmware está actualizado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="37a5b-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="37a5b-300">Las pruebas interactivas permiten confirmar que la funcionalidad esencial funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="37a5b-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="37a5b-301">Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="37a5b-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="37a5b-302">Haga clic en el vínculo para instalarlo desde la Microsoft Store y, a continuación, anclar la aplicación a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="37a5b-303">Configuración adicional</span><span class="sxs-lookup"><span data-stu-id="37a5b-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="37a5b-304">Selección de cola de lápiz para iniciar pizarra</span><span class="sxs-lookup"><span data-stu-id="37a5b-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="37a5b-305">Busque Pluma **y** seleccione **Lápiz & configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="37a5b-306">Cerca de la parte inferior de la página, en **Métodos abreviados de lápiz,** establece **Seleccionar una vez** en Pizarra de **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="37a5b-307">Administración de energía</span><span class="sxs-lookup"><span data-stu-id="37a5b-307">Power management</span></span>

<span data-ttu-id="37a5b-308">Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10 Pro o Enterprise en Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="37a5b-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="37a5b-309">Esto incluye tiempos de espera de pantalla y equipo, y cómo interactúan con la detección de presencia humana integrada (Doppler), el protector de pantalla y la protección de contraseña y, si procede, cómo pasar la configuración de energía de directiva de grupo destinada a usuarios de equipos portátiles o de escritorio.</span><span class="sxs-lookup"><span data-stu-id="37a5b-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="37a5b-310">Windows 10 Pro o Enterprise en Surface Hub 2 impide que la pantalla duerma mediante acciones táctiles, de mouse y de teclado, así como la detección de ocupación humana integrada (Doppler).</span><span class="sxs-lookup"><span data-stu-id="37a5b-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="37a5b-311">La detección de ocupación humana está habilitada de forma predeterminada, pero si se desea se puede deshabilitar en UEFI al alternar la opción de dispositivo en la herramienta Configurador UEFI de Surface como parte de la migración inicial, o mediante la creación y aplicación de un paquete de configuración de UEFI posterior.</span><span class="sxs-lookup"><span data-stu-id="37a5b-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="37a5b-312">Administración de energía: configuración de suspensión de pantalla y equipo</span><span class="sxs-lookup"><span data-stu-id="37a5b-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="37a5b-313">Seleccione **Iniciar**  >  **configuración**  >  **Sistema**  >  **Power & modo de suspensión**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="37a5b-314">Establece el control deslizante del modo de energía en **Mejor rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="37a5b-315">Configure los valores de pantalla y suspensión según su preferencia, al tiempo que también tiene en cuenta la detección de presencia de Doppler que activa el dispositivo cuando se detecta el movimiento.</span><span class="sxs-lookup"><span data-stu-id="37a5b-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="37a5b-316">Por lo tanto, como procedimiento recomendado, se recomienda establecer Pantalla en Desactivar después de **2** horas y el equipo desactivar después de **4 horas.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="37a5b-317">Administración de energía: protector de pantalla</span><span class="sxs-lookup"><span data-stu-id="37a5b-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="37a5b-318">Busque Pantalla **de bloqueo y** abra La configuración de pantalla de **bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="37a5b-319">Configure **la configuración de tiempo de espera de** pantalla y la configuración del **protector** de pantalla según sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="37a5b-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="37a5b-320">Los valores predeterminados recomendados son:</span><span class="sxs-lookup"><span data-stu-id="37a5b-320">Recommended default values are:</span></span>

   - <span data-ttu-id="37a5b-321">Protector de pantalla a (Ninguno) o un protector de pantalla de su elección.</span><span class="sxs-lookup"><span data-stu-id="37a5b-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="37a5b-322">Tiempo de espera a 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="37a5b-323">Al reanudar, muestra la pantalla de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="37a5b-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="37a5b-324">Administración de energía: directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="37a5b-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="37a5b-325">Antes de realizar el siguiente procedimiento, comprueba con el departamento de TI la aprobación para excluir un dispositivo Surface Hub 2S de la directiva global de administración de energía.</span><span class="sxs-lookup"><span data-stu-id="37a5b-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="37a5b-326">Algunas opciones de configuración de administración de energía pueden deshabilitar la función de detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="37a5b-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="37a5b-327">Busque el **Centro de software** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="37a5b-328">Seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-328">Select **Options**.</span></span>

3. <span data-ttu-id="37a5b-329">Expanda Administración **de energía y**  seleccione No aplicar la configuración de energía de mi departamento de TI a este **equipo**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configuración de software](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="37a5b-331">Sensor de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="37a5b-331">Storage Sense</span></span>

<span data-ttu-id="37a5b-332">Surface Hub 2 tiene una SSD de 128 GB para el almacenamiento local, por lo que es necesario considerar el uso de medidas de almacenamiento durante el uso normal.</span><span class="sxs-lookup"><span data-stu-id="37a5b-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="37a5b-333">Para configurar El sentido de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="37a5b-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="37a5b-334">Busque la **configuración de almacenamiento**, que se encuentra en Configuración del **sistema**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="37a5b-335">En **Configuración,** seleccione **Activar el sentido de almacenamiento** para abrir la página **Configuración** de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="37a5b-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="37a5b-336">Active el sentido de almacenamiento **en On**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="37a5b-337">Seleccione **Configurar sentido de almacenamiento o ejecutarlo** ahora y configure las opciones para mantener los archivos en línea tanto como sea posible (debido a un espacio de unidad limitado).</span><span class="sxs-lookup"><span data-stu-id="37a5b-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="37a5b-338">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="37a5b-338">Recommended settings:</span></span>

- <span data-ttu-id="37a5b-339">Ejecute Storage Sense = Every Day.</span><span class="sxs-lookup"><span data-stu-id="37a5b-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="37a5b-340">Eliminar archivos temporales que mis aplicaciones no usan = Cada 14 días (al menos).</span><span class="sxs-lookup"><span data-stu-id="37a5b-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="37a5b-341">Elimine los archivos de la carpeta Descargas si han estado allí durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="37a5b-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="37a5b-342">OneDrive: el contenido se convertirá solo en línea si no se abre durante más de 30 días.</span><span class="sxs-lookup"><span data-stu-id="37a5b-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="37a5b-343">Modo tableta</span><span class="sxs-lookup"><span data-stu-id="37a5b-343">Tablet mode</span></span>

<span data-ttu-id="37a5b-344">Activa el modo tableta si lo deseas para las necesidades de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="37a5b-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="37a5b-345">Configuración de sonido</span><span class="sxs-lookup"><span data-stu-id="37a5b-345">Sound settings</span></span>

1. <span data-ttu-id="37a5b-346">Busque la **configuración de sonidos** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="37a5b-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="37a5b-347">Seleccione **Panel de control de sonido** a la derecha y seleccione la **pestaña** Sonidos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="37a5b-348">En **Eventos del programa,** **establece Device Connect** y Device **Disconnect** en **None**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="37a5b-349">Notificaciones de silencio</span><span class="sxs-lookup"><span data-stu-id="37a5b-349">Silence notifications</span></span>

1. <span data-ttu-id="37a5b-350">Busque ayuda **de foco y** abra esta página.</span><span class="sxs-lookup"><span data-stu-id="37a5b-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="37a5b-351">Seleccione **Solo alarmas**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-351">Select **Alarms Only**.</span></span> <span data-ttu-id="37a5b-352">Esto evitará los control de control de notificaciones constantes.</span><span class="sxs-lookup"><span data-stu-id="37a5b-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="37a5b-353">Liberador de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="37a5b-353">Disk Cleanup</span></span>

1. <span data-ttu-id="37a5b-354">Busca Limpieza **de disco** y abre esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="37a5b-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="37a5b-355">En **Archivos para eliminar,** seleccione los archivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="37a5b-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="37a5b-356">También seleccione **Limpiar archivos del sistema.**</span><span class="sxs-lookup"><span data-stu-id="37a5b-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="37a5b-357">Completar y comprobar</span><span class="sxs-lookup"><span data-stu-id="37a5b-357">Complete and verify</span></span>

1. <span data-ttu-id="37a5b-358">Busca e instala todas las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="37a5b-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="37a5b-359">Actualizar directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="37a5b-360">En un símbolo del sistema con privilegios elevados, escriba **gpupdate /force /boot /wait:0**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="37a5b-361">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="37a5b-361">Restart the device.</span></span>

4. <span data-ttu-id="37a5b-362">Compruebe las aplicaciones de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="37a5b-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="37a5b-363">Connect App</span><span class="sxs-lookup"><span data-stu-id="37a5b-363">Connect App</span></span>
   - <span data-ttu-id="37a5b-364">Icono de bloqueo</span><span class="sxs-lookup"><span data-stu-id="37a5b-364">Lock Icon</span></span>
   - <span data-ttu-id="37a5b-365">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="37a5b-365">Snip & Sketch</span></span>
   - <span data-ttu-id="37a5b-366">Teams (si procede)</span><span class="sxs-lookup"><span data-stu-id="37a5b-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="37a5b-367">Aplicaciones de Office (si procede)</span><span class="sxs-lookup"><span data-stu-id="37a5b-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="37a5b-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="37a5b-368">Surface App</span></span>
   - <span data-ttu-id="37a5b-369">Pizarra</span><span class="sxs-lookup"><span data-stu-id="37a5b-369">Whiteboard</span></span>
    
5. <span data-ttu-id="37a5b-370">Compruebe la detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="37a5b-370">Verify presence detection.</span></span>

   - <span data-ttu-id="37a5b-371">La detección de presencia será un icono verde en la bandeja del sistema.</span><span class="sxs-lookup"><span data-stu-id="37a5b-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="37a5b-372">Compruebe que la proyección a este equipo está habilitada con la aplicación Connect.</span><span class="sxs-lookup"><span data-stu-id="37a5b-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="37a5b-373">Después de configurar  **Project en esta configuración de PC,** ejecute la aplicación Connect al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="37a5b-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="37a5b-374">(Posteriormente, la aplicación Connect no necesita ejecutarse para poder proyectarse en Surface Hub).</span><span class="sxs-lookup"><span data-stu-id="37a5b-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="37a5b-375">Compruebe la configuración de energía y suspensión.</span><span class="sxs-lookup"><span data-stu-id="37a5b-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="37a5b-376">Protector de pantalla: 15 minutos, establecido en (ninguno), Mystify o Blank; asegúrese de que la casilla de verificación para requerir contraseña está activada.</span><span class="sxs-lookup"><span data-stu-id="37a5b-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="37a5b-377">Pantalla: **Desactivar después de 2 horas**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="37a5b-378">PC:  **desactivar después de 4 horas**.</span><span class="sxs-lookup"><span data-stu-id="37a5b-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="37a5b-379">Comprueba que Windows Hello funciona.</span><span class="sxs-lookup"><span data-stu-id="37a5b-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="37a5b-380">Compruebe que la sincronización de la configuración está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="37a5b-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="37a5b-381">Compruebe las aplicaciones de inicio.</span><span class="sxs-lookup"><span data-stu-id="37a5b-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="37a5b-382">Después de instalar y configurar Windows 10, Surface Hub 2S se puede administrar igual que cualquier otro dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="37a5b-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="37a5b-383">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="37a5b-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="37a5b-384">Migrar a Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="37a5b-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>

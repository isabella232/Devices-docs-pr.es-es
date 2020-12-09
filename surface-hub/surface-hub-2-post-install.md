---
title: Configurar Windows 10 Pro o Enterprise en Surface Hub 2
description: En este artículo, se incluyen recomendaciones para garantizar la mejor experiencia al usar un equipo de lápiz y una pantalla grande personalizados.
keywords: Surface Hub, Windows 10, escritorio, instalar, configuración
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
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203571"
---
# <span data-ttu-id="175c8-104">Configurar Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="175c8-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="175c8-105">Después de completar el proceso de instalación de la migración a Windows 10 Pro o Enterprise, puede realizar los siguientes pasos para configurar las aplicaciones y la configuración de su Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="175c8-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="175c8-106">Estos pasos se recomiendan para garantizar la mejor experiencia de uso de este equipo de pantalla táctil y de lápiz de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="175c8-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="175c8-107">Al realizar estos pasos, es posible que le resulte útil usar un teclado y un mouse con cable o inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="175c8-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="175c8-108">Configurar las opciones del sistema</span><span class="sxs-lookup"><span data-stu-id="175c8-108">Configure system settings</span></span>

1. <span data-ttu-id="175c8-109">Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="175c8-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="175c8-110">En los dispositivos Unidos a Azure AD, el usuario que realiza la combinación de Azure AD se agrega automáticamente al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="175c8-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="175c8-111">Los administradores globales de Azure AD y los administradores de dispositivos Azure AD <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> también son administradores locales </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="175c8-112">Puede escribir **net localgroup Administrators** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="175c8-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="175c8-113">Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo: **nombre de usuario-SHub-escritorio**.</span><span class="sxs-lookup"><span data-stu-id="175c8-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="175c8-114">Seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sync Your Settings** y desactiva la **configuración de sincronización** .</span><span class="sxs-lookup"><span data-stu-id="175c8-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="175c8-115">La configuración que se usa aquí tiene el propósito de habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no desee sincronizar otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="175c8-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="175c8-116">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="175c8-116">Restart the device.</span></span>

## <span data-ttu-id="175c8-117">Habilitar el teclado táctil y el panel táctil</span><span class="sxs-lookup"><span data-stu-id="175c8-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="175c8-118">Puntee y mantenga presionado o haga clic con el botón derecho en la barra de tareas y seleccione Mostrar botón de **teclado táctil** y **Mostrar botón de panel táctil**.</span><span class="sxs-lookup"><span data-stu-id="175c8-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="175c8-119">El teclado táctil es útil para la entrada directa por parte del usuario, y el panel táctil virtual ayuda a seleccionar con precisión, mantener la información en la pantalla o como alternativa para tocar y mantener el mouse.</span><span class="sxs-lookup"><span data-stu-id="175c8-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="175c8-120">Consulta el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="175c8-120">See the following example.</span></span>

      ![Configuración táctil](images/touch.png)

2. <span data-ttu-id="175c8-122">Configure el teclado táctil en QWERTY y flotantes.</span><span class="sxs-lookup"><span data-stu-id="175c8-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="175c8-123">Seleccione el icono de **teclado** en la barra de tareas para mostrar el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="175c8-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="175c8-124">En el teclado táctil, seleccione el icono de teclado en la esquina superior izquierda para abrir la configuración del teclado.</span><span class="sxs-lookup"><span data-stu-id="175c8-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="175c8-125">Seleccione el siguiente tipo de teclado en la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar el flotante, que es muy útil en esta gran pantalla.</span><span class="sxs-lookup"><span data-stu-id="175c8-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="175c8-126">Vea los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="175c8-126">See the following examples.</span></span>

       ![Configuración del teclado](images/kbd.png)
 
3. <span data-ttu-id="175c8-128">Establecer la configuración de teclado de pantalla.</span><span class="sxs-lookup"><span data-stu-id="175c8-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="175c8-129">Seleccione el icono de **configuración** en el teclado táctil o busque y Abra **configuración de escritura**.</span><span class="sxs-lookup"><span data-stu-id="175c8-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![configuración de teclado de software](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="175c8-131">Habilite todas las opciones de ortografía, escritura y teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="175c8-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="175c8-132">En el ejemplo siguiente se muestra el panel táctil, que es útil para desplazarse y seleccionar las opciones.</span><span class="sxs-lookup"><span data-stu-id="175c8-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="175c8-133">El teclado en pantalla se usa para buscar en Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="175c8-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usar el panel táctil](images/store.png)

## <span data-ttu-id="175c8-135">Configurar el mouse y el teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="175c8-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="175c8-136">Conecte un teclado y un mouse si usa el dispositivo como dispositivo principal de Windows, o bien Utilícelo a menudo para trabajar con texto o con precisión.</span><span class="sxs-lookup"><span data-stu-id="175c8-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="175c8-137">Si el dispositivo Surface Hub está cerca de un PC, puedes usar el <a href="https://aka.ms/mm" target="_blank"> mouse sin bordes </a> para desplazarte sin problemas entre el Surface Hub y el equipo.</span><span class="sxs-lookup"><span data-stu-id="175c8-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="175c8-138">Para obtener más información, vea <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Descargar Microsoft del garaje: mouse sin bordes.</span><span class="sxs-lookup"><span data-stu-id="175c8-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="175c8-139">Ejemplo de diseño de la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="175c8-139">Example of Taskbar layout</span></span>

<span data-ttu-id="175c8-140">Después de completar los pasos siguientes para configurar/configurar su Surface Hub 2 para Windows 10 Professional o Enterprise, le recomendamos que use el anclaje de las aplicaciones más usadas en la barra de tareas para un inicio rápido y sencillo de cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="175c8-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="175c8-141">A continuación se muestra un ejemplo del aspecto de la barra de tareas:</span><span class="sxs-lookup"><span data-stu-id="175c8-141">Below is an example of what your taskbar could look like:</span></span>

 ![Diseño de la barra de tareas](images/taskblyt.png)
### <span data-ttu-id="175c8-143">Actualizar las aplicaciones instaladas</span><span class="sxs-lookup"><span data-stu-id="175c8-143">Update installed apps</span></span>

<span data-ttu-id="175c8-144">Para actualizar todas las aplicaciones de la tienda instaladas:</span><span class="sxs-lookup"><span data-stu-id="175c8-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="175c8-145">Abra la aplicación Microsoft Store y seleccione **Ver más** puntos suspensivos en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="175c8-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="175c8-146">Seleccione **descargas y actualizaciones.**</span><span class="sxs-lookup"><span data-stu-id="175c8-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="175c8-147">Seleccione **obtener actualizaciones**</span><span class="sxs-lookup"><span data-stu-id="175c8-147">Select **Get updates**</span></span>

### <span data-ttu-id="175c8-148">Buscar e instalar todas las actualizaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="175c8-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="175c8-149">Después de migrar a Windows 10 Professional o Windows 10 Enterprise, es posible que haya actualizaciones de características y mantenimiento disponibles para su instalación.</span><span class="sxs-lookup"><span data-stu-id="175c8-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="175c8-150">Vaya a actualización de **configuración**  >  **& > seguridad** y, a continuación, seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="175c8-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="175c8-151">Si hay alguna actualización, instálela, reinicie y, a continuación, repita el proceso hasta que vea la siguiente notificación:</span><span class="sxs-lookup"><span data-stu-id="175c8-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Notificación de Windows Update "está actualizado"](images/wustatus.png)


## <span data-ttu-id="175c8-153">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="175c8-153">OneDrive for Business</span></span>

<span data-ttu-id="175c8-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive para </a> la empresa para compartir fácilmente herramientas, registros y otros archivos entre todos los dispositivos de su trabajo.</span><span class="sxs-lookup"><span data-stu-id="175c8-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="175c8-155">OneDrive le permite compartir sus archivos de trabajo entre sus equipos portátiles, el escritorio Surface Hub y los dispositivos móviles administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="175c8-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="175c8-156">Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.</span><span class="sxs-lookup"><span data-stu-id="175c8-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="175c8-157">Teniendo en cuenta el tamaño de la SSD del Surface Hub (128 GB), si configura OneDrive en su dispositivo de escritorio Surface Hub, asegúrese de que la configuración predeterminada es mantener los archivos en línea y descargar archivos a medida que los usa.</span><span class="sxs-lookup"><span data-stu-id="175c8-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="175c8-158">Para configurar OneDrive de modo que descargue los archivos solo cuando sea necesario, establezca la configuración **de archivos a petición** para **ahorrar espacio y descargar archivos a medida que los usa**.</span><span class="sxs-lookup"><span data-stu-id="175c8-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="175c8-159">Para obtener más información, vea <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> consultar y establecer los Estados a petición de los archivos en Windows </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![Configuración de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="175c8-161">También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de ahorrar espacio en disco y solo descargar archivos a medida que los necesite.</span><span class="sxs-lookup"><span data-stu-id="175c8-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="175c8-162">SharePoint y Teams</span><span class="sxs-lookup"><span data-stu-id="175c8-162">SharePoint and Teams</span></span>

<span data-ttu-id="175c8-163">Los archivos de canal de SharePoint y Teams también se pueden sincronizar localmente con los dispositivos de escritorio, como equipos portátiles y Surface Hub, con el motor de sincronización de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="175c8-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="175c8-164">Para sincronizar los archivos corporativos internos con la unidad local con la aplicación de sincronización de OneDrive:</span><span class="sxs-lookup"><span data-stu-id="175c8-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="175c8-165">Vaya a un sitio de SharePoint y navegue hasta el directorio de documentos de nivel superior para ver los archivos que le interesa ver o editar desde el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="175c8-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="175c8-166">Seleccione el botón **sincronizar** en la parte superior de la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="175c8-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="175c8-167">Seleccione al **abrir** en el elemento emergente **este sitio está intentando abrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="175c8-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="175c8-168">Compruebe que los archivos de SharePoint se sincronizan con su unidad local seleccionando en el icono de OneDrive en la parte inferior derecha de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="175c8-169">Compruebe que la configuración esté configurada para mantener los archivos en línea y descargar los archivos solo a medida que los usa:</span><span class="sxs-lookup"><span data-stu-id="175c8-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="175c8-170">Abra el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="175c8-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="175c8-171">Vaya al nombre de SharePoint y haga clic con el botón secundario. por ejemplo, \*\*contoso \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="175c8-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="175c8-172">Seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="175c8-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="175c8-173">La columna Estado mostrará el estado de archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="175c8-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="175c8-174">Para obtener más información, vea <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> sincronizar archivos de SharePoint con el cliente de sincronización de OneDrive </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="175c8-175">Los archivos de canales de equipos se almacenan en sitios de SharePoint, con todas las mismas funciones de documento de SharePoint, incluido el historial de versiones y la sincronización con dispositivos de escritorio locales.</span><span class="sxs-lookup"><span data-stu-id="175c8-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="175c8-176">Para sincronizar los archivos de canal:</span><span class="sxs-lookup"><span data-stu-id="175c8-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="175c8-177">Navegue hasta el canal de interés de los equipos y seleccione la pestaña **archivos** en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="175c8-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="175c8-178">Después, seleccione **sincronizar**. Los archivos comenzarán a sincronizarse y se verán en el explorador de archivos en el \*\*escritorio \ contoso \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="175c8-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="175c8-179">Use el mismo procedimiento que usó para sincronizar los sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, pulse y mantenga presionado o haga clic con el botón derecho en el explorador de archivos en el nombre de canal de Teams y, a continuación, seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="175c8-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="175c8-180">Configuración del lápiz de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="175c8-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="175c8-181">Emparejar el lápiz de Surface Hub de Bluetooth</span><span class="sxs-lookup"><span data-stu-id="175c8-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="175c8-182">Emparejar el lápiz para mantener actualizado el firmware del lápiz, configurar los accesos directos del lápiz y obtener información de carga de batería en la página de configuración de dispositivo Bluetooth o en la aplicación Surface:</span><span class="sxs-lookup"><span data-stu-id="175c8-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="175c8-183">Seleccione **Start**  >  **Settings**  >  **Devices**.</span><span class="sxs-lookup"><span data-stu-id="175c8-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="175c8-184">Seleccione **Agregar Bluetooth u otro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="175c8-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="175c8-185">Elija **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="175c8-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="175c8-186">Quite el botón cola de pluma y agite para desconectar la conexión de la batería.</span><span class="sxs-lookup"><span data-stu-id="175c8-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="175c8-187">Vuelva a colocar el tapón y mantenga presionado el tapón hasta que el LED de emparejamiento parpadee.</span><span class="sxs-lookup"><span data-stu-id="175c8-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="175c8-188">En la configuración de Bluetooth Surface Hub, seleccione **lápiz de Surface Hub 2**.</span><span class="sxs-lookup"><span data-stu-id="175c8-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="175c8-189">Complete la operación de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="175c8-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="175c8-190">Si el emparejamiento no se realiza correctamente, puede intentar volver a emparejar el lápiz.</span><span class="sxs-lookup"><span data-stu-id="175c8-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="175c8-191">Si esto no funciona, puede comprobar si la batería se cobra comprobando que el lápiz funciona en la aplicación de pizarra.</span><span class="sxs-lookup"><span data-stu-id="175c8-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="175c8-192">En caso contrario, reemplace la batería y, a continuación, intente volver a emparejar la pluma.</span><span class="sxs-lookup"><span data-stu-id="175c8-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="175c8-193">Si es necesario, reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="175c8-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="175c8-194">**Establecer accesos directos del lápiz** El lápiz del Surface Hub tiene un botón de método abreviado al que a veces se hace referencia como "hacer clic".</span><span class="sxs-lookup"><span data-stu-id="175c8-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="175c8-195">Para configurar los accesos directos debe emparejar primero el lápiz, como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="175c8-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="175c8-196">Busque el lápiz y seleccione **pluma & la configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="175c8-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="175c8-197">Cerca de la parte inferior de la página, seleccione los accesos directos del lápiz que abre el cuadro de diálogo, que se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="175c8-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![Accesos directos de lápiz](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="175c8-199">Configuración de la cámara</span><span class="sxs-lookup"><span data-stu-id="175c8-199">Camera configuration</span></span>

<span data-ttu-id="175c8-200">Puede montar la cámara en la parte superior o en cualquiera de los lados del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="175c8-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="175c8-201">Monte la cámara en una posición para optimizar el ángulo de la cámara si está usando el Hub con un soporte de escritorio en lugar de un carrito o está cerca del concentrador.</span><span class="sxs-lookup"><span data-stu-id="175c8-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="175c8-202">La cámara no gira automáticamente, por lo que debe tener una clave hexadecimal 2mm para girar la cámara de forma manual.</span><span class="sxs-lookup"><span data-stu-id="175c8-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="175c8-203">Para obtener más información sobre cómo montar la cámara y girar la cámara de forma manual, consulte <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2s orientación de lente de la cámara </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="175c8-204">Configuración de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="175c8-204">Windows Hello configuration</span></span>

<span data-ttu-id="175c8-205">Surface Hub 2S si se ejecuta Windows 10 Enterprise, se permite el conjunto completo de aplicaciones de escritorio Win32, así como las opciones de Windows Hello biométricas.</span><span class="sxs-lookup"><span data-stu-id="175c8-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="175c8-206">El accesorio de lector de huellas dactilares Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="175c8-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="175c8-207">Para solicitar un lector de huellas dactilares Surface Hub 2 o para ver especificaciones técnicas, consulta (surface-hub-2-essential-add-ons.md "target =" _blank ">complementos esenciales para Windows 10 Pro y Enterprise en Surface Hub 2 </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="175c8-208">Después de insertar el lector Fingerprint Reader, seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sign-in Options**  >  **huellator de Windows Hello** para inscribir su huella dactilar.</span><span class="sxs-lookup"><span data-stu-id="175c8-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="175c8-209">Usar un dispositivo certificado de Windows Hello para un reconocimiento facial.</span><span class="sxs-lookup"><span data-stu-id="175c8-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="175c8-210">La cámara Surface Hub 2S no admite el reconocimiento facial de Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="175c8-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="175c8-211">Habilitar un icono de método abreviado de pantalla de bloqueo en la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="175c8-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="175c8-212">Para agregar un icono a la barra de tareas que permita un único toque de pantalla similar al método abreviado de teclado Windows-L:</span><span class="sxs-lookup"><span data-stu-id="175c8-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="175c8-213">Puntee y mantenga presionado o haga clic con el botón derecho en el escritorio, seleccione **nuevo**  >  **método abreviado**  >  **examinar**  >  **escritorio**  >  **Aceptar**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="175c8-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="175c8-214">Escriba un nombre para el acceso directo, como **bloquear mi PC**y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="175c8-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="175c8-215">Haga clic con el botón secundario del ratón o mantenga pulsado el acceso directo recién creado en el escritorio y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="175c8-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="175c8-216">En la pestaña **acceso directo** , escriba lo siguiente en el campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="175c8-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="175c8-217">Seleccione el botón **Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione el icono que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="175c8-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="175c8-218">Observa el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="175c8-218">See the following example:</span></span>

    ![Elegir un icono](images/lock.png)
    
1.  <span data-ttu-id="175c8-220">Seleccione **Aceptar** para guardar el método abreviado.</span><span class="sxs-lookup"><span data-stu-id="175c8-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="175c8-221">Haga clic con el botón derecho o mantenga presionado el acceso directo y seleccione **anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="175c8-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="175c8-222">Una vez que haya anclado el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="175c8-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="175c8-223">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="175c8-223">Applications</span></span>


### <span data-ttu-id="175c8-224">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="175c8-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="175c8-225">Para instalar la pizarra de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="175c8-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="175c8-226">Seleccione el icono **área de trabajo de Windows Ink** en la esquina inferior derecha de la barra de tareas y descargar **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="175c8-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Área de trabajo de tinta](images/ink.png) 

<span data-ttu-id="175c8-228">Como alternativa, puede instalar whiteboard desde Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="175c8-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="175c8-229">Abra la aplicación Microsoft Store y busque **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="175c8-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="175c8-230">Elija **no gracias** para iniciar sesión y usar en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="175c8-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="175c8-231">Anclar pizarra a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="175c8-232">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="175c8-232">Surface app</span></span>

1. <span data-ttu-id="175c8-233">En Microsoft Store, busque **Surface**.</span><span class="sxs-lookup"><span data-stu-id="175c8-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="175c8-234">Establezca el filtro **disponible en en** **todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="175c8-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="175c8-235">Instala la aplicación **Surface** .</span><span class="sxs-lookup"><span data-stu-id="175c8-235">Install the **Surface** app.</span></span> <span data-ttu-id="175c8-236">Debe ser la primera aplicación de la lista.</span><span class="sxs-lookup"><span data-stu-id="175c8-236">This should be the first app listed.</span></span> <span data-ttu-id="175c8-237">Es posible que necesites asociar tu MSA a la tienda para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="175c8-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="175c8-238">Ancla la aplicación de **Surface** a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="175c8-239">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="175c8-239">Snip & Sketch</span></span>

1. <span data-ttu-id="175c8-240">Abra el **recorte &** aplicación de boceto y ancle la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="175c8-241">Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="175c8-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="175c8-242">En **configuración**, Active **copiar automáticamente en el portapapeles**, **Guardar recortes**y **varias ventanas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="175c8-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="175c8-243">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="175c8-243">Microsoft Office</span></span>

1. <span data-ttu-id="175c8-244">Abra el <a href="https://portal.office.com/account#installs" target="_blank"> portal de Office </a> e instale las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="175c8-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="175c8-245">Anclar las aplicaciones de Office que desee a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="175c8-246">Si Outlook está instalado, asegúrese de establecer el OST de Outlook para que solo se guarden las últimas dos semanas de caché.</span><span class="sxs-lookup"><span data-stu-id="175c8-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="175c8-247">Esto disminuirá en gran medida el uso del disco y el tiempo de configuración.</span><span class="sxs-lookup"><span data-stu-id="175c8-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="175c8-248">Seleccione **File**  >  **configuración** de la cuenta de archivo y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="175c8-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="175c8-249">Seleccione **cambiar** y el control deslizante para **usar el modo caché de Exchange** en 14 días.</span><span class="sxs-lookup"><span data-stu-id="175c8-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="175c8-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="175c8-250">Microsoft Teams</span></span>

1. <span data-ttu-id="175c8-251">Descargue e instale <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="175c8-252">Establecer la configuración para la aplicación de inicio automático (opcional).</span><span class="sxs-lookup"><span data-stu-id="175c8-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="175c8-253">Anclar equipos a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="175c8-254">Considere la posibilidad de reducir las notificaciones de Teams en el dispositivo para evitar distracciones (opcional).</span><span class="sxs-lookup"><span data-stu-id="175c8-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Notificaciones de Teams](images/teams.png)

### <span data-ttu-id="175c8-256">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="175c8-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="175c8-257">En Windows 10, versión 2004 y posteriores, la aplicación de conexión para proyección inalámbrica con Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="175c8-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="175c8-258">Si ha instalado (o actualizado a) Windows versión 2004 o posterior, es posible que vea lo siguiente en la pantalla proyectar en este equipo en configuración:</span><span class="sxs-lookup"><span data-stu-id="175c8-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Proyectar a este equipo](images/sh2-project.png) 


1. <span data-ttu-id="175c8-260">Para instalar la aplicación desde la página de configuración "proyectar en este equipo", selecciona **características opcionales**  >  **agrega una característica** y luego instala la aplicación de **visualización inalámbrica** .</span><span class="sxs-lookup"><span data-stu-id="175c8-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="175c8-261">En **algunos dispositivos con Windows y Android puede proyectar en este equipo cuando lo digas correctamente**, elija:</span><span class="sxs-lookup"><span data-stu-id="175c8-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="175c8-262">**Disponible en todas partes** si el dispositivo no está en una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="175c8-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="175c8-263">En caso contrario, elija **disponible en todas partes en redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="175c8-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="175c8-264">En **preguntar al proyecto en este equipo**, seleccione **solo la primera vez**.</span><span class="sxs-lookup"><span data-stu-id="175c8-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="175c8-265">En **requerir PIN para el emparejamiento**, elija **nunca**.</span><span class="sxs-lookup"><span data-stu-id="175c8-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="175c8-266">Para iniciar la aplicación y anclarla en la barra de tareas, busque **Connect**.</span><span class="sxs-lookup"><span data-stu-id="175c8-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="175c8-267">Abra la aplicación.</span><span class="sxs-lookup"><span data-stu-id="175c8-267">Open the app.</span></span> <span data-ttu-id="175c8-268">Mientras la aplicación está abierta, haga clic con el botón derecho en el icono de la aplicación conectar en la barra de tareas y seleccione **anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="175c8-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="175c8-269">Después, cierre la aplicación Connect.</span><span class="sxs-lookup"><span data-stu-id="175c8-269">Then close the Connect app.</span></span> <span data-ttu-id="175c8-270">Es posible que el **proyecto a este equipo** no funcione a menos que se haya ejecutado la aplicación al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="175c8-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="175c8-271">Configuración recomendada cuando no se encuentra en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="175c8-271">Recommended configuration when not on the corporate network:</span></span>

![Configuración en casa](images/project1.png)

<span data-ttu-id="175c8-273">Configuración recomendada en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="175c8-273">Recommended configuration on the corporate network:</span></span>

![Configuración en el trabajo](images/project2.png)

### <span data-ttu-id="175c8-275">Tu Teléfono</span><span class="sxs-lookup"><span data-stu-id="175c8-275">Your Phone</span></span>

<span data-ttu-id="175c8-276">La aplicación de **tu teléfono** se instala de forma predeterminada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="175c8-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="175c8-277">Si no está presente, también puede instalarlo desde la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="175c8-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="175c8-278">Para obtener información sobre cómo configurar la aplicación, vea <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> Cómo configurar el teléfono en Windows 10 y cómo sincronizar datos entre su equipo y su teléfono </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="175c8-279">Además, consulta <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> cómo solucionar problemas comunes con tu aplicación de teléfono en Windows 10 </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="175c8-280">Zonas de fantasía</span><span class="sxs-lookup"><span data-stu-id="175c8-280">Fancy Zones</span></span>


<span data-ttu-id="175c8-281">Las **zonas más elegantes** forman parte de una colección de herramientas denominadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> en github..</span><span class="sxs-lookup"><span data-stu-id="175c8-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="175c8-282">Es una excelente manera de usar el equipo de la pantalla en un Surface Hub 2 al darle la posibilidad de definir diseños fijos en la pantalla ("zonas") y, a continuación, seleccionar qué aplicación se ejecutará en cada zona.</span><span class="sxs-lookup"><span data-stu-id="175c8-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="175c8-283">El [wiki de PowerToys](https://github.com/microsoft/PowerToys/wiki) tiene instrucciones sobre cómo usar y personalizar cada herramienta, incluido el [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span><span class="sxs-lookup"><span data-stu-id="175c8-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="175c8-284">En un nivel superior: después de instalar PowerToys, puede seleccionar o crear un diseño personalizado y, a continuación, mantener presionada la tecla Mayús y arrastrar o usar las teclas del teclado para mover una aplicación que se está ejecutando a zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="175c8-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="175c8-285">Con un teclado y un mouse Bluetooth o USB, podrás usar el teclado táctil y el panel táctil.</span><span class="sxs-lookup"><span data-stu-id="175c8-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="175c8-286">Consejos sobre Power Toys</span><span class="sxs-lookup"><span data-stu-id="175c8-286">Power toys tips</span></span>**
- <span data-ttu-id="175c8-287">Para recibir notificaciones por correo electrónico de las actualizaciones de los PowerToys release en GitHub, haga clic en el botón "registrarse" en la parte superior de la [Página](https://github.com/microsoft/PowerToys/releases).</span><span class="sxs-lookup"><span data-stu-id="175c8-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="175c8-288">Una vez que se instalan los PowerToys, puede recibir notificaciones de Windows o descargar e instalar las actualizaciones más recientes al configurar la configuración de PowerToys **Descargar actualizaciones automáticamente** en activado.</span><span class="sxs-lookup"><span data-stu-id="175c8-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="175c8-289">Para acceder a la configuración de PowerToys, seleccione las aplicaciones up intercalación **Running** en la barra de tareas y, a continuación, haga clic con el botón secundario o mantenga presionado el icono de PowerToys hasta que aparezca el menú.</span><span class="sxs-lookup"><span data-stu-id="175c8-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="175c8-290">Seleccione "configuración".</span><span class="sxs-lookup"><span data-stu-id="175c8-290">Select “Settings”.</span></span>
- <span data-ttu-id="175c8-291">En la parte inferior de la página de configuración de PowerToys, Active **Descargar actualizaciones automáticamente** en activado.</span><span class="sxs-lookup"><span data-stu-id="175c8-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="175c8-292">Cuando se publique una actualización, aparecerá una notificación de Windows que le dará la opción de instalar la actualización.</span><span class="sxs-lookup"><span data-stu-id="175c8-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="175c8-293">Explorador de cromo de cromo</span><span class="sxs-lookup"><span data-stu-id="175c8-293">Edge Chromium browser</span></span>

<span data-ttu-id="175c8-294">Descarga e instala el nuevo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> navegador Edge de cromo </a> .</span><span class="sxs-lookup"><span data-stu-id="175c8-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="175c8-295">Herramienta de diagnóstico de hardware Surface Hub</span><span class="sxs-lookup"><span data-stu-id="175c8-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="175c8-296">La <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> herramienta de diagnóstico de hardware de Surface Hub </a> está disponible gratuitamente en Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="175c8-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="175c8-297">La herramienta está diseñada para ayudarte a asegurarte de que Surface Hub funcione de la mejor manera posible.</span><span class="sxs-lookup"><span data-stu-id="175c8-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="175c8-298">Contiene pruebas para determinar si el firmware está actualizado y configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="175c8-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="175c8-299">Las pruebas interactivas permiten confirmar que la funcionalidad esencial funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="175c8-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="175c8-300">Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="175c8-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="175c8-301">Haga clic en el vínculo para instalarlo desde Microsoft Store y, a continuación, ancle la aplicación a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="175c8-302">Configuración adicional</span><span class="sxs-lookup"><span data-stu-id="175c8-302">Additional settings</span></span>

### <span data-ttu-id="175c8-303">Cola de plumas Seleccione para iniciar pizarra</span><span class="sxs-lookup"><span data-stu-id="175c8-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="175c8-304">Busque el **lápiz** y seleccione **pluma & la configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="175c8-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="175c8-305">Cerca de la parte inferior de la página, en **accesos directos de lápiz** , **Seleccione una vez** para la **pizarra de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="175c8-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="175c8-306">Administración de energía</span><span class="sxs-lookup"><span data-stu-id="175c8-306">Power management</span></span>

<span data-ttu-id="175c8-307">Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10 Pro o Enterprise en Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="175c8-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="175c8-308">Esto incluye tiempos de espera de pantalla y equipo y cómo interactúan con la detección de presencia humana integrada (Doppler), el protector de pantalla y la protección con contraseña y, si es adecuado, cómo pasar la configuración de energía de la Directiva de grupo para usuarios de equipos portátiles o de escritorio.</span><span class="sxs-lookup"><span data-stu-id="175c8-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="175c8-309">Windows 10 Pro o Enterprise en Surface Hub 2 evita que la pantalla pase de la pantalla a la entrada táctil, el mouse y el teclado, así como la detección de la ocupación de la ocupación integrada (Doppler).</span><span class="sxs-lookup"><span data-stu-id="175c8-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="175c8-310">La detección de la ocupación de los seres humanos está habilitada de forma predeterminada, pero si se desea, se puede deshabilitar en UEFI al alternar la opción dispositivo en la herramienta de configuración de Surface UEFI, ya sea como parte de la migración inicial o mediante la creación y aplicación de un paquete de configuración UEFI posterior.</span><span class="sxs-lookup"><span data-stu-id="175c8-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="175c8-311">Administración de energía: configuración de suspensión de pantalla y PC</span><span class="sxs-lookup"><span data-stu-id="175c8-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="175c8-312">Seleccione **Start**  >  **Settings**  >  **System**  >  **Power & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="175c8-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="175c8-313">Configure el control deslizante de modo de energía para **obtener el mejor rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="175c8-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="175c8-314">Configure valores de pantalla y de espera para su preferencia, así como para la detección de presencia de Doppler que reactiva el dispositivo cuando se detecta movimiento.</span><span class="sxs-lookup"><span data-stu-id="175c8-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="175c8-315">Como práctica recomendada, se recomienda configurar la pantalla para que se apague **después de dos horas** y el equipo **apagado después de 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="175c8-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="175c8-316">Administración de energía: protector de pantalla</span><span class="sxs-lookup"><span data-stu-id="175c8-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="175c8-317">Busque **pantalla de bloqueo** y Abra **configuración de pantalla de bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="175c8-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="175c8-318">Configure la configuración del **protector de pantalla** y la **configuración del tiempo de espera de pantalla** para sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="175c8-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="175c8-319">Los valores predeterminados recomendados son:</span><span class="sxs-lookup"><span data-stu-id="175c8-319">Recommended default values are:</span></span>

   - <span data-ttu-id="175c8-320">Protector de pantalla a (ninguno) o un protector de pantalla de su elección.</span><span class="sxs-lookup"><span data-stu-id="175c8-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="175c8-321">Tiempo de espera de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="175c8-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="175c8-322">En reanudar, Mostrar la pantalla de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="175c8-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="175c8-323">Administración de energía: Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="175c8-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="175c8-324">Antes de realizar el procedimiento siguiente, consulte con el Departamento de TI para obtener una aprobación para excluir un dispositivo Surface Hub 2S de la Directiva de administración global de energía.</span><span class="sxs-lookup"><span data-stu-id="175c8-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="175c8-325">Algunas configuraciones de administración de energía pueden deshabilitar la función de detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="175c8-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="175c8-326">Busque **software Center** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="175c8-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="175c8-327">Seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="175c8-327">Select **Options**.</span></span>

3. <span data-ttu-id="175c8-328">Expanda la **Administración de energía**  y seleccione no aplicar la **configuración de energía de mi departamento de ti a este equipo**.</span><span class="sxs-lookup"><span data-stu-id="175c8-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configuración de software](images/soft-cntr.png)

### <span data-ttu-id="175c8-330">Sensor de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="175c8-330">Storage Sense</span></span>

<span data-ttu-id="175c8-331">Surface Hub 2 tiene un SSD de 128 GB para almacenamiento local, por lo que es necesario considerar el uso de las medidas de almacenamiento de almacenamiento durante el uso normal.</span><span class="sxs-lookup"><span data-stu-id="175c8-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="175c8-332">Para configurar el sensor de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="175c8-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="175c8-333">Busque la **configuración de almacenamiento**, que se encuentra en **configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="175c8-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="175c8-334">En **configuración**, seleccione **Activar sensor de almacenamiento** para abrir la página Configuración de **almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="175c8-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="175c8-335">Activar el sentido **de**almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="175c8-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="175c8-336">Seleccione **configurar sensor de almacenamiento o ejecutarlo ahora** y configure las opciones para mantener los archivos en línea todo lo posible (debido a un espacio en disco limitado).</span><span class="sxs-lookup"><span data-stu-id="175c8-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="175c8-337">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="175c8-337">Recommended settings:</span></span>

- <span data-ttu-id="175c8-338">Ejecutar sensor de almacenamiento = todos los días.</span><span class="sxs-lookup"><span data-stu-id="175c8-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="175c8-339">Elimine los archivos temporales que mis aplicaciones no usan = cada 14 días (al menos).</span><span class="sxs-lookup"><span data-stu-id="175c8-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="175c8-340">Eliminar archivos de mi carpeta de descargas si ya lo han recibido durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="175c8-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="175c8-341">OneDrive: el contenido se volverá a estar en línea si no se abre durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="175c8-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="175c8-342">Modo tableta</span><span class="sxs-lookup"><span data-stu-id="175c8-342">Tablet mode</span></span>

<span data-ttu-id="175c8-343">Activa el modo tableta si así lo deseas.</span><span class="sxs-lookup"><span data-stu-id="175c8-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="175c8-344">Configuración de sonido</span><span class="sxs-lookup"><span data-stu-id="175c8-344">Sound settings</span></span>

1. <span data-ttu-id="175c8-345">Busque la **configuración de sonidos** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="175c8-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="175c8-346">Seleccione **Panel de control de sonido** a la derecha y seleccione la pestaña **sonidos** .</span><span class="sxs-lookup"><span data-stu-id="175c8-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="175c8-347">En **eventos de programa** , establezca **Conectar dispositivo** y **desconectar dispositivo** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="175c8-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="175c8-348">Notificaciones de silencio</span><span class="sxs-lookup"><span data-stu-id="175c8-348">Silence notifications</span></span>

1. <span data-ttu-id="175c8-349">Busque el **Asistente de concentración** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="175c8-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="175c8-350">Seleccione **solo alarmas**.</span><span class="sxs-lookup"><span data-stu-id="175c8-350">Select **Alarms Only**.</span></span> <span data-ttu-id="175c8-351">Esto evitará controles flotantes de notificaciones constantes.</span><span class="sxs-lookup"><span data-stu-id="175c8-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="175c8-352">Liberador de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="175c8-352">Disk Cleanup</span></span>

1. <span data-ttu-id="175c8-353">Busque el **liberador de espacio en disco** y abra esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="175c8-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="175c8-354">En **archivos para eliminar**, seleccione los archivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="175c8-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="175c8-355">Seleccione **limpiar archivos de sistema**.</span><span class="sxs-lookup"><span data-stu-id="175c8-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="175c8-356">Completar y comprobar</span><span class="sxs-lookup"><span data-stu-id="175c8-356">Complete and verify</span></span>

1. <span data-ttu-id="175c8-357">Busque e instale todas las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="175c8-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="175c8-358">Actualice la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="175c8-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="175c8-359">En un símbolo del sistema con privilegios elevados, escriba **gpupdate/force/boot/wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="175c8-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="175c8-360">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="175c8-360">Restart the device.</span></span>

4. <span data-ttu-id="175c8-361">Comprobar las aplicaciones de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="175c8-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="175c8-362">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="175c8-362">Connect App</span></span>
   - <span data-ttu-id="175c8-363">Icono de candado</span><span class="sxs-lookup"><span data-stu-id="175c8-363">Lock Icon</span></span>
   - <span data-ttu-id="175c8-364">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="175c8-364">Snip & Sketch</span></span>
   - <span data-ttu-id="175c8-365">Teams (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="175c8-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="175c8-366">Aplicaciones de Office (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="175c8-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="175c8-367">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="175c8-367">Surface App</span></span>
   - <span data-ttu-id="175c8-368">Pizarra</span><span class="sxs-lookup"><span data-stu-id="175c8-368">Whiteboard</span></span>
    
5. <span data-ttu-id="175c8-369">Comprobar la detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="175c8-369">Verify presence detection.</span></span>

   - <span data-ttu-id="175c8-370">La detección de presencia será un icono verde en la bandeja del sistema.</span><span class="sxs-lookup"><span data-stu-id="175c8-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="175c8-371">Comprobar que los proyectos se han habilitado con la aplicación Connect.</span><span class="sxs-lookup"><span data-stu-id="175c8-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="175c8-372">Después de configurar  **Project en esta** configuración de equipo, ejecute la aplicación Connect al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="175c8-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="175c8-373">(Posteriormente, no es necesario que la aplicación Connect se esté ejecutando para proyectar en Surface hub).</span><span class="sxs-lookup"><span data-stu-id="175c8-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="175c8-374">Comprobar la configuración de energía y suspensión.</span><span class="sxs-lookup"><span data-stu-id="175c8-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="175c8-375">Protector de pantalla: 15 minutos, establecido en (ninguno), de formas o en blanco; Asegúrese de que la casilla requerir contraseña está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="175c8-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="175c8-376">Pantalla: **apague después de 2 horas**.</span><span class="sxs-lookup"><span data-stu-id="175c8-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="175c8-377">PC:  **apagar después de 4 horas**.</span><span class="sxs-lookup"><span data-stu-id="175c8-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="175c8-378">Compruebe que Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="175c8-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="175c8-379">Comprobar la sincronización la configuración está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="175c8-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="175c8-380">Comprobar las aplicaciones de inicio.</span><span class="sxs-lookup"><span data-stu-id="175c8-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="175c8-381">Después de instalar y configurar Windows 10, Surface Hub 2S se puede administrar como cualquier otro dispositivo de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="175c8-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="175c8-382">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="175c8-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="175c8-383">Migrar a Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="175c8-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>

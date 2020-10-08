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
ms.date: 10/01/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 68f3fe1eb2fba0673444510fc77d3f41e09144af
ms.sourcegitcommit: e0047f07c42b1e3cbd074b66a4704ea72e9d7bae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093900"
---
# <span data-ttu-id="a0203-104">Configurar Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="a0203-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="a0203-105">Después de completar el proceso de instalación de la migración a Windows 10 Pro o Enterprise, puede realizar los siguientes pasos para configurar las aplicaciones y la configuración de su Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="a0203-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="a0203-106">Estos pasos se recomiendan para garantizar la mejor experiencia de uso de este equipo de pantalla táctil y de lápiz de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="a0203-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="a0203-107">Al realizar estos pasos, es posible que le resulte útil usar un teclado y un mouse con cable o inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="a0203-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="a0203-108">Configurar las opciones del sistema</span><span class="sxs-lookup"><span data-stu-id="a0203-108">Configure system settings</span></span>

1. <span data-ttu-id="a0203-109">Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0203-109">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="a0203-110">En los dispositivos Unidos a Azure AD, el usuario que realiza la combinación de Azure AD se agrega automáticamente al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="a0203-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="a0203-111">Los administradores globales de Azure AD y los administradores de dispositivos Azure AD [también son administradores locales](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="a0203-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="a0203-112">Puede escribir **net localgroup Administrators** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="a0203-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="a0203-113">Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo: **nombre de usuario-SHub-escritorio**.</span><span class="sxs-lookup"><span data-stu-id="a0203-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="a0203-114">Seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sync Your Settings** y desactiva la **configuración de sincronización** .</span><span class="sxs-lookup"><span data-stu-id="a0203-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="a0203-115">La configuración que se usa aquí tiene el propósito de habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no desee sincronizar otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a0203-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="a0203-116">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0203-116">Reboot the device.</span></span>

## <span data-ttu-id="a0203-117">Habilitar el teclado táctil y el panel táctil</span><span class="sxs-lookup"><span data-stu-id="a0203-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="a0203-118">Puntee y mantenga presionado o haga clic con el botón derecho en la barra de tareas y seleccione Mostrar botón de **teclado táctil** y **Mostrar botón de panel táctil**.</span><span class="sxs-lookup"><span data-stu-id="a0203-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="a0203-119">El teclado táctil es útil para la entrada directa por parte del usuario, y el panel táctil virtual ayuda a seleccionar con precisión, mantener la información en la pantalla o como alternativa para tocar y mantener el mouse.</span><span class="sxs-lookup"><span data-stu-id="a0203-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="a0203-120">Consulta el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0203-120">See the following example.</span></span>

     ![Configuración táctil](images/touch.png)

2. <span data-ttu-id="a0203-122">Configure el teclado táctil en QWERTY y flotantes.</span><span class="sxs-lookup"><span data-stu-id="a0203-122">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="a0203-123">Seleccione el icono de teclado en la barra de tareas para mostrar el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="a0203-123">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="a0203-124">En el teclado táctil, seleccione el icono de teclado en la esquina superior izquierda para abrir la configuración del teclado.</span><span class="sxs-lookup"><span data-stu-id="a0203-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="a0203-125">Seleccione el siguiente tipo de teclado en la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar el flotante, que es muy útil en esta gran pantalla.</span><span class="sxs-lookup"><span data-stu-id="a0203-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="a0203-126">Vea los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0203-126">See the following examples.</span></span>

     ![Configuración del teclado](images/kbd.png)

3. <span data-ttu-id="a0203-128">Establecer la configuración de teclado de pantalla.</span><span class="sxs-lookup"><span data-stu-id="a0203-128">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="a0203-129">Buscar y abrir la **configuración de escritura**</span><span class="sxs-lookup"><span data-stu-id="a0203-129">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="a0203-130">Habilite todas las opciones de ortografía, escritura y teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="a0203-130">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="a0203-131">En el ejemplo siguiente se muestra el panel táctil, que es útil para desplazarse y seleccionar las opciones.</span><span class="sxs-lookup"><span data-stu-id="a0203-131">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="a0203-132">El teclado en pantalla se usa para buscar en Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="a0203-132">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usar el panel táctil](images/store.png)

## <span data-ttu-id="a0203-134">Configurar el mouse y el teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="a0203-134">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="a0203-135">Conecte un teclado y un mouse si usa el dispositivo como dispositivo principal de Windows, o bien Utilícelo a menudo para trabajar con texto o con precisión.</span><span class="sxs-lookup"><span data-stu-id="a0203-135">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="a0203-136">Si el dispositivo Surface Hub está cerca de un PC, puedes usar el [mouse sin bordes](https://aka.ms/mm) para desplazarte sin problemas entre el Surface Hub y el equipo.</span><span class="sxs-lookup"><span data-stu-id="a0203-136">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="a0203-137">Para obtener más información, vea [Descargar Microsoft del garaje: mouse sin bordes](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="a0203-137">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="a0203-138">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="a0203-138">OneDrive for Business</span></span>

<span data-ttu-id="a0203-139">Use [OneDrive para la empresa](https://docs.microsoft.com/onedrive/onedrive) para compartir fácilmente herramientas, registros y otros archivos entre todos los dispositivos de su trabajo.</span><span class="sxs-lookup"><span data-stu-id="a0203-139">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="a0203-140">OneDrive le permite compartir sus archivos de trabajo entre sus equipos portátiles, el escritorio Surface Hub y los dispositivos móviles administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="a0203-140">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="a0203-141">Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.</span><span class="sxs-lookup"><span data-stu-id="a0203-141">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="a0203-142">Teniendo en cuenta el tamaño de la SSD del Surface Hub (128 GB), si configura OneDrive en su dispositivo de escritorio Surface Hub, asegúrese de que la configuración predeterminada es mantener los archivos en línea y descargar archivos a medida que los usa.</span><span class="sxs-lookup"><span data-stu-id="a0203-142">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="a0203-143">Para configurar OneDrive de modo que descargue los archivos solo cuando sea necesario, establezca la configuración **de archivos a petición** para **ahorrar espacio y descargar archivos a medida que los usa**.</span><span class="sxs-lookup"><span data-stu-id="a0203-143">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="a0203-144">Para obtener más información, vea [consultar y establecer los Estados a petición de los archivos en Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="a0203-144">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Configuración de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="a0203-146">También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de ahorrar espacio en disco y solo descargar archivos a medida que los necesite.</span><span class="sxs-lookup"><span data-stu-id="a0203-146">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="a0203-147">SharePoint y Teams</span><span class="sxs-lookup"><span data-stu-id="a0203-147">SharePoint and Teams</span></span>

<span data-ttu-id="a0203-148">Los archivos de canal de SharePoint y Teams también se pueden sincronizar localmente con los dispositivos de escritorio, como equipos portátiles y Surface Hub, con el motor de sincronización de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a0203-148">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="a0203-149">Para sincronizar los archivos corporativos internos con la unidad local con la aplicación de sincronización de OneDrive:</span><span class="sxs-lookup"><span data-stu-id="a0203-149">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="a0203-150">Vaya a un sitio de SharePoint y navegue hasta el directorio de documentos de nivel superior para ver los archivos que le interesa ver o editar desde el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="a0203-150">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="a0203-151">Seleccione el botón **sincronizar** en la parte superior de la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0203-151">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="a0203-152">Seleccione al **abrir** en el elemento emergente **este sitio está intentando abrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="a0203-152">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="a0203-153">Compruebe que los archivos de SharePoint se sincronizan con su unidad local seleccionando en el icono de OneDrive en la parte inferior derecha de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-153">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="a0203-154">Compruebe que la configuración esté configurada para mantener los archivos en línea y descargar los archivos solo a medida que los usa:</span><span class="sxs-lookup"><span data-stu-id="a0203-154">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="a0203-155">Abra el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="a0203-155">Open file explorer.</span></span>
    2. <span data-ttu-id="a0203-156">Desplácese a la y seleccione la derecha en el \*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="a0203-156">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="a0203-157">Seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="a0203-157">Select **Free up space**.</span></span>
    4. <span data-ttu-id="a0203-158">La columna Estado mostrará el estado de archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="a0203-158">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="a0203-159">Para obtener más información, vea [sincronizar archivos de SharePoint con el cliente de sincronización de OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="a0203-159">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="a0203-160">Los archivos de canales de equipos se almacenan en sitios de SharePoint, con todas las mismas funciones de documento de SharePoint, incluido el historial de versiones y la sincronización con dispositivos de escritorio locales.</span><span class="sxs-lookup"><span data-stu-id="a0203-160">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="a0203-161">Para sincronizar los archivos de canal:</span><span class="sxs-lookup"><span data-stu-id="a0203-161">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="a0203-162">Navegue hasta el canal de interés de los equipos y seleccione en la pestaña **archivos** de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="a0203-162">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="a0203-163">Después, seleccione **sincronizar**. Los archivos comenzarán a sincronizarse y se verán en el explorador de archivos en el \*\*escritorio \ Microsoft \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="a0203-163">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="a0203-164">Use el mismo procedimiento que usó para sincronizar los sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, pulse y mantenga presionado o haga clic con el botón derecho en el explorador de archivos en el nombre de canal de Teams y, a continuación, seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="a0203-164">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="a0203-165">Configuración del lápiz de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a0203-165">Surface Hub pen settings</span></span>

**<span data-ttu-id="a0203-166">Emparejar el lápiz de Surface Hub de Bluetooth</span><span class="sxs-lookup"><span data-stu-id="a0203-166">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="a0203-167">Emparejar el lápiz para mantener actualizado el firmware del lápiz y obtener la información de carga de la batería en la página de configuración del dispositivo Bluetooth o en la aplicación de Surface:</span><span class="sxs-lookup"><span data-stu-id="a0203-167">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="a0203-168">Seleccione **Start**  >  **Settings**  >  **Devices**.</span><span class="sxs-lookup"><span data-stu-id="a0203-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="a0203-169">Seleccione **Agregar Bluetooth u otro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a0203-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="a0203-170">Elija **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="a0203-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="a0203-171">Quite el botón cola de pluma y agite para desconectar la conexión de la batería.</span><span class="sxs-lookup"><span data-stu-id="a0203-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="a0203-172">Vuelva a colocar el tapón y mantenga presionado el tapón hasta que el LED de emparejamiento parpadee.</span><span class="sxs-lookup"><span data-stu-id="a0203-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="a0203-173">En la configuración de Bluetooth Surface Hub, seleccione **lápiz de Surface Hub 2**.</span><span class="sxs-lookup"><span data-stu-id="a0203-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="a0203-174">Complete la operación de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="a0203-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="a0203-175">Si el emparejamiento no se realiza correctamente, intente volver a emparejar el lápiz.</span><span class="sxs-lookup"><span data-stu-id="a0203-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="a0203-176">Si es necesario, reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="a0203-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="a0203-177">Configuración de la cámara</span><span class="sxs-lookup"><span data-stu-id="a0203-177">Camera configuration</span></span>

<span data-ttu-id="a0203-178">Puede montar la cámara en la parte superior o en cualquiera de los lados del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0203-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="a0203-179">Monte la cámara en una posición para optimizar el ángulo de la cámara si está usando el Hub con un soporte de escritorio en lugar de un carrito o está cerca del concentrador.</span><span class="sxs-lookup"><span data-stu-id="a0203-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="a0203-180">La cámara no gira automáticamente, por lo que debe tener una clave hexadecimal 2mm para girar la cámara de forma manual.</span><span class="sxs-lookup"><span data-stu-id="a0203-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="a0203-181">Para obtener más información sobre cómo montar la cámara y girar la cámara de forma manual, consulte [Surface Hub 2s orientación de lente](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation)de la cámara.</span><span class="sxs-lookup"><span data-stu-id="a0203-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="a0203-182">Configuración de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="a0203-182">Windows Hello configuration</span></span>

<span data-ttu-id="a0203-183">Surface Hub 2S si se ejecuta Windows 10 Enterprise, se permite el conjunto completo de aplicaciones de escritorio Win32, así como las opciones de Windows Hello biométricas.</span><span class="sxs-lookup"><span data-stu-id="a0203-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="a0203-184">El accesorio de lector de huellas dactilares Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0203-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="a0203-185">Para solicitar un lector de huellas dactilares Surface Hub 2 o para ver especificaciones técnicas, consulta [Complementos esenciales para Windows 10 Pro y Enterprise en Surface Hub 2](surface-hub-2-essential-add-ons.md).</span><span class="sxs-lookup"><span data-stu-id="a0203-185">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see [Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2](surface-hub-2-essential-add-ons.md).</span></span> 

<span data-ttu-id="a0203-186">Después de insertar el lector Fingerprint Reader, seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sign-in Options**  >  **huellator de Windows Hello** para inscribir su huella dactilar.</span><span class="sxs-lookup"><span data-stu-id="a0203-186">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="a0203-187">Usar un dispositivo certificado de Windows Hello para un reconocimiento facial.</span><span class="sxs-lookup"><span data-stu-id="a0203-187">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="a0203-188">La cámara Surface Hub 2S no admite el reconocimiento facial de Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="a0203-188">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="a0203-189">Habilitar un icono de método abreviado de pantalla de bloqueo en la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="a0203-189">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="a0203-190">Para agregar un icono a la barra de tareas que permita un único toque de pantalla similar al método abreviado de teclado Windows-L:</span><span class="sxs-lookup"><span data-stu-id="a0203-190">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="a0203-191">Puntee y mantenga presionado o haga clic con el botón derecho en el escritorio, seleccione **nuevo**  >  **método abreviado**  >  **examinar**  >  **escritorio**  >  **Aceptar**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="a0203-191">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="a0203-192">Escriba un nombre para el acceso directo, como **bloquear mi PC**y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a0203-192">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="a0203-193">Haga clic con el botón secundario del ratón o mantenga pulsado el acceso directo recién creado en el escritorio y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a0203-193">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="a0203-194">En la pestaña **acceso directo** , escriba lo siguiente en el campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="a0203-194">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="a0203-195">Seleccione el botón **Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione el icono que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="a0203-195">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="a0203-196">Observa el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a0203-196">See the following example:</span></span>

    ![Elegir un icono](images/lock.png)
    
1.  <span data-ttu-id="a0203-198">Seleccione **Aceptar** para guardar el método abreviado.</span><span class="sxs-lookup"><span data-stu-id="a0203-198">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="a0203-199">Haga clic con el botón derecho o mantenga presionado el acceso directo y seleccione **anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="a0203-199">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="a0203-200">Una vez que haya anclado el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.</span><span class="sxs-lookup"><span data-stu-id="a0203-200">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="a0203-201">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a0203-201">Applications</span></span>

### <span data-ttu-id="a0203-202">Actualizar las aplicaciones instaladas</span><span class="sxs-lookup"><span data-stu-id="a0203-202">Update installed apps</span></span>

<span data-ttu-id="a0203-203">Para actualizar todas las aplicaciones de la tienda instaladas:</span><span class="sxs-lookup"><span data-stu-id="a0203-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="a0203-204">Abra la aplicación Microsoft Store y seleccione **Ver más** puntos suspensivos en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="a0203-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="a0203-205">Seleccione **Descargas y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="a0203-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="a0203-206">Seleccione **Obtener actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="a0203-206">Select **Get updates**.</span></span>

### <span data-ttu-id="a0203-207">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="a0203-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="a0203-208">Para instalar la pizarra de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a0203-208">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="a0203-209">Seleccione el icono **área de trabajo de Windows Ink** en la esquina inferior derecha de la barra de tareas y descargar **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="a0203-209">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![Área de trabajo de tinta](images/ink.png) 

<span data-ttu-id="a0203-211">Como alternativa, puede instalar whiteboard desde Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="a0203-211">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="a0203-212">Abra la aplicación Microsoft Store y busque **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="a0203-212">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="a0203-213">Elija **no gracias** para iniciar sesión y usar en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a0203-213">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="a0203-214">Anclar pizarra a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-214">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="a0203-215">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="a0203-215">Surface app</span></span>

1. <span data-ttu-id="a0203-216">En Microsoft Store, busque **Surface**.</span><span class="sxs-lookup"><span data-stu-id="a0203-216">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="a0203-217">Establezca el filtro **disponible en en** **todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="a0203-217">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="a0203-218">Instala la aplicación **Surface** .</span><span class="sxs-lookup"><span data-stu-id="a0203-218">Install the **Surface** app.</span></span> <span data-ttu-id="a0203-219">Debe ser la primera aplicación de la lista.</span><span class="sxs-lookup"><span data-stu-id="a0203-219">This should be the first app listed.</span></span> <span data-ttu-id="a0203-220">Es posible que necesites asociar tu MSA a la tienda para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0203-220">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="a0203-221">Ancla la aplicación de **Surface** a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-221">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="a0203-222">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="a0203-222">Snip & Sketch</span></span>

1. <span data-ttu-id="a0203-223">Abra el **recorte &** aplicación de boceto y ancle la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-223">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="a0203-224">Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="a0203-224">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="a0203-225">En **configuración**, Active **copiar automáticamente en el portapapeles**, **Guardar recortes**y **varias ventanas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="a0203-225">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="a0203-226">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="a0203-226">Microsoft Office</span></span>

1. <span data-ttu-id="a0203-227">Abra el [portal de Office](https://portal.office.com/account#installs) e instale las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="a0203-227">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="a0203-228">Anclar las aplicaciones de Office que desee a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-228">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="a0203-229">Si Outlook está instalado, asegúrese de establecer el OST de Outlook para que solo se guarden las últimas dos semanas de caché.</span><span class="sxs-lookup"><span data-stu-id="a0203-229">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="a0203-230">Esto disminuirá en gran medida el uso del disco y el tiempo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a0203-230">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="a0203-231">Seleccione **File**  >  **configuración** de la cuenta de archivo y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="a0203-231">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="a0203-232">Seleccione **cambiar** y el control deslizante para **usar el modo caché de Exchange** en 14 días.</span><span class="sxs-lookup"><span data-stu-id="a0203-232">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="a0203-233">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0203-233">Microsoft Teams</span></span>

1. <span data-ttu-id="a0203-234">Descargue e instale [Microsoft Teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="a0203-234">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="a0203-235">Establecer la configuración para la aplicación de inicio automático (opcional).</span><span class="sxs-lookup"><span data-stu-id="a0203-235">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="a0203-236">Anclar equipos a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-236">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="a0203-237">Considere la posibilidad de reducir las notificaciones de Teams en el dispositivo para evitar distracciones (opcional).</span><span class="sxs-lookup"><span data-stu-id="a0203-237">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Notificaciones de Teams](images/teams.png)

### <span data-ttu-id="a0203-239">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="a0203-239">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0203-240">En Windows 10, versión 2004 y posteriores, la aplicación de conexión para proyección inalámbrica con Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="a0203-240">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="a0203-241">Para instalar la aplicación, seleccione en la **configuración**  >  **Apps**  >  **características opcionales**  >  **Agregar una característica** y, a continuación, instalar la aplicación de **visualización inalámbrica** .</span><span class="sxs-lookup"><span data-stu-id="a0203-241">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="a0203-242">Busque **Connect**.</span><span class="sxs-lookup"><span data-stu-id="a0203-242">Search for **Connect**.</span></span>
2. <span data-ttu-id="a0203-243">Abra la aplicación y ciérrela (el**proyecto en este equipo** podría no funcionar, a menos que la aplicación se haya ejecutado al menos una vez).</span><span class="sxs-lookup"><span data-stu-id="a0203-243">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="a0203-244">Mantenga pulsado o haga clic con el botón derecho para anclar a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-244">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="a0203-245">Busque la **configuración de proyección**.</span><span class="sxs-lookup"><span data-stu-id="a0203-245">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="a0203-246">En **algunos dispositivos con Windows y Android puede proyectar en este equipo cuando lo digas correctamente**, elija **disponible en todas partes** si el dispositivo no está en una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="a0203-246">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="a0203-247">De lo contrario, puede elegir **disponible en todas partes en redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="a0203-247">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="a0203-248">En **preguntar al proyecto en este equipo**, seleccione **solo la primera vez**.</span><span class="sxs-lookup"><span data-stu-id="a0203-248">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="a0203-249">En **requerir PIN para el emparejamiento**, elija **nunca**.</span><span class="sxs-lookup"><span data-stu-id="a0203-249">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="a0203-250">Configuración recomendada cuando no se encuentra en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="a0203-250">Recommended configuration when not on the corporate network:</span></span>

  ![Configuración en casa](images/project1.png)

<span data-ttu-id="a0203-252">Configuración recomendada en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="a0203-252">Recommended configuration on the corporate network:</span></span>

  ![Configuración en el trabajo](images/project2.png)

### <span data-ttu-id="a0203-254">Tu Teléfono</span><span class="sxs-lookup"><span data-stu-id="a0203-254">Your Phone</span></span>

<span data-ttu-id="a0203-255">La aplicación de **tu teléfono** se instala de forma predeterminada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a0203-255">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="a0203-256">Si no está presente, también puede instalarlo desde la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="a0203-256">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="a0203-257">Para obtener información sobre cómo configurar la aplicación, vea [Cómo configurar el teléfono en Windows 10 y cómo sincronizar datos entre su equipo y su teléfono](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="a0203-257">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="a0203-258">Además, consulta [cómo solucionar problemas comunes con tu aplicación de teléfono en Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="a0203-258">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="a0203-259">Zonas súper sofisticadas</span><span class="sxs-lookup"><span data-stu-id="a0203-259">Super Fancy Zones</span></span>

<span data-ttu-id="a0203-260">Las **zonas súper sofisticadas** ayudan a los usuarios a organizar las ventanas para maximizar el espacio de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a0203-260">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="a0203-261">Ahora se incluye en [PowerToys](https://github.com/microsoft/PowerToys/releases) en github.</span><span class="sxs-lookup"><span data-stu-id="a0203-261">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="a0203-262">Explorador de cromo de cromo</span><span class="sxs-lookup"><span data-stu-id="a0203-262">Edge Chromium browser</span></span>

<span data-ttu-id="a0203-263">Descarga e instala el nuevo [navegador Edge de cromo](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="a0203-263">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="a0203-264">Configuración adicional</span><span class="sxs-lookup"><span data-stu-id="a0203-264">Additional settings</span></span>

### <span data-ttu-id="a0203-265">Cola de plumas Seleccione para iniciar pizarra</span><span class="sxs-lookup"><span data-stu-id="a0203-265">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="a0203-266">Busque el **lápiz** y seleccione **pluma & la configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="a0203-266">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="a0203-267">Cerca de la parte inferior de la página, en **accesos directos de lápiz** , **Seleccione una vez** para la **pizarra de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="a0203-267">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="a0203-268">Administración de energía</span><span class="sxs-lookup"><span data-stu-id="a0203-268">Power management</span></span>

<span data-ttu-id="a0203-269">Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10 Pro o Enterprise en Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="a0203-269">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="a0203-270">Esto incluye tiempos de espera de pantalla y equipo y cómo interactúan con la detección de presencia humana integrada (Doppler), el protector de pantalla y la protección con contraseña y, si es adecuado, cómo pasar la configuración de energía de la Directiva de grupo para usuarios de equipos portátiles o de escritorio.</span><span class="sxs-lookup"><span data-stu-id="a0203-270">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="a0203-271">Windows 10 Pro o Enterprise en Surface Hub 2 evita que la pantalla pase de la pantalla a la entrada táctil, el mouse y el teclado, así como la detección de la ocupación de la ocupación integrada (Doppler).</span><span class="sxs-lookup"><span data-stu-id="a0203-271">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="a0203-272">La detección de la ocupación de los seres humanos está habilitada de forma predeterminada, pero si se desea, se puede deshabilitar en UEFI al alternar la opción dispositivo en la herramienta de configuración de Surface UEFI, ya sea como parte de la migración inicial o mediante la creación y aplicación de un paquete de configuración UEFI posterior.</span><span class="sxs-lookup"><span data-stu-id="a0203-272">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="a0203-273">Administración de energía: configuración de suspensión de pantalla y PC</span><span class="sxs-lookup"><span data-stu-id="a0203-273">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="a0203-274">Seleccione **Start**  >  **Settings**  >  **System**  >  **Power & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="a0203-274">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="a0203-275">Configure el control deslizante de modo de energía para **obtener el mejor rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="a0203-275">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="a0203-276">Configure valores de pantalla y de espera para su preferencia, así como para la detección de presencia de Doppler que reactiva el dispositivo cuando se detecta movimiento.</span><span class="sxs-lookup"><span data-stu-id="a0203-276">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="a0203-277">Como práctica recomendada, se recomienda configurar la pantalla para que se apague **después de dos horas** y el equipo **apagado después de 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="a0203-277">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="a0203-278">Administración de energía: protector de pantalla</span><span class="sxs-lookup"><span data-stu-id="a0203-278">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="a0203-279">Busque **pantalla de bloqueo** y Abra **configuración de pantalla de bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="a0203-279">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="a0203-280">Configure la configuración del **protector de pantalla** y la **configuración del tiempo de espera de pantalla** para sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="a0203-280">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="a0203-281">Sensor de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="a0203-281">Storage Sense</span></span>

<span data-ttu-id="a0203-282">Surface Hub 2 tiene un SSD de 128 GB para almacenamiento local, por lo que es necesario considerar el uso de las medidas de almacenamiento de almacenamiento durante el uso normal.</span><span class="sxs-lookup"><span data-stu-id="a0203-282">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="a0203-283">Para configurar el sensor de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="a0203-283">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="a0203-284">Busque la **configuración de almacenamiento**, que se encuentra en **configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0203-284">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="a0203-285">En **configuración**, seleccione **Activar sensor de almacenamiento** para abrir la página Configuración de **almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="a0203-285">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="a0203-286">Activar el sentido **de**almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a0203-286">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="a0203-287">Seleccione **configurar sensor de almacenamiento o ejecutarlo ahora** y configure las opciones para mantener los archivos en línea todo lo posible (debido a un espacio en disco limitado).</span><span class="sxs-lookup"><span data-stu-id="a0203-287">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="a0203-288">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="a0203-288">Recommended settings:</span></span>
- <span data-ttu-id="a0203-289">Ejecutar sensor de almacenamiento = todos los días.</span><span class="sxs-lookup"><span data-stu-id="a0203-289">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="a0203-290">Elimine los archivos temporales que mis aplicaciones no usan = cada 14 días (al menos).</span><span class="sxs-lookup"><span data-stu-id="a0203-290">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="a0203-291">Eliminar archivos de mi carpeta de descargas si ya lo han recibido durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="a0203-291">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="a0203-292">OneDrive: el contenido se volverá a estar en línea si no se abre durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="a0203-292">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="a0203-293">Modo tableta</span><span class="sxs-lookup"><span data-stu-id="a0203-293">Tablet mode</span></span>

<span data-ttu-id="a0203-294">Activa el modo tableta si así lo deseas.</span><span class="sxs-lookup"><span data-stu-id="a0203-294">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="a0203-295">Administración de energía</span><span class="sxs-lookup"><span data-stu-id="a0203-295">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="a0203-296">Antes de realizar el procedimiento siguiente, consulte con el Departamento de TI para obtener una aprobación para excluir un dispositivo Surface Hub 2S de la Directiva de administración global de energía.</span><span class="sxs-lookup"><span data-stu-id="a0203-296">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="a0203-297">Algunas configuraciones de administración de energía pueden deshabilitar la función de detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="a0203-297">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="a0203-298">Busque **software Center** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="a0203-298">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="a0203-299">Seleccione **las opciones** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="a0203-299">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="a0203-300">Expanda la sección **Administración de energía** y seleccione no **aplicar la configuración de energía del Departamento de ti a este equipo**.</span><span class="sxs-lookup"><span data-stu-id="a0203-300">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![Configuración de software](images/soft-cntr.png)

### <span data-ttu-id="a0203-302">Configuración de sonido</span><span class="sxs-lookup"><span data-stu-id="a0203-302">Sound settings</span></span>

1. <span data-ttu-id="a0203-303">Busque la **configuración de sonidos** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="a0203-303">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="a0203-304">Seleccione **Panel de control de sonido** a la derecha y seleccione la pestaña **sonidos** .</span><span class="sxs-lookup"><span data-stu-id="a0203-304">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="a0203-305">En **eventos de programa** , establezca **Conectar dispositivo** y **desconectar dispositivo** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="a0203-305">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="a0203-306">Notificaciones de silencio</span><span class="sxs-lookup"><span data-stu-id="a0203-306">Silence notifications</span></span>

1. <span data-ttu-id="a0203-307">Busque el **Asistente de concentración** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="a0203-307">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="a0203-308">Seleccione **solo alarmas**.</span><span class="sxs-lookup"><span data-stu-id="a0203-308">Select **Alarms Only**.</span></span> <span data-ttu-id="a0203-309">Esto evitará controles flotantes de notificaciones constantes.</span><span class="sxs-lookup"><span data-stu-id="a0203-309">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="a0203-310">Liberador de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="a0203-310">Disk Cleanup</span></span>

1. <span data-ttu-id="a0203-311">Busque el **liberador de espacio en disco** y abra esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0203-311">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="a0203-312">En **archivos para eliminar**, seleccione los archivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="a0203-312">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="a0203-313">Seleccione **limpiar archivos de sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0203-313">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="a0203-314">Completar y comprobar</span><span class="sxs-lookup"><span data-stu-id="a0203-314">Complete and verify</span></span>

1. <span data-ttu-id="a0203-315">Busque e instale todas las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="a0203-315">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="a0203-316">Actualizar la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a0203-316">Update Group Policy</span></span>
    1. <span data-ttu-id="a0203-317">En un símbolo del sistema con privilegios elevados, escriba **gpupdate/force/boot/wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="a0203-317">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="a0203-318">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0203-318">Reboot the device.</span></span>
4. <span data-ttu-id="a0203-319">Comprobar las aplicaciones de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a0203-319">Verify taskbar apps.</span></span>
    - <span data-ttu-id="a0203-320">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="a0203-320">Connect App</span></span>
    - <span data-ttu-id="a0203-321">Icono de candado</span><span class="sxs-lookup"><span data-stu-id="a0203-321">Lock Icon</span></span>
    - <span data-ttu-id="a0203-322">Recorte y anotación</span><span class="sxs-lookup"><span data-stu-id="a0203-322">Snip & Sketch</span></span>
    - <span data-ttu-id="a0203-323">Teams (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="a0203-323">Teams (if applicable)</span></span>
    - <span data-ttu-id="a0203-324">Aplicaciones de Office (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="a0203-324">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="a0203-325">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="a0203-325">Surface App</span></span>
    - <span data-ttu-id="a0203-326">Pizarra interactiva</span><span class="sxs-lookup"><span data-stu-id="a0203-326">Whiteboard</span></span>
5. <span data-ttu-id="a0203-327">Comprobar la detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="a0203-327">Verify presence detection.</span></span>
    - <span data-ttu-id="a0203-328">La detección de presencia será un icono verde en la bandeja del sistema</span><span class="sxs-lookup"><span data-stu-id="a0203-328">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="a0203-329">Comprobar que los proyectos se han habilitado con la aplicación Connect (la aplicación no necesita estar ejecutándose antes de conectar).</span><span class="sxs-lookup"><span data-stu-id="a0203-329">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="a0203-330">Comprobar la configuración de energía y suspensión.</span><span class="sxs-lookup"><span data-stu-id="a0203-330">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="a0203-331">Protector de pantalla: 15 minutos, establecido en (ninguno), de formas o en blanco; casilla para requerir contraseña</span><span class="sxs-lookup"><span data-stu-id="a0203-331">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="a0203-332">Pantalla: **apague después de 2 horas.**</span><span class="sxs-lookup"><span data-stu-id="a0203-332">Screen: **Turn off after 2 hours.**</span></span>
    - <span data-ttu-id="a0203-333">PC:  **apagar después de 4 horas.**</span><span class="sxs-lookup"><span data-stu-id="a0203-333">PC:  **Turn off after 4 hours.**</span></span>
8. <span data-ttu-id="a0203-334">Compruebe que Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="a0203-334">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="a0203-335">Comprobar la sincronización la configuración está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a0203-335">Verify sync your settings is disabled.</span></span>
10. <span data-ttu-id="a0203-336">Comprobar las aplicaciones de inicio.</span><span class="sxs-lookup"><span data-stu-id="a0203-336">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="a0203-337">Después de instalar y configurar Windows 10, Surface Hub 2S se puede administrar como cualquier otro dispositivo de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a0203-337">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="a0203-338">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a0203-338">Related topics</span></span>

[<span data-ttu-id="a0203-339">Migrar a Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="a0203-339">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)

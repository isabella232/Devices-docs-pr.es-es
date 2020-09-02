---
title: Windows 10 para la configuración posterior a la instalación de Surface Hub 2
description: Windows 10 para la configuración posterior a la instalación de Surface Hub 2
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
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: d6a1cdb2cac01b48c80e0fa4b7ccb6d3bcdb76ac
ms.sourcegitcommit: 6618e8fe05628aa8b17654584657eff0f784dbfd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986713"
---
# <span data-ttu-id="068cf-104">Windows 10 para la configuración posterior a la instalación de Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="068cf-104">Windows 10 for Surface Hub 2 post-install configuration</span></span>

**<span data-ttu-id="068cf-105">Se aplica a: Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="068cf-105">Applies to: Surface Hub 2S</span></span>** 

<span data-ttu-id="068cf-106">Después de completar el proceso de instalación de la migración a Windows 10 Pro o Enterprise, puede realizar los siguientes pasos para configurar las aplicaciones y la configuración de su Surface Hub 2.</span><span class="sxs-lookup"><span data-stu-id="068cf-106">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="068cf-107">Estos pasos se recomiendan para garantizar la mejor experiencia de uso de este equipo de pantalla táctil y de lápiz de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="068cf-107">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="068cf-108">Al realizar estos pasos, es posible que le resulte útil usar un teclado y un mouse con cable o inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="068cf-108">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="068cf-109">Configurar las opciones del sistema</span><span class="sxs-lookup"><span data-stu-id="068cf-109">Configure system settings</span></span>

1. <span data-ttu-id="068cf-110">Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="068cf-110">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="068cf-111">En los dispositivos Unidos a Azure AD, el usuario que realiza la combinación de Azure AD se agrega automáticamente al grupo de administradores local.</span><span class="sxs-lookup"><span data-stu-id="068cf-111">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="068cf-112">Los administradores globales de Azure AD y los administradores de dispositivos Azure AD [también son administradores locales](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span><span class="sxs-lookup"><span data-stu-id="068cf-112">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="068cf-113">Puede escribir **net localgroup Administrators** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="068cf-113">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="068cf-114">Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo: **nombre de usuario-SHub-escritorio**.</span><span class="sxs-lookup"><span data-stu-id="068cf-114">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="068cf-115">Seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sync Your Settings** y desactiva la **configuración de sincronización** .</span><span class="sxs-lookup"><span data-stu-id="068cf-115">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="068cf-116">La configuración que se usa aquí tiene el propósito de habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no desee sincronizar otros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="068cf-116">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="068cf-117">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="068cf-117">Reboot the device.</span></span>

## <span data-ttu-id="068cf-118">Habilitar el teclado táctil y el panel táctil</span><span class="sxs-lookup"><span data-stu-id="068cf-118">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="068cf-119">Puntee y mantenga presionado o haga clic con el botón derecho en la barra de tareas y seleccione Mostrar botón de **teclado táctil** y **Mostrar botón de panel táctil**.</span><span class="sxs-lookup"><span data-stu-id="068cf-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="068cf-120">El teclado táctil es útil para la entrada directa por parte del usuario, y el panel táctil virtual ayuda a seleccionar con precisión, mantener la información en la pantalla o como alternativa para tocar y mantener el mouse.</span><span class="sxs-lookup"><span data-stu-id="068cf-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="068cf-121">Consulta el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="068cf-121">See the following example.</span></span>

     ![Configuración táctil](images/touch.png)

2. <span data-ttu-id="068cf-123">Configure el teclado táctil en QWERTY y flotantes.</span><span class="sxs-lookup"><span data-stu-id="068cf-123">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="068cf-124">Seleccione el icono de teclado en la barra de tareas para mostrar el teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="068cf-124">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="068cf-125">En el teclado táctil, seleccione el icono de teclado en la esquina superior izquierda para abrir la configuración del teclado.</span><span class="sxs-lookup"><span data-stu-id="068cf-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="068cf-126">Seleccione el siguiente tipo de teclado en la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar el flotante, que es muy útil en esta gran pantalla.</span><span class="sxs-lookup"><span data-stu-id="068cf-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="068cf-127">Vea los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="068cf-127">See the following examples.</span></span>

     ![Configuración del teclado](images/kbd.png)

3. <span data-ttu-id="068cf-129">Establecer la configuración de teclado de pantalla.</span><span class="sxs-lookup"><span data-stu-id="068cf-129">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="068cf-130">Buscar y abrir la **configuración de escritura**</span><span class="sxs-lookup"><span data-stu-id="068cf-130">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="068cf-131">Habilite todas las opciones de ortografía, escritura y teclado táctil.</span><span class="sxs-lookup"><span data-stu-id="068cf-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="068cf-132">En el ejemplo siguiente se muestra el panel táctil, que es útil para desplazarse y seleccionar las opciones.</span><span class="sxs-lookup"><span data-stu-id="068cf-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="068cf-133">El teclado en pantalla se usa para buscar en Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="068cf-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![Usar el panel táctil](images/store.png)

## <span data-ttu-id="068cf-135">Configurar el mouse y el teclado Bluetooth (opcional)</span><span class="sxs-lookup"><span data-stu-id="068cf-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="068cf-136">Conecte un teclado y un mouse si usa el dispositivo como dispositivo principal de Windows, o bien Utilícelo a menudo para trabajar con texto o con precisión.</span><span class="sxs-lookup"><span data-stu-id="068cf-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="068cf-137">Si el dispositivo Surface Hub está cerca de un PC, puedes usar el [mouse sin bordes](https://aka.ms/mm) para desplazarte sin problemas entre el Surface Hub y el equipo.</span><span class="sxs-lookup"><span data-stu-id="068cf-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="068cf-138">Para obtener más información, vea [Descargar Microsoft del garaje: mouse sin bordes](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span><span class="sxs-lookup"><span data-stu-id="068cf-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="068cf-139">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="068cf-139">OneDrive for Business</span></span>

<span data-ttu-id="068cf-140">Use [OneDrive para la empresa](https://docs.microsoft.com/onedrive/onedrive) para compartir fácilmente herramientas, registros y otros archivos entre todos los dispositivos de su trabajo.</span><span class="sxs-lookup"><span data-stu-id="068cf-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="068cf-141">OneDrive le permite compartir sus archivos de trabajo entre sus equipos portátiles, el escritorio Surface Hub y los dispositivos móviles administrados por Intune.</span><span class="sxs-lookup"><span data-stu-id="068cf-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="068cf-142">Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.</span><span class="sxs-lookup"><span data-stu-id="068cf-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="068cf-143">Teniendo en cuenta el tamaño de la SSD del Surface Hub (128 GB), si configura OneDrive en su dispositivo de escritorio Surface Hub, asegúrese de que la configuración predeterminada es mantener los archivos en línea y descargar archivos a medida que los usa.</span><span class="sxs-lookup"><span data-stu-id="068cf-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="068cf-144">Para configurar OneDrive de modo que descargue los archivos solo cuando sea necesario, establezca la configuración **de archivos a petición** para **ahorrar espacio y descargar archivos a medida que los usa**.</span><span class="sxs-lookup"><span data-stu-id="068cf-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="068cf-145">Para obtener más información, vea [consultar y establecer los Estados a petición de los archivos en Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span><span class="sxs-lookup"><span data-stu-id="068cf-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![Configuración de OneDrive](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="068cf-147">También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de ahorrar espacio en disco y solo descargar archivos a medida que los necesite.</span><span class="sxs-lookup"><span data-stu-id="068cf-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="068cf-148">SharePoint y Teams</span><span class="sxs-lookup"><span data-stu-id="068cf-148">SharePoint and Teams</span></span>

<span data-ttu-id="068cf-149">Los archivos de canal de SharePoint y Teams también se pueden sincronizar localmente con los dispositivos de escritorio, como equipos portátiles y Surface Hub, con el motor de sincronización de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="068cf-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="068cf-150">Para sincronizar los archivos corporativos internos con la unidad local con la aplicación de sincronización de OneDrive:</span><span class="sxs-lookup"><span data-stu-id="068cf-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="068cf-151">Vaya a un sitio de SharePoint y navegue hasta el directorio de documentos de nivel superior para ver los archivos que le interesa ver o editar desde el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="068cf-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="068cf-152">Seleccione el botón **sincronizar** en la parte superior de la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="068cf-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="068cf-153">Seleccione al **abrir** en el elemento emergente **este sitio está intentando abrir Microsoft OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="068cf-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="068cf-154">Compruebe que los archivos de SharePoint se sincronizan con su unidad local seleccionando en el icono de OneDrive en la parte inferior derecha de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="068cf-155">Compruebe que la configuración esté configurada para mantener los archivos en línea y descargar los archivos solo a medida que los usa:</span><span class="sxs-lookup"><span data-stu-id="068cf-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="068cf-156">Abra el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="068cf-156">Open file explorer.</span></span>
    2. <span data-ttu-id="068cf-157">Desplácese a la y seleccione la derecha en el \*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="068cf-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="068cf-158">Seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="068cf-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="068cf-159">La columna Estado mostrará el estado de archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="068cf-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="068cf-160">Para obtener más información, vea [sincronizar archivos de SharePoint con el cliente de sincronización de OneDrive](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span><span class="sxs-lookup"><span data-stu-id="068cf-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="068cf-161">Los archivos de canales de equipos se almacenan en sitios de SharePoint, con todas las mismas funciones de documento de SharePoint, incluido el historial de versiones y la sincronización con dispositivos de escritorio locales.</span><span class="sxs-lookup"><span data-stu-id="068cf-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="068cf-162">Para sincronizar los archivos de canal:</span><span class="sxs-lookup"><span data-stu-id="068cf-162">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="068cf-163">Navegue hasta el canal de interés de los equipos y seleccione en la pestaña **archivos** de la parte superior.</span><span class="sxs-lookup"><span data-stu-id="068cf-163">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="068cf-164">Después, seleccione **sincronizar**. Los archivos comenzarán a sincronizarse y se verán en el explorador de archivos en el \*\*escritorio \ Microsoft \ \<name of the Teams Channel\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="068cf-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="068cf-165">Use el mismo procedimiento que usó para sincronizar los sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, pulse y mantenga presionado o haga clic con el botón derecho en el explorador de archivos en el nombre de canal de Teams y, a continuación, seleccione **liberar espacio**.</span><span class="sxs-lookup"><span data-stu-id="068cf-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="068cf-166">Emparejar el lápiz de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="068cf-166">Pair the Surface Hub pen</span></span>

<span data-ttu-id="068cf-167">Para emparejar el dispositivo de pluma:</span><span class="sxs-lookup"><span data-stu-id="068cf-167">To pair the pen device:</span></span>

1. <span data-ttu-id="068cf-168">Seleccione **Start**  >  **Settings**  >  **Devices**.</span><span class="sxs-lookup"><span data-stu-id="068cf-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="068cf-169">Seleccione **Agregar Bluetooth u otro dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="068cf-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="068cf-170">Elija **Bluetooth**.</span><span class="sxs-lookup"><span data-stu-id="068cf-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="068cf-171">Quite el botón cola de pluma y agite para desconectar la conexión de la batería.</span><span class="sxs-lookup"><span data-stu-id="068cf-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="068cf-172">Vuelva a colocar el tapón y mantenga presionado el tapón hasta que el LED de emparejamiento parpadee.</span><span class="sxs-lookup"><span data-stu-id="068cf-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="068cf-173">En la configuración de Bluetooth Surface Hub, seleccione **lápiz de Surface Hub 2**.</span><span class="sxs-lookup"><span data-stu-id="068cf-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="068cf-174">Complete la operación de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="068cf-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="068cf-175">Si el emparejamiento no se realiza correctamente, intente volver a emparejar el lápiz.</span><span class="sxs-lookup"><span data-stu-id="068cf-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="068cf-176">Si es necesario, reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="068cf-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="068cf-177">Configuración de la cámara</span><span class="sxs-lookup"><span data-stu-id="068cf-177">Camera configuration</span></span>

<span data-ttu-id="068cf-178">Puede montar la cámara en la parte superior o en cualquiera de los lados del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="068cf-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="068cf-179">Monte la cámara en una posición para optimizar el ángulo de la cámara si está usando el Hub con un soporte de escritorio en lugar de un carrito o está cerca del concentrador.</span><span class="sxs-lookup"><span data-stu-id="068cf-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="068cf-180">La cámara no gira automáticamente, por lo que debe tener una clave hexadecimal 2mm para girar la cámara de forma manual.</span><span class="sxs-lookup"><span data-stu-id="068cf-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="068cf-181">Para obtener más información sobre cómo montar la cámara y girar la cámara de forma manual, consulte [Surface Hub 2s orientación de lente](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation)de la cámara.</span><span class="sxs-lookup"><span data-stu-id="068cf-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="068cf-182">Configuración de Windows Hello</span><span class="sxs-lookup"><span data-stu-id="068cf-182">Windows Hello configuration</span></span>

<span data-ttu-id="068cf-183">Surface Hub 2S si se ejecuta Windows 10 Enterprise, se permite el conjunto completo de aplicaciones de escritorio Win32, así como las opciones de Windows Hello biométricas.</span><span class="sxs-lookup"><span data-stu-id="068cf-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="068cf-184">El accesorio de lector de huellas dactilares Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="068cf-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="068cf-185">El lector de huellas dactilares de Surface Hub 2 estará disponible para su compra en breve.</span><span class="sxs-lookup"><span data-stu-id="068cf-185">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="068cf-186">Para obtener más información sobre cómo comprar, vuelve a consultar esta página.</span><span class="sxs-lookup"><span data-stu-id="068cf-186">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="068cf-187">Después de insertar el lector Fingerprint Reader, seleccione **Start**  >  **Settings**  >  **accounts**  >  **Sign-in Options**  >  **huellator de Windows Hello** para inscribir su huella dactilar.</span><span class="sxs-lookup"><span data-stu-id="068cf-187">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="068cf-188">Usar un dispositivo certificado de Windows Hello para un reconocimiento facial.</span><span class="sxs-lookup"><span data-stu-id="068cf-188">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="068cf-189">La cámara Surface Hub 2S no admite el reconocimiento facial de Windows Hello.</span><span class="sxs-lookup"><span data-stu-id="068cf-189">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="068cf-190">Habilitar un icono de método abreviado de pantalla de bloqueo en la barra de tareas</span><span class="sxs-lookup"><span data-stu-id="068cf-190">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="068cf-191">Para agregar un icono a la barra de tareas que permita un único toque de pantalla similar al método abreviado de teclado Windows-L:</span><span class="sxs-lookup"><span data-stu-id="068cf-191">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="068cf-192">Puntee y mantenga presionado o haga clic con el botón derecho en el escritorio, seleccione **nuevo**  >  **método abreviado**  >  **examinar**  >  **escritorio**  >  **Aceptar**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="068cf-192">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>
2.  <span data-ttu-id="068cf-193">Escriba un nombre para el acceso directo, como **bloquear mi PC**y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="068cf-193">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>
3.  <span data-ttu-id="068cf-194">Haga clic con el botón secundario del ratón o mantenga pulsado el acceso directo recién creado en el escritorio y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="068cf-194">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="068cf-195">En la pestaña **acceso directo** , escriba lo siguiente en el campo de **destino** : **Rundll32.exe User32.dll, LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="068cf-195">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>
4.  <span data-ttu-id="068cf-196">Seleccione el botón **Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione el icono que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="068cf-196">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 
5. <span data-ttu-id="068cf-197">Observa el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="068cf-197">See the following example:</span></span>

    ![Elegir un icono](images/lock.png)
6.  <span data-ttu-id="068cf-199">Seleccione **Aceptar** para guardar el método abreviado.</span><span class="sxs-lookup"><span data-stu-id="068cf-199">Select **OK** to save the shortcut.</span></span>
7.  <span data-ttu-id="068cf-200">Haga clic con el botón derecho o mantenga presionado el acceso directo y seleccione **anclar a la barra de tareas**.</span><span class="sxs-lookup"><span data-stu-id="068cf-200">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="068cf-201">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="068cf-201">Applications</span></span>

### <span data-ttu-id="068cf-202">Actualizar las aplicaciones instaladas</span><span class="sxs-lookup"><span data-stu-id="068cf-202">Update installed apps</span></span>

<span data-ttu-id="068cf-203">Para actualizar todas las aplicaciones de la tienda instaladas:</span><span class="sxs-lookup"><span data-stu-id="068cf-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="068cf-204">Abra la aplicación Microsoft Store y seleccione **Ver más** puntos suspensivos en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="068cf-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="068cf-205">Seleccione **descargas y actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="068cf-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="068cf-206">Seleccione **obtener actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="068cf-206">Select **Get updates**.</span></span>

### <span data-ttu-id="068cf-207">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="068cf-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="068cf-208">Para instalar la pizarra de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="068cf-208">To install the Microsoft Whiteboard:</span></span>

1. <span data-ttu-id="068cf-209">Seleccione el icono del **área de trabajo de Windows Ink** ![ área ](images/ink.png) de trabajo en la esquina inferior derecha de la barra de tareas y descargar **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="068cf-209">Select the **Windows Ink Workspace** icon ![Ink workspace](images/ink.png) on the lower right of the taskbar and download **Whiteboard**.</span></span>

<span data-ttu-id="068cf-210">Como alternativa, puede instalar whiteboard desde Microsoft Store:</span><span class="sxs-lookup"><span data-stu-id="068cf-210">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="068cf-211">Abra la aplicación Microsoft Store y busque **pizarra**.</span><span class="sxs-lookup"><span data-stu-id="068cf-211">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="068cf-212">Elija **no gracias** para iniciar sesión y usar en todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="068cf-212">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="068cf-213">Anclar pizarra a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-213">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="068cf-214">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="068cf-214">Surface app</span></span>

1. <span data-ttu-id="068cf-215">En Microsoft Store, busque **Surface**.</span><span class="sxs-lookup"><span data-stu-id="068cf-215">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="068cf-216">Establezca el filtro **disponible en en** **todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="068cf-216">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="068cf-217">Instala la aplicación **Surface** .</span><span class="sxs-lookup"><span data-stu-id="068cf-217">Install the **Surface** app.</span></span> <span data-ttu-id="068cf-218">Debe ser la primera aplicación de la lista.</span><span class="sxs-lookup"><span data-stu-id="068cf-218">This should be the first app listed.</span></span> <span data-ttu-id="068cf-219">Es posible que necesites asociar tu MSA a la tienda para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="068cf-219">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="068cf-220">Ancla la aplicación de **Surface** a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-220">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="068cf-221">Recorte & esbozo</span><span class="sxs-lookup"><span data-stu-id="068cf-221">Snip & Sketch</span></span>

1. <span data-ttu-id="068cf-222">Abra el **recorte &** aplicación de boceto y ancle la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-222">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="068cf-223">Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="068cf-223">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="068cf-224">En **configuración**, Active **copiar automáticamente en el portapapeles**, **Guardar recortes**y **varias ventanas** (opcional).</span><span class="sxs-lookup"><span data-stu-id="068cf-224">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="068cf-225">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="068cf-225">Microsoft Office</span></span>

1. <span data-ttu-id="068cf-226">Abra el [portal de Office](https://portal.office.com/account#installs) e instale las aplicaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="068cf-226">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="068cf-227">Anclar las aplicaciones de Office que desee a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-227">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="068cf-228">Si Outlook está instalado, asegúrese de establecer el OST de Outlook para que solo se guarden las últimas dos semanas de caché.</span><span class="sxs-lookup"><span data-stu-id="068cf-228">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="068cf-229">Esto disminuirá en gran medida el uso del disco y el tiempo de configuración.</span><span class="sxs-lookup"><span data-stu-id="068cf-229">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="068cf-230">Seleccione **File**  >  **configuración** de la cuenta de archivo y seleccione su cuenta.</span><span class="sxs-lookup"><span data-stu-id="068cf-230">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="068cf-231">Seleccione **cambiar** y el control deslizante para **usar el modo caché de Exchange** en 14 días.</span><span class="sxs-lookup"><span data-stu-id="068cf-231">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="068cf-232">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="068cf-232">Microsoft Teams</span></span>

1. <span data-ttu-id="068cf-233">Descargue e instale [Microsoft Teams](https://teams.microsoft.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="068cf-233">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="068cf-234">Establecer la configuración para la aplicación de inicio automático (opcional).</span><span class="sxs-lookup"><span data-stu-id="068cf-234">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="068cf-235">Anclar equipos a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-235">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="068cf-236">Considere la posibilidad de reducir las notificaciones de Teams en el dispositivo para evitar distracciones (opcional).</span><span class="sxs-lookup"><span data-stu-id="068cf-236">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![Notificaciones de Teams](images/teams.png)

### <span data-ttu-id="068cf-238">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="068cf-238">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="068cf-239">En Windows 10, versión 2004 y posteriores, la aplicación de conexión para proyección inalámbrica con Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional.</span><span class="sxs-lookup"><span data-stu-id="068cf-239">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="068cf-240">Para instalar la aplicación, seleccione en la **configuración**  >  **Apps**  >  **características opcionales**  >  **Agregar una característica** y, a continuación, instalar la aplicación de **visualización inalámbrica** .</span><span class="sxs-lookup"><span data-stu-id="068cf-240">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="068cf-241">Busque **Connect**.</span><span class="sxs-lookup"><span data-stu-id="068cf-241">Search for **Connect**.</span></span>
2. <span data-ttu-id="068cf-242">Abra la aplicación y ciérrela (el**proyecto en este equipo** podría no funcionar, a menos que la aplicación se haya ejecutado al menos una vez).</span><span class="sxs-lookup"><span data-stu-id="068cf-242">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="068cf-243">Mantenga pulsado o haga clic con el botón derecho para anclar a la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-243">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="068cf-244">Busque la **configuración de proyección**.</span><span class="sxs-lookup"><span data-stu-id="068cf-244">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="068cf-245">En **algunos dispositivos con Windows y Android puede proyectar en este equipo cuando lo digas correctamente**, elija **disponible en todas partes** si el dispositivo no está en una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="068cf-245">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="068cf-246">De lo contrario, puede elegir **disponible en todas partes en redes seguras**.</span><span class="sxs-lookup"><span data-stu-id="068cf-246">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="068cf-247">En **preguntar al proyecto en este equipo**, seleccione **solo la primera vez**.</span><span class="sxs-lookup"><span data-stu-id="068cf-247">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="068cf-248">En **requerir PIN para el emparejamiento**, elija **nunca**.</span><span class="sxs-lookup"><span data-stu-id="068cf-248">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="068cf-249">Configuración recomendada cuando no se encuentra en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="068cf-249">Recommended configuration when not on the corporate network:</span></span>

  ![Configuración en casa](images/project1.png)

<span data-ttu-id="068cf-251">Configuración recomendada en la red corporativa:</span><span class="sxs-lookup"><span data-stu-id="068cf-251">Recommended configuration on the corporate network:</span></span>

  ![Configuración en el trabajo](images/project2.png)

### <span data-ttu-id="068cf-253">Tu teléfono</span><span class="sxs-lookup"><span data-stu-id="068cf-253">Your Phone</span></span>

<span data-ttu-id="068cf-254">La aplicación de **tu teléfono** se instala de forma predeterminada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="068cf-254">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="068cf-255">Si no está presente, también puede instalarlo desde la tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="068cf-255">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="068cf-256">Para obtener información sobre cómo configurar la aplicación, vea [Cómo configurar el teléfono en Windows 10 y cómo sincronizar datos entre su equipo y su teléfono](https://www.windowscentral.com/how-set-your-phone-windows-10).</span><span class="sxs-lookup"><span data-stu-id="068cf-256">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="068cf-257">Además, consulta [cómo solucionar problemas comunes con tu aplicación de teléfono en Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span><span class="sxs-lookup"><span data-stu-id="068cf-257">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="068cf-258">Zonas súper sofisticadas</span><span class="sxs-lookup"><span data-stu-id="068cf-258">Super Fancy Zones</span></span>

<span data-ttu-id="068cf-259">Las **zonas súper sofisticadas** ayudan a los usuarios a organizar las ventanas para maximizar el espacio de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="068cf-259">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="068cf-260">Ahora se incluye en [PowerToys](https://github.com/microsoft/PowerToys/releases) en github.</span><span class="sxs-lookup"><span data-stu-id="068cf-260">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="068cf-261">Explorador de cromo de cromo</span><span class="sxs-lookup"><span data-stu-id="068cf-261">Edge Chromium browser</span></span>

<span data-ttu-id="068cf-262">Descarga e instala el nuevo [navegador Edge de cromo](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span><span class="sxs-lookup"><span data-stu-id="068cf-262">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="068cf-263">Configuración adicional</span><span class="sxs-lookup"><span data-stu-id="068cf-263">Additional settings</span></span>

### <span data-ttu-id="068cf-264">Cola de plumas Seleccione para iniciar pizarra</span><span class="sxs-lookup"><span data-stu-id="068cf-264">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="068cf-265">Busque el **lápiz** y seleccione **pluma & la configuración de Windows Ink**.</span><span class="sxs-lookup"><span data-stu-id="068cf-265">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="068cf-266">Cerca de la parte inferior de la página, en **accesos directos de lápiz** , **Seleccione una vez** para la **pizarra de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="068cf-266">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="068cf-267">Configuración de energía y suspensión</span><span class="sxs-lookup"><span data-stu-id="068cf-267">Power and sleep settings</span></span>

1. <span data-ttu-id="068cf-268">Seleccione **Start**  >  **Settings**  >  **System**  >  **Power & Sleep**.</span><span class="sxs-lookup"><span data-stu-id="068cf-268">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="068cf-269">Configure el control deslizante de modo de energía para **obtener el mejor rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="068cf-269">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="068cf-270">Configure valores de pantalla y de espera para sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="068cf-270">Configure screen and sleep values to your preference.</span></span>

### <span data-ttu-id="068cf-271">Protector de pantalla</span><span class="sxs-lookup"><span data-stu-id="068cf-271">Screen saver</span></span>

1. <span data-ttu-id="068cf-272">Busque **pantalla de bloqueo** y Abra **configuración de pantalla de bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="068cf-272">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="068cf-273">Configure la configuración del **protector de pantalla** y la **configuración del tiempo de espera de pantalla** para sus preferencias.</span><span class="sxs-lookup"><span data-stu-id="068cf-273">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="068cf-274">Sensor de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="068cf-274">Storage Sense</span></span>

<span data-ttu-id="068cf-275">Surface Hub 2 tiene un SSD de 128 GB para almacenamiento local, por lo que es necesario considerar el uso de las medidas de almacenamiento de almacenamiento durante el uso normal.</span><span class="sxs-lookup"><span data-stu-id="068cf-275">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="068cf-276">Para configurar el sensor de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="068cf-276">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="068cf-277">Busque la **configuración de almacenamiento**, que se encuentra en **configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="068cf-277">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="068cf-278">En **configuración**, seleccione **Activar sensor de almacenamiento** para abrir la página Configuración de **almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="068cf-278">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="068cf-279">Activar el sentido **de**almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="068cf-279">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="068cf-280">Seleccione **configurar sensor de almacenamiento o ejecutarlo ahora** y configure las opciones para mantener los archivos en línea todo lo posible (debido a un espacio en disco limitado).</span><span class="sxs-lookup"><span data-stu-id="068cf-280">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="068cf-281">Configuración recomendada:</span><span class="sxs-lookup"><span data-stu-id="068cf-281">Recommended settings:</span></span>
- <span data-ttu-id="068cf-282">Ejecutar sensor de almacenamiento = todos los días.</span><span class="sxs-lookup"><span data-stu-id="068cf-282">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="068cf-283">Elimine los archivos temporales que mis aplicaciones no usan = cada 14 días (al menos).</span><span class="sxs-lookup"><span data-stu-id="068cf-283">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="068cf-284">Eliminar archivos de mi carpeta de descargas si ya lo han recibido durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="068cf-284">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="068cf-285">OneDrive: el contenido se volverá a estar en línea si no se abre durante más de = 30 días.</span><span class="sxs-lookup"><span data-stu-id="068cf-285">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="068cf-286">Modo tableta</span><span class="sxs-lookup"><span data-stu-id="068cf-286">Tablet mode</span></span>

<span data-ttu-id="068cf-287">Activa el modo tableta si así lo deseas.</span><span class="sxs-lookup"><span data-stu-id="068cf-287">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="068cf-288">Administración de energía</span><span class="sxs-lookup"><span data-stu-id="068cf-288">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="068cf-289">Antes de realizar el procedimiento siguiente, consulte con el Departamento de TI para obtener una aprobación para excluir un dispositivo Surface Hub 2S de la Directiva de administración global de energía.</span><span class="sxs-lookup"><span data-stu-id="068cf-289">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="068cf-290">Algunas configuraciones de administración de energía pueden deshabilitar la función de detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="068cf-290">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="068cf-291">Busque **software Center** y ábralo.</span><span class="sxs-lookup"><span data-stu-id="068cf-291">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="068cf-292">Seleccione **las opciones** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="068cf-292">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="068cf-293">Expanda la sección **Administración de energía** y seleccione la casilla **no aplicar la configuración de energía del Departamento de ti a este equipo**.</span><span class="sxs-lookup"><span data-stu-id="068cf-293">Expand the **Power management** section and select the checkbox **Do not apply power settings from my IT department to this computer**.</span></span>

  ![Configuración de software](images/soft-cntr.png)

### <span data-ttu-id="068cf-295">Configuración de sonido</span><span class="sxs-lookup"><span data-stu-id="068cf-295">Sound settings</span></span>

1. <span data-ttu-id="068cf-296">Busque la **configuración de sonidos** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="068cf-296">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="068cf-297">Seleccione **Panel de control de sonido** a la derecha y seleccione la pestaña **sonidos** .</span><span class="sxs-lookup"><span data-stu-id="068cf-297">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="068cf-298">En **eventos de programa** , establezca **Conectar dispositivo** y **desconectar dispositivo** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="068cf-298">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="068cf-299">Notificaciones de silencio</span><span class="sxs-lookup"><span data-stu-id="068cf-299">Silence notifications</span></span>

1. <span data-ttu-id="068cf-300">Busque el **Asistente de concentración** y abra esta página.</span><span class="sxs-lookup"><span data-stu-id="068cf-300">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="068cf-301">Seleccione **solo alarmas**.</span><span class="sxs-lookup"><span data-stu-id="068cf-301">Select **Alarms Only**.</span></span> <span data-ttu-id="068cf-302">Esto evitará controles flotantes de notificaciones constantes.</span><span class="sxs-lookup"><span data-stu-id="068cf-302">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="068cf-303">Liberador de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="068cf-303">Disk Cleanup</span></span>

1. <span data-ttu-id="068cf-304">Busque el **liberador de espacio en disco** y abra esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="068cf-304">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="068cf-305">En **archivos para eliminar**, seleccione los archivos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="068cf-305">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="068cf-306">Seleccione **limpiar archivos de sistema**.</span><span class="sxs-lookup"><span data-stu-id="068cf-306">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="068cf-307">Completar y comprobar</span><span class="sxs-lookup"><span data-stu-id="068cf-307">Complete and verify</span></span>

1. <span data-ttu-id="068cf-308">Busque e instale todas las actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="068cf-308">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="068cf-309">Actualizar la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="068cf-309">Update Group Policy</span></span>
    1. <span data-ttu-id="068cf-310">En un símbolo del sistema con privilegios elevados, escriba **gpupdate/force/boot/wait: 0**.</span><span class="sxs-lookup"><span data-stu-id="068cf-310">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="068cf-311">Reinicia el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="068cf-311">Reboot the device.</span></span>
4. <span data-ttu-id="068cf-312">Comprobar las aplicaciones de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="068cf-312">Verify taskbar apps.</span></span>
    - <span data-ttu-id="068cf-313">Conectar aplicación</span><span class="sxs-lookup"><span data-stu-id="068cf-313">Connect App</span></span>
    - <span data-ttu-id="068cf-314">Icono de candado</span><span class="sxs-lookup"><span data-stu-id="068cf-314">Lock Icon</span></span>
    - <span data-ttu-id="068cf-315">Recorte & esbozo</span><span class="sxs-lookup"><span data-stu-id="068cf-315">Snip & Sketch</span></span>
    - <span data-ttu-id="068cf-316">Teams (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="068cf-316">Teams (if applicable)</span></span>
    - <span data-ttu-id="068cf-317">Aplicaciones de Office (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="068cf-317">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="068cf-318">Aplicación Surface</span><span class="sxs-lookup"><span data-stu-id="068cf-318">Surface App</span></span>
    - <span data-ttu-id="068cf-319">Pizarra interactiva</span><span class="sxs-lookup"><span data-stu-id="068cf-319">Whiteboard</span></span>
5. <span data-ttu-id="068cf-320">Comprobar la detección de presencia.</span><span class="sxs-lookup"><span data-stu-id="068cf-320">Verify presence detection.</span></span>
    - <span data-ttu-id="068cf-321">La detección de presencia será un icono verde en la bandeja del sistema</span><span class="sxs-lookup"><span data-stu-id="068cf-321">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="068cf-322">Comprobar que los proyectos se han habilitado con la aplicación Connect (la aplicación no necesita estar ejecutándose antes de conectar).</span><span class="sxs-lookup"><span data-stu-id="068cf-322">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="068cf-323">Comprobar la configuración de energía y suspensión.</span><span class="sxs-lookup"><span data-stu-id="068cf-323">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="068cf-324">Protector de pantalla: 15 minutos, establecido en (ninguno), de formas o en blanco; casilla para requerir contraseña</span><span class="sxs-lookup"><span data-stu-id="068cf-324">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="068cf-325">Pantalla: 2 horas</span><span class="sxs-lookup"><span data-stu-id="068cf-325">Screen: 2 hours</span></span>
    - <span data-ttu-id="068cf-326">PC: 4 horas</span><span class="sxs-lookup"><span data-stu-id="068cf-326">PC: 4 hours</span></span>
8. <span data-ttu-id="068cf-327">Compruebe que Windows Hello está funcionando.</span><span class="sxs-lookup"><span data-stu-id="068cf-327">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="068cf-328">Compruebe la configuración de energía.</span><span class="sxs-lookup"><span data-stu-id="068cf-328">Verify power settings.</span></span>
10. <span data-ttu-id="068cf-329">Comprobar la sincronización la configuración está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="068cf-329">Verify sync your settings is disabled.</span></span>
11. <span data-ttu-id="068cf-330">Comprobar las aplicaciones de inicio.</span><span class="sxs-lookup"><span data-stu-id="068cf-330">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="068cf-331">Después de instalar y configurar Windows 10, Surface Hub 2S se puede administrar como cualquier otro dispositivo de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="068cf-331">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="068cf-332">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="068cf-332">Related topics</span></span>

[<span data-ttu-id="068cf-333">Migrar a Windows 10 Pro o Enterprise en Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="068cf-333">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)

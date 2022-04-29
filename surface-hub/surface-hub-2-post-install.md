---
title: Configurar Pro o Enterprise Windows 10/11 en Surface Hub 2
description: En este artículo se incluyen recomendaciones para garantizar la mejor experiencia al usar un lápiz táctil de pantalla grande personalizado y un ordenador con lápiz.
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
- Windows 10
- Windows 11
ms.openlocfilehash: 2b645ef580eda85a91bf282c8772c42c09cbb67d
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497773"
---
# <a name="configure-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>Configurar Pro o Enterprise Windows 10/11 en Surface Hub 2

Después de migrar a Pro o Enterprise de Windows 10/11, puede configurar aplicaciones y opciones para garantizar la mejor experiencia con este lápiz táctil de pantalla grande personalizado.

Al realizar estos pasos, es posible que le resulte útil usar un teclado y un mouse con cable o inalámbricos.

## <a name="configure-system-settings"></a>Configuración de la configuración del sistema

1. Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.  

    - El usuario que realiza la Azure AD unirse en Azure AD dispositivos unidos se agrega automáticamente al grupo de administradores local.  Azure AD administradores globales y administradores de dispositivos Azure AD también son <a href="/azure/active-directory/devices/assign-local-admin" target="_blank">administradores</a> locales. 

    - Puede escribir **administradores de grupos locales de red** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.
    
2. Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo, **username-SHub-Desktop**.

3. Seleccione Start Configuración AccountsSync your settings (**Iniciar** >  **Configuración** >  **CuentasIncronizar** >  la **configuración** y desactivar **la configuración de sincronización**. 

    - La configuración que se usa aquí está pensada para habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no quiera sincronizar otros dispositivos.
    
4. Reinicia el dispositivo.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Habilitar el teclado táctil y el panel táctil

1. Seleccione Start Configuración DevicesTyping  >  (**Iniciar** >  **Configuración** >  **DispositivosTyping** y active **Mostrar el teclado táctil cuando no esté en modo tableta y no haya ningún teclado conectado**.****

2. Mantenga presionada la tecla o haga clic con el botón derecho en la barra de tareas y seleccione el **botón Mostrar teclado táctil** y **el botón Mostrar panel táctil**. 

    - El teclado táctil es útil para la entrada directa del usuario, y el panel táctil virtual ayuda con selecciones precisas, sugerencias de pantalla que mantienen el puntero o como una alternativa para pulsar y mantener presionado para hacer clic con el botón derecho. 
    
    - Consulta el ejemplo siguiente:

      ![Configuración táctil.](images/touch.png)

3. Configure el teclado táctil en QWERTY y flotante.

    1. Seleccione el icono **Teclado** de la barra de tareas para mostrar el teclado táctil.
    
    1. En el teclado táctil, seleccione el icono de teclado en la esquina superior izquierda para abrir la configuración del teclado.
    
    1. Seleccione el siguiente al último tipo de teclado de la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar flotante, lo que resulta útil en esta pantalla grande. Vea los ejemplos siguientes:

       ![Configuración del teclado.](images/kbd.png)
 
4. Configure los valores de teclado suave.

    1. Seleccione el icono **de Configuración** en el teclado táctil o busque y abra **Configuración de escritura**.
    
       ![configuración de teclado suave.](images/sh2-softkeyboard.png)

    1. Habilite todas las opciones en Ortografía, Escritura y Teclado táctil.


En el ejemplo siguiente se muestra el panel de seguimiento, que es útil para navegar y seleccionar opciones. El teclado en pantalla se usa para buscar en el Microsoft Store:

![Usar el panel de seguimiento.](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Configurar Bluetooth teclado y mouse (opcional)

Conectar un teclado y un mouse si usa el dispositivo como dispositivo de Windows principal, o a menudo lo usa para escribir o trabajar con precisión.

Si el dispositivo Surface Hub está cerca de un PC, puedes usar <a href="https://aka.ms/mm" target="_blank"> Mouse sin bordes</a> para moverse sin problemas entre el Surface Hub y el PC. Para obtener más información, consulte <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Descarga de Microsoft desde El garaje: Mouse sin bordes. </a>

## <a name="example-of-taskbar-layout"></a>Ejemplo de diseño de la barra de tareas

Después de completar los pasos siguientes para configurar el Surface Hub 2 para Windows 10/11 Pro o Enterprise, se recomienda usar el anclaje de las aplicaciones más usadas a la barra de tareas para un inicio rápido de un solo toque de cada aplicación. A continuación se muestra un ejemplo del aspecto que podría tener la barra de tareas:

 ![Diseño de la barra de tareas.](images/taskblyt.png)
### <a name="update-installed-apps"></a>Actualización de aplicaciones instaladas

Para actualizar todas las aplicaciones de la Tienda instaladas:

1. Abra la aplicación Microsoft Store y seleccione ver **más** puntos suspensivos en la esquina superior derecha.
2. Seleccione **Descargas y actualizaciones.**
3. Seleccione **Obtener actualizaciones.**

### <a name="scan-for-and-install-all-windows-updates"></a>Buscar e instalar todas las actualizaciones de Windows

Después de la migración, es posible que haya actualizaciones de mantenimiento y características disponibles para instalar. 

- Vaya a **Configuración** >  **Actualizar & seguridad** > y seleccione **Buscar actualizaciones**.
- Si hay actualizaciones, instálelas, reinicie y repita el proceso hasta que vea la siguiente notificación:

> [!div class="mx-imgBorder"]
> ![Windows Update notificación "Estás al día".](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive para la Empresa

Use <a href="/onedrive/onedrive" target="_blank"> OneDrive para la Empresa</a> para compartir fácilmente herramientas, registros y otros archivos entre todos los dispositivos de trabajo.

- OneDrive permite compartir los archivos de trabajo entre los equipos portátiles, Surface Hub Desktop y los dispositivos móviles administrados por Intune. Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.

- Teniendo en cuenta el tamaño de la SSD de Surface Hub (128 GB), si configura OneDrive en el dispositivo de escritorio de Surface Hub, asegúrese de que la configuración predeterminada es mantener los archivos en línea y descargar archivos a medida que los use.

Para configurar OneDrive para descargar archivos solo cuando sea necesario, establezca la opción **Archivos a petición en** **Guardar espacio y descargar archivos a medida que los use**. Para obtener más información, consulte <a href="/onedrive/files-on-demand-windows" target="_blank"> Consulta y establecimiento de estados de archivos a petición en Windows</a>.

![OneDrive configuración.](images/onedrive.png)

> [!NOTE]
> También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de conservar el espacio en la unidad y descargar solo los archivos cuando los necesite.

## <a name="sharepoint-and-teams"></a>SharePoint y Teams

SharePoint y los archivos de canal de Teams también se pueden sincronizar localmente con los dispositivos de escritorio, como portátiles y Surface Hubs, mediante el motor de Sincronización de OneDrive.

Para sincronizar archivos corporativos internos con la unidad local con la aplicación de Sincronización de OneDrive:

1. Vaya a un sitio SharePoint y vaya al directorio de documentos de nivel superior para ver los archivos que le interesen ver o editar desde el dispositivo local.

2. Seleccione el botón **Sincronizar** de la parte superior de la cinta de SharePoint.

3. Seleccione **Abrir** en el menú emergente **Este sitio está intentando abrir Microsoft OneDrive**.

4. Compruebe que los archivos de SharePoint se sincronizan con la unidad local; para ello, seleccione el icono de OneDrive situado en la parte inferior derecha de la barra de tareas.

5. Compruebe que la configuración está establecida para mantener los archivos en línea y descargue los archivos solo cuando los use:

    1. Abra el Explorador de archivos.
    
    2. Vaya a y haga clic con el botón derecho en el nombre SharePoint; por ejemplo, **Contoso \ \<SharePoint Document Folder Name\>**.
    
    3. Seleccione **Liberar espacio**.
    
    4. La columna Estado mostrará el estado de los archivos y carpetas. Para obtener más información, vea <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar archivos SharePoint con el cliente</a> de Sincronización de OneDrive.
    
6. Teams los archivos de canal se almacenan en sitios de SharePoint, con la misma funcionalidad de documento SharePoint, incluido el historial de versiones y la sincronización con los dispositivos de escritorio locales. Para sincronizar Teams archivos de canal:

    1. Vaya al canal de Teams de interés y seleccione la pestaña **Archivos** en la parte superior. A continuación, seleccione **Sincronizar**. Los archivos comenzarán a sincronizarse y serán visibles en Explorador de archivos en **Escritorio \ Contoso \ \<name of the Teams Channel\>**.
    
    2. Use el mismo procedimiento que usó para sincronizar SharePoint sitios para mantener los archivos en la nube y descargarlos solo cuando los use, pulsando y manteniendo presionado o haciendo clic con el botón derecho en Explorador de archivos en el nombre del canal Teams y, a continuación, **seleccionando Liberar espacio**.

## <a name="surface-hub-pen-settings"></a>configuración del lápiz de Surface Hub

**Emparejar el lápiz de Bluetooth Surface Hub**

Empareje el lápiz para mantener actualizado el firmware del lápiz, establezca los accesos directos del lápiz y obtenga información sobre la carga de la batería en la página de configuración del dispositivo Bluetooth o en la aplicación Surface:

1. Seleccione **Inicio** >  **Configuración** >  **Dispositivos**.

2. Seleccione **Agregar Bluetooth u otro dispositivo**.

3. Elija **Bluetooth**.

4. Quite el botón de cola del lápiz y agite para desconectar la conexión de la batería.

5. Vuelva a colocar la tapa y mantenga presionada la tapa hasta que el LED de emparejamiento parpadee.

6. En la configuración de Surface Hub Bluetooth, elija **Surface Hub lápiz 2**.

7. Complete la operación de emparejamiento. 

8. Si el emparejamiento no se realiza correctamente, intente emparejar el lápiz de nuevo. Si eso no funciona, puede probar para ver si la batería está cargada comprobando que el lápiz funciona en la aplicación Whiteboard. Si no es así, reemplace la batería e intente emparejar el lápiz de nuevo.  Si es necesario, reinicie el dispositivo y vuelva a intentarlo.

**Establecimiento de métodos abreviados de lápiz** El lápiz Surface Hub tiene un botón de acceso directo que a veces se denomina "clic de cola". La configuración de accesos directos requiere emparejar primero el lápiz, como se describió anteriormente.

1. Busque Lápiz y seleccione **Lápiz & Windows Ink configuración**.

2. Cerca de la parte inferior de la página, seleccione Métodos abreviados de lápiz que abre el cuadro de diálogo, que se muestra aquí:

   ![Métodos abreviados de lápiz.](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Configuración de la cámara

Puede montar la cámara en la parte superior o en cualquier lado del dispositivo. Monte la cámara en una posición para optimizar el ángulo de la cámara si usa el centro con un soporte de escritorio en lugar de un carro o está cerca del centro. La cámara no gira automáticamente, por lo que debe tener una tecla hexadecimal de 2 mm para girar manualmente la cámara. 

Para obtener más información sobre cómo montar la cámara de forma lateral y girarla manualmente, consulte <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub orientación</a> de la lente de la cámara 2S.

## <a name="windows-hello-configuration"></a>configuración de Windows Hello

Surface Hub 2S que ejecuta Windows 10/11 Pro o Enterprise permite el conjunto completo de aplicaciones de escritorio win32, así como opciones de Windows Hello biométricas. El accesorio lector de huellas digitales Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo. 

Para ordenar un lector de huellas digitales de Surface Hub 2 o ver las especificaciones técnicas, vea (surface-hub-2-essential-add-ons.md" target="_blank">Complementos esenciales para Windows 10 Pro y Enterprise en Surface Hub 2 </a>. 

Después de insertar el lector de huellas digitales, seleccione **Start** >  **Configuración** >  **AccountsSign-in****** >  options  > **Windows Hello Fingerprint (Huella digital**) para inscribir la huella digital.

Use un dispositivo certificado Windows Hello para el reconocimiento facial. La cámara Surface Hub 2S no admite el reconocimiento facial Windows Hello.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Habilitar un icono de acceso directo de pantalla de bloqueo en la barra de tareas

Para agregar un icono a la barra de tareas que habilita un bloqueo de pantalla táctil similar al método abreviado de teclado Windows-L: 

1.  Pulse y mantenga presionado o haga clic con el botón derecho en **** el escritorio, seleccione **NewShortcutBrowseDesktopOKNext** > .**************** >  >  >  > 

1.  Proporcione un nombre para el acceso directo, como **Bloquear mi PC** y, a continuación, seleccione **Finalizar**.

1.  Haga clic con el botón derecho o mantenga presionado el acceso directo recién creado en el escritorio y seleccione **Propiedades**. En la pestaña **Acceso directo**, escriba lo siguiente en el campo **Destino**: **Rundll32.exe User32.dll,LockWorkStation**.

1.  Seleccione el botón **Cambiar icono** , busque **C:\Windows\System32\imageres.dll** y seleccione un icono para usarlo. 

    Consulta el ejemplo siguiente:

    ![Elija un icono.](images/lock.png)
    
1.  Seleccione **Aceptar** para guardar el acceso directo.

1.  Haga clic con el botón derecho o mantenga presionado el acceso directo y seleccione **Anclar a la barra de tareas**.

1. Una vez anclado el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.

## <a name="applications"></a>Aplicaciones


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Para instalar el Microsoft Whiteboard:

 - Seleccione el icono **de Área de trabajo de Windows Ink** en la esquina inferior derecha de la barra de tareas y descargue **Pizarra**.
 
   ![Área de trabajo de Ink.](images/ink.png) 

Como alternativa, puede instalar Whiteboard desde el Microsoft Store:

1. Abra Microsoft Store aplicación y busque **Pizarra**.

2. Elija **No gracias** a iniciar sesión y usarlo en todos los dispositivos.

3. Ancle Pizarra a la barra de tareas.

### <a name="surface-app"></a>Aplicación Surface

1. En el Microsoft Store, busque **Surface**.

2. Establezca el filtro **Disponible en** **en Todos los dispositivos**.

3. Instala la aplicación **Surface** . Esta debe ser la primera aplicación en la lista. Es posible que deba asociar la MSA a la Tienda para instalar la aplicación.

4. Ancle la aplicación **Surface** a la barra de tareas.

### <a name="snip--sketch"></a>Recorte y anotación

1. Abra la aplicación **Snip & Sketch** y anclarla a la barra de tareas.

2. Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, seleccione **Configuración**.

3. En **Configuración**, active **Copia automática en el Portapapeles**, **Guardar snips** y **Varias ventanas** (opcional).

### <a name="microsoft-office"></a>Microsoft Office

1. Abra el portal</a> de <a href="https://portal.office.com/account#installs" target="_blank"> Office e instale las aplicaciones deseadas.

2. Ancle las aplicaciones Office deseadas a la barra de tareas.

3. Si Outlook está instalado, asegúrese de establecer la Outlook OST para guardar solo la caché de las últimas dos semanas. Esto reducirá considerablemente el tiempo de instalación y el uso del disco.

    - Seleccione **FileAccount** >  **Configuración** y seleccione su cuenta.
    
    - Seleccione **Cambiar** y establezca el control deslizante **Usar modo de Exchange almacenado en caché** en 14 días.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Descargue e instale <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.

2. Configure los valores en Inicio automático de la aplicación (opcional).

3. Ancle Teams a la barra de tareas.

4. Considere la posibilidad de reducir Teams notificaciones en el dispositivo para evitar distracciones (opcional).

   ![Teams notificaciones.](images/teams.png)

### <a name="connect-app"></a>Conectar aplicación

> [!IMPORTANT]
> En Windows 10, versión 2004 y posteriores, la aplicación Conectar para la proyección inalámbrica mediante Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional. Si ha instalado (o actualizado a) Windows versión 2004 o posterior, es posible que vea lo siguiente en la pantalla Proyección a este equipo en la configuración:

![Project a este equipo.](images/sh2-project.png) 


1. Para instalar la aplicación desde la página de configuración "Proyectar a este EQUIPO", seleccione **Características opcionalesAgregar** >  **una característica** e instalar la aplicación **De pantalla inalámbrica**.

2. En **Algunos dispositivos Windows y Android pueden proyectarse en este equipo cuando digas que está bien**, elige:

    - **Disponible en todas partes** si el dispositivo no está en una red corporativa.
    - De lo contrario, elija **Disponible en todas partes en redes seguras**.
    
3. En **Preguntar para proyectar en este equipo**, elija **Solo primera vez**.

4. En **Requerir PIN para emparejamiento**, elija **Nunca**.

5. Para iniciar la aplicación y anclarla a la barra de tareas, busque **Conectar**.

6. Abra la aplicación. Mientras la aplicación está abierta, haga clic con el botón derecho en el icono de Conectar aplicación de la barra de tareas y seleccione **Anclar a la barra de tareas**.

7. A continuación, cierre la aplicación de Conectar. **Project a este equipo** podría no funcionar a menos que la aplicación se haya ejecutado al menos una vez.

Configuración recomendada cuando no está en la red corporativa:

![Configuración en casa.](images/project1.png)

Configuración recomendada en la red corporativa:

![Configuración en el trabajo.](images/project2.png)

### <a name="your-phone"></a>Tu Teléfono

La aplicación **Your Teléfono** está instalada de forma predeterminada en Windows 10. Si no está presente, también puedes instalarlo desde Windows Store.

Para obtener información sobre cómo configurar la aplicación, consulta <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> Cómo configurar tu Teléfono en Windows 10 y sincronizar datos entre tu PC y tu teléfono</a>. <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Consulta también Cómo solucionar problemas comunes con tu aplicación de Teléfono en Windows 10</a>.

###  <a name="fancy-zones"></a>Zonas sofisticadas


**Fancy Zones** forma parte de una colección de herramientas llamadas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> en GitHub. Es una excelente manera de usar el espacio real de pantalla en un Surface Hub 2, ya que le ofrece la capacidad de definir diseños fijos en la pantalla ("zonas") y, a continuación, seleccionar qué aplicación se ejecutará en cada zona. 


La [wiki de PowerToys](https://github.com/microsoft/PowerToys/wiki) tiene instrucciones para usar y personalizar cada herramienta, incluido [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). En un nivel alto: después de instalar PowerToys, puede seleccionar o crear un diseño personalizado y, a continuación, mantener presionada la tecla mayús y arrastrar o usar teclas de teclado para mover una aplicación en ejecución a zonas específicas. El uso de un teclado y un mouse Bluetooth o USB le ayudará con esto, o puede usar el teclado táctil y el panel táctil en pantalla.

**Sugerencias de power toys**
- Para recibir notificaciones por correo electrónico de PowerToys actualizaciones de versión en GitHub, haga clic en el botón "Registrarse" en la parte superior de la [página](https://github.com/microsoft/PowerToys/releases).
- Una vez instalado PowerToys, puede recibir notificaciones Windows o descargar e instalar las actualizaciones más recientes configurando la configuración de PowerToys **Descargar actualizaciones automáticamente**.
- Para acceder a la configuración de PowerToys, seleccione las **aplicaciones en ejecución** de cara superior en la barra de tareas y, a continuación, haga clic con el botón derecho o mantenga presionado el icono de PowerToys hasta que aparezca el menú. Seleccione "Configuración".
- En la parte inferior de la página de configuración de PowerToys, active **Descargar actualizaciones automáticamente**.
- Cuando se haya publicado una actualización, aparecerá una notificación de Windows que le dará la opción de cuándo instalar la actualización.


### <a name="edge-chromium-browser"></a>Explorador edge Chromium

Descargue e instale el nuevo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">explorador</a> edge Chromium.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub herramienta de diagnóstico de hardware

La <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> herramienta</a> de diagnóstico de hardware Surface Hub disponible de forma gratuita en el Microsoft Store. La herramienta está diseñada para ayudarle a asegurarse de que su Surface Hub está funcionando en su mejor momento. Contiene pruebas para determinar si el firmware está actualizado y configurado correctamente. Las pruebas interactivas permiten confirmar que la funcionalidad esencial funciona según lo esperado. Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub. Haga clic en el vínculo para instalarlo desde el Microsoft Store y, a continuación, ancle la aplicación a la barra de tareas.

## <a name="additional-settings"></a>Configuración adicional

### <a name="pen-tail-select-to-launch-whiteboard"></a>Selección de la cola del lápiz para iniciar Pizarra

1. Busque **Lápiz** y seleccione **Lápiz & Windows Ink configuración**.

2. Cerca de la parte inferior de la página, en **Métodos abreviados de lápiz**, establezca **Seleccionar una vez** en **Microsoft Whiteboard**. 

### <a name="power-management"></a>Administración de energía

Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10/11 Pro o Enterprise en Surface Hub 2. Esto incluye tiempos de espera de pantalla y pc y cómo interactúan con la detección de presencia humana (Doppler) integrada, el protector de pantalla y la protección con contraseña y, a continuación, si procede, cómo pasar la configuración de energía de directiva de grupo destinada a los usuarios de equipos portátiles o de escritorio.

Windows 10/11 Pro o Enterprise en Surface Hub 2 evita que la pantalla se vaya a dormir con acciones táctiles, de mouse y de teclado, así como la detección de ocupación humana (Doppler) integrada. La detección de ocupación humana está habilitada de forma predeterminada, pero, si lo desea, se puede deshabilitar en UEFI cambiando la opción del dispositivo en la herramienta Configurador ueFI de Surface como parte de la migración inicial o creando y aplicando un paquete de configuración UEFI posterior. 

**Administración de energía: Configuración de pantalla y suspensión de PC**

1. Seleccione **Inicio** >  **Configuración** >  **SystemPower** >  **& suspensión**.

2. Establezca el control deslizante del modo de energía en **Mejor rendimiento**.

3. Configure los valores de pantalla y suspensión según sus preferencias y, al mismo tiempo, tenga en cuenta la detección de presencia de Doppler que reactiva el dispositivo cuando se detecta el movimiento. Por lo tanto, como procedimiento recomendado, se recomienda establecer Pantalla en **Apagar después de 2 horas** y el EQUIPO para **apagar después de 4 horas.**

**Administración de energía: protector de pantalla**

1. Busque **Pantalla de bloqueo** y abra **La configuración de la pantalla de bloqueo**.

2. Configure **los valores de tiempo de espera de la pantalla** y la **configuración del protector de pantalla** según sus preferencias. Los valores predeterminados recomendados son:

   - Protector de pantalla a (Ninguno) o un protector de pantalla de su elección.
   - Tiempo de espera de 15 minutos.
   - En la reanudación, muestre la pantalla de inicio de sesión.


**Administración de energía: directiva de grupo**

Antes de realizar el procedimiento siguiente, consulte con el departamento de TI para obtener aprobación para excluir un dispositivo Surface Hub 2S de la directiva de administración de energía global. Algunas opciones de administración de energía pueden deshabilitar la función de detección de presencia.

1. Busque **El Centro de software** y ábralo.

2. Seleccione **Opciones**.

3. Expanda **Administración de energía**  y seleccione **No aplicar la configuración de energía de mi departamento de TI a este equipo**.

   ![Configuración de software.](images/soft-cntr.png)

### <a name="storage-sense"></a>Sensor de almacenamiento

El Surface Hub 2 tiene un SSD de 128 GB para el almacenamiento local, por lo que es necesario tener en cuenta el uso de medidas de ahorro de almacenamiento durante el uso normal.  Para configurar Storage Sense:

1.  Busque **la configuración de almacenamiento**, que se encuentra en **Configuración del sistema**.

2.  En **Configuración**, seleccione **Activar el sentido de almacenamiento** para abrir la página de configuración **de Storage**.

3.  Active Storage **Sense.**

4.  Seleccione **Configurar Storage Sense o ejecútelo ahora** y configure los valores para mantener los archivos en línea tanto como sea posible (debido a un espacio limitado en la unidad).

Configuración recomendada:

- Ejecute Storage Sense = Cada día.
- Eliminar archivos temporales que mis aplicaciones no usan = Cada 14 días (al menos).
- Elimine los archivos de la carpeta Descargas si han estado allí durante más de = 30 días.
- OneDrive: el contenido se convertirá en solo en línea si no se abre durante más de = 30 días.

### <a name="tablet-mode"></a>Modo tableta

Active el modo Tableta si lo desea para satisfacer las necesidades de accesibilidad.


### <a name="sound-settings"></a>Configuración de sonido

1. Busque **Configuración de sonidos** y abra esta página.

2. Seleccione **Sonido Panel de control** a la derecha y seleccione la pestaña **Sonidos**.

3. En **Eventos de programa**, establezca **Device Conectar (Dispositivo Conectar**) y **Device Disconnect (Desconexión del dispositivo**) en **None (Ninguno**).

### <a name="silence-notifications"></a>Notificaciones de silencio

1. Busque **Ayuda de foco** y abra esta página.

2. Seleccione **Solo alarmas**. Esto evitará los controles flotantes de notificaciones constantes.

### <a name="disk-cleanup"></a>Liberador de espacio en disco

1. Busque **Limpieza de disco** y abra esta aplicación.

2. En **Archivos que se van a eliminar**, seleccione los archivos que desea eliminar. 

3. Seleccione también **Limpiar archivos del sistema**.

## <a name="complete-and-verify"></a>Completar y comprobar

1. Busque e instale todas las actualizaciones de Windows.

2. Actualice directiva de grupo.

   1. En un símbolo del sistema con privilegios elevados, escriba **gpupdate /force /boot /wait:0**.
   
3. Reinicia el dispositivo.

4. Compruebe las aplicaciones de la barra de tareas.

   - aplicación de Conectar
   - Icono de bloqueo
   - Recorte y anotación
   - Teams (si procede)
   - aplicaciones de Office (si procede)
   - Aplicación Surface
   - Pizarra
    
5. Compruebe la detección de presencia.

   - La detección de presencia será un icono verde en la bandeja del sistema.
    
6. Compruebe que la proyección en este equipo está habilitada con la aplicación Conectar. Después de configurar **Project a esta** configuración de pc, ejecute la aplicación de Conectar al menos una vez. (Posteriormente, no es necesario que la aplicación Conectar se ejecute para proyectar para Surface Hub).

7. Compruebe la configuración de energía y suspensión.

    - Protector de pantalla: 15 minutos, establecido en (ninguno), Mystify o Blank; asegúrese de que está activada la casilla para requerir contraseña.
    - Pantalla: **desactivar después de 2 horas**.
    - PC:  **Apagar después de 4 horas**.
    
8. Compruebe que Windows Hello funciona.

9. Compruebe que la configuración de sincronización está deshabilitada.

10. Compruebe las aplicaciones de inicio.

> [!TIP]
> Después de instalar y configurar Windows 10, el Surface Hub 2S se puede administrar igual que cualquier otro dispositivo Windows 10 o Windows 11.

## <a name="related-topics"></a>Temas relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migración a Pro o Enterprise Windows 10/11 en Surface Hub 2</a>

---
title: Configurar Windows 10 o Windows 11 Pro/Enterprise en Surface Hub 2
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
- Windows 10
- Windows 11
ms.openlocfilehash: 0c43e2c5977321cc2153f468bea7b5f65aa00a51
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448513"
---
# <a name="configure-windows-10-or-windows-11-proenterprise-on-surface-hub-2"></a>Configurar Windows 10 o Windows 11 Pro/Enterprise en Surface Hub 2

Después de migrar a Windows 10 o Windows 11 Pro/Enterprise, puede configurar aplicaciones y configuraciones para garantizar la mejor experiencia con este equipo táctil y de lápiz de pantalla grande personalizado.

Al realizar estos pasos, puede resultar útil usar un teclado y un mouse con cable o inalámbrico.

## <a name="configure-system-settings"></a>Configurar la configuración del sistema

1. Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.  

    - El usuario que realiza la combinación Azure AD en Azure AD unidos se agrega automáticamente al grupo de administradores local.  Azure AD administradores globales y Azure AD de dispositivos <a href="/azure/active-directory/devices/assign-local-admin" target="_blank">también son administradores locales</a>. 

    - Puede escribir **administradores de grupos locales netos** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.
    
2. Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo, **username-SHub-Desktop**.

3. Selecciona **Inicio** >  **Configuración** >  **AccountsSync** >  **la configuración y** desactiva **la configuración de sincronización**. 

    - La configuración que se usa aquí está diseñada para habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no quiera sincronizar otros dispositivos.
    
4. Reinicia el dispositivo.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Habilitar el teclado táctil y el panel táctil

1. Selecciona **Inicio** >  **Configuración** >  **DevicesTyping** >  y activa Mostrar el teclado táctil cuando no esté en modo **tableta y no haya ningún teclado conectado**.****

2. Pulsa y mantén presionado o haz clic con el botón derecho en la barra de tareas y selecciona el botón Mostrar **teclado táctil** y **el botón Mostrar panel táctil**. 

    - El teclado táctil es útil para la entrada directa del usuario y el panel táctil virtual ayuda con selecciones precisas, sugerencias de pantalla activa o como alternativa para pulsar y mantener pulsado el botón secundario. 
    
    - Consulta el ejemplo siguiente:

      ![Configuración táctil.](images/touch.png)

3. Configure el teclado táctil en QWERTY y flotante.

    1. Seleccione el **icono Teclado** de la barra de tareas para mostrar el teclado táctil.
    
    1. En el teclado táctil, selecciona el icono del teclado en la esquina superior izquierda para abrir la configuración del teclado.
    
    1. Seleccione el siguiente al último tipo de teclado de la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar flotante, lo que resulta útil en esta pantalla grande. Vea los ejemplos siguientes:

       ![Configuración del teclado.](images/kbd.png)
 
4. Configure las opciones de teclado suave.

    1. Seleccione el **Configuración** en el teclado táctil o busque y abra **La configuración de escritura**.
    
       ![Configuración de teclado suave.](images/sh2-softkeyboard.png)

    1. Habilita todas las opciones en Ortografía, Escritura y teclado táctil.


En el ejemplo siguiente se muestra el trackpad, que resulta útil para navegar y seleccionar opciones. El teclado en pantalla se usa para buscar en el Microsoft Store:

![Uso del trackpad.](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Configurar Bluetooth teclado y mouse (opcional)

Conectar un teclado y un mouse si usas el dispositivo como dispositivo Windows principal o lo usas a menudo para escribir o trabajar con precisión.

Si el Surface Hub está cerca de un equipo, <a href="https://aka.ms/mm" target="_blank"> puedes usar Mouse sin</a> bordes para moverse sin problemas entre el Surface Hub y el equipo. Para obtener más información, consulta <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Descarga de Microsoft desde El garage: Mouse sin bordes. </a>

## <a name="example-of-taskbar-layout"></a>Ejemplo de diseño de la barra de tareas

Después de completar los pasos siguientes para configurar o configurar su Surface Hub 2 para Windows 10 o Windows 11 Pro/Enterprise, le recomendamos que use anclar las aplicaciones más usadas a la barra de tareas para un inicio rápido con un solo toque de cada aplicación. A continuación se muestra un ejemplo de cómo podría ser la barra de tareas:

 ![Diseño de la barra de tareas.](images/taskblyt.png)
### <a name="update-installed-apps"></a>Actualizar aplicaciones instaladas

Para actualizar todas las aplicaciones de la Tienda instaladas:

1. Abre la Microsoft Store y selecciona **los** puntos suspensivos Ver más en la esquina superior derecha.
2. Selecciona **Descargas y actualizaciones.**
3. Seleccionar **Obtener actualizaciones**

### <a name="scan-for-and-install-all-windows-updates"></a>Buscar e instalar todas las Windows actualizaciones

Después de la migración, es posible que haya actualizaciones de mantenimiento y características disponibles para su instalación. 

- Vaya a **Configuración** >  **Update & Security > y** seleccione **Buscar actualizaciones**.
- Si hay actualizaciones, instáleslas, reinicie y repita el proceso hasta que vea la siguiente notificación:

> [!div class="mx-imgBorder"]
> ![Windows actualizar la notificación "Estás actualizado".](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive para la Empresa

Usa <a href="/onedrive/onedrive" target="_blank"> OneDrive para la Empresa</a> para compartir fácilmente herramientas, registros y otros archivos entre todos los dispositivos de trabajo.

- OneDrive permite compartir los archivos de trabajo entre los portátiles, Surface Hub escritorio y los dispositivos móviles administrados por Intune. Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.

- Teniendo en cuenta el tamaño de la SSD de Surface Hub (128 GB), si configuras OneDrive en el dispositivo de escritorio de Surface Hub, asegúrate de que la configuración predeterminada es mantener los archivos en línea y descargar los archivos mientras los usas.

Para configurar OneDrive para descargar archivos solo cuando sea necesario, establece la opción **** Archivos a petición en Guardar espacio y descargar archivos mientras **los usas**. Para obtener más información, vea <a href="/onedrive/files-on-demand-windows" target="_blank"> Consultar y establecer estados de archivos a petición en Windows</a>.

![OneDrive configuración.](images/onedrive.png)

> [!NOTE]
> También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de conservar el espacio de unidad y solo descargar archivos cuando los necesite.

## <a name="sharepoint-and-teams"></a>SharePoint y Teams

SharePoint y Teams channel también se pueden sincronizar localmente con los dispositivos de escritorio, como portátiles y Surface Hubs, con el motor Sincronización de OneDrive usuario.

Para sincronizar los archivos corporativos internos con la unidad local con la Sincronización de OneDrive:

1. Ve a un SharePoint y ve al directorio de documentos de nivel superior para ver o editar archivos que te interesan ver o editar desde el dispositivo local.

2. Seleccione el botón **Sincronizar** en la parte superior de la cinta SharePoint opciones.

3. Seleccione abrir **en** el elemento emergente **Este sitio está intentando abrir Microsoft OneDrive**.

4. Compruebe que los SharePoint se sincronizan con la unidad local seleccionando el icono OneDrive en la parte inferior derecha de la barra de tareas.

5. Compruebe que la configuración está configurada para mantener los archivos en línea y descargar los archivos solo cuando los use:

    1. Abra el explorador de archivos.
    
    2. Vaya a y haga clic con el botón secundario en SharePoint nombre; por ejemplo, **Contoso \ \<SharePoint Document Folder Name\>**.
    
    3. Seleccione **Liberar espacio**.
    
    4. La columna Estado mostrará el estado de los archivos y carpetas. Para obtener más información, <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> vea Sync SharePoint files with the Sincronización de OneDrive client</a>.
    
6. Teams los archivos de canal se almacenan en sitios SharePoint, con la misma funcionalidad de documento SharePoint, incluido el historial de versiones y la sincronización con los dispositivos de escritorio locales. Para sincronizar Teams de canal:

    1. Vaya al canal Teams de interés y seleccione la **pestaña** Archivos en la parte superior. A continuación, **seleccione Sincronizar**. Los archivos empezarán a sincronizarse y estarán visibles en el Explorador de archivos en **Escritorio \ Contoso \ \<name of the Teams Channel\>**.
    
    2. Use el mismo procedimiento que usó para sincronizar sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, mantenga pulsado o haga clic con el botón secundario en el Explorador de archivos en el nombre del canal de Teams y, a continuación, seleccione Liberar **espacio.**

## <a name="surface-hub-pen-settings"></a>Surface Hub de lápiz

**Emparejar el Bluetooth Surface Hub lápiz**

Empareja el lápiz para mantener actualizado el firmware del lápiz, establecer los accesos directos del lápiz y obtener información de carga de batería en la página de configuración del dispositivo Bluetooth o en la aplicación Surface:

1. Seleccione **Inicio** >  **Configuración** >  **Devices**.

2. Selecciona **Agregar Bluetooth u otro dispositivo**.

3. Elija **Bluetooth**.

4. Quite el botón de cola del lápiz y agite para desconectar la conexión de la batería.

5. Vuelva a colocar la tapa y mantenga presionada la tapa hasta que parpadee el LED de emparejamiento.

6. En la Surface Hub Bluetooth, elija **Surface Hub 2 plumas**.

7. Complete la operación de emparejamiento. 

8. Si el emparejamiento no se realiza correctamente, intente emparejar el lápiz de nuevo. Si eso no funciona, puedes probar para ver si la batería se carga comprobando que el lápiz funciona en la aplicación Pizarra. Si no es así, reemplace la batería y vuelva a emparejar el lápiz.  Si es necesario, reinicia el dispositivo y vuelve a intentarlo.

**Establecer métodos abreviados de lápiz** El Surface Hub tiene un botón de método abreviado a veces denominado "clic de cola". La configuración de métodos abreviados requiere emparejar primero el lápiz, como se describió anteriormente.

1. Busque Pluma y seleccione **Pen & Windows Ink configuración**.

2. Cerca de la parte inferior de la página, seleccione Métodos abreviados de lápiz que abre el cuadro de diálogo, que se muestra aquí:

   ![Métodos abreviados de lápiz.](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Configuración de cámara

Puedes montar la cámara en la parte superior o en cualquier lado del dispositivo. Monta la cámara en una posición para optimizar el ángulo de la cámara si estás usando el concentrador con un soporte de escritorio en lugar de un carro, o si estás cerca del concentrador. La cámara no gira automáticamente, por lo que debes tener una tecla hexadecimal de 2 mm para girar manualmente la cámara. 

Para obtener más información sobre cómo montar la cámara de forma lateral y girar la cámara manualmente, <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> consulta Surface Hub orientación del objetivo de la cámara 2S</a>.

## <a name="windows-hello-configuration"></a>Windows Hello configuración

Surface Hub 2S que ejecuta Windows 10 o Windows 11 Pro/Enterprise permite el conjunto completo de aplicaciones de escritorio de Win32, así como opciones de Windows Hello biométricas. El Surface Hub lector de huellas digitales 2 puede conectarse a cualquier puerto USB-C del dispositivo. 

Para solicitar un lector de huellas digitales Surface Hub 2 o ver especificaciones técnicas, vea (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>. 

Después de insertar el lector de huellas digitales, **seleccione** >  **Start** >  Configuración **AccountsSign-in****** >  options  > **Windows Hello Fingerprint** para inscribir la huella digital.

Usa un dispositivo Windows Hello certificado para el reconocimiento facial. La Surface Hub 2S no admite el reconocimiento Windows Hello rostro.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Habilitar un icono de acceso directo de pantalla de bloqueo en la barra de tareas

Para agregar un icono a la barra de tareas que habilita un bloqueo de pantalla táctil similar al método abreviado de teclado Windows-L: 

1.  Pulsa y mantén presionado o haz clic con el botón secundario en el escritorio, **selecciona** **NewShortcutBrowseDesktopOKNext** > .**************** >  >  >  > 

1.  Proporcione un nombre para el acceso directo, como **Bloquear mi PC** y, a continuación, seleccione **Finalizar**.

1.  Haz clic con el botón derecho o pulsa y mantén presionado el acceso directo recién creado en el escritorio y selecciona **Propiedades**. En la **pestaña Acceso** directo, escriba lo siguiente en el **campo** Destino: **Rundll32.exe User32.dll,LockWorkStation**

1.  Seleccione el **botón Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione un icono para usar. 

    Consulta el ejemplo siguiente:

    ![Elija un icono.](images/lock.png)
    
1.  Seleccione **Aceptar** para guardar el acceso directo.

1.  Haz clic con el botón derecho o pulsa y mantén presionado el acceso directo y selecciona **Anclar a la barra de tareas**.

1. Después de anclar el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.

## <a name="applications"></a>Aplicaciones


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Para instalar el Microsoft Whiteboard:

 - Seleccione el **Área de trabajo de Windows Ink** en la parte inferior derecha de la barra de tareas y descargue **Whiteboard**.
 
   ![Área de trabajo de lápiz.](images/ink.png) 

Como alternativa, puede instalar whiteboard desde el Microsoft Store:

1. Abre Microsoft Store aplicación y busca **Pizarra**.

2. Elige **No gracias para** iniciar sesión y usar en todos los dispositivos.

3. Anclar pizarra a la barra de tareas.

### <a name="surface-app"></a>Aplicación Surface

1. En el Microsoft Store, busca **Surface**.

2. Establece el **filtro Disponible en** todos **los dispositivos**.

3. Instala la **aplicación Surface** . Esta debería ser la primera aplicación enumerada. Es posible que deba asociar la MSA a la Tienda para instalar la aplicación.

4. Anclar la **aplicación Surface** a la barra de tareas.

### <a name="snip--sketch"></a>Recorte y anotación

1. Abre la **aplicación Snip & Sketch** y anclarla a la barra de tareas.

2. Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación **, seleccione Configuración**.

3. En **Configuración**, activa Copia **automática en el** Portapapeles, **Guardar snips** y **Varias ventanas** (opcional).

### <a name="microsoft-office"></a>Microsoft Office

1. Abra el <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal e</a> instale las aplicaciones deseadas.

2. Anclar las Office deseadas a la barra de tareas.

3. Si Outlook está instalado, asegúrese de establecer la Outlook OST para guardar solo la memoria caché de las últimas dos semanas. Esto reducirá en gran medida el uso del disco y el tiempo de instalación.

    - Seleccione **ArchivoAccount** >  **Configuración** y seleccione su cuenta.
    
    - Seleccione **Cambiar** y establezca el control deslizante de **Usar modo Exchange caché** en 14 días.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Descargue e instale Microsoft Teams <a href="https://teams.microsoft.com/downloads" target="_blank"> </a>.

2. Configure las opciones para iniciar automáticamente la aplicación (opcional).

3. Anclar Teams a la barra de tareas.

4. Considera la posibilidad de reducir Teams notificaciones en el dispositivo para evitar distracciones (opcional).

   ![Teams notificaciones.](images/teams.png)

### <a name="connect-app"></a>Conectar app

> [!IMPORTANT]
> En Windows 10, versión 2004 y versiones posteriores, la aplicación Conectar para la proyección inalámbrica mediante Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional. Si ha instalado (o actualizado a) Windows versión 2004 o posterior, puede ver lo siguiente en la pantalla Proyectar a este equipo en configuración:

![Project a este equipo.](images/sh2-project.png) 


1. Para instalar la aplicación desde la página de configuración "Proyectar a este EQUIPO", **** >  selecciona Características opcionalesAgregue una característica y, **a** continuación, instale la **aplicación Pantalla** inalámbrica.

2. En **Algunos Windows dispositivos Android** pueden proyectarse a este equipo cuando diga que está bien, elija:

    - **Disponible en todas** partes si el dispositivo no está en una red corporativa.
    - De lo contrario, elija **Disponible en todas partes en redes seguras**.
    
3. En **Solicitar proyecto a este equipo**, elija **Solo primera vez**.

4. En **Requerir PIN para el emparejamiento**, elija **Nunca**.

5. Para iniciar la aplicación y anclarla a la barra de tareas, busque **Conectar**.

6. Abre la aplicación. Mientras la aplicación está abierta, haz clic con el botón secundario en el icono Conectar de la aplicación en la barra de tareas y selecciona **Anclar a la barra de tareas**.

7. A continuación, cierra Conectar aplicación. **Project a este equipo** puede que no funcione a menos que la aplicación se haya ejecutado al menos una vez.

Configuración recomendada cuando no está en la red corporativa:

![Configuración en casa.](images/project1.png)

Configuración recomendada en la red corporativa:

![Configuración en el trabajo.](images/project2.png)

### <a name="your-phone"></a>Tu Teléfono

La **Tu Teléfono** está instalada de forma predeterminada en Windows 10. Si no está presente, también puedes instalarlo desde Windows Store.

Para obtener información sobre cómo configurar la aplicación, <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> consulta Cómo configurar Tu Teléfono en Windows 10 y sincronizar datos entre el equipo y el teléfono</a>. También consulta <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Cómo solucionar problemas comunes con Tu Teléfono aplicación en Windows 10</a>.

###  <a name="fancy-zones"></a>Zonas de lujo


**Fancy Zones** forma parte de una colección de herramientas denominada <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> en GitHub.. Es una excelente forma de usar la pantalla en un Surface Hub 2, ya que permite definir diseños fijos en la pantalla ("zonas") y, a continuación, seleccionar qué aplicación se ejecutará en cada zona. 


El [PowerToys wiki tiene](https://github.com/microsoft/PowerToys/wiki) instrucciones sobre cómo usar y personalizar cada herramienta, incluidas [las FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). En un nivel alto: después de instalar PowerToys, puedes seleccionar o crear un diseño personalizado y, a continuación, mantener presionada la tecla mayús y arrastrar o usar teclas de teclado para mover una aplicación en ejecución a zonas específicas. Usar un Bluetooth o un teclado y mouse USB te ayudará con esto, o puedes usar el teclado táctil y el panel táctil en pantalla.

**Sugerencias de power toys**
- Para recibir notificaciones por correo electrónico PowerToys actualizaciones de lanzamiento en GitHub, haga clic en el botón "Registrarse" en la parte superior de la [página](https://github.com/microsoft/PowerToys/releases).
- Una vez PowerToys, puede recibir notificaciones de Windows o descargar e instalar las actualizaciones más recientes configurando la configuración de PowerToys Descargar actualizaciones automáticamente en on.****
- Para llegar a la configuración de PowerToys, seleccione el quilate para arriba **** Ejecutando aplicaciones en la barra de tareas y, a continuación, haga clic con el botón secundario o presione y mantenga presionado el icono PowerToys hasta que aparezca el menú. Seleccione "Configuración".
- En la parte inferior de la página PowerToys configuración, activa **Descargar actualizaciones automáticamente**.
- Cuando se haya publicado una actualización, aparecerá Windows notificación que le dará la opción de cuándo instalar la actualización.


### <a name="edge-chromium-browser"></a>Explorador Chromium edge

Descargue e instale el nuevo explorador <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">de Chromium edge</a>.


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub de diagnóstico de hardware

La <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub de diagnóstico de</a> hardware disponible de forma gratuita desde el Microsoft Store. La herramienta está diseñada para ayudarle a asegurarse de que su Surface Hub está funcionando en su mejor momento. Contiene pruebas para determinar si el firmware está actualizado y configurado correctamente. Las pruebas interactivas permiten confirmar que la funcionalidad esencial funciona según lo esperado. Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub. Haga clic en el vínculo para instalarlo desde el Microsoft Store y, a continuación, anclar la aplicación a la barra de tareas.

## <a name="additional-settings"></a>Configuración adicional

### <a name="pen-tail-select-to-launch-whiteboard"></a>Selección de cola de lápiz para iniciar pizarra

1. Busque Pluma **y** seleccione **Pen & Windows Ink configuración**.

2. Cerca de la parte inferior de la página, en **Métodos abreviados de lápiz**, establece **Seleccionar una vez** en **Microsoft Whiteboard**. 

### <a name="power-management"></a>Administración de energía

Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10 o Windows 11 Pro/Enterprise en Surface Hub 2. Esto incluye tiempos de espera de pantalla y equipo, y cómo interactúan con la detección de presencia humana integrada (Doppler), el protector de pantalla y la protección de contraseña y, si procede, cómo pasar la configuración de energía de directiva de grupo destinada a usuarios de equipos portátiles o de escritorio.

Windows 10 o Windows 11 Pro/Enterprise en Surface Hub 2 impide que la pantalla duerma mediante acciones táctiles, de mouse y de teclado, así como la detección de ocupación humana integrada (Doppler). La detección de ocupación humana está habilitada de forma predeterminada, pero si se desea se puede deshabilitar en UEFI al alternar la opción de dispositivo en la herramienta Configurador UEFI de Surface como parte de la migración inicial, o mediante la creación y aplicación de un paquete de configuración de UEFI posterior. 

**Administración de energía: configuración de suspensión de pantalla y equipo**

1. Seleccione **Inicio** >  **Configuración** >  **SystemPower** >  **& suspensión**.

2. Establece el control deslizante del modo de energía en **Mejor rendimiento**.

3. Configure los valores de pantalla y suspensión según su preferencia, al tiempo que también tiene en cuenta la detección de presencia de Doppler que activa el dispositivo cuando se detecta el movimiento. Por lo tanto, como procedimiento recomendado, se recomienda establecer Pantalla en Desactivar después de **2** horas y el equipo desactivar después de **4 horas.**

**Administración de energía: protector de pantalla**

1. Busque Pantalla **de bloqueo y** abra **La configuración de pantalla de bloqueo**.

2. Configure **la configuración de tiempo de espera de** pantalla y **la configuración del protector** de pantalla según sus preferencias. Los valores predeterminados recomendados son:

   - Protector de pantalla a (Ninguno) o un protector de pantalla de su elección.
   - Tiempo de espera a 15 minutos.
   - Al reanudar, muestra la pantalla de inicio de sesión.


**Administración de energía: directiva de grupo**

Antes de llevar a cabo el siguiente procedimiento, compruebe con su departamento de TI la aprobación para excluir un dispositivo Surface Hub 2S de la directiva de administración de energía global. Algunas opciones de configuración de administración de energía pueden deshabilitar la función de detección de presencia.

1. Busque el **Centro de software** y ábralo.

2. Seleccione **Opciones**.

3. Expanda Administración **de energía y**  seleccione **No aplicar la configuración de energía de mi departamento de TI a este equipo**.

   ![Configuración del software.](images/soft-cntr.png)

### <a name="storage-sense"></a>Sensor de almacenamiento

El Surface Hub 2 tiene una SSD de 128 GB para el almacenamiento local, por lo que es necesario tener en cuenta el uso de medidas de ahorro de almacenamiento durante el uso normal.  Para configurar Storage Sense:

1.  Busque la **configuración de almacenamiento**, que se encuentra en **Configuración del sistema**.

2.  En **Configuración**, seleccione **Activar el sentido de almacenamiento** para abrir la **página Storage** configuración.

3.  Activa Storage sense a **On**.

4.  Seleccione **Configurar Storage Sense o** ejecutarlo ahora y configure la configuración para mantener los archivos en línea tanto como sea posible (debido a un espacio de unidad limitado).

Configuración recomendada:

- Ejecute Storage Sense = Every Day.
- Eliminar archivos temporales que mis aplicaciones no usan = Cada 14 días (al menos).
- Elimine los archivos de la carpeta Descargas si han estado allí durante más de 30 días.
- OneDrive: el contenido se convertirá solo en línea si no se abre durante más de 30 días.

### <a name="tablet-mode"></a>Modo tableta

Activa el modo tableta si lo deseas para las necesidades de accesibilidad.


### <a name="sound-settings"></a>Configuración de sonido

1. Busque la **configuración de sonidos** y abra esta página.

2. Seleccione **Panel de control de sonido** a la derecha y seleccione la **pestaña** Sonidos.

3. En **Eventos del programa**, **establece Device Conectar** **y Device Disconnect** en **None**.

### <a name="silence-notifications"></a>Notificaciones de silencio

1. Busque ayuda **de foco y** abra esta página.

2. Seleccione **Solo alarmas**. Esto evitará los control de control de notificaciones constantes.

### <a name="disk-cleanup"></a>Liberador de espacio en disco

1. Busca Limpieza **de disco** y abre esta aplicación.

2. En **Archivos que desea eliminar**, seleccione los archivos que desea eliminar. 

3. También seleccione **Limpiar archivos del sistema**.

## <a name="complete-and-verify"></a>Completar y comprobar

1. Busque e instale todas las Windows actualizaciones.

2. Actualizar directiva de grupo.

   1. En un símbolo del sistema con privilegios elevados, escriba **gpupdate /force /boot /wait:0**.
   
3. Reinicia el dispositivo.

4. Compruebe las aplicaciones de la barra de tareas.

   - Conectar app
   - Icono de bloqueo
   - Recorte y anotación
   - Teams (si procede)
   - Office aplicaciones (si procede)
   - Surface App
   - Pizarra
    
5. Compruebe la detección de presencia.

   - La detección de presencia será un icono verde en la bandeja del sistema.
    
6. Compruebe que la proyección a este equipo está habilitada con la Conectar app. Después de configurar **Project configuración de este equipo**, ejecute la aplicación Conectar al menos una vez. (Posteriormente, la aplicación Conectar no necesita ejecutarse para poder proyectar a Surface Hub).

7. Compruebe la configuración de energía y suspensión.

    - Protector de pantalla: 15 minutos, establecido en (ninguno), Mystify o Blank; asegúrese de que la casilla de verificación para requerir contraseña está activada.
    - Pantalla: **desactivar después de 2 horas**.
    - PC:  **desactivar después de 4 horas**.
    
8. Compruebe Windows Hello está funcionando.

9. Compruebe que la sincronización de la configuración está deshabilitada.

10. Compruebe las aplicaciones de inicio.

> [!TIP]
> Después de instalar y configurar Windows 10, el Surface Hub 2S se puede administrar al igual que cualquier otro dispositivo Windows 10 o Windows 11.

## <a name="related-topics"></a>Temas relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrar a Windows 10 o Windows 11 Pro/Enterprise en Surface Hub 2</a>

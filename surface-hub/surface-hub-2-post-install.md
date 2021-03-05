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
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Configurar Windows 10 Pro o Enterprise en Surface Hub 2

Después de completar el proceso de instalación de la migración a Windows 10 Pro o Enterprise, puedes realizar los siguientes pasos para configurar aplicaciones y configuraciones en Surface Hub 2. Estos pasos se recomiendan para garantizar la mejor experiencia al usar este equipo táctil y de lápiz de pantalla grande personalizado.

Al realizar estos pasos, puede resultar útil usar un teclado y un mouse con cable o inalámbrico.

## <a name="configure-system-settings"></a>Configurar la configuración del sistema

1. Inicie sesión con una cuenta que tenga privilegios de administrador local en el dispositivo.  

    - En los dispositivos unidos a Azure AD, el usuario que realiza la unión a Azure AD se agrega automáticamente al grupo de administradores local. Los administradores globales de Azure AD y los dispositivos de Azure AD también <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> son administradores </a> locales. 
    
    - Puede escribir **administradores de grupos locales netos** en un símbolo del sistema para enumerar las cuentas que tienen derechos de administrador local.
    
2. Cambie el nombre del dispositivo con un nombre descriptivo, por ejemplo: **username-SHub-Desktop**.

3. Seleccione **Iniciar**  >  **configuración**  >  **Cuentas Sincronizar**la  >  **configuración** y desactivar la configuración **de** sincronización. 

    - La configuración que se usa aquí está diseñada para habilitar la mejor experiencia táctil de pantalla grande y, por lo tanto, es posible que no quiera sincronizar otros dispositivos.
    
4. Reinicia el dispositivo.

## <a name="enable-the-touch-keyboard-and-touchpad"></a>Habilitar el teclado táctil y el panel táctil

1. Selecciona **Iniciar**  >  ****  >  **dispositivos de configuración**  >  **Escribiendo** y activa Mostrar **el teclado táctil** cuando no esté en modo tableta y no haya ningún teclado conectado.

2. Pulse y mantenga presionado o haga clic con el botón secundario en la barra de tareas y, a continuación, seleccione **Mostrar botón del teclado táctil** y Mostrar botón del panel **táctil.** 

    - El teclado táctil es útil para la entrada directa del usuario y el panel táctil virtual ayuda con selecciones precisas, sugerencias de pantalla activa o como alternativa para pulsar y mantener pulsado el botón secundario. 
    
    - Consulta el ejemplo siguiente:

      ![Configuración táctil](images/touch.png)

3. Configure el teclado táctil en QWERTY y flotante.

    1. Seleccione el **icono Teclado** de la barra de tareas para mostrar el teclado táctil.
    
    1. En el teclado táctil, selecciona el icono del teclado en la esquina superior izquierda para abrir la configuración del teclado.
    
    1. Seleccione el tipo de teclado junto al último de la fila superior para habilitar QWERTY y la última opción de la segunda fila para habilitar flotante, lo que resulta muy útil en esta pantalla grande. Vea los ejemplos siguientes:

       ![Configuración del teclado](images/kbd.png)
 
4. Configure las opciones de teclado suave.

    1. Seleccione el **icono Configuración** en el teclado táctil o busque y abra La configuración **de escritura.**
    
       ![configuración de teclado suave](images/sh2-softkeyboard.png)

    1. Habilita todas las opciones en Ortografía, Escritura y teclado táctil.


En el ejemplo siguiente se muestra el trackpad, que resulta útil para navegar y seleccionar opciones. El teclado en pantalla se usa para buscar en Microsoft Store:

![Uso del trackpad](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>Configurar Bluetooth teclado y mouse (opcional)

Conecta un teclado y un mouse si usas el dispositivo como dispositivo Windows principal o lo usas a menudo para escribir o trabajar con precisión.

Si el dispositivo Surface Hub está cerca de un equipo, puedes usar Mouse sin bordes para moverse sin problemas <a href="https://aka.ms/mm" target="_blank"> entre Surface Hub y el </a> EQUIPO. Para obtener más información, <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> consulta Descarga de Microsoft desde El garage: Mouse sin bordes. </a>

## <a name="example-of-taskbar-layout"></a>Ejemplo de diseño de la barra de tareas

Después de completar los pasos siguientes para configurar o configurar Surface Hub 2 para Windows 10 Professional o Enterprise, te recomendamos que uses anclar las aplicaciones más usadas a la barra de tareas para un inicio rápido y táctil de cada aplicación. A continuación se muestra un ejemplo de cómo podría ser la barra de tareas:

 ![Diseño de la barra de tareas](images/taskblyt.png)
### <a name="update-installed-apps"></a>Actualizar aplicaciones instaladas

Para actualizar todas las aplicaciones de la Tienda instaladas:

1. Abre la aplicación de Microsoft Store y selecciona **los** puntos suspensivos Ver más en la esquina superior derecha.
2. Selecciona **Descargas y actualizaciones.**
3. Seleccionar **Obtener actualizaciones**

### <a name="scan-for-and-install-all-windows-updates"></a>Buscar e instalar todas las actualizaciones de Windows
Después de migrar a Windows 10 Professional o Windows 10 Enterprise, es posible que haya actualizaciones de mantenimiento y características disponibles para instalar. 

- Vaya a **Configuración**Actualizar & seguridad  >  **>** y, a continuación, seleccione Comprobar si **hay actualizaciones**.
- Si hay actualizaciones, instáleslas, reinicie y repita el proceso hasta que vea la siguiente notificación:

> [!div class="mx-imgBorder"]
> ![Notificación de Windows Update "Estás actualizado"](images/wustatus.png)


## <a name="onedrive-for-business"></a>OneDrive para la Empresa

Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive para la Empresa para compartir fácilmente herramientas, registros y </a> otros archivos entre todos los dispositivos de trabajo.

- OneDrive te permite compartir los archivos de trabajo entre tus portátiles, Surface Hub Desktop y tus dispositivos móviles administrados por Intune. Los archivos se pueden editar en cualquier dispositivo y todos los dispositivos conectados a la red se actualizarán con los cambios.

- Teniendo en cuenta el tamaño de la SSD de Surface Hub (128 GB), si configuras OneDrive en el dispositivo de escritorio de Surface Hub, asegúrate de que la configuración predeterminada sea mantener los archivos en línea y descargar los archivos mientras los usas.

Para configurar OneDrive para descargar archivos **** solo cuando sea necesario, establezca la configuración Archivos a petición en Guardar espacio y descargar archivos a medida **que los use**. Para obtener más información, consulta <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Consultar y establecer estados de archivos a petición en Windows </a> .

![Configuración de OneDrive](images/onedrive.png)

> [!NOTE]
> También puede repetir estos pasos para configurar un OneDrive personal, pero asegúrese de conservar el espacio en la unidad y descargar solo los archivos que necesite.

## <a name="sharepoint-and-teams"></a>SharePoint y Teams

Los archivos de Canal de SharePoint y Teams también pueden sincronizarse localmente con los dispositivos de escritorio, como portátiles y Surface Hubs, mediante el motor de sincronización de OneDrive.

Para sincronizar archivos corporativos internos con la unidad local con la aplicación de sincronización de OneDrive:

1. Vaya a un sitio de SharePoint y vaya al directorio de documentos de nivel superior para obtener los archivos que le interesan ver o editar desde el dispositivo local.

2. Seleccione el botón **Sincronizar** en la parte superior de la cinta de opciones de SharePoint.

3. Seleccione abrir **en** el elemento emergente **Este sitio está intentando abrir Microsoft OneDrive**.

4. Compruebe que los archivos de SharePoint se sincronizan con la unidad local seleccionando el icono de OneDrive en la parte inferior derecha de la barra de tareas.

5. Compruebe que la configuración está configurada para mantener los archivos en línea y descargar los archivos solo cuando los use:

    1. Abra el explorador de archivos.
    
    2. Vaya a y haga clic con el botón secundario en el nombre de SharePoint; por ejemplo, **Contoso \ \<SharePoint Document Folder Name\> **.
    
    3. Seleccione **Liberar espacio**.
    
    4. La columna Estado mostrará el estado de los archivos y carpetas. Para obtener más información, vea <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sincronizar archivos de SharePoint con el cliente de sincronización de OneDrive </a> .
    
6. Los archivos de canal de Teams se almacenan en sitios de SharePoint, con todas las mismas funciones de documentos de SharePoint, incluido el historial de versiones y la sincronización con los dispositivos de escritorio locales. Para sincronizar archivos de canal de Teams:

    1. Vaya al Canal de interés de Teams y seleccione la **pestaña** Archivos en la parte superior. A continuación, **seleccione Sincronizar**. Los archivos comenzarán a sincronizarse y estarán visibles en el Explorador de archivos en **Escritorio \ Contoso \ \<name of the Teams Channel\> **.
    
    2. Use el mismo procedimiento que usó para sincronizar sitios de SharePoint para mantener los archivos en la nube y descargarlos solo cuando los use, pulsando y mantén presionado o haciendo clic con el botón secundario en el Explorador de archivos en el nombre del canal de Teams y seleccionando Liberar espacio **.**

## <a name="surface-hub-pen-settings"></a>Configuración del lápiz de Surface Hub

**Emparejar el lápiz Bluetooth Surface Hub**

Emparejar el lápiz para mantener actualizado el firmware del lápiz, establecer los accesos directos del lápiz y obtener información de carga de batería en la página de configuración del dispositivo Bluetooth o en la aplicación Surface:

1. Seleccione **Iniciar**  >  **dispositivos de**  >  **configuración**.

2. Selecciona **Agregar Bluetooth u otro dispositivo**.

3. Elija **Bluetooth**.

4. Quite el botón de cola del lápiz y agite para desconectar la conexión de la batería.

5. Vuelva a colocar la tapa y mantenga presionada la tapa hasta que parpadee el LED de emparejamiento.

6. En la configuración de Bluetooth Surface Hub, elige **Lápiz de Surface Hub 2**.

7. Complete la operación de emparejamiento. 

8. Si el emparejamiento no se realiza correctamente, puede intentar emparejar el lápiz de nuevo. Si eso no funciona, puedes probar para ver si la batería se carga comprobando que el lápiz funciona en la aplicación Pizarra. Si no es así, reemplace la batería y vuelva a emparejar el lápiz. Si es necesario, reinicia el dispositivo y vuelve a intentarlo.

**Establecer métodos abreviados de lápiz** El lápiz de Surface Hub tiene un botón de acceso directo que a veces se conoce como "clic de cola". La configuración de métodos abreviados requiere emparejar primero el lápiz, como se describió anteriormente.

1. Busque Pluma y seleccione **Lápiz & configuración de Windows Ink**.

2. Cerca de la parte inferior de la página, seleccione Métodos abreviados de lápiz que abre el cuadro de diálogo, que se muestra aquí:

   ![Métodos abreviados de lápiz](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>Configuración de cámara

Puedes montar la cámara en la parte superior o en cualquier lado del dispositivo. Monta la cámara en una posición para optimizar el ángulo de la cámara si estás usando el concentrador con un soporte de escritorio en lugar de un carro, o si estás cerca del concentrador. La cámara no gira automáticamente, por lo que debes tener una tecla hexadecimal de 2 mm para girar manualmente la cámara. 

Para obtener más información sobre cómo montar de forma lateral la cámara y girar la cámara manualmente, consulta Orientación del objetivo de la cámara de <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S </a> .

## <a name="windows-hello-configuration"></a>Configuración de Windows Hello

Surface Hub 2S que ejecuta Windows 10 Enterprise permite el conjunto completo de aplicaciones de escritorio de Win32, así como opciones biométricas de Windows Hello. El accesorio lector de huellas digitales de Surface Hub 2 se puede conectar a cualquier puerto USB-C del dispositivo. 

Para solicitar un lector de huellas digitales de Surface Hub 2 o ver especificaciones técnicas, consulta (surface-hub-2-essential-add-ons.md" target="_blank">Complementos esenciales para Windows 10 Pro y Enterprise en Surface Hub 2 </a> . 

Después de insertar el lector de huellas digitales, selecciona **Opciones**de inicio de sesión cuentas de configuración  >  ****  >  ****  >  ****  >  **Windows Hello Fingerprint** para inscribir la huella digital.

Usa un dispositivo certificado de Windows Hello para el reconocimiento facial. La cámara de Surface Hub 2S no admite el reconocimiento facial de Windows Hello.

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>Habilitar un icono de acceso directo de pantalla de bloqueo en la barra de tareas

Para agregar un icono a la barra de tareas que habilita un bloqueo de pantalla táctil similar al método abreviado de teclado windows-L: 

1.  Pulsa y mantén presionado o haz clic con el botón derecho en el escritorio, selecciona **Nuevo**  >  **acceso directo**  >  **Examinar**  >  **escritorio**  >  **Aceptar**  >  **siguiente**.

1.  Proporcione un nombre para el acceso directo como **Bloquear mi PC**y, a continuación, seleccione **Finalizar**.

1.  Haga clic con el botón secundario o pulse y mantenga presionado el acceso directo recién creado en el escritorio y seleccione **Propiedades**. En la **pestaña Acceso** directo, escriba lo siguiente en el **campo Destino:** **Rundll32.exe User32.dll,LockWorkStation**

1.  Seleccione el **botón Cambiar icono** y vaya a **C:\Windows\System32\imageres.dll** y seleccione un icono para usar. 

    Observa el siguiente ejemplo:

    ![Elegir un icono](images/lock.png)
    
1.  Seleccione **Aceptar** para guardar el acceso directo.

1.  Haga clic con el botón secundario o pulse y mantenga presionado el acceso directo y seleccione **Anclar a la barra de tareas**.

1. Después de anclar el acceso directo de bloqueo a la barra de tareas, puede eliminarlo del escritorio.

## <a name="applications"></a>Aplicaciones


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

Para instalar la pizarra de Microsoft:

 - Selecciona el **icono Área de trabajo** de Windows Ink en la parte inferior derecha de la barra de tareas y descarga **Pizarra.**
 
   ![Área de trabajo de lápiz](images/ink.png) 

Como alternativa, puedes instalar whiteboard desde Microsoft Store:

1. Abre la aplicación de Microsoft Store y busca **Whiteboard**.

2. Elige **No gracias para** iniciar sesión y usar en todos los dispositivos.

3. Anclar pizarra a la barra de tareas.

### <a name="surface-app"></a>Aplicación Surface

1. En Microsoft Store, busque **Surface**.

2. Establece el **filtro Disponible en** todos los **dispositivos**.

3. Instala la **aplicación Surface.** Esta debería ser la primera aplicación enumerada. Es posible que deba asociar la MSA a la Tienda para instalar la aplicación.

4. Anclar la **aplicación Surface** a la barra de tareas.

### <a name="snip--sketch"></a>Recorte y anotación

1. Abre la **aplicación Snip & Sketch** y anclarla a la barra de tareas.

2. Seleccione los puntos suspensivos en la esquina superior derecha y, a continuación, **seleccione Configuración**.

3. En **Configuración,** activa Copia **automática en el Portapapeles**, Guardar **snips**y **Varias ventanas** (opcional).

### <a name="microsoft-office"></a>Microsoft Office

1. Abra <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal </a> e instale las aplicaciones deseadas.

2. Anclar las aplicaciones de Office deseadas a la barra de tareas.

3. Si Outlook está instalado, asegúrese de establecer la OST de Outlook para que solo guarde la memoria caché de las últimas dos semanas. Esto reducirá en gran medida el uso del disco y el tiempo de instalación.

    - Selecciona **Configuración de**la cuenta  >  **de** archivo y selecciona tu cuenta.
    
    - Seleccione **Cambiar** y establezca el control deslizante para Usar el modo **caché de Exchange** en 14 días.

### <a name="microsoft-teams"></a>Microsoft Teams

1. Descargar e instalar <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a> .

2. Configure las opciones para iniciar automáticamente la aplicación (opcional).

3. Anclar Teams a la barra de tareas.

4. Considera la posibilidad de reducir las notificaciones de Teams en el dispositivo para evitar distracciones (opcional).

   ![Notificaciones de Teams](images/teams.png)

### <a name="connect-app"></a>Aplicación Connect

> [!IMPORTANT]
> En Windows 10, versión 2004 y versiones posteriores, la aplicación Connect para la proyección inalámbrica con Miracast no está instalada de forma predeterminada, pero está disponible como una característica opcional. Si has instalado (o actualizado a) Windows versión 2004 o posterior, puedes ver lo siguiente en la pantalla Proyectar a este equipo en configuración:

![Proyecto para este equipo](images/sh2-project.png) 


1. Para instalar la aplicación desde la página de configuración ****"Proyectar a este equipo", selecciona Características opcionales Agregar una característica y,  >  **a** continuación, instala la **aplicación Pantalla** inalámbrica.

2. En **Algunos dispositivos Windows y Android pueden proyectarse**a este equipo cuando diga que está bien , elija:

    - **Disponible en todas** partes si el dispositivo no está en una red corporativa.
    - De lo contrario, **elija Disponible en todas partes en redes seguras.**
    
3. En **Solicitar proyecto a este equipo,** elija Solo primera **vez**.

4. En **Requerir PIN para el emparejamiento,** elija **Nunca**.

5. Para iniciar la aplicación y anclarla a la barra de tareas, busque **Conectar**.

6. Abre la aplicación. Mientras la aplicación está abierta, haz clic con el botón secundario en el icono Conectar aplicación de la barra de tareas y selecciona **Anclar a la barra de tareas**.

7. A continuación, cierra la aplicación Conectar. **Es posible que el proyecto en este equipo** no funcione a menos que la aplicación se haya ejecutado al menos una vez.

Configuración recomendada cuando no está en la red corporativa:

![Configuración en casa](images/project1.png)

Configuración recomendada en la red corporativa:

![Configuración en el trabajo](images/project2.png)

### <a name="your-phone"></a>Tu Teléfono

La **aplicación Tu teléfono** está instalada de forma predeterminada en Windows 10. Si no está presente, también puedes instalarlo desde la Tienda Windows.

Para obtener información sobre cómo configurar la aplicación, consulta Cómo configurar Tu teléfono en Windows 10 y sincronizar datos <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> entre el equipo y el </a> teléfono. Consulta también <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> Cómo solucionar problemas comunes con la aplicación Tu teléfono en Windows 10 </a> .

###  <a name="fancy-zones"></a>Zonas de lujo


**Zonas elegantes** forma parte de una colección de herramientas <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> denominadas PowerToys </a> en GitHub. Es una excelente manera de usar la pantalla en un Surface Hub 2, ya que te permite definir diseños fijos en la pantalla ("zonas") y, a continuación, seleccionar qué aplicación se ejecutará en cada zona. 


El [wiki de PowerToys](https://github.com/microsoft/PowerToys/wiki) tiene instrucciones sobre cómo usar y personalizar cada herramienta, [incluidos FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview). En un nivel alto: después de instalar PowerToys, puedes seleccionar o crear un diseño personalizado y, a continuación, mantener presionada la tecla mayús y arrastrar o usar teclas de teclado para mover una aplicación en ejecución a zonas específicas. El uso Bluetooth teclado y mouse USB te ayudarán con esto, o puedes usar el teclado táctil y el panel táctil en pantalla.

**Sugerencias de power toys**
- Para recibir notificaciones por correo electrónico de las actualizaciones de la versión de PowerToys en GitHub, haga clic en el botón "Registrarse" en la parte superior de la [página](https://github.com/microsoft/PowerToys/releases).
- Una vez instalado PowerToys, puedes recibir notificaciones de Windows o descargar e instalar las actualizaciones **** más recientes configurando la configuración de PowerToys Descargar actualizaciones automáticamente en on.
- Para llegar a la configuración de PowerToys, seleccione las aplicaciones en ejecución de quilates en la barra de tareas y, a continuación, haga clic con el botón secundario o presione y mantenga presionado el icono PowerToys hasta que aparezca el menú. **** Seleccione "Configuración".
- En la parte inferior de la página de configuración de PowerToys, activa **Descargar actualizaciones automáticamente.**
- Cuando se haya publicado una actualización, aparecerá una notificación de Windows que te dará la opción de cuándo instalar la actualización.


### <a name="edge-chromium-browser"></a>Explorador Chromium perimetral

Descargue e instale el nuevo <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> explorador Edge Chromium </a> .


### <a name="surface-hub-hardware-diagnostic-tool"></a>Herramienta de diagnóstico de hardware de Surface Hub

La <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> herramienta de diagnóstico de hardware de Surface Hub disponible de forma gratuita en Microsoft </a> Store. La herramienta está diseñada para ayudarte a asegurarte de que surface hub funciona en su mejor momento. Contiene pruebas para determinar si el firmware está actualizado y configurado correctamente. Las pruebas interactivas permiten confirmar que la funcionalidad esencial funciona según lo esperado. Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub. Haga clic en el vínculo para instalarlo desde la Microsoft Store y, a continuación, anclar la aplicación a la barra de tareas.

## <a name="additional-settings"></a>Configuración adicional

### <a name="pen-tail-select-to-launch-whiteboard"></a>Selección de cola de lápiz para iniciar pizarra

1. Busque Pluma **y** seleccione **Lápiz & configuración de Windows Ink**.

2. Cerca de la parte inferior de la página, en **Métodos abreviados de lápiz,** establece **Seleccionar una vez** en Pizarra de **Microsoft**. 

### <a name="power-management"></a>Administración de energía

Hay varias opciones de configuración de energía disponibles para obtener la mejor experiencia con Windows 10 Pro o Enterprise en Surface Hub 2. Esto incluye tiempos de espera de pantalla y equipo, y cómo interactúan con la detección de presencia humana integrada (Doppler), el protector de pantalla y la protección de contraseña y, si procede, cómo pasar la configuración de energía de directiva de grupo destinada a usuarios de equipos portátiles o de escritorio.

Windows 10 Pro o Enterprise en Surface Hub 2 impide que la pantalla duerma mediante acciones táctiles, de mouse y de teclado, así como la detección de ocupación humana integrada (Doppler). La detección de ocupación humana está habilitada de forma predeterminada, pero si se desea se puede deshabilitar en UEFI al alternar la opción de dispositivo en la herramienta Configurador UEFI de Surface como parte de la migración inicial, o mediante la creación y aplicación de un paquete de configuración de UEFI posterior. 

**Administración de energía: configuración de suspensión de pantalla y equipo**

1. Seleccione **Iniciar**  >  **configuración**  >  **Sistema**  >  **Power & modo de suspensión**.

2. Establece el control deslizante del modo de energía en **Mejor rendimiento.**

3. Configure los valores de pantalla y suspensión según su preferencia, al tiempo que también tiene en cuenta la detección de presencia de Doppler que activa el dispositivo cuando se detecta el movimiento. Por lo tanto, como procedimiento recomendado, se recomienda establecer Pantalla en Desactivar después de **2** horas y el equipo desactivar después de **4 horas.**

**Administración de energía: protector de pantalla**

1. Busque Pantalla **de bloqueo y** abra La configuración de pantalla de **bloqueo**.

2. Configure **la configuración de tiempo de espera de** pantalla y la configuración del **protector** de pantalla según sus preferencias. Los valores predeterminados recomendados son:

   - Protector de pantalla a (Ninguno) o un protector de pantalla de su elección.
   - Tiempo de espera a 15 minutos.
   - Al reanudar, muestra la pantalla de inicio de sesión.


**Administración de energía: directiva de grupo**

Antes de realizar el siguiente procedimiento, comprueba con el departamento de TI la aprobación para excluir un dispositivo Surface Hub 2S de la directiva global de administración de energía. Algunas opciones de configuración de administración de energía pueden deshabilitar la función de detección de presencia.

1. Busque el **Centro de software** y ábralo.

2. Seleccione **Opciones**.

3. Expanda Administración **de energía y**  seleccione No aplicar la configuración de energía de mi departamento de TI a este **equipo**.

   ![Configuración de software](images/soft-cntr.png)

### <a name="storage-sense"></a>Sensor de almacenamiento

Surface Hub 2 tiene una SSD de 128 GB para el almacenamiento local, por lo que es necesario considerar el uso de medidas de almacenamiento durante el uso normal.  Para configurar El sentido de almacenamiento:

1.  Busque la **configuración de almacenamiento**, que se encuentra en Configuración del **sistema**.

2.  En **Configuración,** seleccione **Activar el sentido de almacenamiento** para abrir la página **Configuración** de almacenamiento.

3.  Active el sentido de almacenamiento **en On**.

4.  Seleccione **Configurar sentido de almacenamiento o ejecutarlo** ahora y configure las opciones para mantener los archivos en línea tanto como sea posible (debido a un espacio de unidad limitado).

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

3. En **Eventos del programa,** **establece Device Connect** y Device **Disconnect** en **None**.

### <a name="silence-notifications"></a>Notificaciones de silencio

1. Busque ayuda **de foco y** abra esta página.

2. Seleccione **Solo alarmas**. Esto evitará los control de control de notificaciones constantes.

### <a name="disk-cleanup"></a>Liberador de espacio en disco

1. Busca Limpieza **de disco** y abre esta aplicación.

2. En **Archivos para eliminar,** seleccione los archivos que desea eliminar. 

3. También seleccione **Limpiar archivos del sistema.**

## <a name="complete-and-verify"></a>Completar y comprobar

1. Busca e instala todas las actualizaciones de Windows.

2. Actualizar directiva de grupo.

   1. En un símbolo del sistema con privilegios elevados, escriba **gpupdate /force /boot /wait:0**.
   
3. Reinicia el dispositivo.

4. Compruebe las aplicaciones de la barra de tareas.

   - Connect App
   - Icono de bloqueo
   - Recorte y anotación
   - Teams (si procede)
   - Aplicaciones de Office (si procede)
   - Surface App
   - Pizarra
    
5. Compruebe la detección de presencia.

   - La detección de presencia será un icono verde en la bandeja del sistema.
    
6. Compruebe que la proyección a este equipo está habilitada con la aplicación Connect. Después de configurar  **Project en esta configuración de PC,** ejecute la aplicación Connect al menos una vez. (Posteriormente, la aplicación Connect no necesita ejecutarse para poder proyectarse en Surface Hub).

7. Compruebe la configuración de energía y suspensión.

    - Protector de pantalla: 15 minutos, establecido en (ninguno), Mystify o Blank; asegúrese de que la casilla de verificación para requerir contraseña está activada.
    - Pantalla: **Desactivar después de 2 horas**.
    - PC:  **desactivar después de 4 horas**.
    
8. Comprueba que Windows Hello funciona.

9. Compruebe que la sincronización de la configuración está deshabilitada.

10. Compruebe las aplicaciones de inicio.

> [!TIP]
> Después de instalar y configurar Windows 10, Surface Hub 2S se puede administrar igual que cualquier otro dispositivo Windows 10.

## <a name="related-topics"></a>Temas relacionados

<a href="surface-hub-2s-migrate-os.md" target="_blank"> Migrar a Windows 10 Pro o Enterprise en Surface Hub 2</a>

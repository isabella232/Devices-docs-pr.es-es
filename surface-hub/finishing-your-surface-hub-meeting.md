---
title: 'Finalizar sesión: finalizar una reunión de Surface Hub'
description: Para finalizar una reunión de Surface Hub, pulsa Terminar la sesión. Surface Hub limpiará el estado de la aplicación, el estado del sistema operativo y la interfaz de usuario para que Surface Hub esté listo para la próxima reunión.
keywords: I am Done, He terminado, end Surface Hub meeting, terminar reunión de Surface Hub, finish Surface Hub meeting finalizar reunión de Surface Hub, clean up Surface Hub meeting, limpiar reunión de Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836234"
---
# Finalizar una reunión de Surface Hub con Finalizar sesión
Surface Hub es un dispositivo de colaboración que se ha diseñado para que lo usen distintos grupos de personas en espacios de reuniones. Al final de una reunión, los usuarios pueden presionar **Terminar la sesión** para limpiar los datos confidenciales y preparar el dispositivo para la próxima reunión. Surface Hub limpiará o restablecerá los siguientes estados:
- Aplicaciones
- Sistema operativo
- Interfaz de usuario

En este tema se explica qué restablece la opción **Terminar la sesión** para cada uno de estos estados.

##  <a name="applications"></a>Aplicaciones
Al iniciar aplicaciones en Surface Hub, estas se almacenan en la memoria y los datos se almacenan en el nivel de la aplicación. Estos datos están disponibles para todos los usuarios durante esa sesión (o reunión) hasta que se quitan o se sobrescriben. Cuando se selecciona **Terminar la sesión**, el estado de aplicación de Surface Hub se limpia mediante el cierre de aplicaciones, la eliminación del historial del navegador, el restablecimiento de las aplicaciones y la eliminación de los registros de Skype.

###  <a name="close-applications"></a>Cierre de aplicaciones
Surface Hub cierra todas las ventanas visibles, incluidas las aplicaciones Win32 y la Plataforma universal de Windows (UWP). La fase de cierre de aplicaciones usa la vista de multitarea para consultar las ventanas visibles. Las ventanas de Win32 que se cierran en un determinado período de tiempo se cierran mediante **TerminateProcess**. 
   
###  <a name="delete-browser-history"></a>Eliminación del historial del navegador
Surface Hub usa la función Eliminar historial del explorador (DBH) de Edge para borrar el historial de Edge y los datos almacenados en caché. Esto es similar a la forma en la que un usuario puede borrar el historial de su navegador manualmente, pero **Terminar la sesión** también garantiza que los estados de las aplicaciones se borran y los datos se eliminan antes de que empiece la siguiente sesión o reunión. 
 
###  <a name="reset-applications"></a>Restablecer las aplicaciones
**Terminar la sesión** restablece el estado de todas las aplicaciones instaladas en Surface Hub. El restablecimiento de una aplicación borra todas las tareas en segundo plano, los datos de las aplicaciones, las notificaciones y los cuadros de diálogo de consentimiento del usuario. Las aplicaciones vuelven a su estado de primera ejecución para las siguientes personas que usen Surface Hub.  
 
###  <a name="remove-skype-logs"></a>Eliminación de los registros de Skype
Skype no almacena información de identificación personal en Surface Hub. La información se almacena en el servicio de Skype para cumplir con las pautas existentes de Skype Empresarial. La información de registro local de Skype son los únicos datos que se quitan cuando se selecciona **Terminar la sesión**. Esto incluye los registros de la plataforma unificada de cliente de comunicaciones (UCCP) y los registros multimedia.   

##  <a name="operating-system"></a>Sistema operativo
El sistema operativo contiene una gran variedad de información sobre el estado de las sesiones que debe borrarse después de cada reunión de Surface Hub. 

###  <a name="file-system"></a>Sistema de archivos
Los asistentes a la reunión tienen acceso a un conjunto limitado de directorios en Surface Hub. Cuando se selecciona **Terminar la sesión**, Surface Hub borra estos directorios:<br>
- Música
- Vídeos
- Documentos
- Imágenes
- Descargas

Surface Hub, también borra estos directorios, dado que muchas aplicaciones a menudo escriben en ellos:
- Escritorio
- Favoritos
- Recientes
- Documentos públicos
- Música pública
- Vídeos públicos
- Descargas públicas

###  <a name="credentials"></a>Credenciales
Las credenciales de usuario que se almacenan en **TokenBroker**, **PasswordVault** o el **Administrador de credenciales** se borran al pulsar **Terminar la sesión**.

##  <a name="user-interface"></a>Interfaz de usuario
Las opciones de configuración de la interfaz de usuario vuelven a sus valores predeterminados cuando se selecciona **Terminar la sesión**. 

###  <a name="ui-items"></a>Elementos de la interfaz de usuario
- Restablecimiento de las acciones rápidas a su estado predeterminado
- Borrado de las notificaciones del sistema
- Restablecimiento de los niveles de volumen
- Restablecimiento del ancho de la barra lateral
- Restablecer el diseño del modo de tableta
- Cerrar la sesión del usuario en las reuniones y archivos de Office 365

###  <a name="accessibility"></a>Accesibilidad
Las características de accesibilidad y las aplicaciones se devuelven a la configuración predeterminada cuando se selecciona **Terminar la sesión**.
- Teclas de filtro
- Contraste alto
- Teclas especiales
- Teclas de alternancia
- Teclas del mouse
- Lupa
- Narrador

###  <a name="clipboard"></a>Portapapeles
El portapapeles se borra para eliminar los datos copiados en él durante la sesión. 

##  <a name="faq"></a>Preguntas más frecuentes
**¿Qué sucede si olvido pulsar Terminar la sesión al final de una reunión y otra persona usa Surface Hub más adelante?**<br>
Surface Hub solo limpia el contenido de las reuniones cuando los usuarios pulsan **Terminar la sesión**. Si abandonas la reunión sin pulsar **Terminar la sesión**, el dispositivo volverá a la pantalla de inicio de sesión transcurrido cierto tiempo. Desde la pantalla de inicio de sesión, los usuarios pueden reanudar la sesión anterior o iniciar una nueva. También puedes deshabilitar la posibilidad de reanudar la sesión si no se pulsa **Terminar la sesión**.

**¿Los documentos se pueden recuperar?**<br> La eliminación de archivos de la unidad de disco duro cuando se selecciona **Terminar la sesión** es igual que cualquier otra eliminación de archivos de una unidad de disco duro. Es posible que exista software de terceros que pueda recuperar datos de esta unidad de disco duro, pero la recuperación de archivos no es una característica compatible en Surface Hub. Para evitar la pérdida de datos, guarda siempre los datos que necesitas antes de salir de una reunión.

**¿Las acciones de limpieza desde Terminar la sesión cumplen con el estándar de limpieza e higiene del Departamento de Defensa de los Estados Unidos DoD 5220.22-M?**<br>
No. Actualmente, las acciones de limpieza de **Terminar la sesión** no cumplen con este estándar.  
  

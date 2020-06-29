---
title: Miracast en una red inalámbrica o LAN existente
description: Windows 10 te permite enviar una emisión Miracast a través de una red local.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836974"
---
# Miracast sobre la infraestructura

En Windows 10, versión 1703, Microsoft ha ampliado la capacidad de enviar una emisión de Miracast a través de una red local, en lugar de a través de un vínculo directo inalámbrico. Esta funcionalidad se basa en el [Protocolo de establecimiento de conexión de Miracast a través de infraestructura (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx).

Miracast a través de infraestructura ofrece una serie de ventajas:

- Windows detecta automáticamente cuándo se puede enviar la emisión de vídeo a través de esta ruta.
- Windows solo elige esta ruta si la conexión se realiza a través de Ethernet o de una red Wi-Fi segura.
- Los usuarios no tienen que cambiar la forma en que se conectan al receptor de Miracast. Usan la misma experiencia del usuario que en las conexiones de Miracast estándar.
- No es necesario realizar ningún cambio en los controladores inalámbricos existentes ni en el hardware del equipo.
- Funciona bien con el hardware inalámbrico más antiguo que no se haya optimizado para Miracast a través de Wi-Fi Direct.
- Aprovecha la conexión existente, lo que reduce el tiempo de conexión y ofrece una emisión muy estable.


## Cómo funciona

Los usuarios intentan conectarse a un receptor Miracast a través de su adaptador Wi-Fi como antes. Cuando se llena la lista de receptores de Miracast, Windows 10 identificará el receptor que puede admitir una conexión a través de la infraestructura. Cuando el usuario selecciona un receptor de Miracast, Windows 10 intentará resolver el nombre de host del dispositivo a través de DNS estándar y de DNS multidifusión (mDNS). Si el nombre no se puede resolver a través de ninguno de estos métodos DNS, Windows 10 recurrirá a establecer la sesión de Miracast con la conexión de Wi-Fi Direct estándar.

> [!NOTE]
> Para obtener más información sobre la secuencia de negociación de conexión, consulte [Miracast sobre el protocolo de establecimiento de conexiones de infraestructura (MS-ratones)](https://msdn.microsoft.com/library/mt796768.aspx)




## Habilitar Miracast a través de la infraestructura 

Si tienes un dispositivo Surface Hub u otro dispositivo con Windows 10 que se ha actualizado a Windows 10, versión 1703, tendrás automáticamente esta nueva característica. Para poder aprovecharla en el entorno, debes asegurarte de que se cumplan las siguientes condiciones en la implementación:

- Surface Hub o el dispositivo (PC o teléfono con Windows) debe ejecutar Windows 10, versión 1703.
- Abrir puerto TCP: **7250**.
- Surface Hub o un PC Windows se puede emplear como *receptor* de Miracast a través de la infraestructura. Un equipo o teléfono con Windows se puede emplear como *origen* de Miracast a través de la infraestructura.
    - Para que funcione como receptor de Miracast, Surface Hub o el dispositivo debe estar conectado a la red de empresa a través de Ethernet o de una conexión Wi-Fi segura (por ejemplo, con seguridad WPA2-PSK o WPA2-Enterprise). Si el Surface Hub o dispositivo está conectado a una conexión Wi-Fi abierta, Miracast sobre la infraestructura se deshabilitará.
    - Para servir de origen de Miracast, el equipo o teléfono con Windows debe estar conectado a la misma red de empresa a través de Ethernet o de una conexión Wi-Fi segura.
- El nombre de host DNS (nombre del dispositivo) del concentrador o dispositivo Surface debe poder resolverse a través de los servidores DNS. Puedes lograrlo permitiendo que Surface Hub se registre automáticamente a través de DNS dinámico, o crear manualmente un registro A o AAAA para el nombre de host de Surface Hub. 
- Los equipos con Windows 10 deben estar conectados a la misma red de empresa a través de Ethernet o de una conexión Wi-Fi segura. 
-   En los equipos PC con Windows 10, la característica de **proyección a este equipo** debe estar habilitada en la configuración del sistema y el dispositivo debe tener habilitada una interfaz Wi-Fi para poder responder a las solicitudes de descubrimiento que solo se realizan a través del adaptador Wi-Fi.


Es importante tener en cuenta que Miracast a través de la infraestructura no es un sustituto de Miracast estándar. Por el contrario, la funcionalidad es complementaria y ofrece ventajas a los usuarios que forman parte de la red de empresa. Los usuarios invitados en una determinada ubicación que no tengan acceso a la red de empresa seguirán conectándose mediante el método de conexión Wi-Fi Direct.

La opción de configuración **InBoxApps/WirelessProjection/PinRequired** en el [proveedor de servicios de configuración (CSP) de SurfaceHub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) no es necesaria para Miracast a través de la infraestructura. Esto es porque Miracast a través de la infraestructura solo funciona si ambos dispositivos están conectados a la misma red de empresa. De este modo, se elimina de Miracast la restricción de seguridad que faltaba anteriormente. Te recomendamos que sigas usando esta opción de configuración (si la usabas anteriormente), ya que Miracast recurrirá a Miracast normal si la conexión a través de la infraestructura no funciona. 

## Preguntas más frecuentes
**¿Por qué todavía necesito Wi-Fi para usar Miracast en la infraestructura?**<br>
Las solicitudes de detección para identificar receptores de Miracast solo pueden realizarse a través del adaptador Wi-Fi. Una vez que se hayan identificado los receptores, Windows 10 podrá entonces intentar la conexión a la red.

---
title: Adaptadores ethernet e implementación Surface (Surface)
description: En este artículo se proporcionan instrucciones y respuestas que te ayudarán a realizar una implementación de red en dispositivos Surface.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: Ethernet, implementar, extraíble, red, conectividad, arranque, firmware, dispositivo, adaptador, arranque PXE, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ec73d437d2784ffbceb350f38507524e761df8dd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448483"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>Adaptadores ethernet e implementación Surface

En este artículo se describe cómo realizar una implementación de red de los dispositivos Surface más recientes, incluidos Surface Pro 3 y versiones posteriores.

La implementación de red en dispositivos Surface puede suponer algunos retos únicos para los administradores del sistema. Debido a la falta de un adaptador Ethernet nativo con cable, los administradores deben proporcionar conectividad a través de un adaptador Ethernet extraíble.

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>Seleccionar un adaptador Ethernet para dispositivos Surface

Antes de que puedas abordar los problemas de cómo arrancará en el entorno de implementación o cómo la solución de implementación reconocerá los dispositivos, tienes que usar un adaptador de red con cable.

Al seleccionar adaptadores Ethernet, la principal preocupación es cómo arrancarán los dispositivos Surface desde la red. Supongamos que es cliente de almacenamiento provisional previo con Windows Deployment Services (WDS) o mediante Microsoft Endpoint Configuration Manager. En ese caso, es posible que también quieras considerar si los adaptadores Ethernet extraíbles se dedicarán a un dispositivo Surface específico o se compartirán entre varios dispositivos. Para obtener más información sobre posibles conflictos con adaptadores compartidos, vea [Administrar direcciones MAC](#manage-mac-addresses) con adaptadores Ethernet extraíbles más adelante en este artículo.

El arranque desde la red (arranque PXE) solo se admite cuando se usa un adaptador Ethernet o una estación de acoplamiento de Microsoft. El conjunto de chips del adaptador Ethernet o dock debe detectarse y configurarse como un dispositivo de arranque en el firmware del dispositivo Surface. Los adaptadores Ethernet de Microsoft, como el adaptador Ethernet de Surface y [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock), usan un conjunto de chips compatible con el firmware de Surface.

Los dispositivos Ethernet siguientes son compatibles con el arranque de red con dispositivos Surface:

- Adaptador de Surface USB-C a Ethernet y USB 3.0
- Adaptador De Surface USB 3.0 a Gigabit Ethernet
- Microsoft USB-C Travel Hub
- Surface Dock
- Surface Dock 2
- Estación de acoplamiento para Surface 3
- Estación de acoplamiento para Surface Pro 3 
- Estación de acoplamiento para Surface Pro y Surface Pro 2

También se admiten adaptadores Ethernet de terceros para la implementación de red, aunque no son compatibles con el arranque PXE. Para usar un adaptador Ethernet de terceros, debes cargar los controladores en la imagen de arranque de implementación y debes iniciar esa imagen de arranque desde un dispositivo de almacenamiento independiente, como un stick USB.

## <a name="boot-surface-devices-from-the-network"></a>Arrancar dispositivos Surface desde la red

Para arrancar desde la red o un stick USB conectado, debes indicar al dispositivo Surface que arranque desde un dispositivo de arranque alternativo. Puedes modificar el orden de arranque en el firmware del sistema para priorizar los dispositivos de arranque USB o arrancar desde un dispositivo de arranque alternativo durante el proceso de arranque.

**Para arrancar desde un dispositivo de arranque alternativo:**

1. Asegúrate de que el dispositivo Surface esté apagado.
2. Mantén presionado el botón **Bajar el volumen**.
3. Presiona y suelta el botón **inicio/apagado**.
4. Una vez que el sistema comienza a arrancar desde el stick USB o adaptador Ethernet, suelta el botón **Bajar el volumen**.

>[!NOTE]
>Además de un adaptador Ethernet, también debes tener conectado un teclado al dispositivo Surface para tener acceso al entorno de preinstalación y navegar por el Asistente para la implementación.

Para Windows 10, versión 1511 y posteriores, incluido el Windows Assessment and Deployment Kit (Windows ADK) para Windows 10, versión 1511; los controladores para adaptadores Ethernet de Microsoft Surface están presentes de forma predeterminada. Si usa una solución de implementación que usa un entorno de preinstalación de Windows (WinPE), como el Toolkit de implementación de Microsoft, y el arranque desde la red con PXE, asegúrese de que la solución de implementación use la versión más reciente del Windows ADK.

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>Administrar direcciones MAC con adaptadores Ethernet extraíbles

Otra consideración para los administradores que Windows a través de la red es identificar equipos al usar el mismo adaptador Ethernet para implementar en más de un equipo. Un identificador común usado por las tecnologías de implementación es la dirección de control de acceso a medios (MAC) asociada a cada adaptador Ethernet. Sin embargo, cuando usa el mismo adaptador Ethernet para implementarlo en varios equipos, no puede usar una tecnología de implementación que inspeccione las direcciones MAC porque no hay forma de diferenciar la dirección MAC del adaptador extraíble cuando se usa en equipos diferentes.

La solución más sencilla para evitar conflictos de direcciones MAC es proporcionar un adaptador Ethernet extraíble exclusivo para cada dispositivo Surface. Esto puede tener sentido en muchos escenarios donde el adaptador Ethernet o la funcionalidad adicional de la estación de acoplamiento se usarán con frecuencia. Sin embargo, no todos los escenarios exigen la conectividad adicional de una estación de acoplamiento ni compatibilidad con redes cableadas.

Otra solución posible para evitar conflictos cuando se comparten adaptadores es usar [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) para realizar la implementación en dispositivos Surface. MDT no usa la dirección MAC para identificar equipos individuales y, por consiguiente, no está sujeta a esta limitación. Sin embargo, MDT usa Windows Deployment Services para proporcionar la funcionalidad de arranque PXE y está sujeta a las limitaciones relativas a los clientes preconfigurados, tal como se describe más adelante en esta sección.

Al usar un adaptador compartido para la implementación, la solución para las tecnologías de implementación afectadas es usar otros medios para identificar sistemas exclusivos. Para Configuration Manager y WDS, que pueden verse afectados por este problema, la solución es usar el identificador único universal del sistema (UUID del sistema) incrustado en el firmware del equipo por el fabricante del equipo. Para los dispositivos Surface, puedes ver esta entrada en el firmware del equipo en **Información del dispositivo**.

**Para obtener acceso al firmware de un dispositivo Surface:**

1. Asegúrate de que el dispositivo Surface esté apagado.
2. Mantén presionado el botón para **subir el volumen**.
3. Presiona y suelta el botón **inicio/apagado**.
4. Cuando la máquina comience a arrancar, suelta el **botón Subir** volumen.

Al implementar con WDS, la dirección MAC solo se usa para identificar un equipo cuando el servidor de implementación se configura para responder únicamente a los clientes conocidos preconfigurados. Al preconfigurar un cliente, un administrador crea una cuenta de equipo en Active Directory y define ese equipo por la dirección MAC o el UUID del sistema. Para evitar los conflictos de identidad provocados por adaptadores Ethernet compartidos, debes usar el [UUID del sistema para definir los clientes preconfigurados](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11)). 

Como alternativa, puede configurar WDS para responder a clientes desconocidos que no requieren definición por dirección MAC o UUID del sistema. Seleccione la **opción Responder a todos los equipos cliente (** conocidos y desconocidos) en la pestaña [**Respuesta PXE**](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) en **Windows del servidor de implementación**.

La posibilidad de que haya conflictos con adaptadores Ethernet compartidos es mucho más alta con Configuration Manager. Cuando WDS solo usa direcciones MAC para definir sistemas individuales, Configuration Manager usa la dirección MAC para definir sistemas independientes siempre que se implemente en equipos nuevos o desconocidos. Esto puede provocar la configuración incorrecta de dispositivos o incluso la imposibilidad de implementar más de un sistema con un adaptador Ethernet compartido. En How [to Use The Same External Ethernet Adapter for Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374) se describen varias soluciones potenciales para esta situación.

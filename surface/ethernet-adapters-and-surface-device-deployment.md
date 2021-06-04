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
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834706"
---
# Adaptadores ethernet e implementación Surface


En este artículo se proporcionan instrucciones y respuestas para ayudarle a realizar una implementación de red en dispositivos Surface, incluidos Surface Pro 3 y versiones posteriores.

La implementación de red en dispositivos Surface puede suponer algunos retos únicos para los administradores del sistema. Debido a la falta de un adaptador Ethernet nativo con cable, los administradores deben proporcionar conectividad a través de un adaptador Ethernet extraíble.

##  <a name="select-an-ethernet-adapter-for-surface-devices"></a>Seleccionar un adaptador Ethernet para dispositivos Surface


Antes de que puedas abordar los problemas de cómo arrancará en el entorno de implementación o cómo la solución de implementación reconocerá los dispositivos, tienes que usar un adaptador de red con cable.

La preocupación principal al seleccionar un adaptador Ethernet es cómo ese adaptador arrancará el dispositivo Surface desde la red. Si va a ensayar previamente los clientes con los servicios de implementación de Windows (WDS) o si usa Microsoft Endpoint Configuration Manager, también puede considerar si los adaptadores de Ethernet extraíbles se dedicarán a un dispositivo Surface específico o se compartirán entre varios dispositivos. Para obtener más información sobre posibles conflictos con los adaptadores compartidos, vea [administrar direcciones MAC con adaptadores Ethernet extraíbles](#manage-mac-addresses) más adelante en este artículo.

El arranque desde la red (arranque PXE) solo se admite cuando se usa un adaptador Ethernet o una estación de acoplamiento de Microsoft. Para arrancar desde la red, el conjunto de chips del adaptador Ethernet o de la estación debe detectarse y configurarse como dispositivo de arranque en el firmware del dispositivo Surface. Los adaptadores Ethernet de Microsoft, como el Adaptador Ethernet de Surface y la [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock), usan un conjunto de chips que es compatible con el firmware de Surface.

Los dispositivos Ethernet siguientes son compatibles con el arranque de red con dispositivos Surface:

-   Adaptador USB-C a Ethernet y USB 3,0

-   Adaptador USB 3,0 de Surface a Gigabit Ethernet

-   Surface Dock

-   Estación de acoplamiento de Surface 3

-   Estación de acoplamiento de Surface Pro 3

-   Estación de acoplamiento para Surface Pro y Surface Pro 2

También se admiten adaptadores Ethernet de terceros para la implementación de red, aunque no son compatibles con el arranque PXE. Para usar un adaptador Ethernet de terceros, debes cargar los controladores en la imagen de arranque de implementación y debe iniciar esa imagen de arranque desde un dispositivo de almacenamiento independiente, como un stick USB.

##  <a name="boot-surface-devices-from-the-network"></a>Arrancar dispositivos Surface desde la red

Para arrancar desde la red o un stick USB conectado, debes indicar al dispositivo Surface que arranque desde un dispositivo de arranque alternativo. Puedes modificar el orden de arranque en el firmware del sistema para dar prioridad a los dispositivos de arranque USB, o bien puede indicarle que arranque desde un dispositivo de arranque alternativo durante el proceso de arranque.

Para arrancar un dispositivo Surface desde un dispositivo de arranque alternativo, sigue estos pasos:

1.  Asegúrate de que el dispositivo Surface esté apagado.
2.  Mantén presionado el botón **Bajar el volumen**.
3.  Presiona y suelta el botón **inicio/apagado**.
4.  Una vez que el sistema comienza a arrancar desde el stick USB o adaptador Ethernet, suelta el botón **Bajar el volumen**.

>[!NOTE]
>Además de un adaptador Ethernet, también debes tener conectado un teclado al dispositivo Surface para tener acceso al entorno de preinstalación y navegar por el Asistente para la implementación.

 
Para Windows 10, versión 1511 y posteriores, incluido el Windows Assessment and Deployment Kit (Windows ADK) para Windows 10, versión 1511; los controladores para adaptadores Ethernet de Microsoft Surface están presentes de forma predeterminada. Si usas una solución de implementación que usa el Entorno de preinstalación de Windows (WinPE), como Microsoft Deployment Toolkit, y arrancas desde la red con PXE, asegúrate de que la solución de implementación use la versión más reciente de Windows ADK.

## <a href="" id="manage-mac-addresses"></a>Administrar direcciones MAC con adaptadores Ethernet extraíbles

Otra consideración que deben tener en cuenta los administradores que realicen la implementación de Windows a través de la red es cómo se identificarán los equipos cuando uses el mismo adaptador Ethernet para implementar en varios equipos. Un identificador común usado por las tecnologías de implementación es la dirección Media Access Control (MAC) que está asociada a cada adaptador Ethernet. Sin embargo, si usas el mismo adaptador Ethernet para la implementación en varios equipos, no puedes usar una tecnología de implementación que inspecciona las direcciones MAC, ya que no hay ninguna manera de diferenciar la dirección MAC del adaptador extraíble cuando se usa en distintos equipos.

La solución más sencilla para evitar conflictos de direcciones MAC es proporcionar un adaptador Ethernet extraíble exclusivo para cada dispositivo Surface. Esto puede tener sentido en muchos escenarios donde el adaptador Ethernet o la funcionalidad adicional de la estación de acoplamiento se usarán con frecuencia. Sin embargo, no todos los escenarios exigen la conectividad adicional de una estación de acoplamiento ni compatibilidad con redes cableadas.

Otra solución posible para evitar conflictos cuando se comparten adaptadores es usar [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) para realizar la implementación en dispositivos Surface. MDT no usa la dirección MAC para identificar equipos individuales y, por consiguiente, no está sujeta a esta limitación. Sin embargo, MDT usa los Servicios de implementación de Windows para proporcionar la funcionalidad de arranque PXE y está sujeta a las limitaciones relativas a los clientes preconfigurados que se trata más adelante en esta sección.

Al usar un adaptador compartido para la implementación, la solución para las tecnologías de implementación afectadas es usar otros medios para identificar sistemas exclusivos. Para Configuration Manager y WDS, que pueden verse afectados por este problema, la solución es usar el identificador único universal del sistema (UUID del sistema) que el fabricante del equipo integra en el firmware. Para los dispositivos Surface, puedes ver esta entrada en el firmware del equipo en **Información del dispositivo**.

Para tener acceso al firmware de un dispositivo Surface, sigue estos pasos:

1.  Asegúrate de que el dispositivo Surface esté apagado.
2.  Mantén presionado el botón para **subir el volumen**.
3.  Presiona y suelta el botón **inicio/apagado**.
4.  Una vez que el dispositivo comienza a arrancar, suelta el botón **Subir el volumen**.

Al implementar con WDS, la dirección MAC solo se usa para identificar un equipo cuando el servidor de implementación se configura para responder únicamente a los clientes conocidos preconfigurados. Al preconfigurar un cliente, un administrador crea una cuenta de equipo en Active Directory y define ese equipo por la dirección MAC o el UUID del sistema. Para evitar los conflictos de identidad provocados por adaptadores Ethernet compartidos, debes usar el [UUID del sistema para definir los clientes preconfigurados](https://technet.microsoft.com/library/cc742034). Como alternativa, puedes configurar WDS para responder a los clientes desconocidos que no requieren definición por dirección MAC ni por UUID del sistema; para ello, selecciona la opción **Responder a todos los equipos cliente (conocidos y desconocidos)** en la [**ficha Respuesta PXE**](https://technet.microsoft.com/library/cc732360) en **Propiedades del servidor de implementación de Windows**.

La posibilidad de que haya conflictos con adaptadores Ethernet compartidos es mucho más alta con Configuration Manager. Donde WDS solo usa direcciones MAC para definir sistemas individuales cuando se configura para ello, Configuration Manager usa la dirección MAC para definir sistemas individuales siempre que realiza una implementación en equipos nuevos o desconocidos. Esto puede provocar la configuración incorrecta de dispositivos o incluso la imposibilidad de implementar más de un sistema con un adaptador Ethernet compartido. Hay varias soluciones posibles para esta situación que se describen en detalle en [Cómo usar el mismo adaptador Ethernet externo para varias OSD de SCCM](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), una entrada de blog en la infraestructura básica y el blog de seguridad.

 

 






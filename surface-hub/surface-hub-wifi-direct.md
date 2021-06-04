---
title: Cómo gestiona Surface Hub los problemas de seguridad de Wi-Fi Direct
description: Orientación sobre los riesgos de seguridad de Wi-Fi Direct.
keywords: historial de cambios
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/27/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d877d9b6a4e330a74a9d79cf1150487d89c0da23
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835001"
---
# Cómo gestiona Surface Hub los problemas de seguridad de Wi-Fi Direct

Microsoft Surface Hub es un dispositivo de productividad todo en uno que permite a los equipos realizar una mejor lluvia de ideas, colaborar y compartir ideas. Surface Hub depende de Miracast para la proyección inalámbrica a través de Wi-Fi Direct.

En este artículo se describen las vulnerabilidades de seguridad de Wi-Fi Direct, cómo afronta Surface Hub esos riesgos y cómo los administradores pueden configurar Surface hub para obtener el mayor nivel de seguridad. Esta información ayudará a los clientes que tienen requisitos de alta seguridad a proteger sus redes conectadas en el Hub y los datos en tránsito.

Las audiencias previstas para este artículo son administradores de ti y de redes que desean implementar Surface Hub en su entorno corporativo con una configuración de seguridad óptima.

##  <a name="introduction"></a>Introducción

La seguridad de Surface Hub depende ampliamente de Wi-Fi Direct/Miracast y de los estándares asociados de 802,11, Wi-Fi Protected Access (WPA2) y de configuración protegida inalámbrica (WPS). Dado que el dispositivo solo es compatible con WPS (a diferencia de la clave previamente compartida de WPA2 o WPA2 Enterprise), los problemas que se suelen asociar con el cifrado de 802,11 se simplifican.

Surface Hub funciona de su equivalente con el campo de los receptores Miracast. Por lo tanto, es vulnerable a un conjunto similar de exploits que todos los dispositivos de red inalámbrica basados en WPS. Pero la implementación de Surface Hub de WPS tiene precauciones adicionales integradas. Además, su arquitectura interna ayuda a evitar que un atacante que ha puesto en peligro la capa Wi-Fi Direct o Miracast pase la interfaz de red a otras superficies de ataque y redes empresariales conectadas.

##  <a name="wi-fi-direct-background"></a>Wi-Fi Direct en segundo plano

Miracast forma parte del estándar de visualización de Wi-Fi, que es compatible con el protocolo Wi-Fi Direct. Estos estándares son compatibles con dispositivos móviles modernos para colaboración y uso compartido de pantalla.

Wi-Fi Direct o Wi-Fi "de par a par" (P2P) es un estándar de la Alianza Wi-Fi para redes "ad-hoc". Los dispositivos compatibles pueden comunicarse directamente y crear grupos de redes sin un punto de acceso o conexión a Internet convencional.

WPA2 proporciona seguridad para Wi-Fi Direct en el estándar WPS. El mecanismo de autenticación para dispositivos puede ser un PIN numérico (código PIN de WPS), un botón de inserción físico o virtual (WPS-PBC) o un mensaje fuera de banda, como una comunicación Near Field (WPS-OOO). Surface Hub admite el método de ANCLAr y el método pulsador, que es el predeterminado.

En Wi-Fi Direct, los grupos se crean como uno de los siguientes tipos:
- *Persistente*, en el que puede realizarse la reconexión automática mediante material de clave almacenado
- *Temporal*, en el que los dispositivos no pueden volver a autenticarse sin la acción del usuario

Los grupos de Wi-Fi Direct determinan el propietario de un *Grupo* (ir) a través de un protocolo de negociación, que imita la funcionalidad "estación" o "punto de acceso" para el grupo de Wi-Fi Direct establecido. Wi-Fi Direct GO proporciona autenticación (a través de un "registrador interno") y facilita la transmisión de conexiones de red. Para Surface Hub, la negociación de este GO no se produce. La red solo funciona en modo "autónomo" y Surface Hub siempre es el propietario del grupo. Por último, Surface Hub no se une a otras redes Wi-Fi Direct como cliente.

##  <a name="how-surface-hub-addresses-wi-fi-direct-vulnerabilities"></a>Cómo afronta Surface Hub las vulnerabilidades de Wi-Fi Direct

**Vulnerabilidades y ataques en las invitaciones directas, la difusión y el proceso de detección de Wi-Fi:** Los ataques de Wi-Fi Direct/Miracast pueden dirigirse a debilidades en el establecimiento de grupos, detección de elementos de mismo nivel, difusión de dispositivo o procesos de invitación.

|Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| El proceso de descubrimiento puede permanecer activo durante un período de tiempo prolongado, lo que puede permitir que se establezcan invitaciones y conexiones sin la aprobación del propietario del dispositivo. | Surface Hub solo funciona como propietario del grupo, que no realiza los procesos de negociación o descubrimiento de clientes. Puede desactivar completamente la proyección inalámbrica para desactivar la difusión. |
| Invitación y descubrimiento a través de PBC permite que un atacante no autenticado realice repetidos intentos de conexión o se acepten conexiones no autenticadas de forma automática. | Al requerir la seguridad del PIN de WPS, los administradores pueden reducir el potencial de conexiones no autorizadas o "bombas de invitación" en las que las invitaciones se envían repetidamente hasta que un usuario acepta por error. |

**Botón de comando de configuración de Wi-Fi Protected Setup (WPS) Connect (PBC) vs:** Se han demostrado puntos débiles públicos en el diseño y la implementación de métodos de WPS-PIN. WPS-PBC tiene otras vulnerabilidades que podrían permitir ataques activos contra un protocolo diseñado para un uso único.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| WPS-PBC es vulnerable a atacantes activos. La especificación de WPS dice: "el método PBC tiene cero bits de entropía y solo protege contra ataques de escucha pasiva. PBC protege contra los ataques de interceptación y toma medidas para evitar que un dispositivo se una a una red que no seleccionó el propietario del dispositivo. Sin embargo, la ausencia de autenticación significa que PBC no protege contra un ataque activo. " Los atacantes pueden usar una interconexión inalámbrica selectiva o cualquier otra técnica de denegación de servicio para desencadenar una conexión o un conexión Wi-Fi Direct o no deseada. Además, un atacante activo que simplemente tiene la proximidad física puede destruir varias veces cualquier grupo de Wi-Fi Direct e intentar el ataque hasta que se complete. | Habilitar la seguridad de PIN de WPS en la configuración de Surface Hub. La especificación WPS de Wi-Fi dice: "el método PBC solo se debe usar si no hay registrador con capacidad para PIN y el usuario de WLAN está dispuesto a aceptar los riesgos asociados con PBC". |
| Las implementaciones de PIN de WPS pueden estar sujetas a ataques de fuerza bruta que se destinan a una vulnerabilidad en el estándar de WPS. El diseño de la verificación de PATILLAs dividida condujo varias vulnerabilidades de implementación durante los últimos años en una variedad de fabricantes de hardware de Wi-Fi. En 2011, los investigadores Martín Viehböck y Craig Heffner publicaron información sobre esta vulnerabilidad y herramientas como "Reaver" como prueba de concepto. |   La implementación de Microsoft de WPS en Surface Hub cambia el PIN cada 30 segundos. Para descifrar el PIN, un atacante debe completar todo el exploit en menos de 30 segundos. Dado el estado actual de las herramientas y la investigación en esta área, es poco probable que un ataque de craqueo a PIN de fuerza bruta a través de WPS tenga éxito. |
| WPS-PIN se puede adivinar mediante un ataque sin conexión debido a una clave inicial débil (E-S1, E S2) entropía. En 2014, Dominique Bongard describía un ataque de "polvo Pixie" en el que la aleatoriedad inicial del generador de números pseudoaleatorios (PRNG) en el dispositivo inalámbrico permitía un ataque de fuerza bruta sin conexión. | La implementación de Microsoft de WPS en Surface Hub no es susceptible a este ataque de la fuerza bruta sin conexión. El PIN de WPS es aleatorio para cada conexión. |

**Exposición no deseada de servicios de red:** Los daemons de red pensados para los servicios de Ethernet o WLAN pueden exponerse accidentalmente debido a un error de configuración (como el enlace a interfaces "todas"/0.0.0.0). Otras causas posibles son que el firewall del dispositivo esté mal configurado o que falten reglas de Firewall.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Un error de configuración enlaza un servicio de red no autenticado o vulnerable a interfaces "all", incluida la interfaz de Wi-Fi Direct. Esto puede exponer servicios que no deberían ser accesibles para clientes de Wi-Fi Direct, que pueden autenticarse de manera débil o automática. | En Surface Hub, las reglas de Firewall predeterminadas solo permiten los puertos de red TCP y UDP requeridos y deniegan de forma predeterminada todas las conexiones entrantes. Habilite el modo de PIN de WPS para configurar la autenticación robusta.|

**Puentes de Wi-Fi Direct y otras redes cableadas o inalámbricas:** El puente de red entre redes WLAN o Ethernet es una violación de la especificación Wi-Fi Direct. Un puente o una configuración no recomendable puede reducir o quitar de forma eficaz los controles de acceso inalámbrico para la red corporativa interna.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Los dispositivos de Wi-Fi Direct podrían permitir acceso no autenticado o deficiente para las conexiones de red conectadas. Esto podría permitir que las redes Wi-Fi Direct enruten el tráfico a una LAN Ethernet interna u otra infraestructura o a redes WLAN de la empresa infringiendo los protocolos de seguridad de TI existentes. | Surface Hub no se puede configurar para enlazar interfaces inalámbricas o permitir el enrutamiento entre redes dispares. Las reglas de firewall predeterminadas agregan una defensa más profunda para este tipo de conexiones de enrutamiento o puente. |

**El uso del modo Wi-Fi Direct "heredado":** La exposición a redes o dispositivos no deseados puede producirse cuando opera en modo "heredado". Si no está habilitado el PIN de WPS, se podrían producir conexiones no intencionadas o suplantación de identidades del dispositivo.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Al ser compatible con los clientes de infraestructura 802.11 y Wi-Fi Direct, el sistema funciona en un modo de compatibilidad "heredado". Esto puede exponer la fase de configuración de la conexión de forma indefinida, lo que permite que los grupos se unan o los dispositivos invitados a conectarse correctamente después de finalizar la fase de configuración previstas. |    Surface Hub no es compatible con clientes heredados de Wi-Fi Direct. Solo se pueden realizar conexiones de Wi-Fi Direct a Surface Hub, incluso cuando el modo PIN de WPS está habilitado. |

**Negociación de Wi-Fi Direct go durante la configuración de la conexión:** El propietario del grupo en Wi-Fi Direct es análogo al "punto de acceso" en una red inalámbrica de 802,11 convencionales. Un dispositivo malintencionado puede sortear la negociación.

|Vulnerabilidad de Wi-Fi Direct |   Mitigación del Surface Hub |
| --- | --- |
| Si se establecen dinámicamente grupos o se puede hacer que el dispositivo Wi-Fi Direct se unan a grupos nuevos, la negociación de propietarios del grupo puede hacerse con un dispositivo malintencionado que siempre especifica el valor máximo de 15 como propietario del grupo. (Pero se produce un error en la conexión si el dispositivo está configurado para ser siempre un propietario del grupo).  | Surface Hub aprovecha el modo autónomo "Wi-Fi Direct", que omite la fase de negociación GO de configuración de conexión. Y Surface Hub siempre es el propietario del grupo. |

**Desautenticación de Wi-Fi inesperada o malintencionada:** La desautenticación Wi-Fi es un ataque antiguo en el que un atacante local puede acelerar la pérdida de información en el proceso de configuración de la conexión, desencadenar nuevos protocolos de enlace de cuatro vías, dirigirse a una versión de Wi-Fi Direct-PBC para ataques activos o crear ataques de denegación de servicio.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Los atacantes no autenticados pueden enviar paquetes de deautenticación para hacer que la estación se vuelva a autenticar y rastrear el protocolo de enlace resultante. Pueden intentarse ataque criptográfico o de fuerza bruta en el protocolo de enlace resultante. La mitigación de estos ataques incluye la aplicación de directivas de longitud y complejidad para las claves previamente compartidas, la configuración del punto de acceso (si procede) para detectar niveles malintencionados de paquetes de desautenticación y el uso de WPS para generar automáticamente claves seguras. En el modo PBC, el usuario interactúa con un botón físico o virtual para permitir una asociación de dispositivo arbitraria. Este proceso solo debe realizarse durante la configuración, en un breve lapso de tiempo. Después de insertar el botón automáticamente, el dispositivo aceptará cualquier estación que se asocie a un valor de PIN canónico (todos los ceros). La desautenticación puede forzar un proceso de instalación repetido. |   Surface Hub usa WPS en modo PIN o PBC. No se permite ninguna configuración de PSK. Este método ayuda a exigir la generación de claves sólidas. Lo mejor es habilitar la seguridad de PIN de WPS para Surface Hub. |
| Además de los ataques de denegación de servicio, los paquetes de desautenticación se pueden usar para desencadenar una reconexión que vuelva a abrir la ventana de oportunidad de ataques activos contra WPS-PBC. |   Habilitar la seguridad de PIN de WPS en la configuración de Surface Hub. |

**Revelación de información inalámbrica básica:** Las redes inalámbricas, 802,11 o de otro modo, son inherentes al riesgo de revelación de información. Aunque esta información es principalmente metadatos de conexión o dispositivo, este problema sigue siendo un riesgo conocido para cualquier administrador de red de 802,11. Wi-Fi Direct con autenticación de dispositivos a través de PIN de WPS revela eficazmente la misma información como una red PSK o Enterprise 802.11

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Durante la difusión, la configuración de la conexión o incluso el funcionamiento normal de las conexiones ya cifradas, la información básica sobre los dispositivos y los tamaños de los paquetes es transmitida de manera inalámbrica. En un nivel básico, un atacante local que se encuentra dentro del rango inalámbrico puede examinar los elementos de información de 802,11 pertinentes para determinar los nombres de los dispositivos inalámbricos, las direcciones MAC de los equipos de comunicación y posiblemente otros detalles, como la versión de la pila inalámbrica, los tamaños de paquete o las opciones del punto de acceso configurado o el propietario del grupo.  | La red Wi-Fi Direct que usa Surface Hub no puede protegerse aún más de las pérdidas de metadatos, como las de 802,11 Enterprise o PSK Wireless. La seguridad física y la eliminación de las amenazas potenciales de la proximidad inalámbrica pueden ayudar a reducir las fugas potenciales en información. |

**Ataques inalámbricos de gemelas o de suplantación:**  La suplantación de nombre inalámbrico es un ataque sencillo y muy conocido que puede usar un atacante local para atraer a usuarios insospechados o malintencionados para que se conecten.

| Vulnerabilidad de Wi-Fi Direct | Mitigación del Surface Hub |
| --- | --- |
| Al imitar o clonar el nombre inalámbrico o el "SSID" de la red de destino, un atacante puede engañar al usuario para que se conecte a una red falsa y malintencionada. Al permitir la combinación automática de Miracast sin autenticar, un atacante podría capturar los materiales de visualización previstos o lanzar ataques de red en el dispositivo de conexión. | Aunque no existen protecciones específicas contra la Unión a un Surface Hub imitado, esta vulnerabilidad se ha mitigado parcialmente de dos maneras. En primer lugar, cualquier potencial ataque debe producirse físicamente dentro del alcance Wi-Fi. En segundo lugar, este ataque solo es posible durante la primera conexión. Las conexiones posteriores usan un grupo de Wi-Fi Direct persistente y Windows recordará y establecerá la prioridad de esta conexión anterior durante el uso del concentrador. (Nota: no se consideró la suplantación de la dirección MAC, el canal Wi-Fi y el SSID al mismo tiempo para este informe y esto puede dar lugar a un comportamiento de Wi-Fi incoherente). En general, este punto débil es un problema fundamental para cualquier red inalámbrica de 802,11 que carezca de protocolos de WPA2 empresarial como EAP-TLS o EAP-PWD, que no es compatible con Wi-Fi Direct. |

##  <a name="surface-hub-hardening-guidelines"></a>Directrices de refuerzo de Surface Hub

Surface Hub está diseñado para facilitar la colaboración y permitir que los usuarios puedan iniciar o unirse a reuniones de una manera rápida y eficaz. La configuración predeterminada de Wi-Fi Direct para Surface Hub está optimizada para este escenario.

Para la seguridad de interfaz inalámbrica adicional, los usuarios de Surface Hub deben habilitar la configuración de seguridad de WPS-PIN. Esta opción deshabilita el modo WPS-PBC y ofrece autenticación de cliente. Proporciona el nivel de protección más potente evitando la conexión no autorizada a Surface Hub.

Si aún tienes dudas sobre la autenticación y la autorización de Surface Hub, te recomendamos que conectes el dispositivo a una red independiente. Puede usar Wi-Fi (como una red Wi-Fi "de invitado") o una red Ethernet independiente, preferiblemente una red física totalmente diferente. Pero una VLAN también puede proporcionar seguridad adicional. Por supuesto, este enfoque puede impedir las conexiones a los recursos o servicios de la red interna y puede requerir una configuración de red adicional para recuperar el acceso.

También se recomienda:
- [Instalar actualizaciones normales del sistema](manage-windows-updates-for-surface-hub.md) 
- Actualizar la configuración de Miracast para deshabilitar el modo de presentación automática

##  <a name="learn-more"></a>Más información

- [Especificaciones de Wi-Fi Direct](http://www.wi-fi.org/discover-wi-fi/wi-fi-direct)
- [Especificación de Wireless Protected Setup (WPS)](http://www.wi-fi.org/discover-wi-fi/wi-fi-protected-setup)




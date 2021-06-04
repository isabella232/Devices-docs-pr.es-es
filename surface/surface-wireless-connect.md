---
title: Optimizar la conectividad Wi-Fi para dispositivos Surface
description: En este tema se describe la configuración Wi-Fi para garantizar que los dispositivos Surface permanezcan conectados en entornos de red congestionados y escenarios móviles.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271384"
---
# Optimizar la conectividad Wi-Fi para dispositivos Surface


Para mantener la conexión con la duración de la batería de todo el día, los dispositivos Surface implementan configuraciones de conectividad inalámbrica que equilibra el rendimiento y la alimentación. Fuera de los escenarios de movilidad más exigentes, los usuarios pueden mantener suficiente conectividad inalámbrica sin modificar el adaptador de red predeterminado o la configuración relacionada. Esta página resalta las consideraciones clave de conectividad inalámbrica en escenarios móviles con los dispositivos Surface más recientes, como Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3 y Surface Pro 7.

##  <a name="prerequisites"></a>Requisitos previos

En este documento se supone que has implementado correctamente una red inalámbrica compatible con 802.11n (Wi-Fi 4) o posterior de acuerdo con las recomendaciones de prácticas recomendadas de los principales proveedores de equipos.

##  <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>Configuración de puntos de acceso para unas capacidades de movilidad óptimas

Si administras una red inalámbrica a la que normalmente acceden muchos tipos diferentes de dispositivos cliente, se recomienda habilitar protocolos específicos en puntos de acceso (PUNTOS de acceso) en tu WLAN, como se describe en [Fast Roaming con 802.11k, 802.11v y 802.11r.](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r) Los dispositivos Surface pueden aprovechar los siguientes protocolos inalámbricos:

- **802.11r.** "Transición rápida de**BSS"** acelera la conexión a nuevos puntos de acceso inalámbrico reduciendo el número de fotogramas necesarios para que el dispositivo pueda acceder a otra AP a medida que se mueve con el dispositivo. En la nueva generación de dispositivos Surface publicada desde 2019, los usuarios finales pueden obtener acceso a la configuración de agresividad de movilidad en su dispositivo. Aunque no se recomienda modificar la configuración predeterminada, los usuarios deben tener en cuenta esta funcionalidad y comprender cómo la configuración específica puede afectar a su capacidad para permanecer conectado.
- **802,11k.** **"Informes de vecinos"** proporciona a los dispositivos información sobre las condiciones actuales en los puntos de acceso vecinos. Puede ayudar a tu dispositivo Surface a elegir el mejor AP con criterios distintos de la intensidad de señal, como el uso de AP.

Los dispositivos Surface específicos también pueden usar "Fotogramas de administración de transición BSS" de 802.11v, que funciona de forma muy parecido a 802.11k para proporcionar información sobre los ap candidatos cercanos. Estos incluyen Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X y Surface Laptop 3. 

##  <a name="managing-user-settings"></a>Administración de la configuración de usuario

Puedes lograr capacidades de movilidad óptimas a través de una red bien diseñada que admite 802.11r y 802.11k en todos los puntos de acceso. Asegurarse de que la red está configurada correctamente para proporcionar a los usuarios la mejor experiencia inalámbrica es el enfoque recomendado frente a intentar administrar la configuración de usuario en dispositivos individuales. 

###  <a name="recommended-user-settings-and-best-practices"></a>Configuración de usuario recomendada y procedimientos recomendados

En determinadas situaciones, la modificación de la configuración avanzada del adaptador de red integrada en dispositivos Surface puede facilitar una conexión más confiable. No obstante, tenga en cuenta que la incapacidad de conectarse a recursos inalámbricos suele deberse a un problema de punto de acceso, un error de diseño de red o un problema del sitio del entorno.

> [!NOTE]
> La forma en que mantienes Surface Pro o Surface Go también puede afectar a la intensidad de la señal. Si está experimentando una pérdida de ancho de banda, compruebe que no está manteniendo la parte superior de la pantalla, donde se encuentra el receptor de Wi-Fi de radio. Aunque mantener la parte superior de la pantalla no bloquea las señales inalámbricas, puede desencadenar que el controlador del dispositivo inicie cambios que reduzcan la conectividad.

###  <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>Mantener la configuración predeterminada de Auto para la funcionalidad de ancho de banda dual

En la mayoría de los dispositivos Surface, puedes configurar las opciones del adaptador de red de cliente para que solo se conecten a puntos de acceso inalámbricos a más de 5 gigahercios (GHz), solo conectarse a más de 2,4 GHz o permitir que el sistema operativo elija la mejor opción (configuración automática predeterminada).

**Para acceder a la configuración del adaptador de red, vaya a:**

- **Inicio**  >  **Panel de control**  >  **Centro de redes y uso compartido**  >  **su Wi-Fi de datos**  >  **Propiedades**  >  **Configurar**  >  **Avanzadas.**

![* wifi-band settings*](images/wifi-band.png) <br>

Tenga en cuenta que 2,4 GHz tiene algunas ventajas sobre 5 GHz: se extiende aún más y penetra más fácilmente a través de las paredes u otros objetos sólidos. A menos que tenga un caso de uso claro que indique que se conecta a 5 GHz, se recomienda dejar la configuración de banda en el estado predeterminado para evitar posibles consecuencias negativas. Por ejemplo:


- Muchas zonas de acceso que se encuentran en restaurantes, cafeterías y aeropuertos siguen utilizando solo 2,4 GHz, lo que bloquea de forma eficaz el acceso a los dispositivos si La banda está establecida en 5 GHz únicamente.
- Dado que las conexiones de pantalla inalámbrica de Miracast requieren que el protocolo de enlace inicial se complete en canales de 2,4 GHz, los dispositivos no podrán conectarse solo a 5 GHz.

> [!NOTE]
> De forma predeterminada, los dispositivos Surface prefieren conectarse a 5 GHz si están disponibles. Sin embargo, para conservar la energía en un estado de batería bajo, Surface buscará primero una conexión de 2,4 GHz.

También puede alternar la configuración de banda según sea necesario para adaptarse a su entorno. Por ejemplo, los usuarios que viven en edificios de departamentos de alta densidad con varias zonas de acceso Wi-Fi (evitar la presencia de dispositivos de consumo en todas las transmisiones a través de 2,4 GHz) probablemente se beneficiarán configurando su dispositivo Surface para conectarse solo a 5 GHz y, a continuación, revertir a Auto cuando sea necesario.

###  <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>Configuración de agresividad de movilidad en dispositivos Surface con adaptadores Intel 

Es posible que los usuarios deseen seleccionar un umbral de intensidad de señal que pida al dispositivo que busque un nuevo punto de acceso cuando la señal caiga (agresividad de movilidad). De manera predeterminada, los dispositivos Surface con adaptadores Intel intentan tracción a un nuevo punto de acceso si la intensidad de la señal cae por debajo de **Medium** (72 por ciento de intensidad de señal). Ten en cuenta también que las organizaciones pueden implementar protocolos inalámbricos creados a propósito en varios puntos de acceso de red para facilitar la movilidad de entornos de red congestionados, como se explicó anteriormente en esta página. 

Aunque el aumento de **** la agresividad de movilidad por encima del medio puede producir una conectividad mejorada en entornos de oficina o de oficinas muy congestionados, puede provocar una conectividad degradada al salir de estos entornos. 

Se recomienda dejar la configuración de agresividad de movilidad en el estado predeterminado a menos que encuentre problemas de conectividad en escenarios móviles específicos, como la realización de inspecciones de sitios del entorno y, al mismo tiempo, mantener la conectividad de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al estado medio predeterminado. Ten en cuenta que si aumentas la agresividad de movilidad, también aceleras el consumo de energía de la batería. 

**Para habilitar la agresividad de movilidad en Surface:**

1. Ve a **Inicio del Administrador**de  >  **dispositivos.**
2. En **Adaptadores de** red, **seleccione Intel Wi-Fi 6** y, a continuación, haga clic con el botón secundario en **Propiedades.**
3. Seleccione la **pestaña** Avanzadas.
4. Selecciona **Agresividad de movilidad** y elige tu valor preferido en el menú desplegable.

![* Configuración de agresividad de movilidad-Intel *](images/wifi-roaming-int.png) <br>

###  <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Configuración de agresividad de movilidad en Surface Go y Surface Pro X

Es posible que los trabajadores de primera línea que usan Surface Go deseen seleccionar un umbral de intensidad de señal que pida al dispositivo que busque un nuevo punto de acceso cuando la intensidad de señal disminuye (agresividad de movilidad). De forma predeterminada, los dispositivos Surface intentan llegar a un nuevo punto de acceso si la intensidad de la señal cae por debajo de **Medium** (50 por ciento de intensidad de señal). Ten en cuenta que siempre que aumentas la agresividad de movilidad, aceleras el consumo de energía de la batería.

Deje la configuración de agresividad de movilidad en el estado predeterminado a menos que encuentre problemas de conectividad en escenarios móviles específicos, como realizar inspecciones de sitios del entorno y mantener la conectividad de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al **estado medio** predeterminado.

**Para habilitar la agresividad de movilidad en Surface Go:**

1. Vaya a **Inicio > red del Panel de control**y el Centro  >  **de**redes y uso compartido de  >  **Internet.**
2. En **Conexiones,** **seleccione Wi-Fi** y, a continuación, **seleccione Propiedades.**
3. Seleccione **Cliente para redes Microsoft y,** a continuación, seleccione **Configurar**
4. Selecciona ****  >  **Agresividad de movilidad avanzada** y elige tu valor preferido en el menú desplegable.

![* Configuración de agresividad de movilidad-QualComm *](images/wifi-roaming.png) <br>


##  <a name="conclusion"></a>Conclusión

Los dispositivos Surface están diseñados con la configuración predeterminada para una conectividad inalámbrica óptima equilibrada junto con la necesidad de conservar la duración de la batería. La forma más eficaz de habilitar una conectividad confiable para dispositivos Surface es a través de una red bien diseñada que admite 802.11r y 802.11k. Los usuarios pueden ajustar la configuración del adaptador de red o la agresividad de movilidad, pero solo deben hacerlo en respuesta a factores específicos del entorno y volver al estado predeterminado si no hay ninguna mejora notable.

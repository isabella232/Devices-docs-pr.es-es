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
ms.date: 11/30/2021
ms.openlocfilehash: e031b485979b20d6206398840466d553772b6f1d
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338253"
---
# <a name="optimize-wi-fi-connectivity-on-surface-devices"></a>Optimizar Wi-Fi conectividad en dispositivos Surface

Para mantener la conexión con la duración de la batería durante todo el día, los dispositivos Surface implementan configuraciones de conectividad inalámbrica que equilibran el rendimiento y la conservación de la energía. Fuera de las cargas de trabajo de movilidad más exigentes, los usuarios pueden mantener una conectividad inalámbrica suficiente sin modificar el adaptador de red predeterminado o la configuración relacionada. En esta página se destacan las consideraciones clave de conectividad inalámbrica en escenarios móviles con dispositivos Surface.

## <a name="prerequisites"></a>Requisitos previos

En este documento se supone que ha implementado correctamente una red inalámbrica compatible con 802.11n (Wi-Fi 4) o posterior siguiendo las recomendaciones de prácticas recomendadas de los principales proveedores de equipamiento.

## <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>Configuración de puntos de acceso para funcionalidades óptimas de movilidad

Supongamos que administra una red inalámbrica a la que suelen tener acceso muchos tipos diferentes de dispositivos cliente. En ese caso, se recomienda habilitar protocolos específicos en puntos de acceso (AP) en su WLAN, como se describe en [Fast Roaming with 802.11k, 802.11v y 802.11r](/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Los dispositivos Surface pueden aprovechar los siguientes protocolos inalámbricos:

- **802.11r.** "**Transición rápida de BSS"** acelera la conexión a nuevos puntos de acceso inalámbrico al reducir el número de fotogramas necesarios para que el dispositivo pueda acceder a otra AP a medida que se mueve con el dispositivo. En la nueva generación de dispositivos Surface lanzados desde 2019, los usuarios finales pueden tener acceso a la configuración de agresividad móvil en su dispositivo. Aunque no se recomienda modificar la configuración predeterminada, los usuarios deben ser conscientes de esta funcionalidad y comprender cómo la configuración específica puede afectar a su capacidad para permanecer conectado.
- **802.11k.** **"Informes de vecinos"** proporciona a los dispositivos información sobre las condiciones actuales en los puntos de acceso vecinos. Puede ayudar a tu dispositivo Surface a elegir el mejor DISPOSITIVO AP con criterios distintos de la intensidad de la señal, como el uso de AP.

Los dispositivos Surface específicos también pueden usar 802.11v "Fotogramas de administración de transición de BSS", que funciona de forma muy parecido a 802.11k al proporcionar información sobre los AP candidatos cercanos. Estos incluyen Surface Pro 8, Surface Pro 7+, Surface Laptop Studio, Surface Go 3, Surface Go 2, Surface Go, Surface Pro 7, Surface Pro X y Surface Laptop 3.

## <a name="managing-user-settings"></a>Administración de la configuración de usuario

Puede lograr capacidades óptimas de movilidad a través de una red bien diseñada que admite 802.11r y 802.11k en todos los puntos de acceso. Asegurarse de que la red está configurada correctamente para proporcionar a los usuarios la mejor experiencia inalámbrica es el enfoque recomendado frente a la administración de la configuración de usuario en dispositivos individuales.

### <a name="recommended-user-settings-and-best-practices"></a>Configuración de usuario recomendada y procedimientos recomendados

En determinadas situaciones, modificar la configuración avanzada del adaptador de red integrada en dispositivos Surface puede facilitar una conexión más confiable. Sin embargo, tenga en cuenta que la incapacidad para conectarse a recursos inalámbricos se debe con más frecuencia a un problema de punto de acceso, un defecto de diseño de red o un problema de sitio ambiental.

> [!TIP]
> La forma en que mantienes la Surface Pro o Surface Go también puede afectar a la intensidad de la señal. Si está experimentando una pérdida de ancho de banda, compruebe que no está manteniendo la parte superior de la pantalla, donde se encuentra el receptor Wi-Fi de radio. Aunque mantener la parte superior de la pantalla no bloquea las señales inalámbricas, puede desencadenar el controlador del dispositivo para iniciar cambios que reduzcan la conectividad.

### <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>Mantener la configuración automática predeterminada para la funcionalidad de ancho de banda dual

En la mayoría de los dispositivos Surface, puedes configurar la configuración del adaptador de red cliente para que solo se conecte a ap inalámbricos de más de 5 gigahercios (GHz), solo conectarse a más de 2,4 GHz o permitir que el sistema operativo elija la mejor opción (configuración predeterminada de Auto).

**Para obtener acceso a la configuración del adaptador de red, vaya a:**

- **Inicio** >  **Panel de control** >  **Centro de red y uso compartido** >  **su Wi-Fi de Wi-Fi de datos** >  **Propiedades** >  **Configurar** >  **Avanzado**.

![* configuración de banda wifi*.](images/wifi-band.png) <br>

Tenga en cuenta que 2,4 GHz tiene algunas ventajas sobre 5 GHz: se extiende más lejos y penetra más fácilmente a través de las paredes u otros objetos sólidos. A menos que tenga un caso de uso claro que amerite la conexión a 5 GHz, se recomienda dejar la configuración banda en el estado predeterminado para evitar posibles consecuencias negativas. Por ejemplo:

- Muchos puntos de acceso que se encuentran en los hoteles, cafeterías y aeropuertos todavía solo usan 2,4 GHz, lo que bloquea eficazmente el acceso a los dispositivos si Band está establecido en 5 GHz solo.
- Dado que Miracast conexiones de pantalla inalámbrica requieren que el protocolo de enlace inicial se complete a través de canales de 2,4 GHz, los dispositivos no podrán conectarse solo a 5 GHz.

> [!NOTE]
> De forma predeterminada, los dispositivos Surface prefieren conectarse a 5 GHz si están disponibles. Sin embargo, Surface buscará primero una conexión de 2,4 GHz para conservar la energía en un estado de batería baja.

También puede alternar la configuración de banda según sea necesario para adaptarse a su entorno. Por ejemplo, los usuarios que viven en edificios de departamentos de alta densidad con varios puntos de acceso Wi-Fi (en medio de la presencia de dispositivos de consumo que emiten a través de 2,4 GHz) probablemente se beneficiarán al establecer su dispositivo Surface para conectarse solo a 5 GHz y, a continuación, revertir a Auto cuando sea necesario.

### <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>Configuración de agresividad móvil en dispositivos Surface con adaptadores Intel

Es posible que los usuarios deseen seleccionar un umbral de intensidad de señal que pida al dispositivo que busque un nuevo punto de acceso cuando la señal caiga (agresividad itinerante). De forma predeterminada, los dispositivos Surface con adaptadores Intel intentan recorrer un nuevo punto de acceso si la intensidad de la señal cae por debajo de **Medium** (72 por ciento de intensidad de señal). Las organizaciones también pueden implementar protocolos inalámbricos específicos en varios puntos de acceso a la red para facilitar la movilidad de entornos de red congestionados, como se explicó anteriormente en esta página.

Aunque aumentar la agresividad de movilidad por encima de **Medium** puede producir una conectividad mejorada en entornos residenciales o de oficina altamente congestionados, puede provocar una conectividad degradada al salir de estos entornos.

Deje la configuración de agresividad de movilidad en el estado predeterminado a menos que encuentre problemas de conectividad en escenarios móviles específicos, como la realización de inspecciones de sitios ambientales mientras mantiene la conectividad de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al estado medio predeterminado. Ten en cuenta que si aumentas la agresividad de movilidad, también aceleras el consumo de energía de la batería.

**Para habilitar la agresividad de movilidad en Surface:**

1. Vaya a **StartDevice** >  **Manager**.
2. En **Adaptadores de** red, **seleccione Intel Wi-Fi 6** y, a continuación, haga clic con el botón **secundario en Propiedades**.
3. Seleccione la **pestaña** Avanzadas.
4. Selecciona **Agresividad móvil** y elige el valor que prefieras en el menú desplegable.

![* Configuración de agresividad de movilidad-Intel *.](images/wifi-roaming-int.png) <br>

### <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Configuración de agresividad móvil en Surface Go y Surface Pro X

Es posible que los trabajadores de línea frontal que usan Surface Go deseen seleccionar un umbral de intensidad de señal que pida al dispositivo que busque un nuevo punto de acceso cuando la intensidad de la señal disminuye (agresividad de movilidad). De forma predeterminada, los dispositivos Surface intentan recorrer un nuevo punto de acceso si la intensidad de la señal cae por debajo de **Medium** (50 por ciento de intensidad de la señal). Ten en cuenta que cada vez que aumentas la agresividad de movilidad, aceleras el consumo de energía de la batería.

Deje la configuración de agresividad de movilidad en el estado predeterminado a menos que encuentre problemas de conectividad en escenarios móviles específicos, como la realización de inspecciones de sitios ambientales mientras mantiene la conectividad de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al estado **medio** predeterminado.

**Para habilitar la agresividad móvil en Surface Go:**

1. Vaya a **Inicio > Panel de controlNetwork** >  **e InternetNetwork** >  **y centro de uso compartido.**
2. En **Conexiones**, **seleccione Wi-Fi** y, a continuación, elija **Propiedades.**
3. Seleccione **Cliente para Microsoft Networks** y, a continuación, **seleccione Configurar**
4. Selecciona **AdvancedRoaming** >  **Aggressiveness** y elige tu valor preferido en el menú desplegable.

![* Configuración de agresividad de movilidad-QualComm *.](images/wifi-roaming.png) <br>

## <a name="conclusion"></a>Conclusión

Los dispositivos Surface están diseñados con la configuración predeterminada para una conectividad inalámbrica óptima equilibrada junto con la necesidad de conservar la duración de la batería. La forma más eficaz de habilitar una conectividad confiable para dispositivos Surface es a través de una red bien diseñada que admite 802.11r y 802.11k. Los usuarios pueden ajustar la configuración del adaptador de red o la agresividad de movilidad, pero solo deben hacerlo en respuesta a factores de entorno específicos y revertir al estado predeterminado si no hay ninguna mejora notable.

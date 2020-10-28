---
title: Optimizar la conectividad Wi-Fi para dispositivos Surface
description: En este tema se describe la configuración recomendada de Wi-Fi para garantizar que los dispositivos Surface permanezcan conectados en entornos de red y escenarios móviles congestionados.
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
ms.date: 10/26/2020
ms.openlocfilehash: d211ceea20b89824d45e433cf9670abe137130a0
ms.sourcegitcommit: 07ac65bf70c8c6efcda28eecc3013983fc386e0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136154"
---
# Optimizar la conectividad Wi-Fi para dispositivos Surface


Para mantenerse conectado con la vida útil de la batería de todo el día, los dispositivos de Surface implementan configuración de conectividad inalámbrica que equilibra el rendimiento y el ahorro de energía. Fuera de los escenarios de movilidad más exigentes, los usuarios pueden mantener la conectividad inalámbrica suficiente sin modificar el adaptador de red predeterminado ni la configuración relacionada. Esta página resume consideraciones clave sobre la conectividad inalámbrica en escenarios móviles con los últimos dispositivos de Surface, incluidos Surface Pro 7, Surface Pro X, Surface Laptop 3, Surface Book 3, Surface Go 2 y Surface Laptop go.  

## Requisitos previos

En este documento se supone que ha implementado correctamente una red inalámbrica compatible con 802.11 n (Wi-Fi 4) o posterior según las recomendaciones de prácticas recomendadas de los principales proveedores de equipos.

## Configuración de puntos de acceso para capacidades de itinerancia óptimas

Si está administrando una red inalámbrica a la que acceden muchos tipos diferentes de dispositivos cliente, se recomienda habilitar protocolos específicos en puntos de acceso (AP) en la WLAN, como se describe en [movilidad rápida con 802.11 k, 802.11 v y 802.11 r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r). Los dispositivos Surface pueden aprovecharse de los siguientes protocolos inalámbricos:

- **802.11 r.** "**Transición rápida de BSS"** acelera la conexión a nuevos puntos de acceso inalámbricos reduciendo la cantidad de tramas necesarias antes de que el dispositivo pueda acceder a otro punto de acceso mientras se desplaza con el dispositivo. En la nueva generación de dispositivos Surface lanzados desde 2019, los usuarios finales pueden obtener acceso a la configuración de agresividad de itinerancia de su dispositivo. Aunque no es recomendable modificar la configuración predeterminada, los usuarios deben ser conscientes de esta capacidad y comprender cómo la configuración específica puede influir en su capacidad para permanecer conectada.
- **802.11 k.** **"Informes de vecinos"** proporciona a los dispositivos información sobre las condiciones actuales en puntos de acceso vecinos. Puede ayudar a su dispositivo Surface a elegir el mejor PA con criterios que no sean la intensidad de la señal, como la utilización de AP.

Los dispositivos de superficie específicos pueden usar también los "Marcos de administración de transición de BSS" 802.11, que funcionan de manera muy similar a 802.11 k al proporcionar información sobre AP candidatos cercanos. Esto incluye Surface Go, Surface Pro 7, Surface Pro X y Surface Laptop 3. 

## Administrar la configuración de usuario

Puede lograr capacidades de itinerancia óptimas a través de una red bien diseñada que admita 802.11 r y 802.11 k en todos los puntos de acceso. Asegurarse de que su red está configurada correctamente para proporcionar a los usuarios la mejor experiencia inalámbrica es el enfoque recomendado en lugar de tratar de administrar la configuración de usuario en dispositivos individuales. 

### Procedimientos recomendados y la configuración de usuario recomendada

En determinadas situaciones, la modificación de la configuración avanzada del adaptador de red integrada en dispositivos Surface puede facilitar una conexión más confiable. No obstante, tenga en cuenta que la incapacidad de conectarse a los recursos inalámbricos suele deberse a un problema de punto de acceso, un error de diseño de red o un problema del sitio del entorno.

> [!NOTE]
> La forma de mantener la superficie de Surface Pro o Surface puede afectar también la intensidad de la señal. Si experimentas una pérdida de ancho de banda, verifica que no estés en la parte superior de la pantalla, donde se encuentra el receptor de radio Wi-Fi. Aunque mantener la parte superior de la pantalla no bloquea las señales inalámbricas, puede desencadenar que el controlador de dispositivo inicie cambios que reduzcan la conectividad.

### Mantener la configuración automática predeterminada para la función de ancho de banda doble

En la mayoría de los dispositivos de la superficie, puede configurar los parámetros del adaptador de red del cliente para que solo se conecten a los puntos de conexión inalámbricos a través de 5 gigahercios (GHz), solo se conecten a 2,4 GHz o que el sistema operativo elija la mejor opción (configuración automática predeterminada).

**Para obtener acceso a la configuración del adaptador de red, vaya a:**

- **Iniciar**  >  **Panel**  >  de control Centro de redes **y recursos compartidos**  >  **su adaptador**  >  de Wi-Fi **Propiedades**  >  **Configurar**  >  **Avanzado**.

![* configuración de banda wifi *](images/wifi-band.png) <br>

Tenga en cuenta que 2,4 GHz tiene algunas ventajas más de 5 GHz: extiende más y más fácilmente los penetrantes con paredes u otros objetos sólidos. A menos que tenga un caso de uso claro que garantice la conexión a 5 GHz, se recomienda que deje la configuración de banda en el estado predeterminado para evitar posibles consecuencias adversas. Por ejemplo:


- Muchos puntos de acceso público que se encuentran en hoteles, cafeterías y aeropuertos siguen usando solo 2,4 GHz, lo que bloquea el acceso a los dispositivos si banda se establece en solo 5 GHz.
- Dado que las conexiones de visualización inalámbrica Miracast requieren que el protocolo de enlace inicial se complete en canales de 2,4 GHz, los dispositivos no podrán conectarse solo a 5 GHz.

> [!NOTE]
> De forma predeterminada, los dispositivos Surfaces prefieren conectarse a 5 GHz si está disponible. Sin embargo, para preservar la energía en un estado de batería baja, Surface buscará primero una conexión de 2,4 GHz.

También puede cambiar la configuración de la banda según sea necesario para adaptarla a su entorno. Por ejemplo, los usuarios que viven en edificios de apartamento de alta densidad con varias zonas interactivas Wi-Fi, en medio de la presencia de dispositivos para consumidores, toda la difusión a través de 2,4 GHz, probablemente se beneficien de la configuración de su dispositivo Surface para que se conecte solo a 5 GHz y, después, vuelva a estar automático cuando sea necesario.

### Configuración de agresividad de itinerancia en dispositivos Surface con adaptadores Intel 

Es posible que los usuarios deseen seleccionar un umbral de intensidad de señal que solicite al dispositivo que busque un nuevo punto de acceso cuando se desplace la señal (intensidad de itinerancia). De forma predeterminada, los dispositivos Surface con adaptadores Intel intentan moverse a un punto de acceso nuevo si la intensidad de la señal cae por debajo de **medio** (intensidad de señal de 72 por ciento). Tenga en cuenta también que las organizaciones pueden implementar protocolos inalámbricos creados en varios puntos de acceso de red para facilitar el uso de entornos de red congestionados con movilidad, tal y como se explicó anteriormente en esta página. 

Aunque aumentar la agresividad de itinerancia por encima del **medio** puede ofrecer una conectividad mejorada en entornos residenciales o de oficina altamente congestionados, puede dar lugar a que se vea afectado la conectividad al salir de estos entornos. 

Se recomienda que deje la configuración de agresividad de itinerancia en el estado predeterminado, a menos que se encuentre con problemas de conectividad en escenarios específicos de telefonía móvil, como la realización de inspecciones de sitio de entorno y la conexión de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al estado de medio predeterminado. Tenga en cuenta que si aumenta la agresividad de itinerancia, también acelera el consumo de energía de la batería. 

**Para habilitar la agresividad de itinerancia en la superficie:**

1. Vaya a **iniciar**el  >  **Administrador de dispositivos**.
2. En **adaptadores de red** , seleccione **Intel Wi-Fi 6** y haga clic con el botón derecho en **propiedades**.
3. Seleccione la pestaña **avanzadas** .
4. Seleccione **agresividad de itinerancia** y elija su valor preferido en el menú desplegable.

![* Configuración de agresividad de itinerancia: Intel *](images/wifi-roaming-int.png) <br>

### Configuración de agresividad de itinerancia en Surface Go y Surface Pro X

Es posible que los trabajadores de primera línea que usen Surface go quieran seleccionar un umbral de intensidad de señal que solicite al dispositivo que busque un nuevo punto de acceso cuando baje la intensidad de la señal (intensidad de itinerancia). De forma predeterminada, los dispositivos de superficie intentan ir a un punto de acceso nuevo si la intensidad de la señal cae por debajo de **medio** (intensidad de señal de 50 por ciento). Tenga en cuenta que cada vez que aumenta la agresividad de itinerancia, se acelera el consumo de energía de la batería.

Deje la configuración de agresividad de itinerancia en el estado predeterminado, a menos que se encuentre con problemas de conectividad en escenarios móviles específicos, como la realización de inspecciones del sitio de entorno y la conexión de voz y vídeo durante una reunión de conferencia. Si no observa ninguna mejora, vuelva al estado de **medio** predeterminado.

**Para habilitar la agresividad de itinerancia en Go Go:**

1. Vaya a **Inicio > panel de control**  >  **red y**  >  **centro de redes y recursos compartidos.**
2. En **conexiones** , seleccione **Wi-Fi** y, a continuación, haga clic en **propiedades.**
3. Seleccione **cliente para redes Microsoft** y, después, seleccione **configurar**
4. Seleccione **Advanced**  >  **agresividad de itinerancia** avanzada y elija su valor preferido en el menú desplegable.

![* Configuración de agresividad de itinerancia: QualComm *](images/wifi-roaming.png) <br>


## Conclusión

Los dispositivos Surface están diseñados con ajustes predeterminados para una conectividad inalámbrica óptima equilibrada junto a la necesidad de preservar la duración de la batería. La manera más eficaz de habilitar una conectividad confiable para dispositivos Surface es a través de una red bien diseñada que admita 802.11 r y 802.11 k. Los usuarios pueden ajustar la configuración del adaptador de red o la agresividad de itinerancia pero solo deben hacerlo en respuesta a factores ambientales específicos y revertir al estado predeterminado si no hay ninguna mejora apreciable.

---
title: Conectarse a otros dispositivos y mostrar su contenido con Surface Hub
description: Puedes conectar otro dispositivo a tu Surface Hub para mostrar su contenido.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 2d8d814d5e33a878fab066321a0d7800ae5104c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836705"
---
# Conectarse a otros dispositivos y mostrar su contenido con Surface Hub


Puedes conectar otros dispositivos a tu Microsoft Surface Hub para mostrar su contenido. En este tema se describen el modo Invitado, el modo Equipo de reemplazo y la funcionalidad Salida de vídeo disponible a través de conexiones con cable, y también se indican los accesorios que se pueden conectar a Surface Hub mediante [Bluetooth](#bluetooth-accessories).

>[!NOTE]
>Surface Hub usará la entrada de video que seleccione hasta que se haga una nueva conexión, se interrumpa la conexión existente o se cierre la aplicación Connect.

## ¿Qué método debo elegir?

Al conectar dispositivos y pantallas externas a Surface Hub, existen varias opciones. El método que uses dependerá del escenario y tus necesidades. 

| Cuando quieras: | Usa este método: |
| --- | --- |
| Reflejar la pantalla de Surface Hub en otro dispositivo. | [Salida de vídeo](#video-out) |
| Presentar la pantalla de otro dispositivo en la pantalla de Surface Hub e interactuar con el contenido del dispositivo y la experiencia integrada de Surface Hub. | [Modo Invitado](#guest-mode) |
| Enciende Surface Hub desde un equipo externo con Windows 10 y apaga el equipo integrado de Surface Hub. Las cámaras, los micrófonos, los altavoces y otros periféricos se envían al equipo externo, además de las entradas de lápiz y táctiles. | [Modo de equipo de reemplazo](#replacement-pc-mode) |


## Modo Invitado


El modo Invitado usa una conexión por cable para que los usuarios puedan mostrar el contenido de sus dispositivos en Surface Hub. Si el dispositivo de origen es un dispositivo Windows, dicho dispositivo también puede proporcionar touchback e inkback. El equipo interno de Surface Hub toma el audio y el vídeo del dispositivo conectado y los presenta en Surface Hub. Si Surface Hub encuentra una señal de protección de contenido digital (HDCP) de ancho de banda alto, el origen se mostrará como una imagen en negro. Para mostrar tu contenido sin infringir los requisitos de HDCP, usa el teclado del lado derecho de Surface Hub para elegir directamente el origen externo.

>[!NOTE]
>Cuando haya un origen HDCP conectado, usa el teclado lateral para cambiar las entradas de origen.

### Puertos

Usa estos puertos en Surface Hub para el modo Invitado.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Interfaz</th>
<th>Tipo</th>
<th>Descripción</th>
<th>Funcionalidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Puerto de pantalla 1.1a</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de invitado 1</p></td>
<td><ul>
<li><p>Admite la visualización de esta entrada de invitado a la vez que la entrada de invitado 2 y la entrada de invitado 3 (una en alta resolución y dos en miniaturas).</p></li>
<li><p>Compatible con HDCP en el modo de omisión</p></li>
<li><p>Touchback habilitado</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI 1.4</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de invitado 2</p></td>
<td><ul>
<li><p>Admite la visualización de esta entrada de invitado a la vez que la entrada de invitado 1 y la entrada de invitado 3 (una en alta resolución y dos en miniaturas).</p></li>
<li><p>Compatible con HDCP en el modo de omisión</p></li>
<li><p>Touchback habilitado</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>Entrada de invitado 3</p></td>
<td><ul>
<li><p>Admite la visualización de esta entrada de invitado a la vez que la entrada de invitado 1 y la entrada de invitado 2 (una en alta resolución y dos en miniaturas).</p></li>
<li><p>Compatible con HDCP en el modo de omisión</p></li>
<li><p>Touchback habilitado</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Conector de 3,5mm</p></td>
<td><p>Entrada de audio</p></td>
<td><p>Entrada de audio analógico</p></td>
<td><ul>
<li><p>Se consume en el equipo de Surface Hub, normalmente con la entrada de vídeo VGA.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 2.0, tipo B</p></td>
<td><p>Salida USB</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>Proporciona acceso los dispositivos de entrada HID (mouse, entrada táctil, teclado y el lápiz) de vuelta al equipo invitado.</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### Ubicaciones de los puertos

Estas son las conexiones de puerto usadas para el modo Invitado en Surface Hubs de 55" y de 84".

![Imagen que muestra los puertos de invitado en un Surface Hub de 55".](images/sh-55-guest-ports.png)

Conexiones de puerto cableadas en un Surface Hub de 55"

![Imagen que muestra los puertos de invitado en un Surface Hub de 84".](images/sh-84-guest-ports.png)

Conexiones de puerto cableadas en un Surface Hub de 84"

### Enumeración de puertos

Cuando se conecta un Surface Hub a un equipo de invitado con el puerto USB de conexión cableada, se descubren y configuran varios dispositivos USB. Estos dispositivos periféricos se han creado para touchback e inkback. Los dispositivos periféricos pueden verse en el Administrador de dispositivos. El Administrador de dispositivos mostrará nombres duplicados para algunos dispositivos.

**Dispositivos de interfaz humana (HID)**

-   Dispositivo de control del consumidor compatible con HID

-   Lápiz compatible con HID

-   Lápiz compatible con HID (elemento duplicado)

-   Lápiz compatible con HID (elemento duplicado)

-   Pantalla táctil compatible con HID

-   Dispositivo de entrada USB

-   Dispositivo de entrada USB (elemento duplicado)

**Teclados**

-   Teclado PS/2 estándar

**Mouse y otros dispositivos señaladores**

-   Mouse compatible con HID

**Controladoras de bus serie universal**

-   Concentrador USB genérico

-   Dispositivo compuesto USB

### Conectividad de modo Invitado

La elección del cable de vídeo la determinará qué está disponible desde la entrada de origen. Surface Hub tiene 3 opciones de entrada de vídeo: DisplayPort, HDMI y VGA. Consulta el siguiente gráfico para conocer las resoluciones disponibles.

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de señal</th>
<th>Resolución</th>
<th>Velocidad de fotogramas</th>
<th>HDMI - RGB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PC</p></td>
<td><p>640 x 480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>PC</p></td>
<td><p>720 x 480</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>PC</p></td>
<td><p>1024 x 768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59,94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

El audio de origen lo proporcionan los cables de DisplayPort y HDMI. Si tienes que usar VGA, Surface Hub dispone de un puerto de entrada de audio que usa un conector de 3,5mm. Surface Hub también usa un cable USB que proporciona las capacidades de touchback e inkback desde Surface Hub a los dispositivos Windows10 compatibles. El cable USB puede usarse con cualquier entrada de vídeo que ya esté conectada con un cable.

Alguien que usa el modo Invitado para conectar un equipo usaría una de estas opciones:

**DisplayPort**: Cable DisplayPort y cable USB 2.0

**HDMI**: Cable HDMI y cable USB 2.0

**VGA**: Cable VGA, cable de audio de 3,5mm y cable USB 2.0

Si el equipo que usas para el modo Invitado no es compatible con touchback e inkback, el cable USB no será necesario.

## Modo de equipo de reemplazo


En el modo Equipo de reemplazo, el equipo integrado de Surface Hub se apaga y se conecta un equipo externo a Surface Hub. Las conexiones con los puertos del equipo de reemplazo dan acceso a dispositivos periféricos clave de Surface Hub, lo que incluye la pantalla, el lápiz y las características táctiles. Esto significa que tu Surface Hub no tendrá el beneficio de la experiencia del Equipo de Windows, pero tendrás la flexibilidad que ofrecen el proporcionar y el administrar su propio equipo Windows.

### Requisitos de software

Surface Hub puede ejecutarse en modo Equipo de reemplazo con las versiones de 64 bits de Windows10 Home, Windows10 Pro y Windows10 Enterprise. Puedes descargar el [paquete de controladores de PC de reemplazo para Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) desde el Centro de descarga de Microsoft. Te recomendamos que instales a estos controladores en cualquier equipo que vayas a usar como equipo de reemplazo.

### Requisitos de hardware

Surface Hub es compatible con una gran variedad de hardware. Elige la confirmación del procesador y la memoria para el equipo de reemplazo, de forma que admita los programas que usarás. El hardware del equipo de reemplazo debe admitir las versiones de 64 bits de Windows10.

### Tarjeta gráfica

En el modo Equipo de reemplazo, Surface Hub admite cualquier tarjeta gráfica que pueda producir una señal de DisplayPort. Mejorarás tu experiencia si usas una tarjeta gráfica que puede igualar la resolución y la frecuencia de actualización de Surface Hub. Por ejemplo, para obtener la mejor experiencia de equipo de reemplazo en Surface Hub, se recomienda una señal de vídeo de 120Hz.

**Surface Hub 55"**: Para lograr la mejor experiencia, usa una tarjeta gráfica que admita una resolución de 1080p a 120Hz.

**Surface Hub 84"**: Para lograr la mejor experiencia, usa una tarjeta gráfica que pueda generar 4 emisiones DisplayPort 1.2 para producir 2160p a 120Hz (3840 x 2160 con una actualización vertical de 120Hz). Hemos verificado que esto funciona con las tarjetas NVIDIA Quadro K2200, NVIDIA Quadro K4200, NVIDIA Quadro M6000, AMD FirePro W5100, AMD FirePro W7100 y AMD FirePro W9100. Estas no son las únicas tarjetas gráficas, ya que hay otras disponibles de otros proveedores. 

Consulta directamente a los proveedores de tarjetas gráficas para obtener los controladores más recientes.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Proveedor de tarjetas gráficas</th>
<th>Página de descarga de controladores</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### Puertos

Puertos del equipo de reemplazo en Surface Hub 55".

![Imagen que muestra los puertos del equipo de reemplazo en Surface Hub 55".](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Tipo</th>
<th>Interfaz</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vídeo del equipo</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>DP 1.2</p></td>
<td><ul>
<li><p>Visualización de pantalla completa de 1080p a 120 Hz, más audio</p></li>
<li><p>Compatible con HDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Periféricos internos</p></td>
<td><p>Salida USB</p></td>
<td><p>USB 2.0 tipo B</p></td>
<td><ul>
<li><p>Función táctil</p></li>
<li><p>Lápiz</p></li>
<li><p>Altavoces</p></li>
<li><p>Micrófono</p></li>
<li><p>Cámaras</p></li>
<li><p>Sensor NFC</p></li>
<li><p>Sensor de luz ambiental</p></li>
<li><p>Sensor de infrarrojos pasivo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Concentrador USB</p></td>
<td><p>Salida USB</p></td>
<td><p>USB 2.0 tipo B</p></td>
<td><ul>
<li><p>Puertos USB inferiores</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

Puertos del equipo de reemplazo en Surface Hub 84".

![Imagen que muestra los puertos del equipo de reemplazo en Surface Hub 84".](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Tipo</th>
<th>Interfaz</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vídeo del equipo</p></td>
<td><p>Entrada de vídeo</p></td>
<td><p>DP 1.2 (2x)</p></td>
<td><ul>
<li><p>Visualización de pantalla completa de 2160p a 120 Hz, más audio</p></li>
<li><p>Compatible con HDCP</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Periféricos internos</p></td>
<td><p>Salida USB</p></td>
<td><p>USB 2.0 tipo B</p></td>
<td><ul>
<li><p>Función táctil</p></li>
<li><p>Lápiz</p></li>
<li><p>Altavoces</p></li>
<li><p>Micrófono</p></li>
<li><p>Cámaras</p></li>
<li><p>Sensor NFC</p></li>
<li><p>Sensor de luz ambiental</p></li>
<li><p>Sensor de infrarrojos pasivo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Concentrador USB</p></td>
<td><p>Salida USB</p></td>
<td><p>USB 2.0 tipo B</p></td>
<td><ul>
<li><p>Puertos USB inferiores</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### Instrucciones de configuración para el equipo de reemplazo

**Para usar el modo Equipo de reemplazo**

1.  Descarga e instala el [paquete de controladores de PC de reemplazo para Surface Hub](https://www.microsoft.com/download/details.aspx?id=52210) en el equipo de reemplazo.

    >[!NOTE]
    >Te recomendamos que pongas el equipo de reemplazo en reposo o hibernación, ya que Surface Hub apagará la pantalla cuando no se use.

2.  Apaga Surface Hub con el interruptor de alimentación situado junto al cable de alimentación.

3.  Conecta los cables de los puertos del equipo de reemplazo de Surface Hub al equipo de reemplazo. Generalmente estos puertos se encuentra cubiertos por una tapa de plástico extraíble.

    Surface Hub 55": Conecta 1 cable DisplayPort y 2 cables USB.

    Surface Hub 84": Conecta 2 cables DisplayPort y 2 cables USB.

4.  Cambia el conmutador de modo a **Equipo de reemplazo**. El conmutador de modo está junto a los puertos del equipo de reemplazo.

5.  Enciende Surface Hub con el interruptor de alimentación situado junto al cable de alimentación.

6.  Presiona el botón de alimentación en el lado derecho de Surface Hub.

Puedes cambiar Surface Hub para usar su PC interno.

**Para volver a su PC interno**

1.  Apaga Surface Hub con el interruptor de alimentación situado junto al cable de alimentación.

2.  Cambia el control de modo a PC interno. El conmutador de modo está junto a los puertos del equipo de reemplazo.

3.  Enciende Surface Hub con el interruptor de alimentación situado junto al cable de alimentación.

 
## Salida de vídeo
 
Surface Hub incluye un puerto de salida de vídeo para reflejar el contenido visual desde Surface Hub a otra pantalla.

### Puertos

Puerto de salida de vídeo en Surface Hub 55"

![Ilustración del puerto de salida de vídeo](images/video-out-55.png)

Puerto de salida de vídeo en Surface Hub 84"

![Ilustración del puerto de salida de vídeo](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Tipo</th>
<th>Interfaz</th>
<th>Funcionalidades</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Reflejo de salida de vídeo</p></td>
<td><p>Salida de vídeo</p></td>
<td><p>Salida de vídeo</p></td>
<td><ul>
<li><p>Admite la conexión a un monitor DisplayPort estándar (solo admite un vínculo x4 que muestre una resolución 1080p60 a 24bpp)</p></li>
<li><p>Admite el uso con monitores HDMI (compatibles con resoluciones de 1080p60) mediante un adaptador de DisplayPort a HDMI</p></li>
</ul></td>
</tr>
</tbody>
</table>

## Cables

Se ha demostrado que los dispositivos Surface Hub de 55" y 84" funcionan con cables DisplayPort certificados y con cables HDMI.  Aunque algunos proveedores venden cables más largos que pueden funcionar con el Surface Hub, únicamente se garantiza el funcionamiento con dispositivos Surface Hub de aquellos cables certificados por laboratorios de pruebas. Por ejemplo, únicamente están certificados cables DisplayPort de hasta 3metros; sin embargo, muchos proveedores venden cables que tienen el triple de dicha longitud. Si es necesario un cable largo, recomendamos encarecidamente usar HDMI.  HDMI posee muchas soluciones asequibles de cables de largo alcance, incluido el uso de repetidores. Casi todas las fuentes DisplayPort cambian automáticamente a señalización HDMI si se detecta un receptor HDMI.


## Accesorios Bluetooth

Los accesorios siguientes pueden conectarse a Surface Hub mediante Bluetooth:

- Ratones
- Teclados
- Auriculares
- Altavoces

>[!NOTE]
>Tras conectar unos auriculares o un altavoz Bluetooth, es posible que debas cambiar la [configuración predeterminada de micrófono y altavoces](local-management-surface-hub-settings.md).

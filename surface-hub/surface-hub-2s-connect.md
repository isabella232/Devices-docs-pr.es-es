---
title: Conectar dispositivos a Surface Hub 2S
description: Esta página explica cómo conectar dispositivos externos a Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835745"
---
# Conectar dispositivos a Surface Hub 2S
Surface Hub 2S le permite conectar dispositivos externos, reflejar la pantalla en Surface Hub 2S a otro dispositivo y conectar varios periféricos de terceros, como cámaras de videoconferencia, teléfonos de conferencia y dispositivos de sistema Room.

Puedes mostrar el contenido de tus dispositivos a Surface Hub 2S. Si el dispositivo de origen está basado en Windows, ese dispositivo también puede proporcionar TouchBack y InkBack, que toma vídeo y audio del dispositivo conectado y los presenta en Surface Hub 2S. Si Surface Hub 2S encuentra una señal de protección de contenido digital (HDCP) de ancho de banda alto, como un reproductor de DVD Blu-Ray, el origen se muestra como una imagen en negro.

> [!NOTE]
> Surface Hub 2S usa la entrada de video seleccionada hasta que se establece una nueva conexión, se interrumpe la conexión existente o se cierra la aplicación Connect.

##  <a name="recommended-wired-configurations"></a>Configuraciones cableadas recomendadas 

En general, se recomienda usar conexiones de cable nativas siempre que sea posible, como USB-C o USB-C o HDMI a HDMI. Otras combinaciones, como MiniDP a HDMI o MiniDP a USB-C también funcionan. Es posible que se necesite una configuración adicional para optimizar la experiencia de salida del video, tal y como se describe en esta página.

| **Conexión** | **Funcionalidad** | **Descripción**|
| --- | --- | ---|
| HDMI + USB-C | HDMI-in para audio y vídeo<br><br>USB-C para TouchBack y InkBack | USB-C admite TouchBack y InkBack con la conexión A/V HDMI.<br><br>Use USB-C para USB-A para conectarse a equipos heredados.<br><br>**Nota:** Para obtener los mejores resultados, conecta HDMI antes de conectar un cable USB-C. Si el equipo que usas para HDMI no es compatible con TouchBack y InkBack, no necesitarás un cable USB-C. |
| USB-C <br> (mediante módulo de cálculo) | Vídeo: en vídeo <br>Audio en | Cable único necesario para A/V<br><br>TouchBack y InkBack son compatibles<br><br>HDCP habilitado |
| HDMI (en Puerto) | Vídeo, audio en Surface Hub 2S | Cable único necesario para A/V<br><br>TouchBack y InkBack no compatibles<br><br>HDCP habilitado |
| Salida de MiniDP 1,2 | Vídeo: salida, como el reflejo a un proyector más grande. | Cable único necesario para A/V |

Al conectar un equipo invitado a Surface Hub 2S a través del puerto USB-C, se descubren y configuran varios dispositivos USB. Estos dispositivos periféricos se crean para TouchBack y InkBack. Como se muestra en la tabla siguiente, los dispositivos periféricos se pueden ver en el administrador de dispositivos, que mostrará nombres duplicados para algunos dispositivos, como se muestra en la tabla siguiente.

 
|**Periféricos**| **Listado en el administrador de dispositivos** |
| ---------------------------- |------------- | ------------------------------|
| Dispositivos de interfaz humana (HID) | Dispositivo de control del consumidor compatible con HID<br>Lápiz compatible con HID<br>Lápiz compatible con HID (elemento duplicado)<br>Lápiz compatible con HID (elemento duplicado)<br>Pantalla táctil compatible con HID<br>Dispositivo de entrada USB<br>Dispositivo de entrada USB (elemento duplicado) |
| Teclados | Teclado PS/2 estándar |
| Mouse y otros dispositivos señaladores | Mouse compatible con HID |
| Controladores USB | Concentrador USB genérico<br>Dispositivo compuesto USB |

##  <a name="connecting-video-in-to-surface-hub-2s"></a>Conexión de vídeo en Surface Hub 2S

Puedes introducir video en Surface Hub 2S con USB-C o HDMI, como se indica en la tabla siguiente.  

###  <a name="surface-hub-2s-video-in-settings"></a>Configuración de vídeo de Surface Hub 2S

| **Tipo de señal** | **Resolución** | **Velocidad de fotogramas** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 0,30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 0,30             | X        | X         |

> [!NOTE]
> La resolución de 4K UHD (3840 × 2560) solo se admite al conectarse a puertos en el módulo de cálculo. No es compatible con los puertos USB "de invitado" que se encuentran en los lados izquierdo, superior y derecho del dispositivo.

> [!NOTE]
> Es posible que el video de un PC externo conectado aparezca más pequeño cuando se muestra en Surface Hub 2S.

##  <a name="mirroring-surface-hub-2s-display-on-another-device"></a>Reflejar la pantalla de 2.

Puede enviar video a otra pantalla con MiniDP, como se indica en la tabla siguiente.

###  <a name="surface-hub-2s-video-out-settings"></a>Configuración de salida de video de Surface Hub 2S

| **Tipo de señal** | **Resolución** | **Velocidad de fotogramas** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| PC              | 720 x 480      | 60             | X          |
| PC              | 1024 x 768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S incluye un puerto de salida de video de MiniDP para proyectar contenido visual desde Surface Hub 2S a otra pantalla. Si tiene previsto usar Surface Hub 2S para proyectar en otra pantalla, tenga en cuenta las siguientes recomendaciones:

- **Teclado requerido.** Antes de empezar, deberás conectar un teclado externo con cable o Bluetooth a Surface Hub 2S. Ten en cuenta que, a diferencia de la Surface Hub original, un teclado para Surface Hub 2S se vende por separado y no se incluye en el paquete de envío.<br><br>
- **Establecer el modo duplicado.** Surface Hub 2S admite vídeo: solo en modo duplicado. Sin embargo, aún tendrá que configurar manualmente el modo de presentación cuando se conecte por primera vez:
    1. Escriba la **tecla del logotipo de Windows**  +  **P**, que abre el panel del proyecto en el lado derecho de Surface Hub 2s y, a continuación, seleccione **duplicar** modo.
    2. Cuando haya terminado con la sesión de Surface Hub 2S, seleccione **finalizar sesión**. Esto garantiza que la configuración duplicada se guardará para la siguiente sesión.<br><br>
- **Planear diferentes relaciones de aspecto.** Al igual que otros dispositivos de Surface, Surface Hub 2S usa una relación de aspecto de 3:2 (la relación entre el ancho y el alto de la pantalla). La proyección de Surface Hub 2 en pantallas con diferentes relaciones de aspecto es compatible. Sin embargo, ten en cuenta que, dado que Surface Hub 2 duplica la pantalla, la salida de MiniDP también se muestra solo en una relación de aspecto 3:2, lo que puede dar lugar a una panorámica o a una cortina en función de la relación de aspecto de la pantalla de recepción. 

> [!NOTE]
> Si su segundo monitor usa una relación de aspecto de 16:9 (la relación predominante para la mayoría de los monitores de TV), es posible que aparezcan barras negras a la izquierda y a la derecha de la pantalla reflejada. Si esto sucede, es posible que desee informar a los usuarios de que no es necesario ajustar la segunda pantalla.

##  <a name="selecting-cables"></a>Selección de cables

Tenga en cuenta las siguientes recomendaciones:

- **USB.** Cables USB 3,1 Gen 2.
- **MiniDP.** Cables de DisplayPort certificados para un máximo de 3 metros de longitud.
- **HDMI.** Si se necesita un cable largo, se recomienda usar HDMI debido a la amplia disponibilidad de los cables de largo alcance y rentable con la capacidad de instalar repetidores si es necesario.

> [!NOTE]
> La mayoría de los orígenes de DisplayPort cambiarán automáticamente a la señalización HDMI si se detecta HDMI.

##  <a name="wirelessly-connect-to-surface-hub-2s"></a>Conexión inalámbrica a Surface Hub 2S

Windows 10 es compatible de forma nativa con Miracast, que te permite conectarte a Surface Hub 2S.<br><br>

###  <a name="to-connect-using-miracast"></a>Para conectar con Miracast:

1. En el dispositivo Windows 10, escriba la **tecla del logotipo de Windows**  +  **K**. 
2. En la ventana de conexión, busca el nombre de tu Surface Hub 2 en la lista de dispositivos cercanos. Puede encontrar el nombre de su Surface Hub 2 en la esquina inferior izquierda de la pantalla.
3. Escribe un PIN si el administrador del sistema ha habilitado la configuración del PIN para las conexiones Miracast. Para ello, debes introducir un número PIN cuando te conectes a Surface Hub 2S por primera vez.

> [!NOTE]
>Si no ve el nombre del dispositivo Surface Hub 2S de la forma esperada, es posible que la sesión anterior se haya cerrado prematuramente. Si es así, inicie sesión en Surface Hub 2S directamente para finalizar la sesión anterior y, a continuación, conéctese desde el dispositivo externo.

##  <a name="connecting-peripherals-to-surface-hub-2s"></a>Conexión de periféricos a Surface Hub 2S

###  <a name="bluetooth-accessories"></a>Accesorios Bluetooth

Puede conectar los siguientes accesorios a Surface Hub-2 con Bluetooth:

- Ratones
- Teclados
- Auriculares
- Altavoces
- Surface Hub 2 plumas

> [!NOTE]
> Tras conectar unos auriculares o un altavoz Bluetooth, es posible que debas cambiar la configuración predeterminada de micrófono y altavoces. Para obtener más información, vea [**Administración local para la configuración de Surface Hub**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings).

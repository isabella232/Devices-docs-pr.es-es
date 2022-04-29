---
title: Conectar dispositivos a Surface Hub 2S
description: En esta página se explica cómo conectar dispositivos externos a Surface Hub 2S.
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
ms.openlocfilehash: e3d1aa79ad056e790d5dc6a46f299cbaa9b5f9b0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497480"
---
# <a name="connect-devices-to-surface-hub-2s"></a>Conectar dispositivos a Surface Hub 2S

Surface Hub 2S le permite conectar dispositivos externos, reflejar la pantalla en Surface Hub 2S a otro dispositivo y conectar varios periféricos de terceros, como cámaras de videoconferencia, teléfonos de conferencia y dispositivos de sistema de salas.

Puede mostrar contenido de los dispositivos a Surface Hub 2S. Si el dispositivo de origen está basado en Windows, ese dispositivo también puede proporcionar TouchBack y InkBack, que toma vídeo y audio del dispositivo conectado y los presenta en Surface Hub 2S. Si Surface Hub 2S encuentra una señal de protección de contenido digital (HDCP) High-Bandwidth, como un reproductor de DVD blu-ray, el origen se muestra como una imagen negra.

> [!NOTE]
> Surface Hub 2S usa la entrada de vídeo seleccionada hasta que se realiza una nueva conexión, se interrumpe la conexión existente o se cierra la aplicación Conectar.

## <a name="recommended-wired-configurations"></a>Configuraciones cableadas recomendadas 

En general, se recomienda usar conexiones de cable nativas siempre que sea posible, como USB-C a USB-C o HDMI a HDMI. Otras combinaciones como MiniDP a HDMI o MiniDP a USB-C también funcionarán. Es posible que se necesite alguna configuración adicional para optimizar la experiencia de salida de vídeo, como se describe en esta página.

| **Conexión** | **Funcionalidad** | **Descripción**|
| --- | --- | ---|
| HDMI + USB-C | HDMI-in para audio y vídeo<br><br>USB-C para TouchBack y InkBack | USB-C admite TouchBack y InkBack con la conexión HDMI A/V.<br><br>Use USB-C a USB-A para conectarse a equipos heredados.<br><br>**NOTA:** Para obtener los mejores resultados, conecte HDMI antes de conectar un cable USB-C. Si el equipo que usas para HDMI no es compatible con TouchBack y InkBack, no necesitarás un cable USB-C. |
| USB-C <br> (a través del módulo de proceso) | Entrada de vídeo <br>Entrada de audio | Cable único necesario para A/V<br><br>Se admiten TouchBack y InkBack<br><br>HDCP habilitado |
| HDMI (en puerto) | Vídeo, audio en Surface Hub 2S | Cable único necesario para A/V<br><br>No se admiten TouchBack ni InkBack<br><br>HDCP habilitado |
| Salida de MiniDP 1.2 | Vídeo de salida, como la creación de reflejos en un proyector más grande. | Cable único necesario para A/V |

Al conectar un equipo invitado a Surface Hub 2S a través del puerto USB-C, se detectan y configuran varios dispositivos USB. Estos dispositivos periféricos se crean para TouchBack y InkBack. Como se muestra en la tabla siguiente, los dispositivos periféricos se pueden ver en Administrador de dispositivos, que mostrará nombres duplicados para algunos dispositivos, como se muestra en la tabla siguiente.

 
|**Periféricos**| **Lista en Administrador de dispositivos** |
| ---------------------------- |------------- | ------------------------------|
| Dispositivos de interfaz humana (HID) | Dispositivo de control del consumidor compatible con HID<br>Lápiz compatible con HID<br>Lápiz compatible con HID (elemento duplicado)<br>Lápiz compatible con HID (elemento duplicado)<br>Pantalla táctil compatible con HID<br>Dispositivo de entrada USB<br>Dispositivo de entrada USB (elemento duplicado) |
| Teclados | Teclado PS/2 estándar |
| Mouse y otros dispositivos señaladores | Mouse compatible con HID |
| Controladores USB | Concentrador USB genérico<br>Dispositivo compuesto USB |

## <a name="connecting-video-in-to-surface-hub-2s"></a>Conexión de vídeo a Surface Hub 2S

Puede introducir vídeo en Surface Hub 2S mediante USB-C o HDMI, como se indica en la tabla siguiente.  

### <a name="surface-hub-2s-video-in-settings"></a>configuración de vídeo en Surface Hub 2S

| **Tipo de señal** | **Resolución** | **Velocidad de fotogramas** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> La resolución 4K UHD (3840×2560) solo se admite al conectarse a puertos en el módulo de proceso. No se admite en los puertos USB "invitados" situados a la izquierda, la parte superior y la derecha del dispositivo.

> [!NOTE]
> El vídeo de un equipo externo conectado puede parecer más pequeño cuando se muestra en Surface Hub 2S.

## <a name="mirroring-surface-hub-2s-display-on-another-device"></a>Creación de reflejo Surface Hub pantalla 2S en otro dispositivo

Puede enviar vídeo a otra pantalla mediante MiniDP, como se indica en la tabla siguiente.

### <a name="surface-hub-2s-video-out-settings"></a>Surface Hub configuración de salida de vídeo 2S

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


 
Surface Hub 2S incluye un puerto de salida de vídeo MiniDP para proyectar contenido visual de Surface Hub 2S a otra pantalla. Si tiene previsto usar Surface Hub 2S para proyectar en otra pantalla, tenga en cuenta las siguientes recomendaciones:

- **Teclado necesario.** Antes de empezar, deberá conectar un teclado externo con cable o habilitado para Bluetooth a Surface Hub 2S. Tenga en cuenta que a diferencia de la Surface Hub original, un teclado para Surface Hub 2S se vende por separado y no está incluido en el paquete de envío.<br><br>
- **Establezca el modo duplicado.** Surface Hub 2S solo admite la salida de vídeo en modo duplicado. Sin embargo, deberá configurar manualmente el modo de visualización cuando se conecte por primera vez:
    1. Escriba la **tecla** +  de logotipo Windows **P**, que abre el panel de Project en el lado derecho de Surface Hub 2S y, a continuación, seleccione **Modo duplicado**.
    2. Cuando haya terminado con la sesión de Surface Hub 2S, seleccione **Finalizar sesión**. Esto garantiza que la configuración duplicada se guarde para la siguiente sesión.<br><br>
- **Planee diferentes relaciones de aspecto.** Al igual que otros dispositivos Surface, Surface Hub 2S usa una relación de aspecto de visualización 3:2 (la relación entre el ancho y el alto de la pantalla). Se admite la proyección de Surface Hub 2S en pantallas con diferentes relaciones de aspecto. Sin embargo, tenga en cuenta que, dado que Surface Hub 2S duplica la pantalla, la salida de MiniDP también se mostrará en una relación de aspecto de 3:2, lo que puede dar lugar a la caja de letras o el cortinaje en función de la relación de aspecto de la pantalla receptora. 

> [!NOTE]
> Si el segundo monitor usa una relación de aspecto de 16:9 (la proporción predominante para la mayoría de los monitores de TV), pueden aparecer barras negras en los lados izquierdo y derecho de la pantalla reflejada. Si esto ocurre, es posible que desee informar a los usuarios de que no es necesario ajustar la segunda pantalla.

## <a name="selecting-cables"></a>Selección de cables

Tenga en cuenta las siguientes recomendaciones:

- **USB.** Cables USB 3.1 Gen 2.
- **MiniDP.** Cables DisplayPort certificados de hasta 3 metros de longitud.
- **HDMI.** Si es necesario un cable largo, se recomienda HDMI debido a la amplia disponibilidad de cables rentables de larga distancia con la capacidad de instalar repetidores si es necesario.

> [!NOTE]
> La mayoría de los orígenes de DisplayPort cambiarán automáticamente a la señalización HDMI si se detecta HDMI.

## <a name="wirelessly-connect-to-surface-hub-2s"></a>Conexión inalámbrica a Surface Hub 2S

Windows 10/11 admite de forma nativa Miracast, lo que le permite conectarse de forma inalámbrica a Surface Hub 2S.<br><br>

### <a name="to-connect-using-miracast"></a>Para conectarse mediante Miracast:

1. En el dispositivo Windows 10/11, escriba **Windows clave** +  de logotipo **.** 
2. En la ventana Conectar, busque el nombre del Surface Hub 2S en la lista de dispositivos cercanos. Puede encontrar el nombre del Surface Hub 2S en la esquina inferior izquierda de la pantalla.
3. Escriba un PIN si el administrador del sistema ha habilitado la configuración de PIN para las conexiones Miracast. Esto requiere que escriba un número pin al conectarse a Surface Hub 2S por primera vez.

> [!NOTE]
>Si no ve el nombre del dispositivo Surface Hub 2S según lo esperado, es posible que la sesión anterior se haya cerrado prematuramente. Si es así, inicie sesión en Surface Hub 2S directamente para finalizar la sesión anterior y, a continuación, conéctese desde el dispositivo externo.

## <a name="connecting-peripherals-to-surface-hub-2s"></a>Conexión de periféricos a Surface Hub 2S

### <a name="bluetooth-accessories"></a>Accesorios Bluetooth

Puede conectar los siguientes accesorios a Surface Hub-2S mediante Bluetooth:

- Ratones
- Teclados
- Auriculares
- Altavoces
- Surface Hub 2 plumas

> [!NOTE]
> Tras conectar unos auriculares o un altavoz Bluetooth, es posible que debas cambiar la configuración predeterminada de micrófono y altavoces. Para obtener más información, consulta [Administración local para la configuración de Surface Hub](local-management-surface-hub-settings.md).

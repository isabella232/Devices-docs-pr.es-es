---
title: Compatibilidad de aplicaciones Surface Pro X
description: Este artículo proporciona información de compatibilidad de la aplicación de presentación para PC Surface Pro X ARM.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835569"
---
# Compatibilidad de aplicaciones Surface Pro X

Las aplicaciones se ejecutan de manera diferente en equipos Windows 10 basados en ARM, como Surface Pro X. las limitaciones son las siguientes:

- **Los drivers de hardware, juegos y aplicaciones solo funcionarán si están diseñados para un equipo basado en ARM de Windows 10**. Para obtener más información, consulte al fabricante del hardware o a la organización que desarrolló el controlador. Los drivers son programas de software que se comunican con dispositivos de hardware, que suelen usarse para software antivirus y antimalware, software de impresión o PDF, tecnologías de asistencia, utilidades de CD y DVD y software de virtualización. Si un controlador no funciona, la aplicación o el hardware que depende de él no funcionará (al menos no completo). Los periféricos y dispositivos solo funcionan si los drivers de los que dependen están integrados en Windows 10 o si el desarrollador de hardware ha publicado ARM64 drivers para el dispositivo.
- las **aplicaciones de 64 bits (x64) no funcionan**. Necesitarás aplicaciones de 64 bits (ARM64), aplicaciones de 32 bits (ARM32) o aplicaciones de 32 bits (x86). Normalmente, puede encontrar las versiones de 32 bits (x86) de las aplicaciones, pero algunos desarrolladores de aplicaciones solo ofrecen aplicaciones de 64 bits (x64).
- **Algunos juegos no funcionan**. Los juegos y las aplicaciones no funcionarán si usan una versión de OpenGL mayor que 1,1 o si dependen de los "controladores de trampa" que no se han hecho para equipos basados en Windows 10 ARM. Consulta al editor de tu juego para ver si funciona un juego.
- **Es posible que las aplicaciones que personalizan la experiencia de Windows tengan problemas**. Esto incluye algunos editores de métodos de entrada (IME), tecnologías de asistencia y aplicaciones de almacenamiento en la nube. La organización que desarrolla la aplicación determina si su aplicación funcionará en un equipo con Windows 10 ARM.
- **No se puede instalar algún software antivirus de terceros**. No podrá instalar un software antivirus de terceros en un equipo con Windows 10 ARM. Sin embargo, la seguridad de Windows le ayudará a mantener el ciclo de vida admitido de su dispositivo Windows 10.
- **Fax y escáner de Windows no está disponible**. Esta característica no está disponible en un equipo con Windows 10 ARM.

Para obtener más información sobre la compatibilidad de las aplicaciones, consulte [preguntas más frecuentes sobre equipos con Windows 10 ARM](https://support.microsoft.com/en-us/help/4521606)

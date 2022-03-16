---
title: Compatibilidad de dispositivos Surface con Windows 10 Long-Term de mantenimiento (Surface)
description: Descubra la compatibilidad y las limitaciones de los dispositivos Surface que Windows 10 Enterprise ltsb edition.
keywords: ltsb, update, opciones de mantenimiento de superficie
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 07/21/2021
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: d8c1e0996b02ac385b587661f3894ce30e406d9a
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448923"
---
# <a name="surface-device-compatibility-with-windows-10-long-term-servicing-channel-ltsc"></a>Compatibilidad de dispositivos Surface con Windows 10 Long-Term de mantenimiento (LTSC)

Los dispositivos Surface están diseñados para proporcionar las mejores experiencias de su clase en escenarios de productividad y de propósito general. Las actualizaciones regulares permiten que los dispositivos Surface traigan innovaciones y evolucionen con las nuevas funcionalidades que Windows 10 actualizaciones de características. Las actualizaciones de características solo están disponibles en Windows 10 Pro o Windows 10 Enterprise que reciben actualizaciones continuas a través del canal de Semi-Annual (SAC).

A diferencia de la opción de mantenimiento sac, anteriormente conocida como las opciones de mantenimiento Rama actual (CB) o Rama actual para empresas (CBB), no puede seleccionar la opción canal de mantenimiento de Long-Term (LTSC) en la configuración Windows 10. Para usar la opción de mantenimiento LTSC, debe instalar una edición independiente de Windows 10 Enterprise, conocida como Windows 10 Enterprise LTSC, anteriormente conocida como LTSB Windows 10 Enterprise (rama de mantenimiento a largo plazo).

>[!TIP]
>Para obtener la información más reciente acerca de LTSC, consulte las siguientes preguntas frecuentes: la siguiente Windows 10 de servicio a largo plazo [(LTSC](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232)).

 Además de proporcionar un modelo de mantenimiento extendido, la Windows 10 Enterprise ltsc edition también proporciona un entorno con varios componentes Windows eliminados. Las experiencias principales de Surface que afectan a LTSC incluyen:

* Windows actualizaciones de características, incluidas mejoras como:

  * Mejoras en el rechazo de lápiz directo y palma proporcionados en Windows 10, versión 1607 (también denominada Actualización de aniversario)
  * Compatibilidad mejorada con aplicaciones de PPP elevadas proporcionadas en Windows 10, versión 1703 (también denominada Actualización de creadores)

* Configuración de confidencialidad de presión proporcionada por la aplicación Surface

* El Área de trabajo de Windows Ink

* Aplicaciones integradas con optimización táctil clave, incluidas Microsoft Edge, OneNote, Calendario y cámara

El uso del entorno ltsc de Windows 10 Enterprise en dispositivos Surface da como resultado experiencias de usuario final sub-óptimas y debes evitar usarlo en entornos donde los usuarios desean y esperan una experiencia de usuario premium y actualizada.

La opción de mantenimiento LTSC está diseñada para los tipos de dispositivos y escenarios en los que el atributo clave es para que las características o funcionalidades nunca cambien. Algunos ejemplos son los sistemas de fabricación de energía o equipos médicos, o sistemas incrustados en quioscos, como cajeros automáticos o sistemas de venta de entradas de aeropuerto.

>[!NOTE]
>Para obtener información general sobre Windows de mantenimiento, incluido LTSC, vea [Overview of Windows como servicio](/windows/deployment/update/waas-overview).

Como directriz general, los dispositivos que cumplen los siguientes criterios se consideran dispositivos de uso general y deben emparejarse con Windows 10 Pro o Windows 10 Enterprise mediante la opción de mantenimiento del canal Semi-Annual:

* Dispositivos que ejecutan software de productividad como Microsoft Office

* Dispositivos que usan Microsoft Store aplicaciones

* Dispositivos que se usan para la exploración general de Internet (por ejemplo, investigación o acceso a redes sociales)

Antes de elegir usar la Windows 10 Enterprise LTSC en dispositivos Surface, tenga en cuenta las siguientes limitaciones:

* Las actualizaciones de controladores y firmware no se prueban explícitamente en las versiones de Windows 10 Enterprise LTSC.

* Si tiene problemas, el Soporte técnico de Microsoft proporcionará asistencia para solucionar problemas. Sin embargo, debido a la naturaleza de mantenimiento de la LTSC de Windows, la resolución de problemas puede requerir que los dispositivos se actualicen a una versión más reciente de Windows 10 Enterprise LTSC o Windows 10 Pro o Enterprise con la opción de mantenimiento SAC.

* Los reemplazos de dispositivos Surface (por ejemplo, dispositivos reemplazados en garantía) pueden contener variaciones sutiles en los componentes de hardware que requieren controladores de dispositivo y firmware actualizados. La compatibilidad con estas actualizaciones puede requerir la instalación de una versión más reciente de Windows 10 Enterprise LTSC o Windows 10 Pro o Enterprise con la opción de mantenimiento sac.

>[!NOTE]
>Es posible que las organizaciones que se estandarizan en una versión específica de Windows 10 Enterprise LTSC no puedan adoptar nuevas generaciones de hardware de Surface, como Surface Pro 8, Surface Pro X o Surface Laptop 4 sin actualizar a una versión posterior de Windows 10 Enterprise LTSC o Windows 10 Pro o Enterprise. Para obtener más información, consulte las preguntas [más frecuentes sobre el ciclo de vida: Windows](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--).

Los dispositivos Surface Windows 10 Enterprise la edición LTSC no recibirán nuevas características. En muchos casos, los clientes solicitan estas características para mejorar la facilidad de uso y las capacidades del hardware de Surface. Por ejemplo, mejoras adicionales para aplicaciones de ppp altos en Windows 10, versión 1703. Los clientes que usan dispositivos Surface en la configuración ltsc no verán las mejoras hasta que actualicen a una nueva versión de Windows 10 Enterprise LTSC o actualicen a una versión de Windows 10 con compatibilidad con la opción de mantenimiento sac.

Los dispositivos se pueden cambiar de Windows 10 Enterprise LTSC a una versión más reciente de Windows 10 Enterprise, con compatibilidad con la opción de mantenimiento sac, sin perder datos de usuario mediante la instalación de una actualización. También puede realizar una instalación de actualización en varios dispositivos aprovechando las plantillas de secuencia de tareas de actualización disponibles en microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager. Para obtener más información, consulta [Actualizar dispositivos Surface a Windows 10 con Microsoft Deployment Toolkit](upgrade-surface-devices-to-windows-10-with-mdt.md).

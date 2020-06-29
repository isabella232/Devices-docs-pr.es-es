---
title: Compatibilidad del dispositivo Surface con el canal de mantenimiento a largo plazo de Windows 10 (Surface)
description: Más información sobre la compatibilidad y las limitaciones de los dispositivos Surface que ejecutan Windows 10 Enterprise LTSB Edition.
keywords: ltsb, actualizar, opciones de mantenimiento de Surface
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834290"
---
# Compatibilidad del dispositivo Surface con el canal de mantenimiento a largo plazo de Windows 10 (LTSC)

Los dispositivos Surface están diseñados para ofrecer las mejores experiencias en la productividad y en escenarios de propósito general. Las actualizaciones periódicas permiten que los dispositivos Surfaces aporten nuevas innovaciones y evolucionen con las nuevas capacidades que ofrecen las actualizaciones de características de Windows 10. Las actualizaciones de características solo están disponibles en Windows 10 Pro o Windows 10 Enterprise Edition que reciben actualizaciones continuas a través del canal semianual (SAC).

A diferencia de la opción de mantenimiento de SAC, anteriormente conocida como rama actual (CB) o rama actual para empresas (CBB), no puede seleccionar la opción canal de mantenimiento de larga duración (LTSC) en configuración de Windows 10. Para usar la opción de mantenimiento LTSC, debe instalar una edición independiente de Windows 10 Enterprise, conocida como Windows 10 Enterprise LTSC, anteriormente conocida como Windows 10 Enterprise LTSB (rama de mantenimiento a largo plazo. Además de ofrecer un modelo de servicio ampliado, Windows 10 Enterprise LTSC Edition también proporciona un entorno con varios componentes de Windows que se han quitado. Entre las experiencias de superficie básicas afectadas por LTSC se incluyen:

* Actualizaciones de características de Windows, incluidas mejoras como:

  *  Mejoras en la entrada de lápiz directo y la palma de la mano proporcionadas en Windows 10, versión 1607 (también conocida como actualización de aniversario)
  *  Se ha mejorado la compatibilidad con aplicaciones de alta resolución de PPP proporcionadas en Windows 10, versión 1703 (también conocida como la actualización de Creators)

* Configuración de sensibilidad a la presión proporcionada por la aplicación de Surface

* Área de trabajo de Windows Ink

* Aplicaciones integradas y optimizadas para toque clave como Microsoft Edge, OneNote, calendario y cámara

El uso del entorno de LTSC empresarial de Windows 10 en dispositivos Surface da lugar a experiencias de usuario final óptimas y debe evitar usarlos en entornos en los que los usuarios quieran y esperen una experiencia de usuario actualizada y actualizada.

La opción de mantenimiento LTSC está diseñada para tipos de dispositivos y escenarios en los que el atributo clave es para que las características o la funcionalidad no cambien nunca. Algunos ejemplos son los sistemas que fabrican energía o equipos médicos, o los sistemas incorporados en quioscos, como los cajeros automáticos o los sistemas de vales de aeropuertos.

>[!NOTE]
>Para obtener información general sobre las ramas de mantenimiento de Windows, incluido LTSC, vea [información general de Windows como un servicio](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch).

Como pauta general, los dispositivos que cumplen los siguientes criterios se consideran dispositivos de propósito general y deben estar emparejados con Windows 10 Pro o Windows 10 Enterprise mediante la opción de mantenimiento de canal semianual:

* Dispositivos que ejecutan software de productividad como Microsoft Office

* Dispositivos que usan aplicaciones de Microsoft Store

* Dispositivos que se usan para la exploración general de Internet (por ejemplo, investigación o acceso a redes sociales)

Antes de elegir usar Windows 10 Enterprise LTSC Edition en dispositivos Surface, tenga en cuenta las siguientes limitaciones:

* Las actualizaciones de drivers y firmware no se prueban explícitamente en las versiones de Windows 10 Enterprise LTSC.

* Si encuentra problemas, el soporte técnico de Microsoft proporcionará ayuda para la solución de problemas. Sin embargo, debido al tipo de servicio de la LTSC de Windows, la resolución de problemas puede requerir que los dispositivos se actualicen a una versión más reciente de Windows 10 Enterprise LTSC o a Windows 10 Pro o Enterprise con la opción de servicio SAC.

* Las sustituciones de dispositivos Surface (por ejemplo, los dispositivos reemplazados bajo garantía) pueden contener variaciones sutiles en componentes de hardware que requieren controladores de dispositivo actualizados y firmware. Es posible que la compatibilidad con estas actualizaciones requiera la instalación de una versión más reciente de Windows 10 Enterprise LTSC o Windows 10 Pro o Enterprise con la opción de mantenimiento SAC.

>[!NOTE]
>Las organizaciones que estandarizan en una versión específica de Windows 10 Enterprise LTSC no pueden adoptar nuevas generaciones de hardware Surface, como Surface Pro 7, Surface Pro X o Surface Laptop 3 sin actualizar también a una versión posterior de Windows 10 Enterprise LTSC o Windows 10 Pro o Enterprise. Para obtener más información, consulte el tema **¿cómo se admitirá Windows 10 LTSBs?** tema en la sección **compatibilidad con los últimos procesadores y conjuntos de chips de Windows** de la sección [preguntas más frecuentes sobre la Directiva de ciclo de vida: productos de Windows](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4).

Los dispositivos Surface que ejecutan Windows 10 Enterprise LTSC Edition no recibirán las nuevas características. En muchos casos, estas características son solicitadas por los clientes para mejorar la facilidad de uso y las capacidades del hardware de la superficie. Por ejemplo, nuevas mejoras para aplicaciones de alta resolución de PPP en Windows 10, versión 1703. Los clientes que usan dispositivos Surface en la configuración de LTSC no verán las mejoras hasta que actualicen una nueva versión de Windows 10 Enterprise LTSC o actualicen a una versión de Windows 10 con compatibilidad para la opción de servicio SAC.

Los dispositivos se pueden cambiar en Windows 10 Enterprise LTSC a una versión más reciente de Windows 10 Enterprise, con compatibilidad para la opción de mantenimiento SAC, sin pérdida de datos de usuario al realizar una instalación de actualización. También puede realizar una instalación de actualización en varios dispositivos aprovechando las plantillas de secuencia de tareas de actualización disponibles en Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager. Para obtener más información, consulte [actualizar dispositivos Surface a Windows 10 con Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt).

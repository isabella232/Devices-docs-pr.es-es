---
title: Administrar actualizaciones de Windows en Surface Hub
description: Describe los procedimientos recomendados para administrar actualizaciones en Microsoft Surface Hub o Surface Hub 2S.
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: administrar actualizaciones de Windows, Surface Hub, Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: d6b95ac565132c4e4f1632c2abaffa13ddb2c54c
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142899"
---
# Administrar actualizaciones de Windows en Surface Hub

Las nuevas versiones del sistema operativo de Surface Hub se publican a través de Windows Update, igual que las versiones de Windows 10. Esta página explica los procedimientos recomendados para administrar actualizaciones de dispositivos Surface Hub. 

## Windows Update para empresas

Windows Update para empresas es un conjunto de características diseñadas para proporcionar a las empresas un control adicional sobre cómo y cuándo instala Windows Update las versiones, a la vez que reduce los costos de administración de dispositivos. Con este método, los Surface Hubs están conectados directamente al servicio Windows Update de Microsoft.

- Recibir actualizaciones directamente del servicio Windows Update de Microsoft, sin ninguna infraestructura adicional necesaria. 
- Aplazar actualizaciones para proporcionar más tiempo para pruebas y evaluaciones. 
- Implementar actualizaciones para seleccionar grupos de dispositivos. 
- Definir ventanas de mantenimiento para instalar actualizaciones. 

> [!TIP]
> Usar el uso compartido de contenido de punto a punto para reducir los problemas de ancho de banda durante las actualizaciones. Consulta [Optimizar la distribución de actualizaciones de Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates) para obtener más información.

> [!NOTE]
> Surface Hub no admite actualmente revertir las actualizaciones.


## Modelo de mantenimiento de Surface Hub

Surface Hub usa el modelo de mantenimiento de Windows 10, que se denomina [Windows como servicio (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Tradicionalmente, las nuevas características se agregan solo en las nuevas versiones de Windows que se publican cada pocos años. Cada nueva versión requiere implementar procesos largos y costosos en una organización. Como resultado, los usuarios finales y las organizaciones no suelen disfrutar de las ventajas de las nuevas innovaciones. El objetivo de Windows como servicio es proporcionar continuamente nuevas funcionalidades y mantener al mismo tiempo un alto nivel de calidad.

Microsoft publica dos tipos de versiones de Surface Hub ampliamente de manera continua:
- **Actualizaciones de características** - Actualizaciones que instalan las funciones, experiencias y capacidades nuevas más recientes. Microsoft espera publicar dos nuevas actualizaciones de características por año.
- **Actualizaciones de calidad** - Actualizaciones que se centran en la instalación de revisiones de seguridad, controladores y otras actualizaciones de mantenimiento. Microsoft espera publicar una actualización de calidad acumulativa cada mes.

A fin de mejorar la calidad de las versiones y simplificar las implementaciones, todas las nuevas versiones que Microsoft publique para Windows 10, incluidas las de Surface Hub, serán acumulativas. Esto significa que las nuevas actualizaciones de características y de calidad incluirán las cargas de todas las versiones anteriores (de forma optimizada para reducir los requisitos de almacenamiento y de redes) y la instalación de la versión en un dispositivo hará que este esté totalmente actualizado. Además, a diferencia de las versiones anteriores de Windows, no puedes instalar un subconjunto del contenido de una actualización de calidad de Windows 10. Por ejemplo, si una actualización de calidad incluye correcciones para tres vulnerabilidades de seguridad y un problema de confiabilidad, la implementación de la actualización dará como resultado la instalación de las cuatro correcciones.

El sistema operativo de Surface Hub recibe actualizaciones en el [Canal semianual](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Al igual que otras ediciones de Windows 10, el período de duración de mantenimiento es finito. Debes instalar actualizaciones de nuevas características en equipos que ejecuten estas ramas para seguir recibiendo actualizaciones de calidad.

Para obtener más información acerca de Windows como servicio, consulta [Información general de Windows como servicio](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Usar Windows Update para empresas

Surface Hubs, como todos los dispositivos Windows 10, incluye **Windows Update para empresas (WUfB)** que te permite controlar cómo se actualizan los dispositivos. Windows Update para empresas ayuda a reducir los costos de administración de dispositivos y ofrece el control sobre la implementación de actualizaciones, así como acceso rápido a actualizaciones de seguridad y a las últimas innovaciones de Microsoft de manera continua. Para obtener más información, consulta [Administrar actualizaciones con Windows Update para empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**Para configurar Windows Update para empresas:**
1. [Agrupar Surface Hub en anillos de implementación](#group-surface-hub-into-deployment-rings)
2. [Configurar cuándo recibe actualizaciones Surface Hub](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> Puede usar Microsoft Intune, Microsoft Endpoint Configuration Manager o un proveedor de MDM de terceros compatible para configurar WUfB. [Tutorial: usar Microsoft InTune para configurar Windows Update para empresas.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Agrupar Surface Hub en anillos de implementación

Usa anillos de implementación para controlar cuándo se lanzan las actualizaciones para tus Surface Hubs, dándote tiempo para que las valides. Por ejemplo, puedes actualizar un grupo reducido de dispositivos para comprobar la calidad antes de realizar un lanzamiento general en tu organización. En función de quién administre Surface Hub en tu organización, considera la posibilidad de incorporar Surface Hub en los anillos de implementación generados para tus otros dispositivos Windows 10. Para obtener más información acerca de los anillos de implementación, consulta [Generar anillos de implementación para las actualizaciones de Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

Consulte la tabla siguiente para obtener ejemplos de anillos de implementación.

| Anillo de implementación | Tamaño del anillo | Rama de mantenimiento | Aplazamiento para actualizaciones de características | Aplazamiento para actualizaciones de calidad (revisiones de seguridad, controladores y otras actualizaciones) | Paso de validación |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Versión preliminar (por ejemplo, dispositivos de prueba o que no sean imprescindibles) | Pequeña | Windows Insider Preview | Ninguno.  | Ninguno.  | Probar y evaluar la nueva funcionalidad manualmente. Pausar actualizaciones si hay problemas. |
| Versión publicada (por ejemplo, los dispositivos que usan equipos seleccionados) | Media | Canal semianual  | Ninguno. | Ninguno.  | Supervisar uso de dispositivos y comentarios de los usuarios. Pausar actualizaciones si hay problemas. |
| Implementación general (por ejemplo, la mayoría de los dispositivos de la organización) | Grande | Canal semianual |  120 días después del lanzamiento. | 7-14 días después del lanzamiento. | Supervisar uso de dispositivos y comentarios de los usuarios. Pausar actualizaciones si hay problemas. |
| Crítica (por ejemplo, los dispositivos en salas de reuniones de ejecutivos) | Pequeña | Canal semianual |  180 días después del lanzamiento (aplazamiento máximo para actualizaciones de características). | 30 días después del lanzamiento (aplazamiento máximo para actualizaciones de calidad). | Supervisar uso de dispositivos y comentarios de los usuarios. |


### Configurar cuándo recibe actualizaciones Surface Hub

Cuando hayas determinado los anillos de implementación para los Surface Hubs, configura directivas de aplazamiento de las actualizaciones para cada anillo:
- Para aplazar las actualizaciones de características, establece una directiva [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) para cada anillo.
- Para aplazar actualizaciones de calidad, establece una directiva [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) para cada anillo.

> [!NOTE]
> Si se producen problemas durante el lanzamiento de las actualizaciones, puedes pausarlas mediante [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) y [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).

**Si usas un servidor proxy u otro método para bloquear las direcciones URL**

Agregue las siguientes direcciones URL de sitios de confianza de Windows Update a la "lista de permitidos":
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Una vez instalada la Actualización de aniversario de Windows 10 Team, puedes quitar estas direcciones para restablecer Surface Hub a su estado anterior.

## Ventana de mantenimiento

Para garantizar que el dispositivo está siempre disponible para su uso durante las horas laborables, Surface Hub realiza sus funciones administrativas durante una ventana de mantenimiento especificada. Durante la ventana de mantenimiento, Surface Hub instala automáticamente las actualizaciones a través de Windows Update y reinicia el dispositivo 20 minutos antes del final de la ventana.

Surface Hub sigue estas directrices para aplicar las actualizaciones:
- Instala la actualización durante la siguiente ventana de mantenimiento. Si una reunión está programada para iniciarse durante el mantenimiento o si los sensores de Surface Hub detectan que se está usando el dispositivo, se pospondrá la actualización pendiente hasta la siguiente ventana de mantenimiento.
- Si la siguiente ventana de mantenimiento es después del período de gracia especificado de la actualización, el dispositivo calculará la siguiente ranura disponible durante las horas laborables usando el tiempo estimado de instalación a partir de los metadatos de la actualización. Continuará posponiendo la actualización si se ha programado una reunión o si los sensores de Surface Hub detectan que el dispositivo esté en uso.
- Si la siguiente ventana de mantenimiento **no** supera el período de gracia de la actualización, el Surface Hub seguirá pospuesto la actualización.
- Si se necesita reiniciar, el Surface Hub se reiniciará automáticamente durante la siguiente ventana de mantenimiento.

> [!NOTE]
> Reserva tiempo para las actualizaciones cuando configures por primera vez tu Surface Hub. Por ejemplo, un trabajo pendiente de definiciones de virus puede estar disponible y deberá instalarse inmediatamente.

Se establece una ventana de mantenimiento predeterminada para todos los Surface Hubs nuevos:
-   **Hora de Inicio:** 2:00 AM
-   **Duración:** 2 horas

**Para cambiar manualmente la ventana de mantenimiento:**
1.  Abre **Configuración** en tu Surface Hub.
2.  Ve a **Actualización y seguridad** > **Windows Update** > **Opciones avanzadas**.
3.  En **Horas de mantenimiento**, selecciona **Cambiar**.

Para cambiar la ventana de mantenimiento con MDM, establece el nodo **MOMAgent** en el [proveedor de servicios de configuración de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). Consulta [Administrar la configuración con un proveedor de MDM](manage-settings-with-mdm-for-surface-hub.md) para obtener más información.


## Más información

- [Entrada de blog: mantenimiento, vuelo y administración de actualizaciones de Surface Hub (con Intune, por supuesto)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)


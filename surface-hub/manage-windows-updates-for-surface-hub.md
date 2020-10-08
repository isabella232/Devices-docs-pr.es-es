---
title: Manage Windows updates on Surface Hub
description: You can manage Windows updates on your Microsoft Surface Hub or Surface Hub 2S by setting the maintenance window, deferring updates, or using Windows Server Update Services (WSUS).
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: manage Windows updates, Surface Hub, Windows Server Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103794"
---
# Manage Windows updates on Surface Hub

New releases of the Surface Hub operating system are published through Windows Update, just like releases of Windows 10. Hay un par de formas de administrar qué actualizaciones se instalan en los Surface Hubs y el tiempo en el que se aplican las actualizaciones.
- **Windows Update para empresas** - Nuevo en Windows 10, Windows Update para empresas es un conjunto de características que proporcionan un mayor control a las empresas sobre cómo y cuándo Windows Update instala versiones, permitiendo al mismo tiempo reducir los costes de administración de los dispositivos. Con este método, los Surface Hubs están conectados directamente al servicio Windows Update de Microsoft.
- **Windows Server Update Services (WSUS)** - Conjunto de servicios que permite a los administradores de TI obtener las actualizaciones que Windows Update determina que son aplicables para los dispositivos de su empresa, realizar pruebas y evaluaciones adicionales de las actualizaciones y seleccionar las que quieran instalar. Con este método, los Surface Hubs recibirán actualizaciones de WSUS en lugar de Windows Update.

También puedes configurar el Surface Hub para recibir actualizaciones tanto de Windows Update para empresas como de WSUS. Consulta [Integrar Windows Update para empresas con Windows Server Update Services](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services) para obtener más información.

| Funcionalidades | Windows Update para empresas | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| Recibir actualizaciones directamente del servicio Windows Update de Microsoft, sin ninguna infraestructura adicional necesaria.  | Sí  | No  |
| Aplazar actualizaciones para proporcionar más tiempo para pruebas y evaluaciones. | Sí  | Sí  |
| Implementar actualizaciones para seleccionar grupos de dispositivos. | Sí | Sí |
| Definir ventanas de mantenimiento para instalar actualizaciones. | Sí  | Sí  |

> [!TIP]
> Usar el uso compartido de contenido de punto a punto para reducir los problemas de ancho de banda durante las actualizaciones. Consulta [Optimizar la distribución de actualizaciones de Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates) para obtener más información.

> [!NOTE]
> Surface Hub no admite actualmente revertir las actualizaciones.


## Modelo de mantenimiento de Surface Hub

Surface Hub usa el modelo de mantenimiento de Windows 10, que se denomina [Windows como servicio (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Tradicionalmente, las nuevas características se agregan solo en las nuevas versiones de Windows que se publican cada pocos años. Cada nueva versión requiere implementar procesos largos y costosos en una organización. Como resultado, los usuarios finales y las organizaciones no suelen disfrutar de las ventajas de las nuevas innovaciones. El objetivo de Windows como servicio es proporcionar continuamente nuevas funcionalidades y mantener al mismo tiempo un alto nivel de calidad.

Microsoft publica dos tipos de versiones de Surface Hub ampliamente de manera continua:
- **Feature updates** - Updates that install the latest new features, experiences, and capabilities. Microsoft expects to publish two new feature updates per year.
- **Quality updates** - Updates that focus on the installation of security fixes, drivers, and other servicing updates. Microsoft espera publicar una actualización de calidad acumulativa cada mes.

A fin de mejorar la calidad de las versiones y simplificar las implementaciones, todas las nuevas versiones que Microsoft publique para Windows 10, incluidas las de Surface Hub, serán acumulativas. Esto significa que las nuevas actualizaciones de características y de calidad incluirán las cargas de todas las versiones anteriores (de forma optimizada para reducir los requisitos de almacenamiento y de redes) y la instalación de la versión en un dispositivo hará que este esté totalmente actualizado. Además, a diferencia de las versiones anteriores de Windows, no puedes instalar un subconjunto del contenido de una actualización de calidad de Windows 10. Por ejemplo, si una actualización de calidad incluye correcciones para tres vulnerabilidades de seguridad y un problema de confiabilidad, la implementación de la actualización dará como resultado la instalación de las cuatro correcciones.

The Surface Hub operating system receives updates on the [Semi-Annual Channel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Like other editions of Windows 10, the servicing lifetime is finite. You must install new feature updates on machines running these branches in order to continue receiving quality updates.

Para obtener más información acerca de Windows como servicio, consulta [Información general de Windows como servicio](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Usar Windows Update para empresas
Surface Hubs, como todos los dispositivos Windows 10, incluye **Windows Update para empresas (WUfB)** que te permite controlar cómo se actualizan los dispositivos. Windows Update para empresas ayuda a reducir los costos de administración de dispositivos y ofrece el control sobre la implementación de actualizaciones, así como acceso rápido a actualizaciones de seguridad y a las últimas innovaciones de Microsoft de manera continua. Para obtener más información, consulta [Administrar actualizaciones con Windows Update para empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

**Para configurar Windows Update para empresas:**
1. [Agrupar Surface Hub en anillos de implementación](#group-surface-hub-into-deployment-rings)
2. [Configure when Surface Hub receives updates](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> You can use Microsoft Intune, Microsoft Endpoint Configuration Manager, or a supported third-party MDM provider to set up WUfB. [Walkthrough: use Microsoft Intune to configure Windows Update for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Agrupar Surface Hub en anillos de implementación
Usa anillos de implementación para controlar cuándo se lanzan las actualizaciones para tus Surface Hubs, dándote tiempo para que las valides. Por ejemplo, puedes actualizar un grupo reducido de dispositivos para comprobar la calidad antes de realizar un lanzamiento general en tu organización. En función de quién administre Surface Hub en tu organización, considera la posibilidad de incorporar Surface Hub en los anillos de implementación generados para tus otros dispositivos Windows 10. Para obtener más información acerca de los anillos de implementación, consulta [Generar anillos de implementación para las actualizaciones de Windows10](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

En esta tabla encontrarás ejemplos de anillos de implementación.

| Anillo de implementación | Tamaño del anillo | Rama de mantenimiento | Aplazamiento para actualizaciones de características | Aplazamiento para actualizaciones de calidad (revisiones de seguridad, controladores y otras actualizaciones) | Paso de validación |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Versión preliminar (por ejemplo, dispositivos de prueba o que no sean imprescindibles) | Small | Windows Insider Preview | None.  | Ninguno.  | Probar y evaluar la nueva funcionalidad manualmente. Pausar actualizaciones si hay problemas. |
| Versión publicada (por ejemplo, los dispositivos que usan equipos seleccionados) | Media | Canal semianual  | Ninguno. | Ninguno.  | Supervisar uso de dispositivos y comentarios de los usuarios. Pausar actualizaciones si hay problemas. |
| Implementación general (por ejemplo, la mayoría de los dispositivos de la organización) | Grande | Canal semianual |  120 días después del lanzamiento. | 7-14 días después del lanzamiento. | Supervisar uso de dispositivos y comentarios de los usuarios. Pausar actualizaciones si hay problemas. |
| Crítica (por ejemplo, los dispositivos en salas de reuniones de ejecutivos) | Pequeña | Canal semianual |  180 días después del lanzamiento (aplazamiento máximo para actualizaciones de características). | 30 días después del lanzamiento (aplazamiento máximo para actualizaciones de calidad). | Supervisar uso de dispositivos y comentarios de los usuarios. |





### Configurar cuándo recibe actualizaciones Surface Hub
Cuando hayas determinado los anillos de implementación para los Surface Hubs, configura directivas de aplazamiento de las actualizaciones para cada anillo:
- Para aplazar las actualizaciones de características, establece una directiva [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) para cada anillo.
- Para aplazar actualizaciones de calidad, establece una directiva [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) para cada anillo.

> [!NOTE]
> Si se producen problemas durante el lanzamiento de las actualizaciones, puedes pausarlas mediante [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) y [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).


## Usar Windows Server Update Services

Puedes conectar Surface Hub al servidor de Windows Server Update Services (WSUS) para administrar las actualizaciones. Las actualizaciones se controlarán mediante aprobaciones o reglas de implementación automáticas configuradas en el servidor WSUS, por lo que no se implementarán las nuevas actualizaciones hasta que decidas implementarlas.

**Para conectar manualmente un Surface Hub a un servidor WSUS:**
1. Abre **Configuración** en tu Surface Hub.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Ve a **Actualización y seguridad** > **Windows Update** > **Opciones avanzadas** > **Configurar el servidor Windows Server Update Services (WSUS)**.
4. Haz clic en **Usar el servidor WSUS para descargar actualizaciones** y escribe la dirección URL de tu servidor WSUS.

Para conectar Surface Hub a un servidor WSUS con MDM, establece una directiva [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl) adecuada.

**Si usas un servidor proxy u otro método para bloquear las direcciones URL**

Si usas un método distinto de WSUS para bloquear determinadas direcciones URL y evitar las actualizaciones, tendrás que agregar las siguientes direcciones URL del sitio de confianza de Windows Update a la lista de direcciones permitidas:
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Una vez instalada la Actualización de aniversario de Windows 10 Team, puedes quitar estas direcciones para restablecer Surface Hub a su estado anterior.

## Ventana de mantenimiento

To ensure the device is always available for use during business hours, Surface Hub performs its administrative functions during a specified maintenance window. During the maintenance window, the Surface Hub automatically installs updates through Windows Update or WSUS, and reboots the device 20 minutes before the end of the window.

Surface Hub follows these guidelines to apply updates:
- Instala la actualización durante la siguiente ventana de mantenimiento. Si una reunión está programada para iniciarse durante el mantenimiento o si los sensores de Surface Hub detectan que se está usando el dispositivo, se pospondrá la actualización pendiente hasta la siguiente ventana de mantenimiento.
- Si la siguiente ventana de mantenimiento es después del período de gracia especificado de la actualización, el dispositivo calculará la siguiente ranura disponible durante las horas laborables usando el tiempo estimado de instalación a partir de los metadatos de la actualización. Continuará posponiendo la actualización si se ha programado una reunión o si los sensores de Surface Hub detectan que el dispositivo esté en uso.
- If the next maintenance window is **not** past the update's grace period, the Surface Hub will continue to postpone the update.
- If a reboot is needed, the Surface Hub will automatically reboot during the next maintenance window.

> [!NOTE]
> Reserva tiempo para las actualizaciones cuando configures por primera vez tu Surface Hub. Por ejemplo, un trabajo pendiente de definiciones de virus puede estar disponible y deberá instalarse inmediatamente.

A default maintenance window is set for all new Surface Hubs:
-   **Start time:** 2:00 AM
-   **Duration:** 2 hours

**To manually change the maintenance window:**
1.  Abre **Configuración** en tu Surface Hub.
2.  Ve a **Actualización y seguridad** > **Windows Update** > **Opciones avanzadas**.
3.  En **Horas de mantenimiento**, selecciona **Cambiar**.

Para cambiar la ventana de mantenimiento con MDM, establece el nodo **MOMAgent** en el [proveedor de servicios de configuración de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for more details.


## More information

- [Blog post: Servicing, Flighting, and Managing updates for Surface Hub (With Intune, of course!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Related topics

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)


---
title: Administrar e implementar actualizaciones de controladores y firmware de Surface
description: En este artículo se explican las opciones disponibles para administrar e implementar actualizaciones de firmware y controladores para dispositivos Surface.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, actualización, dispositivo, administrar, implementar, controlador, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: afc7b2e82519fb42ca07b107bff73ddea894cfdf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911645"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Administrar e implementar actualizaciones de controladores y firmware de Surface

La forma en que administras las actualizaciones de controladores y firmware de Surface varía en función de los requisitos del entorno y de la organización. En dispositivos Surface, el firmware se expone al sistema operativo como controlador y está visible en el Administrador de dispositivos. Esto permite que el firmware y los controladores del dispositivo se actualicen automáticamente Windows Update o Windows Update for Business. Aunque este enfoque simplificado puede ser viable para las startups y las pequeñas o medianas empresas, las organizaciones más grandes normalmente necesitan que los administradores de TI distribuyan las actualizaciones internamente. Esto puede implicar una planeación completa, pruebas de compatibilidad de aplicaciones y pruebas piloto y validación de actualizaciones antes de la aprobación y distribución finales en toda la red.

> [!NOTE]
> Este artículo está pensado para agentes de soporte técnico y profesionales de TI y se aplica solo a dispositivos Surface. Si buscas ayuda para instalar actualizaciones de Surface o firmware en un dispositivo principal, consulta Actualizar el firmware de [Surface y Windows 10](https://support.microsoft.com/help/4023505).

Aunque las soluciones de distribución de software de nivel empresarial siguen evolucionando, la lógica empresarial para administrar las actualizaciones de forma centralizada sigue siendo la misma: mantener la seguridad de los dispositivos Surface y mantenerlos actualizados con las mejoras más recientes del sistema operativo y las características. Esto es esencial para mantener un entorno de producción estable y asegurarse de que los usuarios no se bloqueen para que no sean productivos. En este artículo se proporciona información general sobre las herramientas y los procesos recomendados para que las organizaciones más grandes cumplan estos objetivos.

## <a name="central-update-management-in-commercial-environments"></a>Administración de actualizaciones centrales en entornos comerciales

Microsoft tiene herramientas optimizadas para administrar dispositivos (incluidas las actualizaciones de controladores y firmware) en una única experiencia unificada que se denomina [Microsoft Endpoint Manager centro](https://devicemanagement.microsoft.com/) de administración y a la que se accede desde [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home).

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Administrar actualizaciones con Configuration Manager e Intune

Microsoft Endpoint Configuration Manager permite sincronizar e implementar actualizaciones de controladores y firmware de Surface con el cliente de Configuration Manager. La integración con Microsoft Intune le permite ver todos los dispositivos administrados, administrados por el asociado y administrados por asociados en un solo lugar. Esta es la solución recomendada para que las grandes organizaciones administren las actualizaciones de Surface.

Para ver los pasos detallados, consulte los siguientes recursos:

- [Administrar actualizaciones de controladores de Surface en Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentación de Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Administrar actualizaciones con Microsoft Deployment Toolkit

Microsoft Deployment Toolkit (MDT) se incluye en Endpoint Configuration Manager. Contiene herramientas de implementación opcionales que puede que desee usar, según el entorno. Estos incluyen el kit de evaluación e implementación de Windows (Windows ADK), Windows System Image Manager (Windows SIM), administración y mantenimiento de imágenes de implementación (DISM) y herramienta de migración de estado de usuario (USMT). Puede descargar la versión más reciente de MDT desde la página de descarga de [Microsoft Deployment Toolkit .](https://www.microsoft.com/download/details.aspx?id=54259)

Para ver los pasos detallados, consulte los siguientes recursos:

- [Documentación sobre Toolkit implementación de Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Implementar Windows 10 con Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implementar Windows 10 dispositivos Surface con Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Las actualizaciones de controladores y firmware de Surface se empaquetan como Windows installer (*.msi). Para implementar estos paquetes Windows Installer, puede usar Endpoint Configuration Manager o MDT. Para obtener información sobre cómo seleccionar el archivo .msi correcto para un dispositivo y un sistema operativo, consulte las instrucciones de las siguientes secciones sobre cómo descargar .msi archivos.

Para obtener instrucciones sobre cómo implementar actualizaciones mediante Endpoint Configuration Manager, vea [Deploy applications with Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Para obtener instrucciones sobre cómo implementar actualizaciones mediante MDT, vea [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Controladores y firmware de WindowsPE y Surface**

Endpoint Configuration Manager y MDT usan el Windows de preinstalación (WindowsPE) durante el proceso de implementación. WindowsPE solo admite un conjunto limitado de controladores básicos, como los de adaptadores de red y controladores de almacenamiento. Los controladores Windows componentes que no forman parte de WindowsPE pueden producir errores. Como práctica recomendada, puedes evitar estos errores configurando el proceso de implementación para usar solo los controladores necesarios durante la fase de WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

A partir de Endpoint Configuration Manager, puedes sincronizar e implementar actualizaciones de controladores y firmware de Microsoft Surface mediante el cliente de Configuration Manager. Para obtener información adicional, consulte KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>Dispositivos compatibles

Los archivos .msi están disponibles para Surface Pro dispositivos 2 y posteriores (excepto Surface Pro X que se ejecuta Windows 10 en ARM).

## <a name="managing-firmware-with-dfci"></a>Administración de firmware con DFCI

Al tener perfiles de interfaz de configuración de firmware de dispositivo (DFCI) integrados en Intune (ahora disponible en versión preliminar [pública),](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)la administración de UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware uefi. DFCI admite el aprovisionamiento sin intervención táctil, elimina las contraseñas de BIOS, proporciona control de la configuración de seguridad (incluidas las opciones de inicio y periféricos integrados) y establece las bases para escenarios de seguridad avanzados en el futuro. Para obtener más información, consulta los artículos siguientes:

- [Administración de Intune de la configuración de la UEFI de Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Anuncio de](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)la administración remota de la configuración de UEFI de Surface desde Intune .

## <a name="best-practices-for-update-deployment-processes"></a>Procedimientos recomendados para actualizar procesos de implementación

Para mantener un entorno estable, se recomienda encarecidamente mantener la paridad con la versión más reciente de Windows 10.  Para obtener recomendaciones de procedimientos recomendados, vea Crear anillos de implementación [para Windows 10 actualizaciones.](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

## <a name="downloadable-surface-update-packages"></a>Paquetes de actualización de Surface descargables

Las versiones específicas de Windows 10 tienen archivos .msi independientes, cada uno con todas las actualizaciones acumulativas de controladores y firmware necesarias para dispositivos Surface. Los paquetes de actualización pueden incluir algunos o todos los componentes siguientes:

- Wi-Fi y LTE
- Vídeo
- Unidad de estado sólido
- Módulo de agregador de sistema (SAM)
- Batería
- Controlador de teclado
- Controlador incrustado (EC)
- Motor de administración (ME)
- Interfaz de firmware extensible unificada (UEFI)

### <a name="downloading-msi-files"></a>Descargar archivos .msi archivos

1. Vaya a [Descargar controladores y firmware para Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) en el Centro de descarga de Microsoft.
2. Selecciona el .msi de archivo que coincida con el modelo de Surface y la versión de Windows. El .msi archivo incluye el número mínimo de Windows de compilación admitido que es necesario para instalar los controladores y el firmware. Por ejemplo, consulte la siguiente figura. Para actualizar un Surface Book 2 que tiene la compilación 18362 de Windows 10, **elijaSurfaceBook2_Win10_18362_19.101.13994.msi.** Para un Surface Book 2 que tiene la compilación 16299 de Windows 10, elija **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Figura 1. Descargar actualizaciones de Surface.](images/fig1-downloads-msi.png)

    *Figura 1. Descargar actualizaciones de Surface*

### <a name="surface-msi-naming-convention"></a>Convención .msi nomenclatura de Surface

Desde agosto de 2019, los .msi están usando la siguiente convención de nomenclatura:

- *Product*_*Windows release Windows*_ build number Version*number*_**_ Revision of version*number (typically zero)*.

**Por ejemplo:**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Este nombre de archivo proporciona la siguiente información:

- **Producto:** SurfacePro6
- **Windows versión:** Win10
- **Compilación:** 18362
- **Versión:** 19.073.44195: muestra la fecha y hora en que se creó el archivo, de la siguiente manera:
  - **Año:** 19 (2019)
  - **Mes y semana:** 073 (tercera semana de julio)
  - **Minuto del mes:** 44195
- **Revisión de la versión:** 0 (primera versión de esta versión)

### <a name="legacy-surface-msi-naming-convention"></a>Convención de nomenclatura .msi surface heredada

Los archivos .msi heredados (archivos que se crearon antes de agosto de 2019) siguieron la misma fórmula de nomenclatura general, pero usaron un método diferente para derivar el número de versión.

**Por ejemplo:**

- SurfacePro6_Win10_16299_1900307_0.msi

Este nombre de archivo proporciona la siguiente información:

- **Producto:** SurfacePro6
- **Windows versión:** Win10
- **Compilación:** 16299
- **Versión:** 1900307: muestra la fecha en que se creó el archivo y su posición en la secuencia de lanzamiento, de la siguiente manera:
  - **Año:** 19 (2019)
  - **Número de versión:** 003 (tercera versión del año)
  - **Número de versión del producto:** 07 (Surface Pro 6 es oficialmente la séptima versión de Surface Pro)
- **Revisión de la versión:** 0 (primera versión de esta versión)

## <a name="learn-more"></a>Obtén más información

- [Descargar controladores y firmware para Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Cómo administrar las actualizaciones de controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentación de Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/)
- [Documentación sobre Toolkit implementación de Microsoft](https://docs.microsoft.com/configmgr/mdt/)
- [Implementar Windows 10 con Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implementar Windows 10 dispositivos Surface con Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Administración de Intune de la configuración de la UEFI de Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019: Anuncio de](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)la administración remota de la configuración de UEFI de Surface desde Intune .
- [Generar anillos de implementación para las actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

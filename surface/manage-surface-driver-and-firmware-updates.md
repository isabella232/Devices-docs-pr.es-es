---
title: Administrar e implementar actualizaciones de controladores y firmware de Surface
description: En este artículo, se describen las opciones disponibles para administrar e implementar actualizaciones de firmware y controladores para dispositivos Surface.
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
ms.openlocfilehash: f41974193d62e4c0cbc1e286976105c20534d906
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897068"
---
# Administrar e implementar actualizaciones de controladores y firmware de Surface

El modo en que se administran las actualizaciones del controlador y firmware de la superficie varía según el entorno y los requisitos de la organización. En los dispositivos Surface, el firmware se expone al sistema operativo como un controlador y está visible en el administrador de dispositivos. Esto permite que el firmware y los drivers del dispositivo se actualicen automáticamente con Windows Update o Windows Update para empresas. Aunque este enfoque simplificado puede ser factible para los inicios y las pequeñas y medianas empresas, generalmente las organizaciones grandes necesitan que los administradores de ti distribuyan las actualizaciones internamente. Esto puede implicar una planificación completa, pruebas de compatibilidad de aplicaciones y pruebas piloto y validación de actualizaciones antes de la aprobación y distribución final en la red.

> [!NOTE]
> Este artículo está destinado a agentes de soporte técnico y profesionales de ti y se aplica únicamente a los dispositivos Surface. Si está buscando ayuda para instalar actualizaciones de Surface o firmware en un dispositivo doméstico, consulte [actualizar firmware de superficie y Windows 10](https://support.microsoft.com/help/4023505).

A pesar de que las soluciones de distribución de software para empresas siguen evolucionando, la lógica empresarial para la administración centralizada de las actualizaciones sigue siendo la misma: mantener la seguridad de los dispositivos de Surface y mantenerlos actualizados con el sistema operativo y las mejoras de características más recientes. Esto es esencial para mantener un entorno de producción estable y asegurarte de que no se bloquee a los usuarios para que no sean productivos. Este artículo proporciona una descripción general de las herramientas y los procesos recomendados para que las organizaciones grandes realicen estos objetivos.

## Administración de actualizaciones centralizada en entornos comerciales

Microsoft ha simplificado las herramientas de administración de dispositivos, entre las que se incluyen las actualizaciones de drivers y firmware, en una única experiencia unificada que se denomina [centro de administración de Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/) y a la que se accede desde [devicemanagement.Microsoft.com](https://devicemanagement.microsoft.com/#home).

### Administrar las actualizaciones con Configuration Manager e Intune

Microsoft Endpoint Configuration Manager le permite sincronizar e implementar el firmware de la superficie y las actualizaciones de controladores con el cliente de Configuration Manager. La integración con Microsoft Intune le permite ver todos los dispositivos administrados y administrados por el Partner en un solo lugar. Esta es la solución recomendada para que las grandes organizaciones administren actualizaciones de superficie.

Para conocer los pasos detallados, vea los siguientes recursos:

- [Administrar actualizaciones de controladores de Surface en Configuration Manager](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentación del administrador de configuración de extremos](https://docs.microsoft.com/configmgr/)

### Administrar las actualizaciones con Microsoft Deployment Toolkit

Microsoft Deployment Toolkit (MDT) se incluye en el administrador de configuración de extremo. Contiene herramientas de implementación opcionales que puede que quiera usar en función de su entorno. Estos incluyen el Windows Assessment and Deployment Kit (Windows ADK), el administrador de imágenes de sistema de Windows (Windows SIM), la administración y el mantenimiento de imágenes de implementación (DISM) y la herramienta de migración del estado de usuario (USMT). Puede descargar la última versión de MDT desde la [Página de descarga de Microsoft Deployment Toolkit](https://www.microsoft.com/download/details.aspx?id=54259).

Para conocer los pasos detallados, vea los siguientes recursos:

- [Documentación de Microsoft Deployment Toolkit](https://docs.microsoft.com/configmgr/mdt/)
- [Implementar Windows 10 con Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implementar Windows 10 en Surface Devices con Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Los drivers de Surface y las actualizaciones de firmware se empaquetan como archivos de Windows Installer (*. msi). Para implementar estos paquetes de Windows Installer, puede usar el administrador de configuración de extremos o MDT. Para obtener más información sobre cómo seleccionar el archivo. msi correcto para un dispositivo y sistema operativo, consulte las instrucciones de las secciones siguientes sobre la descarga de archivos. msi.

Para obtener instrucciones sobre cómo implementar actualizaciones con el administrador de configuración de extremos, consulte [implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications). Para obtener instrucciones sobre cómo implementar actualizaciones con MDT, consulte [implementar una imagen de Windows 10 con MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Drivers y firmware de superficie y WindowsPE**

El administrador de configuración de puntos de conexión y MDT usan el entorno de preinstalación de Windows (WindowsPE) durante el proceso de implementación. WindowsPE solo admite un conjunto limitado de controladores básicos, como los de los adaptadores de red y los controladores de almacenamiento. Los drivers de los componentes de Windows que no forman parte de WindowsPE pueden producir errores. Como práctica recomendada, puede evitar estos errores si configura el proceso de implementación para usar solo los drivers necesarios durante la fase WindowsPE.

### Endpoint Configuration Manager

A partir del extremo de Configuration Manager, puede sincronizar e implementar actualizaciones de controlador y firmware de Surface de Microsoft con el cliente de Configuration Manager. Para obtener más información, consulte KB 4098906, [Cómo administrar las actualizaciones de los controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## Dispositivos compatibles

Los archivos. msi descargables están disponibles para los dispositivos Surface Pro 2 y versiones posteriores. La información sobre los archivos. msi para los dispositivos de superficie más recientes, como Surface Pro 7 y Surface Laptop 3, estará disponible en esta página al soltarlo.

## Administración del firmware con DFCI

Al disponer de los perfiles de la interfaz de configuración de firmware (DFCI) de dispositivos integrados en Intune (ahora disponible en [Public Preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), la administración de Surface UEFI extiende la pila de administración moderna al nivel de hardware UEFI. DFCI es compatible con el aprovisionamiento sin contacto, elimina las contraseñas del BIOS, proporciona el control de la configuración de seguridad (incluidas las opciones de inicio y los periféricos incorporados) y establece las bases para escenarios de seguridad avanzada en el futuro. Para obtener más información, consulta los artículos siguientes:

- [Administración de Intune de la configuración de la UEFI de Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Encendido 2019: anuncio de la administración remota de la configuración de Surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Procedimientos recomendados para los procesos de implementación de actualizaciones

Para mantener un entorno estable, le recomendamos encarecidamente que mantenga la paridad con la versión más reciente de Windows 10.  Para obtener recomendaciones sobre prácticas recomendadas, consulte [crear timbres de implementación para actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).

## Paquetes de actualización superficial descargables

Las versiones específicas de Windows 10 tienen archivos. msi independientes, cada uno de los cuales contiene todas las actualizaciones de controlador y firmware acumulativas necesarias para los dispositivos Surface. Los paquetes de actualización pueden incluir algunos o todos los componentes siguientes:

- Wi-Fi y LTE
- Vídeo
- Unidad de estado sólido
- Módulo de agregador del sistema (SAM)
- Batería
- Controlador de teclado
- Controladora integrada (EC)
- Motor de administración (yo)
- Unified extensible firmware Interface (UEFI)

### Descargar archivos. msi

1. Explore para [Descargar drivers y firmware de Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) en el centro de descarga de Microsoft.
2. Seleccione el nombre de archivo. msi que coincida con el modelo de superficie y la versión de Windows. El nombre de archivo. msi incluye el número mínimo de compilación de Windows admitido que es necesario para instalar los drivers y el firmware. Por ejemplo, consulte la siguiente ilustración. Para actualizar una superficie de la libreta 2 que tiene la compilación 18362 de Windows 10, elija **SurfaceBook2_Win10_18362_19.101.13994.msi.** Para un libro de superficie 2 que tenga la compilación 16299 de Windows 10, elija **SurfaceBook2_Win10_16299_1803509_3.msi**.

    ![Figura 1. Descargar actualizaciones de superficie](images/fig1-downloads-msi.png)

    *Figura 1. Descargar actualizaciones de superficie*

### Convención de nomenclatura de Surface. msi

Desde agosto de 2019, los archivos. msi usan la Convención de nomenclatura siguiente:

- *Producto*_*Windows versión*_*compilación de Windows*número de_*versión*_*revisión del número de versión (normalmente, cero)*.

**Ejemplo**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Este nombre de archivo proporciona la siguiente información:

- **Producto:** SurfacePro6
- **Versión de Windows:** Win10
- **Compilación:** 18362
- **Versión:** 19.073.44195: muestra la fecha y la hora en que se creó el archivo, de la siguiente manera:
  - **Año:** 19 (2019)
  - **Mes y semana:** 073 (tercera semana de julio)
  - **Minuto del mes:** 44195
- **Revisión de la versión:** 0 (primera versión de esta versión)

### Convención de nomenclatura de la superficie heredada. msi

Los archivos. msi heredados (archivos que se crearon antes 2019 de agosto) siguieron la misma fórmula general de nomenclatura pero usaban un método diferente para derivar el número de versión.

**Ejemplo**

- SurfacePro6_Win10_16299_1900307_0.msi

Este nombre de archivo proporciona la siguiente información:

- **Producto:** SurfacePro6
- **Versión de Windows:** Win10
- **Compilación:** 16299
- **Versión:** 1900307: muestra la fecha en la que se creó el archivo y su posición en la secuencia de versiones, de la siguiente manera:
  - **Año:** 19 (2019)
  - **Número de versión:** 003 (tercera versión del año)
  - **Número de versión del producto:** 07 (Surface Pro 6 es oficialmente la séptima versión de Surface Pro).
- **Revisión de la versión:** 0 (primera versión de esta versión)

## Obtén más información

- [Descargar drivers y firmware para Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [Cómo administrar las actualizaciones de los controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implementar aplicaciones con Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [Documentación del administrador de configuración de extremos](https://docs.microsoft.com/configmgr/)
- [Documentación de Microsoft Deployment Toolkit](https://docs.microsoft.com/configmgr/mdt/)
- [Implementar Windows 10 con Microsoft Deployment Toolkit](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Implementar Windows 10 en Surface Devices con Microsoft Deployment Toolkit](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Administración de Intune de la configuración de la UEFI de Surface](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Encendido 2019: anuncio de la administración remota de la configuración de Surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Generar anillos de implementación para las actualizaciones de Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)

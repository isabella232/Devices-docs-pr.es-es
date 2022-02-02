---
title: Administrar e implementar actualizaciones de controladores y firmware de Surface
description: En este artículo se proporcionan vínculos a paquetes descargables que contienen actualizaciones de controladores y firmware para dispositivos Surface y se explican las soluciones de implementación y administración disponibles.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 8, Surface Go, Surface Laptop, Surface Studio, Surface Pro 3, firmware, actualización, dispositivo, administrar, implementar, controlador, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
ms.openlocfilehash: 6cfe5f44c156c8042172741739fffbfed3ceba07
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338583"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>Administrar e implementar actualizaciones de controladores y firmware de Surface

La forma en que administras las actualizaciones de controladores y firmware de Surface puede variar en función de los requisitos del entorno y de la organización. En organizaciones más grandes, los administradores de TI suelen realizar implementaciones internamente y asignar tiempo para probar las actualizaciones antes de implementarlas en dispositivos de usuario.

> [!NOTE]
> Este artículo está pensado para profesionales de TI y agentes de soporte técnico y se aplica solo a dispositivos Surface. Si buscas ayuda para instalar actualizaciones o firmware de Surface en un dispositivo principal, consulta [Descargar controladores y firmware para Surface](https://support.microsoft.com/help/4023505).

Aunque las soluciones de distribución de software de nivel empresarial siguen evolucionando, la lógica empresarial para administrar las actualizaciones de forma centralizada sigue siendo la misma: mantener la seguridad de los dispositivos Surface y mantenerlos actualizados con las mejoras más recientes del sistema operativo y las características. Esto es esencial para mantener un entorno de producción estable y asegurarse de que los usuarios no se bloqueen para que no sean productivos.

## <a name="whats-in-surface-driver-and-firmware-updates"></a>What's in Surface driver and firmware updates

Windows installer .msi contienen todas las actualizaciones de controladores y firmware acumulativas necesarias para dispositivos Surface. Los paquetes de actualización pueden incluir algunos o todos los componentes siguientes:

- Wi-Fi y LTE
- Vídeo
- Unidad de estado sólido
- Módulo de agregador de sistema (SAM)
- Batería
- Controlador de teclado
- Controlador incrustado (EC)
- Motor de administración (ME)
- Interfaz de firmware extensible unificada (UEFI)

## <a name="download-msi-files"></a>Descargar .msi archivos

En esta sección se proporcionan vínculos directos a paquetes descargables que contienen actualizaciones de controladores y firmware para dispositivos Surface. 

1. Seleccione Windows 10 o Windows 11 según corresponda. 
2. Para dispositivos con varios archivos .msi, selecciona el nombre de archivo .msi que coincida con el modelo de Surface y la versión de Windows implementados en tu organización.  


| Dispositivo Surface                                                                                                                                        | .msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ y Surface Pro 7+ (LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE)](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface Laptop**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop 4 con procesador Intel](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 con procesador AMD](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 con procesador Intel](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 con procesador AMD](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop Studio**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE)](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE): operador de Norteamérica desbloqueado](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE): fuera de Norteamérica y Y!mobile en Japón](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub ejecución** [**Windows 10 Pro o Windows 10 Enterprise**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub ejecutar Windows 10 Teams actualización de 2020**                                                                                                  | - Consulte [Manage Windows updates on Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> Para dispositivos anteriores que incluyen archivos independientes para diferentes Windows versiones, seleccione el nombre de archivo .msi que coincida con el modelo de Surface y la versión de Windows. El .msi archivo incluye el número mínimo de Windows de compilación admitido que es necesario para instalar los controladores y el firmware. Por ejemplo, para actualizar un Surface Book 2 que tiene la compilación 18362 de Windows 10, ** elijaSurfaceBook2_Win10_18362_19.101.13994.msi.** Para un Surface Book 2 que tiene la compilación 16299 de Windows 10, elija **SurfaceBook2_Win10_16299_1803509_3.msi**.

## <a name="central-update-management-in-commercial-environments"></a>Administración de actualizaciones centrales en entornos comerciales

Herramientas para administrar dispositivos, incluidas las actualizaciones de controladores y firmware, incluidas [en Microsoft Endpoint Manager](https://devicemanagement.microsoft.com/). 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>Administrar actualizaciones con Configuration Manager e Intune

Microsoft Endpoint Configuration Manager permite sincronizar e implementar actualizaciones de controladores y firmware de Surface con el cliente de Configuration Manager. La integración con Microsoft Intune le permite ver todos los dispositivos administrados, administrados por el asociado y administrados por asociados en un solo lugar. Esta es la solución recomendada para que las grandes organizaciones administren las actualizaciones de Surface.

Para ver los pasos detallados, consulte los siguientes recursos:

- [Administrar actualizaciones de controladores de Surface en Configuration Manager](manage-surface-driver-updates-configuration-manager.md)
- [Implementar aplicaciones con Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Documentación de Endpoint Configuration Manager](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>Administrar actualizaciones con Microsoft Deployment Toolkit

Microsoft Deployment Toolkit (MDT) se incluye en Endpoint Configuration Manager. Según el entorno, contiene herramientas de implementación opcionales que puede que desee usar.  Estos incluyen el kit de evaluación e implementación de Windows (Windows ADK), Windows System Image Manager (Windows SIM), administración y mantenimiento de imágenes de implementación (DISM) y herramienta de migración de estado de usuario (USMT). Puede descargar la versión más reciente de MDT desde la página de descarga de [Microsoft Deployment Toolkit.](https://www.microsoft.com/download/details.aspx?id=54259)

Para ver los pasos detallados, consulte los siguientes recursos:

- [Documentación sobre Toolkit implementación de Microsoft](/configmgr/mdt/)
- [Preparar la implementación con MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

Para obtener instrucciones sobre cómo implementar actualizaciones mediante Endpoint Configuration Manager, consulte [Deploy applications with Configuration Manager](/configmgr/apps/deploy-use/deploy-applications). Para obtener instrucciones sobre cómo implementar actualizaciones mediante MDT, consulte [Deploy a Windows 10 image using MDT](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**Controladores y firmware de WindowsPE y Surface**

Endpoint Configuration Manager y MDT usan el Windows de preinstalación (WindowsPE) durante el proceso de implementación. WindowsPE solo admite un conjunto limitado de controladores básicos, como adaptadores de red y controladores de almacenamiento. Los controladores Windows componentes que no forman parte de WindowsPE pueden producir errores. Como práctica recomendada, puedes evitar estos errores configurando el proceso de implementación para usar solo los controladores necesarios durante la fase de WindowsPE.

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

A partir de Endpoint Configuration Manager, puedes sincronizar e implementar actualizaciones de controladores y firmware de Microsoft Surface mediante el cliente de Configuration Manager. Para obtener más información, consulta KB 4098906, [Administrar actualizaciones de controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## <a name="supported-devices"></a>Dispositivos compatibles

Los archivos .msi están disponibles para Surface Pro dispositivos 2 y posteriores (excepto Surface Pro X que se ejecuta Windows 10 en ARM).

## <a name="managing-firmware-with-dfci"></a>Administración de firmware con DFCI

Al tener perfiles de interfaz de configuración de firmware de dispositivo (DFCI) integrados [en Intune](/intune/configuration/device-firmware-configuration-interface-windows), la administración de UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware de UEFI. DFCI admite el aprovisionamiento sin intervención táctil, elimina las contraseñas de BIOS, proporciona control de la configuración de seguridad (incluidas las opciones de inicio y periféricos integrados) y establece las bases para escenarios de seguridad avanzados en el futuro. Para obtener más información, consulte:

- [Administrar DFCI en dispositivos Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: Anuncio de la administración remota de la configuración de UEFI de Surface desde Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## <a name="best-practices-for-update-deployment-processes"></a>Procedimientos recomendados para actualizar procesos de implementación

Para mantener un entorno estable, se recomienda encarecidamente mantener la paridad con la versión más reciente de Windows 10.  Para obtener recomendaciones de procedimientos recomendados, vea [Prepare servicing strategy for Windows client updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### <a name="surface-msi-naming-convention"></a>Convención .msi nomenclatura de Surface

Desde agosto de 2019, los .msi están usando la siguiente convención de nomenclatura:

- *Product* _*Windows release*_ *Windows build numberVersion*_**_ *numberRevision of version number (typically zero)*.

**Por ejemplo:**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

Este nombre de archivo proporciona la siguiente información:

- **Producto:** SurfacePro6
- **Windows:** Win10
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
- **Windows:** Win10
- **Compilación:** 16299
- **Versión:** 1900307: muestra la fecha en que se creó el archivo y su posición en la secuencia de lanzamiento, de la siguiente manera:
  - **Año:** 19 (2019)
  - **Número de versión:** 003 (tercera versión del año)
  - **Número de versión del producto:** 07 (Surface Pro 6 es oficialmente la séptima versión de Surface Pro)
- **Revisión de la versión:** 0 (primera versión de esta versión)

## <a name="learn-more"></a>Obtén más información

- [Preparación de la estrategia de mantenimiento para las actualizaciones del cliente Windows](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [Administrar actualizaciones de controladores de Surface en Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Implementar aplicaciones con Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Documentación de Endpoint Configuration Manager](/configmgr/)
- [Documentación sobre Toolkit implementación de Microsoft](/configmgr/mdt/)
- [Preparar la implementación con MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Administrar DFCI en dispositivos Surface](surface-manage-dfci-guide.md)
- [Ignite 2019: Anuncio de la administración remota de la configuración de UEFI de Surface desde Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).


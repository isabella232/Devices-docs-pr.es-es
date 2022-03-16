---
title: Consideraciones sobre Surface y Microsoft Endpoint Configuration Manager
description: La administración e implementación de dispositivos Surface con Configuration Manager es fundamentalmente la misma que cualquier otro equipo; En este artículo se describen escenarios que pueden requerir consideraciones adicionales.
keywords: administrar, implementar, actualizaciones, controlador, firmware
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 08/12/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 88d25786601bdb88c027b689431d1c08c80cb9ec
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448343"
---
# <a name="considerations-for-surface-and-microsoft-endpoint-configuration-manager"></a>Consideraciones sobre Surface y Microsoft Endpoint Configuration Manager

Fundamentalmente, la administración e implementación de dispositivos Surface con Microsoft Endpoint Configuration Manager es la misma que la administración e implementación de cualquier otro equipo. Como cualquier otro equipo, una implementación de dispositivos Surface incluye la importación de controladores, la importación de una imagen Windows, la preparación de una secuencia de tareas de implementación y, a continuación, la implementación de la secuencia de tareas en una colección. Después de la implementación, los dispositivos Surface son como cualquier otro cliente de Windows; para publicar aplicaciones, configuraciones y directivas, usas el mismo proceso que usarías para cualquier otro dispositivo.

Para obtener más información, [consulte Microsoft Endpoint Configuration Manager documentación](/mem/configmgr/).

Aunque la implementación y administración de dispositivos Surface es fundamentalmente similar a otros equipos, algunos escenarios pueden requerir tareas de IT adicionales, como se describe en este artículo. 

> [!TIP]
> Usa la [Rama actual de Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates) para administrar dispositivos Surface.

## <a name="update-surface-device-drivers-and-firmware"></a>Actualizar controladores y firmware de dispositivos Surface

Para implementar actualizaciones de controladores de dispositivo y firmware con Configuration Manager o Windows Server Update Services (WSUS), consulta Administrar actualizaciones de [controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md).

## <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Adaptadores Ethernet de Surface e implementación de Configuration Manager

El mecanismo predeterminado que Configuration Manager usa para identificar dispositivos durante la implementación es la dirección de Control de acceso a medios (MAC). Dado que la dirección MAC está asociada con el controlador Ethernet, un adaptador Ethernet compartido entre varios dispositivos hará que Configuration Manager identifique cada uno de los dispositivos como un solo dispositivo, lo que da como resultado un error en la implementación. 

Para asegurarte de que los dispositivos Surface que usan el mismo adaptador Ethernet se identifican como dispositivos únicos durante la implementación, puedes indicar a Configuration Manager que identifique los dispositivos con otro método. Puede especificar que Configuration Manager use otros métodos de identificación, como se documenta en [Administrar identificadores de hardware duplicados](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers):

- Agrega una exclusión para las direcciones MAC de los adaptadores Ethernet de Surface, lo que fuerza a Configuration Manager a pasar por alto la dirección MAC en preferencia del UUID del sistema.

- Usa un script para identificar un dispositivo Surface recién implementado mediante la dirección MAC de su adaptador inalámbrico.

### <a name="surface-ethernet-driver"></a>Controlador ethernet de Surface

Desde 2016, el controlador del adaptador Ethernet de Surface se ha incluido de forma predeterminada en Windows y no requiere ninguna configuración de TI adicional. A partir de su inclusión en Windows 10, el controlador ya no está disponible para su descarga desde el Centro de descarga de Microsoft. (Si necesita implementar versiones anteriores de Windows 10 Pro, puede descargar el controlador más reciente del Catálogo [de Microsoft Update](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers)).

## <a name="deploy-surface-app-with-configuration-manager"></a>Implementar la aplicación Surface con Configuration Manager

Con la versión de Microsoft Store para Empresas, la aplicación Surface ya no está disponible como controlador y descarga de firmware. Las organizaciones que implementan la aplicación Surface en dispositivos Surface administrados o durante la implementación a través de Configuration Manager, primero deben adquirir la aplicación Surface a través de Microsoft Store para Empresas. Para obtener más información, consulta [Implementar la aplicación Surface con Microsoft Store para Empresas](deploy-surface-app-with-windows-store-for-business.md).

## <a name="use-prestaged-media-with-surface-clients"></a>Usar medios preconfigurados con clientes de Surface

Si tu organización usa medios preconfigurados para cargar recursos de implementación en máquinas antes de la implementación con Configuration Manager, es posible que la naturaleza de los dispositivos Surface como dispositivos UEFI requiera que sigas pasos adicionales. En concreto, un entorno UEFI nativo requiere crear varias particiones en el disco de arranque del sistema. Si sigues junto con la documentación para medios preconfigurados [, las](/mem/configmgr/osd/deploy-use/create-prestaged-media) instrucciones proporcionan solo discos de arranque de partición única y, por lo tanto, producirán errores cuando se apliquen a dispositivos Surface.

Las instrucciones para aplicar medios preconfigurados a dispositivos UEFI, como dispositivos Surface, se pueden encontrar en la entrada de blog Cómo aplicar medios preconfigurados de secuencia de tareas en discos con particiones múltiples para [equipos BIOS o UEFI](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) en el blog Sistema.

## <a name="licensing-conflicts-with-oem-activation-30"></a>Conflictos de licencias con la activación oem 3.0

Los dispositivos Surface vienen preinstalados con una copia con licencia de Windows. La clave de licencia de esta copia preinstalada de Windows está incrustada en el firmware del dispositivo con [la activación oem 3.0](/windows-hardware/manufacture/desktop/oem-activation-3) (OA 3.0). Al ejecutar un Windows de instalación en un dispositivo con una clave OA 3.0, el programa de instalación de Windows lee automáticamente la clave de licencia y la usa para instalar y activar Windows. En la mayoría de las situaciones, esto simplifica la reinstalación de Windows, ya que el usuario no tiene que buscar ni escribir una clave de licencia.

Al volver a crear una imagen de un dispositivo mediante Windows Enterprise, esta clave de licencia incrustada no provoca un conflicto. Esto se debe a que el medio de instalación de Windows Enterprise está configurado para instalar solo una edición Enterprise de Windows y, por lo tanto, es incompatible con la clave de licencia incrustada en el firmware del sistema. Si no se especifica una clave de producto (por ejemplo, cuando tiene previsto activar con Key Management Services [KMS] o Active Directory Based Activation), se usa una clave de licencia por volumen genérica (GVLK) hasta que una de estas tecnologías active Windows.

Sin embargo, pueden surgir problemas cuando las organizaciones tienen la intención de usar versiones de Windows que son compatibles con la clave incrustada de firmware. Por ejemplo, una organización que desea instalar Windows 10 Pro en un dispositivo que originalmente se incluye con Windows 10 Home puede encontrar dificultades cuando el programa de instalación de Windows lee automáticamente la clave de la edición inicio durante la instalación y se instala como Windows 10 Home en lugar de Windows 10 Pro. Para evitar este conflicto, use el archivo Ei.cfg o Pid.txt para indicar explícitamente Windows la instalación que solicite una clave de producto o escriba una clave de producto específica en la secuencia de tareas de implementación. Para obtener más información, [vea Windows Configuración de Setup Edition y Archivos de id. de producto](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt). Si no tiene una clave específica, puede usar las claves de producto predeterminadas para Windows. Para obtener más información, vea [Deploy Windows 10](/windows/deployment/deploy).

## <a name="apply-an-asset-tag-during-deployment"></a>Aplicar una etiqueta de activo durante la implementación

Con la [herramienta de etiqueta De activos de Surface](assettag.md), puedes identificar dispositivos de UEFI incluso si se produce un error en el sistema operativo. Para obtener más información sobre cómo administrar activos con Configuration Manager, consulte [Introducción a la inteligencia de activos en Configuration Manager](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence).

## <a name="configure-push-button-reset"></a>Configurar el restablecimiento de botones

Al implementar Windows en un dispositivo Surface, la funcionalidad de restablecimiento de botón de Windows se configura de forma predeterminada para revertir el sistema a un estado en el que el entorno aún no está configurado. Cuando se usa la función de restablecimiento, el sistema descarta cualquier configuración y aplicaciones instaladas. Aunque en algunas situaciones puede ser beneficioso restaurar el sistema en un estado sin aplicaciones y configuraciones, en un entorno profesional esto hace que el sistema sea inutilizable para el usuario final.

Sin embargo, se puede configurar el restablecimiento del botón para restaurar la configuración del sistema a un estado en el que esté listo para su uso por el usuario final. Siga el proceso descrito en [Deploy push-button reset features](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) to customize the push-button reset experience for your devices.

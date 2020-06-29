---
title: Consideraciones para Surface y el administrador de configuración de Microsoft Endpoint
description: La administración e implementación de dispositivos Surface con Configuration Manager es fundamentalmente idéntica a cualquier otro equipo. en este artículo se describen escenarios que pueden requerir consideraciones adicionales.
keywords: administrar, implementación, actualizaciones, controlador, firmware
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
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834730"
---
# Consideraciones para Surface y el administrador de configuración de Microsoft Endpoint

Fundamentalmente, la administración e implementación de dispositivos Surface con Microsoft Endpoint Configuration Manager es la misma que la administración y la implementación de cualquier otro equipo. Como cualquier otro equipo, una implementación en dispositivos Surface incluye la importación de controladores, la importación de una imagen de Windows, la preparación de una secuencia de tareas de implementación y la implementación de la secuencia de tareas en una colección. Después de la implementación, los dispositivos Surfaces son como cualquier otro cliente de Windows; para publicar las aplicaciones, la configuración y las directivas, use el mismo proceso que usaría para cualquier otro dispositivo.

Puede encontrar más información sobre cómo usar Configuration Manager para implementar y administrar dispositivos en la [documentación de Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/index).

Aunque la implementación y la administración de los dispositivos Surfaces son fundamentalmente idénticas a cualquier otro equipo, hay algunos escenarios que pueden requerir consideraciones o pasos adicionales. En este artículo se proporcionan descripciones e instrucciones para estos escenarios. Las soluciones documentadas en este artículo pueden aplicarse también a otros dispositivos y fabricantes.

> [!NOTE]
> Para la administración de dispositivos Surface, se recomienda usar la rama actual de Microsoft Endpoint Configuration Manager.

## Actualización de los drivers y el firmware de los dispositivos de superficie

En el caso de los dispositivos que reciben actualizaciones a través de Windows Update, los drivers para los componentes de Surface (e incluso las actualizaciones de firmware) se aplican automáticamente como parte del proceso de Windows Update. Para los dispositivos con actualizaciones administradas, como las que se actualizan a través de Windows Server Update Services (WSUS) o administrador de configuración, consulte [administrar actualizaciones de firmware y controlador de superficie](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/).

> [!NOTE]
> Los drivers y el firmware de los dispositivos Surface están firmados con SHA-256, que no es compatible de forma nativa con Windows Server 2008 R2. Hay una solución alternativa disponible para entornos de Configuration Manager que se ejecutan en Windows Server 2008 R2. Para obtener más información, consulte [no se pueden importar drivers en el administrador de configuración de Microsoft Endpoint (KB3025419)](https://support.microsoft.com/kb/3025419).

## Adaptadores Ethernet de Surface y implementación de Configuration Manager

El mecanismo predeterminado que usa Configuration Manager para identificar los dispositivos durante la implementación es la dirección de control de acceso de medios (MAC). Debido a que la dirección MAC está asociada con el controlador Ethernet, un adaptador Ethernet compartido entre varios dispositivos hará que Configuration Manager identifique cada uno de los dispositivos como un único dispositivo. Esto puede provocar que una implementación de Configuration Manager de Windows no se aplique a los dispositivos previstos.

Para asegurarse de que los dispositivos Surface que usan el mismo adaptador Ethernet se identifiquen como dispositivos únicos durante la implementación, puede indicar a Configuration Manager que identifique los dispositivos con otro método. Este otro método podría ser la dirección MAC del adaptador de red inalámbrica o el identificador único universal (UUID del sistema). Puede especificar que Configuration Manager use otros métodos de identificación con las siguientes opciones:

* Agregue una exclusión para las direcciones MAC de los adaptadores de Surface Ethernet, lo que fuerza a que Configuration Manager pase por alto la dirección MAC de preferencia del UUID del sistema, tal y como se explica en la [reutilización de la misma NIC para varias implementaciones iniciadas por PXE en la publicación de blog OSD de Microsoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) .

* Preensayar dispositivos según el UUID del sistema según se describe en la [reutilización de la misma NIC para varias implementaciones iniciadas por PXE en la publicación de blog OSD de Microsoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/) .

* Use un script para identificar un dispositivo Surface recientemente implementado por la dirección MAC de su adaptador inalámbrico, como se describe en [Cómo usar el mismo adaptador Ethernet externo para varias entradas de blog de SCCM OSD](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/) .

Otra consideración para el adaptador de Ethernet Surface durante las implementaciones con Configuration Manager es el controlador para el controlador Ethernet. A partir de Windows 10, versión 1511, el controlador para el adaptador Surface Ethernet está incluido de forma predeterminada en Windows. Para las organizaciones que desean implementar la última versión de Windows 10 y usar la versión más reciente de WinPE, el uso del adaptador Surface Ethernet no requiere acciones adicionales.

Para las versiones de Windows anteriores a Windows 10, versión 1511 (incluyendo Windows 10 RTM y Windows 8,1), es posible que tenga que instalar el controlador del adaptador de Ethernet Surface e incluir el controlador en los medios de inicio de WinPE. Con su inclusión en Windows 10, el controlador ya no se puede descargar desde el centro de descarga de Microsoft. Para descargar el controlador del adaptador de Surface Ethernet, descárguelo desde el catálogo de Microsoft Update, tal como se describe en la publicación de blog de [Surface Ethernet drivers](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/) desde el blog de preguntar al equipo principal.

## Implementar la aplicación Surface con Configuration Manager

Con el lanzamiento de Microsoft Store para empresas, Surface App ya no está disponible como una descarga de controlador y firmware. Las organizaciones que deseen implementar Surface app para dispositivos de Surface administrados o durante la implementación con el uso de Configuration Manager, deben adquirir la aplicación de Surface a través de Microsoft Store para empresas y, a continuación, implementar Surface App con PowerShell. Puede encontrar los comandos de PowerShell para la implementación de Surface App, instrucciones para descargar Surface App y los marcos de trabajo de requisitos previos de Microsoft Store para empresas en la [aplicación implementar Surface con Microsoft Store para empresas](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business) en la biblioteca de TechNet.

## Usar medios preconfigurados con clientes Surface

Si su organización usa medios preconfigurados para cargar previamente recursos de implementación en equipos antes de la implementación con Configuration Manager, la naturaleza de los dispositivos Surface como dispositivos UEFI puede requerir que se realicen pasos adicionales. Específicamente, un entorno UEFI nativo requiere la creación de varias particiones en el disco de inicio del sistema. Si está siguiendo la [documentación de los medios preconfigurados](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia), las instrucciones proporcionan solo discos de inicio de partición única y, por lo tanto, darán error cuando se aplican a dispositivos Surface.

Encontrará instrucciones para la aplicación de medios preconfigurados en dispositivos UEFI, como dispositivos de Surface, en el tema [Cómo aplicar contenido multimedia preconfigurado de secuencia de tareas en discos con varias particiones para el BIOS o los equipos UEFI en la publicación de blog de Microsoft Endpoint Configuration Manager](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/) .

## Conflictos de licencias con activación de OEM 3,0

Los dispositivos Surface vienen preinstalados con una copia con licencia de Windows. Por ejemplo, Surface Pro 4 está preinstalado con Windows 10 Professional. La clave de licencia para esta copia preinstalada de Windows se inserta en el firmware del dispositivo con activación de OEM 3,0 (OA 3,0). Cuando ejecuta los medios de instalación de Windows en un dispositivo con una clave OA 3,0, el programa de instalación de Windows lee automáticamente la clave de licencia y la usa para instalar y activar Windows. En la mayoría de los casos, esto simplifica la reinstalación de Windows, porque el usuario no tiene que buscar o introducir una clave de licencia.

Cuando se renueva la imagen de un dispositivo con Windows Enterprise, esta clave de licencia insertada no provoca un conflicto. Esto se debe a que el medio de instalación de Windows Enterprise está configurado para instalar solo una edición Enterprise de Windows y, por lo tanto, no es compatible con la clave de licencia incrustada en el firmware del sistema. Si no se especifica una clave de producto (como cuando tiene previsto activar con servicios de administración clave [KMS] o activación basada en Active Directory), se usa una clave de licencia por volumen genérica (GVLK) hasta que una de esas tecnologías Active Windows.

Sin embargo, pueden surgir problemas cuando las organizaciones deseen usar versiones de Windows compatibles con la clave de firmware incorporada. Por ejemplo, una organización que desea instalar Windows 10 Professional en un dispositivo Surface 3 que originalmente se incluía con Windows 10 Home Edition puede encontrarse con problemas cuando el programa de instalación de Windows lee automáticamente la tecla Home Edition durante la instalación y se instala como Home Edition en lugar de Professional. Para evitar este conflicto, puede usar el archivo ei. cfg o Pid.txt para indicar explícitamente al programa de instalación de Windows que solicite una clave de producto, o bien puede escribir una clave de producto específica en la secuencia de tareas de implementación. Para obtener más información, consulte [configuración de la edición de configuración y archivos Product ID de Windows](https://technet.microsoft.com/library/hh824952.aspx). Si no tiene una clave específica, puede usar las claves de producto predeterminadas para Windows, que puede encontrar en [personalizar e implementar un sistema operativo Windows 10](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build) en el centro de socios de dispositivos.

## Aplicar una etiqueta de activo durante la implementación

Surface Studio, Surface Book, Surface Pro 4, Surface Pro 3 y dispositivos Surface 3 admiten la aplicación de una etiqueta de activo en UEFI. Esta etiqueta de activo se puede usar para identificar el dispositivo a través de UEFI incluso si se produce un error en el sistema operativo y también se puede consultar desde el sistema operativo. Para obtener más información sobre la función de etiqueta de activos de Surface, consulte la [herramienta de etiqueta de activos de la entrada de blog de Surface Pro 3](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/) .

Para aplicar una etiqueta de activo mediante la [utilidad CLI de etiqueta de activos de Surface](https://www.microsoft.com/download/details.aspx?id=44076) durante una secuencia de tareas de implementación de Configuration Manager, use el script y las instrucciones de la [etiqueta establecer activo de superficie durante una secuencia de tareas de Configuration Manager](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/) .

## Configurar restablecimiento del botón

Al implementar Windows en un dispositivo Surface, la funcionalidad de restablecimiento del botón de Windows está configurada de forma predeterminada para volver a revertir el sistema a un estado en el que aún no se ha configurado el entorno. Cuando se usa la función restablecer, el sistema descarta las aplicaciones y la configuración que haya instalado. Aunque en algunos casos puede ser ventajoso restaurar el sistema a un estado sin las aplicaciones y la configuración, en un entorno profesional esto hace que el sistema no se pueda usar para el usuario final.

Sin embargo, puede configurar el botón para restaurar la configuración del sistema a un estado en el que esté listo para que la use el usuario final. Siga el proceso que se describe en [implementar características de restablecimiento con botón Push](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features) para personalizar la experiencia de restablecimiento del botón para los dispositivos.

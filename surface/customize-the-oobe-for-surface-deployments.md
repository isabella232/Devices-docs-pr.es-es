---
title: Personalizar la OOBE para las implementaciones de Surface (Surface)
description: Este artículo te guiará por el proceso de personalización de la experiencia del primer inicio en Surface para los usuarios finales de tu organización.
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: implementar, personalizar, automatizar, red, lápiz, emparejar, arranque
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: de84d4db52006991308bf19893a50594f6a1d1dc
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449523"
---
# <a name="customize-the-oobe-for-surface-deployments"></a>Personalizar la OOBE para las implementaciones de Surface

En este artículo se describe la personalización de la experiencia personalizada de Surface para los usuarios finales de la organización.

Es habitual en una implementación de Windows personalizar la experiencia del usuario para el primer inicio de equipos implementados: la configuración rápida u OOBE.

>[!TIP]
>A menudo, OOBE también se usa para describir la fase o la etapa de configuración del programa de instalación de Windows durante la cual se muestra la experiencia del usuario. Para obtener más información sobre la fase OOBE de la instalación, consulta [Funcionamiento de las fases de configuración](/windows-hardware/manufacture/desktop/how-configuration-passes-work).

En algunos escenarios, es posible que quieras proporcionan una automatización completa para asegurar que, al final de la implementación, los equipos estén listos para su uso sin ninguna interacción por parte del usuario. En otros escenarios, puede que quieras dejar los elementos clave de la experiencia para que los usuarios realicen las acciones necesarias o seleccionen entre las opciones importantes. Para los administradores que implementan en dispositivos Surface, cada uno de estos escenarios presenta un reto único.

> [!NOTE]
> Este artículo no se aplica a Surface Pro X. Para obtener más información, consulte [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)

En este artículo se proporciona un resumen de los escenarios donde una implementación podría requerir pasos adicionales. También proporciona la información necesaria para garantizar que se logre la experiencia deseada en cualquier dispositivo Surface recientemente implementado. Este artículo está pensado para los administradores que estén familiarizados con el proceso de implementación, así como con conceptos como archivos de respuesta e [imágenes de referencia](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).

>[!NOTE]
>Aunque la fase de configuración de OOBE todavía se ejecuta como parte de una solución de implementación automatizada, como [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) o [Microsoft Endpoint Configuration Manager Operating System Deployment (OSD),](/mem/configmgr/osd/) se automatiza mediante la configuración proporcionada en el asistente de implementación y la secuencia de tareas.

## <a name="scenario-1-wireless-networking-in-oobe-with-mdt-2013"></a>Escenario 1: Redes inalámbricas en OOBE con MDT 2013

Cuando un adaptador de red inalámbrica está presente durante la configuración rápida, aparece la página **Unirse a una red inalámbrica**, que pide al usuario que se conecte a una red inalámbrica. Las tecnologías de implementación, como MDT 2013, no ocultan automáticamente esta página y, por lo tanto, se mostrará incluso cuando una implementación se configura para una automatización completa.

Para garantizar que esta página no haya detenido una implementación automatizada, la página debe ocultarse mediante la configuración de una opción adicional en el archivo de respuesta **HideWirelessSetupInOOBE**. Puedes encontrar información adicional sobre la opción **HideWirelessSetupInOOBE** en la [Referencia de instalación desatendida de Windows](/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-oobe-hidewirelesssetupinoobe).

## <a name="scenario-2-surface-pen-pairing-in-oobe"></a>Escenario 2: Emparejamiento del Lápiz para Surface en OOBE

La primera vez que tomes un dispositivo Surface e inícielo, la experiencia de primera ejecución de la imagen de fábrica incluye un mensaje que te pide que pares el lápiz de Surface incluido en el dispositivo. Este mensaje solo se proporciona en la imagen de fábrica que se incluye con el dispositivo y no está incluido en otras imágenes usadas para la implementación, como los medios de instalación de Windows Enterprise descargados del Centro de servicios de licencias por volumen. Dado que el emparejamiento del Lápiz para Surface Bluetooth fuera de esta experiencia requiere que vayas al Panel de control o a la Configuración de PC y emparejes manualmente un dispositivo Bluetooth, puede que quieras que los usuarios o un técnico usen este mensaje para realizar la operación de emparejamiento.

Para proporcionar la experiencia de emparejamiento de fábrica del Lápiz para Surface en OOBE, debes copiar cuatro archivos de la imagen de fábrica de Surface en la imagen de referencia. Puedes copiar estos archivos en el entorno de referencia antes de capturar la imagen de referencia o puedes agregarlos más adelante mediante la Administración y mantenimiento de imágenes de implementación (DISM) para montar la imagen. Los cuatro archivos necesarios son:

- %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
- %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!TIP]
>Debes copiar los archivos de una imagen de fábrica para un dispositivo Surface del mismo modelo donde vayas a realizar la implementación. Por ejemplo, debe usar los archivos de un Surface Pro 8 para implementar en Surface Pro 8 y los archivos de Surface Book 3 para implementar Surface Book 3, pero no debe usar los archivos de Surface Pro 8 para implementar Surface Book 3 o Surface Pro 7.

El proceso paso a paso para agregar estos archivos necesarios a una imagen se describe en [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/) (Consejos de implementación en Surface Pro 3 y OneNote). Esta entrada de blog incluye también sugerencias para asegurar que se instalen las actualizaciones necesarias para la experiencia de toma de notas rápidas del Lápiz para Surface, que permite a los usuarios enviar notas de OneNote con un solo clic.

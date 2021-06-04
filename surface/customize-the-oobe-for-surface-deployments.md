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
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835666"
---
# Personalizar la OOBE para las implementaciones de Surface

En este artículo se describe la personalización de la experiencia rápida de la superficie para los usuarios finales de su organización.

Es habitual en una implementación de Windows personalizar la experiencia del usuario para el primer inicio de equipos implementados: la configuración rápida u OOBE.

>[!NOTE]
>A menudo, OOBE también se usa para describir la fase o la etapa de configuración del programa de instalación de Windows durante la cual se muestra la experiencia del usuario. Para obtener más información sobre la fase OOBE de la instalación, consulta [Funcionamiento de las fases de configuración](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).

En algunos escenarios, es posible que quieras proporcionan una automatización completa para asegurar que, al final de la implementación, los equipos estén listos para su uso sin ninguna interacción por parte del usuario. En otros escenarios, puede que quieras dejar los elementos clave de la experiencia para que los usuarios realicen las acciones necesarias o seleccionen entre las opciones importantes. Para los administradores que implementan en dispositivos Surface, cada uno de estos escenarios presenta un reto único.

> [!NOTE]
> Este artículo no se aplica a Surface Pro X. Para obtener más información, consulte [implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md)

En este artículo se proporciona un resumen de los escenarios donde una implementación podría requerir pasos adicionales. También proporciona la información necesaria para garantizar que se logre la experiencia deseada en cualquier dispositivo Surface recientemente implementado. Este artículo está pensado para los administradores que estén familiarizados con el proceso de implementación, así como con conceptos como archivos de respuesta e [imágenes de referencia](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).

>[!NOTE]
>Aunque la fase de OOBE del programa de instalación se sigue ejecutando durante una implementación con una solución de implementación automatizada, como [Microsoft Deployment Toolkit (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) o la implementación de sistema operativo Microsoft Endpoint Configuration Manager (OSD), se automatiza con la configuración suministrada en el Asistente de implementación y en la secuencia de tareas. Para obtener más información, consulta:<br/>
>- [Implementar Windows10 con Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [Implementar Windows10 con System Center 2012R2 Configuration Manager](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

##  <a name="scenario-1:-wireless-networking-in-oobe-with-mdt-2013"></a>Escenario 1: Redes inalámbricas en OOBE con MDT 2013


Cuando un adaptador de red inalámbrica está presente durante la configuración rápida, aparece la página **Unirse a una red inalámbrica**, que pide al usuario que se conecte a una red inalámbrica. Las tecnologías de implementación, como MDT 2013, no ocultan automáticamente esta página y, por lo tanto, se mostrará incluso cuando una implementación se configura para una automatización completa.

Para garantizar que esta página no haya detenido una implementación automatizada, la página debe ocultarse mediante la configuración de una opción adicional en el archivo de respuesta **HideWirelessSetupInOOBE**. Puedes encontrar información adicional sobre la opción **HideWirelessSetupInOOBE** en la [Referencia de instalación desatendida de Windows](https://technet.microsoft.com/library/ff716213.aspx).

##  <a name="scenario-2:-surface-pen-pairing-in-oobe"></a>Escenario 2: Emparejamiento del Lápiz para Surface en OOBE


Cuando saques por primera vez tu Surface Pro 3, Surface Pro 4, Surface Book o Surface Studio del paquete y lo inicies, la experiencia de primera ejecución de la imagen de fábrica incluye un mensaje que te pide que emparejes con el dispositivo el Lápiz para Surface incluido. Este mensaje solo se proporciona en la imagen de fábrica que se incluye con el dispositivo y no está incluido en otras imágenes usadas para la implementación, como los medios de instalación de Windows Enterprise descargados del Centro de servicios de licencias por volumen. Dado que el emparejamiento del Lápiz para Surface Bluetooth fuera de esta experiencia requiere que vayas al Panel de control o a la Configuración de PC y emparejes manualmente un dispositivo Bluetooth, puede que quieras que los usuarios o un técnico usen este mensaje para realizar la operación de emparejamiento.

Para proporcionar la experiencia de emparejamiento de fábrica del Lápiz para Surface en OOBE, debes copiar cuatro archivos de la imagen de fábrica de Surface en la imagen de referencia. Puedes copiar estos archivos en el entorno de referencia antes de capturar la imagen de referencia o puedes agregarlos más adelante mediante la Administración y mantenimiento de imágenes de implementación (DISM) para montar la imagen. Los cuatro archivos necesarios son:

-   %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
-   %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!NOTE]
>Debes copiar los archivos de una imagen de fábrica para un dispositivo Surface del mismo modelo donde vayas a realizar la implementación. Por ejemplo, debe usar los archivos de Surface Pro 7 para implementar en Surface Pro 7, y los archivos de Surface Book 2 para implementar Surface Book 2, pero no debe usar los archivos de Surface Pro 7 para implementar Surface Book o Surface Pro 6.

 

El proceso paso a paso para agregar estos archivos necesarios a una imagen se describe en [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/) (Consejos de implementación en Surface Pro 3 y OneNote). Esta entrada de blog incluye también sugerencias para asegurar que se instalen las actualizaciones necesarias para la experiencia de toma de notas rápidas del Lápiz para Surface, que permite a los usuarios enviar notas de OneNote con un solo clic.

 

 






---
title: Implementar la calidad de servicio en Surface Hub
ms.reviewer: ''
manager: laurawi
description: Más información sobre cómo configurar QoS en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835193"
---
# Implementar calidad de servicio (QoS) en Surface Hub

Calidad de servicio (QoS) es una combinación de tecnologías de red que permite a los administradores optimizar la experiencia de las comunicaciones de audio, vídeo y uso compartido de aplicaciones en tiempo real.
 
La configuración [de QoS para Skype empresarial](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) en Surface Hub se puede realizar con el [proveedor de administración de dispositivos móviles (MDM)](manage-settings-with-mdm-for-surface-hub.md) o a través de un [paquete de aprovisionamiento](provisioning-packages-for-surface-hub.md). 
 
 
Este procedimiento explica cómo configurar QoS para Surface Hub con Microsoft Intune. 

1. En Intune, [cree una directiva personalizada](https://docs.microsoft.com/intune/custom-settings-configure).

    ![Captura de pantalla del cuadro de diálogo de creación de directiva personalizada en Intune](images/qos-create.png)

2. En **Configuración personalizada de OMA-URI**, seleccione **Agregar**. Para cada configuración que agregue, tendrá que escribir un nombre, una descripción (opcional), un tipo de datos, OMA-URI y valor.

    ![Captura de pantalla de un cuadro de diálogo Configuración OMA-URI en blanco](images/qos-setting.png)

3. Agregue la siguiente configuración personalizada de OMA-URI:

    Nombre | Tipo de datos | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Valor
    --- | --- | --- | ---
    Puerto de origen de audio | Cadena |  /HubAudio/SourcePortMatchCondition  |   Obtén los valores de tu Administrador de Skype
    DSCP de audio | Integer |  /HubAudio/DSCPAction  |   46
    Puerto de origen de video | Cadena |  /HubVideo/SourcePortMatchCondition   |  Obtén los valores de tu Administrador de Skype
    DSCP de vídeo | Integer |  /HubVideo/DSCPAction   |   34
    Nombre del proceso de audio | Cadena |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Nombre del proceso de vídeo | Cadena |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Cada ruta **OMA-URI** comienza por `./Device/Vendor/MSFT/NetworkQoSPolicy` . La ruta de acceso completa de la configuración del puerto de origen de audio, por ejemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .




4. Cuando se haya creado la Directiva, [impleméntela en Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>Por el momento, no puede configurar la opción de configuración **IPProtocolMatchCondition** en el [CSP de NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Si esta configuración está configurada, la Directiva no se aplicará.
 

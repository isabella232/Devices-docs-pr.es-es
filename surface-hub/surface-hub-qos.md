---
title: Implementar la calidad de servicio en Surface Hub
ms.reviewer: ''
manager: laurawi
description: Aprende a configurar QoS en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470488"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>Implementar calidad de servicio (QoS) en Surface Hub

Calidad de servicio (QoS) es una combinación de tecnologías de red que permite a los administradores optimizar la experiencia de comunicaciones de uso compartido de aplicaciones y audio en tiempo real.
 
La configuración [de QoS para Skype Empresarial](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) en Surface Hub se puede realizar con el proveedor de administración de dispositivos móviles [(MDM)](manage-settings-with-mdm-for-surface-hub.md) o a través de un paquete [de aprovisionamiento.](provisioning-packages-for-surface-hub.md) 
 
 
En este procedimiento se explica cómo configurar QoS para Surface Hub con Microsoft Intune. 

1. En Intune, [cree una directiva personalizada](https://docs.microsoft.com/intune/custom-settings-configure).

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla del cuadro de diálogo de creación de directivas personalizadas en Intune](images/qos-create.png)

2. En **Configuración personalizada de OMA-URI,** seleccione **Agregar**. Para cada configuración que agregue, escribirá un nombre, una descripción (opcional), un tipo de datos, OMA-URI y un valor.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla de un cuadro de diálogo de configuración de OMA-URI en blanco](images/qos-setting.png)

3. Agregue la siguiente configuración de OMA-URI personalizada:<br/><br/>

    Nombre | Tipo de datos | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  Valor
    --- | --- | --- | ---
    Puerto de origen de audio | Cadena |  /HubAudio/SourcePortMatchCondition  |   Obtener los valores del administrador de Skype
    DSCP de audio | Integer |  /HubAudio/DSCPAction  |   46
    Puerto de origen de vídeo | Cadena |  /HubVideo/SourcePortMatchCondition   |  Obtener los valores del administrador de Skype
    DSCP de vídeo | Integer |  /HubVideo/DSCPAction   |   34
    Nombre del proceso de audio | Cadena |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    Nombre del proceso de vídeo | Cadena |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >Cada **ruta de acceso de OMA-URI** comienza por `./Device/Vendor/MSFT/NetworkQoSPolicy` . La ruta de acceso completa para la configuración del puerto de origen de audio, por ejemplo, será `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` .

4. Cuando se haya creado la directiva, impleméntela en Surface Hub.


>[!WARNING]
>Actualmente, no puede configurar la **configuración IPProtocolMatchCondition** en [networkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp). Si esta configuración está configurada, la directiva no se aplicará.
 

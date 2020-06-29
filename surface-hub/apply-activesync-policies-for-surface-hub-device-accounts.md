---
title: Aplicación de directivas de ActiveSync a las cuentas de dispositivo (Surface Hub)
description: La cuenta del dispositivo de Microsoft Surface Hub usa ActiveSync para sincronizar el correo y el calendario. Esto permite a los usuarios unirse e iniciar reuniones programadas desde Surface Hub, así como enviar por correo electrónico cualquier pizarra interactiva realizada durante la reunión.
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, directivas de ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 6e93069c2d90bdc4c2f505bc28ba0ec1a4f08076
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835801"
---
# Aplicación de directivas de ActiveSync a las cuentas de dispositivo (Surface Hub)


La cuenta del dispositivo de Microsoft Surface Hub usa ActiveSync para sincronizar el correo y el calendario. Esto permite a los usuarios unirse e iniciar reuniones programadas desde Surface Hub, así como enviar por correo electrónico cualquier pizarra interactiva realizada durante la reunión.

Para que estas características funcionen, las directivas de ActiveSync de tu organización deben configurarse de la siguiente manera:

-   No puede haber ninguna directiva global que bloquee la sincronización del buzón de recursos que está usando la cuenta del dispositivo de Surface Hub. Si hay una directiva de bloqueo, deberás agregar el Surface Hub como dispositivo permitido.
-   Debes establecer una directiva de buzón de dispositivo móvil donde la **PasswordEnabled** configuración esté establecida en False. Otras opciones de configuración de directiva de buzón de dispositivo móvil no son compatibles con el Surface Hub.

## Permitir el DeviceID


La organización puede tener una directiva global que impida la sincronización de cuentas de dispositivos aprovisionadas en Surface Hubs. Para configurar esta propiedad, consulta [Permitir id. de dispositivo para ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#whitelisting-device-ids-cmdlet).

## Configuración PasswordEnabled


La cuenta del dispositivo debe tener una directiva ActiveSync donde el atributo **PasswordEnabled** esté establecido en False o 0. Para configurar esta propiedad, consulta [Creación de una directiva de Microsoft Exchange ActiveSync compatible con Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 






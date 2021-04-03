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
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: e8181ec499364c48586f5218983f667331788fc3
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470448"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a>Aplicación de directivas de ActiveSync a las cuentas de dispositivo (Surface Hub)


Los Surface Hub que usan el sistema operativo Windows 10 Team 1703 usan ActiveSync para sincronizar el correo y el calendario de la cuenta del dispositivo. Esto permite a los usuarios unirse e iniciar reuniones programadas desde Surface Hub, así como enviar por correo electrónico cualquier pizarra interactiva realizada durante la reunión.

Para que estas características funcionen, las directivas de ActiveSync de tu organización deben configurarse de la siguiente manera:

-   No puede haber ninguna directiva global que bloquee la sincronización del buzón de recursos que está usando la cuenta del dispositivo de Surface Hub. Si hay una directiva de bloqueo de este tipo, debes agregar Surface Hub como dispositivo permitido.
-   Debes establecer una directiva de buzón de dispositivo móvil donde la **PasswordEnabled** configuración esté establecida en False. Otras opciones de configuración de directiva de buzón de dispositivo móvil no son compatibles con el Surface Hub.

## <a name="allowing-the-deviceid"></a>Permitir deviceid

La organización puede tener una directiva global que impida la sincronización de cuentas de dispositivos aprovisionadas en Surface Hubs. Para configurar esta propiedad, consulta [Permitir id. de dispositivo para ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## <a name="setting-passwordenabled"></a>Configuración PasswordEnabled

La cuenta del dispositivo debe tener una directiva ActiveSync donde el atributo **PasswordEnabled** esté establecido en False o 0. Para configurar esta propiedad, consulta [Creación de una directiva de Microsoft Exchange ActiveSync compatible con Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).

 

 






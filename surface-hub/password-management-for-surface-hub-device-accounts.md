---
title: Administración de contraseñas (Surface Hub)
description: Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: contraseña, administración de contraseñas, rotación de contraseñas, cuenta del dispositivo
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836681"
---
# Administración de contraseñas (Surface Hub)

Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo. Por motivos de seguridad, es posible que quieras cambiar (o "rotar") esta contraseña con regularidad. Sin embargo, si la contraseña de la cuenta del dispositivo cambia, la contraseña que estaba almacenada en el dispositivo Surface Hub no será válida y se deshabilitarán todas las características que dependan de dicha cuenta del dispositivo. Tendrás que actualizar la contraseña de la cuenta del dispositivo en el Surface Hub desde la aplicación Configuración para volver a habilitar estas características.

Para simplificar la administración de contraseñas de las cuentas de dispositivo de Surface Hub, hay dos opciones:

1.  Desactivar la expiración de la contraseña para la cuenta del dispositivo.
2.  Permitir que el dispositivo Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo.


## Desactivar la rotación de contraseñas para la cuenta del dispositivo.

Establece la propiedad **PasswordNeverExpires** de la cuenta del dispositivo en True. Deberías comprobar si se cumplen los requisitos de seguridad de la organización.


## Permitir que el Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo

El Surface Hub puede administrar la contraseña de la cuenta de un dispositivo cambiándola con frecuencia sin necesidad de actualizar manualmente la información de la cuenta del dispositivo. Puedes habilitar esta característica en **Configuración**. Una vez habilitada, la contraseña de la cuenta del dispositivo cambiará semanalmente durante las horas de mantenimiento.

Ten en cuenta que al cambiar la contraseña de la cuenta del dispositivo, no se mostrará la nueva contraseña. Si necesitas iniciar sesión en la cuenta o proporcionar la contraseña de nuevo (por ejemplo, si quieres cambiar la configuración de la cuenta del dispositivo en el Surface Hub), necesitarás usar Active Directory o el portal de administración de Office 365 para restablecer la contraseña.

> [!IMPORTANT]
> Si la organización usa una topología híbrida (algunos servicios se hospedan localmente y otros se hospedan en línea mediante Office 365), debes configurar la cuenta del dispositivo con el formato **dominio\usuario**. De lo contrario, la rotación de contraseñas no funcionará.

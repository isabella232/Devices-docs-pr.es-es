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
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445586"
---
# <a name="password-management-surface-hub"></a>Administración de contraseñas (Surface Hub)

Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo. Por motivos de seguridad, es posible que quieras cambiar (o "rotar") esta contraseña con regularidad. Sin embargo, si la contraseña de la cuenta del dispositivo cambia, la contraseña que estaba almacenada en el dispositivo Surface Hub no será válida y se deshabilitarán todas las características que dependan de dicha cuenta del dispositivo. Tendrás que actualizar la contraseña de la cuenta del dispositivo en el Surface Hub desde la aplicación Configuración para volver a habilitar estas características.

Para simplificar la administración de contraseñas de las cuentas de dispositivo de Surface Hub, hay dos opciones:

1.  Desactivar la expiración de la contraseña para la cuenta del dispositivo.
2.  Permitir que el dispositivo Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo.


## <a name="turn-off-password-rotation-for-the-device-account"></a>Desactivar la rotación de contraseñas para la cuenta del dispositivo.

Establece la propiedad **PasswordNeverExpires** de la cuenta del dispositivo en True. Deberías comprobar si se cumplen los requisitos de seguridad de la organización.


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>Permitir que el Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo

Surface Hub puede cambiar automáticamente la contraseña de una cuenta de dispositivo sin necesidad de actualizarla manualmente. Puedes habilitar esta característica en **Configuración Cuentas**de  >  **Surface Hub**  >  ****. Si activas La rotación de contraseñas, Surface Hub intentará cambiar la contraseña cada 7 días durante las horas de mantenimiento. Las contraseñas no cambian durante una reunión. Si han transcurrido 7 días desde la última rotación de contraseña, pero Surface Hub estaba desactivado, intentará cambiar la contraseña inmediatamente cuando se haya activado o cada 10 minutos hasta que se haya realizado correctamente.

Las contraseñas generadas automáticamente contienen de 15 a 32 caracteres, incluida una combinación de letras mayúsculas y minúsculas, números y caracteres especiales. Ten en cuenta que cuando se cambie la contraseña de la cuenta del dispositivo, no se mostrará la nueva contraseña. Si necesitas iniciar sesión en la cuenta o volver a proporcionar la contraseña (por ejemplo, si quieres cambiar la configuración de la cuenta del dispositivo en Surface Hub), necesitarás usar Active Directory o el portal de administración de Microsoft 365 para restablecer la contraseña.

> [!IMPORTANT]
> El formato usado al agregar la cuenta de dispositivo [](prepare-your-environment-for-surface-hub.md) a Surface Hub tiene un impacto en la opción de afiliación del dispositivo que se debe usar para que funcione la rotación de contraseñas. Si agrega la cuenta en **formato dominio\nombredeusuario,** afilia el Concentrador a Active Directory local durante la instalación inicial. Si agrega la cuenta en `username@domain.com` formato, afilia el Concentrador a Azure Active Directory durante la instalación inicial. De lo contrario, la rotación de contraseñas no funcionará.

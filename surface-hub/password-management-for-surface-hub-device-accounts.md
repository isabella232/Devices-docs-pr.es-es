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
ms.openlocfilehash: ab2726577201157ed9a7ff4d265e826c063cf477
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676614"
---
# <a name="password-management-surface-hub"></a>Administración de contraseñas (Surface Hub)

Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo. Por motivos de seguridad, es posible que quieras cambiar (o "rotar") esta contraseña con regularidad. Sin embargo, si la contraseña de la cuenta del dispositivo cambia, la contraseña que estaba almacenada en el dispositivo Surface Hub no será válida y se deshabilitarán todas las características que dependan de dicha cuenta del dispositivo. Tendrás que actualizar la contraseña de la cuenta del dispositivo en el Surface Hub desde la aplicación Configuración para volver a habilitar estas características.

Para simplificar la administración de contraseñas de las cuentas de dispositivo de Surface Hub, hay dos opciones:

1.  Desactivar la expiración de la contraseña para la cuenta del dispositivo.
2.  Permitir que el dispositivo Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo.


## <a name="turn-off-password-rotation-for-the-device-account"></a>Desactivar la rotación de contraseñas para la cuenta del dispositivo.

Establece la propiedad **PasswordNeverExpires** de la cuenta del dispositivo en True. Deberías comprobar si se cumplen los requisitos de seguridad de la organización.


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>Permitir que el Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo

El Surface Hub puede cambiar automáticamente la contraseña de una cuenta de dispositivo sin necesidad de actualizarla manualmente. Puede habilitar esta característica en **Configuración**  >  **Surface Hub**  >  **Cuentas**. Si activa la rotación de contraseñas, Surface Hub intentará cambiar la contraseña cada 7 días durante el horario de mantenimiento. Las contraseñas no cambian durante una reunión. Si han transcurrido 7 días desde la última rotación de contraseña, pero el Surface Hub estaba desactivado, intentará cambiar la contraseña inmediatamente cuando se haya activado o cada 10 minutos hasta que se haya realizado correctamente.

Las contraseñas generadas automáticamente contienen de 15 a 32 caracteres, incluida una combinación de letras mayúsculas y minúsculas, números y caracteres especiales. Ten en cuenta que cuando se cambie la contraseña de la cuenta del dispositivo, no se mostrará la nueva contraseña. Si necesitas iniciar sesión en la cuenta o volver a proporcionar la contraseña (por ejemplo, si quieres cambiar la configuración de la cuenta de dispositivo en el Surface Hub), necesitarás usar Active Directory o el portal de administración de Microsoft 365 para restablecer la contraseña.

> [!IMPORTANT]
> La [opción de afiliación](prepare-your-environment-for-surface-hub.md) de dispositivos seleccionada durante la configuración inicial del Surface Hub tiene un impacto en el formato de cuenta del dispositivo que se puede usar con el giro de contraseña. Los concentradores asociados con un Active Directory local solo pueden girar las contraseñas de las cuentas de dispositivo especificadas en **formato dominio\nombredeusuario.** Los concentradores asociados con un Azure Active Directory solo pueden girar las contraseñas de las cuentas de dispositivo especificadas en formato, pero solo si la cuenta es solo en la nube o si el dominio de AAD está configurado para la autenticación en la nube y la escritura de escritura de `username@domain.com` contraseñas. [](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication) [](/azure/active-directory/authentication/concept-sspr-writeback)

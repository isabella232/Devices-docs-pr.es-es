---
title: Autenticación moderna en Surface Hub
description: En esta página se describe el uso de la autenticación moderna en Surface Hub en contraste con la autenticación básica heredada.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474776"
---
# <a name="modern-authentication-on-surface-hub"></a>Autenticación moderna en Surface Hub

La actualización de Windows 10 Team 2020 agrega compatibilidad con la autenticación moderna de la cuenta del dispositivo Hub en algunos escenarios. Una vez instalada la actualización de 2020, puede migrar desde la autenticación básica heredada para usar las mejoras de seguridad más recientes si la cuenta del dispositivo se autentica a través de Azure Active Directory y el buzón de la cuenta está hospedado en Exchange Online. Con la actualización de 2020, Surface Hub admite protocolos de Exchange Web Services (EWS) y autenticación basada en la Biblioteca de autenticación de Active Directory (ADAL) al sincronizar la cuenta del dispositivo con Exchange Online.

Para las nuevas cuentas basadas en la nube, Surface Hub usa automáticamente la autenticación moderna para conectarse a Exchange Online sin necesidad de configuración adicional más allá de simplemente agregar la cuenta de dispositivo a Surface Hub con el formato [alias@contoso.com](mailto:alias@contoso.com). No use el formato heredado: Contoso\alias, que no es compatible con la autenticación moderna. Para obtener más información, consulta [crear y probar una cuenta de dispositivo.](create-and-test-a-device-account-surface-hub.md)

> [!NOTE]
> La autenticación moderna no es compatible con las cuentas locales de Surface Hub. Las cuentas solo deben usar Azure AD para la autenticación.

---
title: Autenticación moderna en Surface Hub
description: Esta página describe el uso de la autenticación moderna en Surface Hub, en contraste con la autenticación básica heredada.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004472"
---
# Autenticación moderna en Surface Hub

La compatibilidad con la autenticación moderna de las cuentas basadas en la nube está totalmente integrada en la próxima actualización de Windows 10 Team 2020, con versiones preliminares disponibles en el [programa Windows Insider](https://insider.windows.com/). Una vez [instalada la versión preliminar](surface-hub-install-2020preview.md), puede migrar desde la autenticación básica heredada y usar las últimas mejoras de seguridad de Microsoft Azure y Exchange Online. Con la actualización de 2020, Surface Hub es compatible con los protocolos de servicios web Exchange (EWS) y la autenticación basada en la biblioteca de autenticación de Active Directory (ADAL) que habilita Exchange Online para la sincronización de cuentas de dispositivos.

Para las nuevas cuentas basadas en la nube, Surface Hub usa de forma automática la autenticación moderna para conectarse a Exchange online sin requerir una configuración adicional más allá de la creación de cuentas de dispositivos con el formato [alias@contoso.com](mailto:alias@contoso.com). No use el formato heredado: Contoso\alias, que no es compatible con la autenticación moderna. Para obtener más información, consulta [crear cuenta de dispositivo de Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub no admite la autenticación moderna para cuentas locales. Las cuentas deben crearse en la nube.


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
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893157"
---
# <span data-ttu-id="7d4c1-104">Autenticación moderna en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="7d4c1-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="7d4c1-105">La compatibilidad con la autenticación moderna de las cuentas basadas en la nube está totalmente integrada en Windows 10 Team 2020 Update, lo que le permite migrar desde la autenticación básica heredada y usar las últimas mejoras de seguridad de Microsoft Azure y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7d4c1-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="7d4c1-106">Con la actualización de 2020, Surface Hub es compatible con los protocolos de servicios web Exchange (EWS) y la autenticación basada en la biblioteca de autenticación de Active Directory (ADAL) que habilita Exchange Online para la sincronización de cuentas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7d4c1-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="7d4c1-107">Para las nuevas cuentas basadas en la nube, Surface Hub usa de forma automática la autenticación moderna para conectarse a Exchange online sin requerir una configuración adicional más allá de la creación de cuentas de dispositivos con el formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7d4c1-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="7d4c1-108">No use el formato heredado: Contoso\alias, que no es compatible con la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="7d4c1-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="7d4c1-109">Para obtener más información, consulta [crear cuenta de dispositivo de Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="7d4c1-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="7d4c1-110">Surface Hub no admite la autenticación moderna para cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="7d4c1-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="7d4c1-111">Las cuentas deben crearse en la nube.</span><span class="sxs-lookup"><span data-stu-id="7d4c1-111">The accounts must be created in the cloud.</span></span>


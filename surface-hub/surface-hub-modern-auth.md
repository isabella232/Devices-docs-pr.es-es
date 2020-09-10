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
# <span data-ttu-id="f0182-104">Autenticación moderna en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f0182-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="f0182-105">La compatibilidad con la autenticación moderna de las cuentas basadas en la nube está totalmente integrada en la próxima actualización de Windows 10 Team 2020, con versiones preliminares disponibles en el [programa Windows Insider](https://insider.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="f0182-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="f0182-106">Una vez [instalada la versión preliminar](surface-hub-install-2020preview.md), puede migrar desde la autenticación básica heredada y usar las últimas mejoras de seguridad de Microsoft Azure y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f0182-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="f0182-107">Con la actualización de 2020, Surface Hub es compatible con los protocolos de servicios web Exchange (EWS) y la autenticación basada en la biblioteca de autenticación de Active Directory (ADAL) que habilita Exchange Online para la sincronización de cuentas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f0182-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="f0182-108">Para las nuevas cuentas basadas en la nube, Surface Hub usa de forma automática la autenticación moderna para conectarse a Exchange online sin requerir una configuración adicional más allá de la creación de cuentas de dispositivos con el formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f0182-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="f0182-109">No use el formato heredado: Contoso\alias, que no es compatible con la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="f0182-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="f0182-110">Para obtener más información, consulta [crear cuenta de dispositivo de Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="f0182-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="f0182-111">Surface Hub no admite la autenticación moderna para cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="f0182-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="f0182-112">Las cuentas deben crearse en la nube.</span><span class="sxs-lookup"><span data-stu-id="f0182-112">The accounts must be created in the cloud.</span></span>


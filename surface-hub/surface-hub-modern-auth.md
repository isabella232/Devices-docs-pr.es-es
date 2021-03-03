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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385168"
---
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="c5eeb-104">Autenticación moderna en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c5eeb-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="c5eeb-105">La actualización de Windows 10 Team 2020 agrega compatibilidad con la autenticación moderna de la cuenta del dispositivo Hub en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="c5eeb-106">Una vez instalada la actualización de 2020, puede migrar desde la autenticación básica heredada para usar las mejoras de seguridad más recientes si la cuenta del dispositivo se autentica a través de Azure Active Directory y el buzón de la cuenta está hospedado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="c5eeb-107">Con la actualización de 2020, Surface Hub admite protocolos de Exchange Web Services (EWS) y autenticación basada en la Biblioteca de autenticación de Active Directory (ADAL) al sincronizar la cuenta del dispositivo con Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="c5eeb-108">Para las nuevas cuentas basadas en la nube, Surface Hub usa automáticamente la autenticación moderna para conectarse a Exchange Online sin necesidad de configuración adicional más allá de simplemente crear cuentas de dispositivo con el formato [alias@contoso.com](mailto:alias@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5eeb-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="c5eeb-109">No use el formato heredado: Contoso\alias, que no es compatible con la autenticación moderna.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="c5eeb-110">Para obtener más información, consulta [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span><span class="sxs-lookup"><span data-stu-id="c5eeb-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="c5eeb-111">Surface Hub no admite la autenticación moderna para cuentas locales.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="c5eeb-112">Las cuentas deben crearse en la nube.</span><span class="sxs-lookup"><span data-stu-id="c5eeb-112">The accounts must be created in the cloud.</span></span>


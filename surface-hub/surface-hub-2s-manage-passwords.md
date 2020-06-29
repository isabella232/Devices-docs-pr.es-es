---
title: Administrar la rotación de contraseñas de cuentas de dispositivos
description: Más información sobre cómo configurar Surface Hub 2 cuentas locales con PowerShell
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836641"
---
# <span data-ttu-id="0df77-104">Administrar la rotación de contraseñas de cuentas de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0df77-104">Manage device account password rotation</span></span>

<span data-ttu-id="0df77-105">Puede configurar Surface Hub 2S para cambiar automáticamente la contraseña de la cuenta del dispositivo sin necesidad de actualizar manualmente la información de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0df77-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="0df77-106">Si activa la rotación de contraseñas, Surface Hub 2S cambiará la contraseña cada 7 días.</span><span class="sxs-lookup"><span data-stu-id="0df77-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="0df77-107">Las contraseñas generadas automáticamente contienen 15-32 caracteres, entre los que se incluyen una combinación de letras en mayúsculas y minúsculas, números y caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="0df77-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="0df77-108">Las contraseñas no cambian durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="0df77-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="0df77-109">Si Surface Hub 2S está desactivado, intenta cambiar la contraseña inmediatamente cuando está activada o cada 10 minutos hasta que tenga éxito.</span><span class="sxs-lookup"><span data-stu-id="0df77-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>

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
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474737"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="6580c-105">Aplicación de directivas de ActiveSync a las cuentas de dispositivo (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="6580c-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="6580c-106">Los Surface Hub que usan cuentas de dispositivo \*\*\*\* de Active Directory (aprovisionadas en el concentrador en formato dominio\nombredeusuario) y los servicios de Exchange locales usan ActiveSync para sincronizar el correo y el calendario.</span><span class="sxs-lookup"><span data-stu-id="6580c-106">Surface Hubs using Active Directory device accounts (provisioned on the Hub in **domain\username** format) and on-premises Exchange services make use of ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="6580c-107">Esto permite a los usuarios unirse e iniciar reuniones programadas desde Surface Hub, así como enviar por correo electrónico cualquier pizarra interactiva realizada durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="6580c-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="6580c-108">Para que estas características funcionen, las directivas de ActiveSync de tu organización deben configurarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6580c-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="6580c-109">No puede haber ninguna directiva global que bloquee la sincronización del buzón de recursos que está usando la cuenta del dispositivo de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6580c-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="6580c-110">Si hay una directiva de bloqueo de este tipo, debes agregar Surface Hub como dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="6580c-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="6580c-111">Debes establecer una directiva de buzón de dispositivo móvil donde la **PasswordEnabled** configuración esté establecida en False.</span><span class="sxs-lookup"><span data-stu-id="6580c-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="6580c-112">Otras opciones de configuración de directiva de buzón de dispositivo móvil no son compatibles con el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="6580c-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="6580c-113">Permitir deviceid</span><span class="sxs-lookup"><span data-stu-id="6580c-113">Allowing the DeviceID</span></span>

<span data-ttu-id="6580c-114">La organización puede tener una directiva global que impida la sincronización de cuentas de dispositivos aprovisionadas en Surface Hubs.</span><span class="sxs-lookup"><span data-stu-id="6580c-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="6580c-115">Para configurar esta propiedad, consulta [Permitir id. de dispositivo para ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span><span class="sxs-lookup"><span data-stu-id="6580c-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="6580c-116">Configuración PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="6580c-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="6580c-117">La cuenta del dispositivo debe tener una directiva ActiveSync donde el atributo **PasswordEnabled** esté establecido en False o 0.</span><span class="sxs-lookup"><span data-stu-id="6580c-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="6580c-118">Para configurar esta propiedad, consulta [Creación de una directiva de Microsoft Exchange ActiveSync compatible con Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span><span class="sxs-lookup"><span data-stu-id="6580c-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 






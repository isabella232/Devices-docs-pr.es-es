---
title: Propiedades de Microsoft Exchange (Surface Hub)
description: Algunas propiedades de Microsoft Exchange de la cuenta del dispositivo se deben establecer en determinados valores para obtener la mejor experiencia de reunión en Microsoft Surface Hub.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Propiedades de Microsoft Exchange, cuenta del dispositivo, Surface Hub, cmdlet de Windows PowerShell
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836241"
---
# <span data-ttu-id="38dba-104">Propiedades de Microsoft Exchange (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="38dba-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="38dba-105">Algunas propiedades de Microsoft Exchange de la cuenta del dispositivo se deben establecer en determinados valores para obtener la mejor experiencia de reunión en Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="38dba-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="38dba-106">La siguiente tabla enumera varias propiedades de Exchange basadas en parámetros de cmdlet de PowerShell, su propósito y los valores en los que se deberían establecer.</span><span class="sxs-lookup"><span data-stu-id="38dba-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="38dba-107">Propiedad</span><span class="sxs-lookup"><span data-stu-id="38dba-107">Property</span></span></th>
<th align="left"><span data-ttu-id="38dba-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="38dba-108">Description</span></span></th>
<th align="left"><span data-ttu-id="38dba-109">Valor</span><span class="sxs-lookup"><span data-stu-id="38dba-109">Value</span></span></th>
<th align="left"><span data-ttu-id="38dba-110">Impacto</span><span class="sxs-lookup"><span data-stu-id="38dba-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38dba-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="38dba-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-112">El parámetro AutomateProcessing habilita o deshabilita el procesamiento de calendario en el buzón.</span><span class="sxs-lookup"><span data-stu-id="38dba-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="38dba-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-114">El Surface Hub podrá aceptar o rechazar automáticamente las convocatorias de reunión según su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="38dba-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38dba-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="38dba-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-116">El parámetro AddOrganizerToSubject especifica si el nombre del organizador de la reunión se usa como el asunto de la convocatoria de reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-117">$False</span><span class="sxs-lookup"><span data-stu-id="38dba-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-118">La pantalla de bienvenida no mostrará al organizador de la reunión dos veces (en lugar de mostrarlo tanto como el organizador como el asunto de la reunión).</span><span class="sxs-lookup"><span data-stu-id="38dba-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38dba-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="38dba-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-120">El parámetro AllowConflicts especifica si se permiten convocatorias de reunión en conflicto.</span><span class="sxs-lookup"><span data-stu-id="38dba-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-121">$False</span><span class="sxs-lookup"><span data-stu-id="38dba-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-122">El Surface Hub rechazará las convocatorias de reunión que entren en conflicto con la hora de otra reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38dba-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="38dba-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-124">El parámetro DeleteComments especifica si se quita o se mantiene cualquier texto en el cuerpo del mensaje de las convocatorias de reunión entrantes.</span><span class="sxs-lookup"><span data-stu-id="38dba-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-125">$False</span><span class="sxs-lookup"><span data-stu-id="38dba-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-126">El cuerpo del mensaje de las reuniones se puede conservar y recuperar desde un Surface Hub si lo necesitas durante una reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38dba-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="38dba-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-128">El parámetro DeleteSubject especifica si se debe quitar o mantener el asunto de las convocatorias de reunión entrantes.</span><span class="sxs-lookup"><span data-stu-id="38dba-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-129">$False</span><span class="sxs-lookup"><span data-stu-id="38dba-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-130">Los temas de las convocatorias de reunión se puede mostrar en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="38dba-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38dba-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="38dba-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-132">El parámetro RemovePrivateProperty especifica si se borra la marca privada para las convocatorias de reunión entrantes.</span><span class="sxs-lookup"><span data-stu-id="38dba-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-133">$False</span><span class="sxs-lookup"><span data-stu-id="38dba-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-134">Los temas de las reuniones privadas se mostrará como Privado en la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="38dba-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38dba-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="38dba-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-136">El parámetro AddAdditionalResponse especifica si se enviará información adicional desde el buzón de recursos al responder a las convocatorias de reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-137">$True</span><span class="sxs-lookup"><span data-stu-id="38dba-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-138">Cuando se envía una respuesta a una convocatoria de reunión, se proporcionará texto personalizado en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="38dba-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38dba-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="38dba-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-140">El parámetro AdditionalResponse especifica la información adicional que se incluirá en las respuestas a las convocatorias de reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="38dba-141">Nota: </strong> este texto no se enviará a menos que AddAdditionalResponse se establezca en $true.</span><span class="sxs-lookup"><span data-stu-id="38dba-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="38dba-142">Tu elección: la respuesta adicional se puede usar para indicar a los usuarios cómo usar un Surface Hub o guiarlos a los recursos.</span><span class="sxs-lookup"><span data-stu-id="38dba-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="38dba-143">Al añadir un mensaje de respuesta adicional se puede proporcionar a los usuarios una introducción sobre cómo pueden usar un Surface Hub en su reunión.</span><span class="sxs-lookup"><span data-stu-id="38dba-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 






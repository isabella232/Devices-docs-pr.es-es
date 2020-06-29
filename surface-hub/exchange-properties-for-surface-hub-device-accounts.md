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
# Propiedades de Microsoft Exchange (Surface Hub)


Algunas propiedades de Microsoft Exchange de la cuenta del dispositivo se deben establecer en determinados valores para obtener la mejor experiencia de reunión en Microsoft Surface Hub. La siguiente tabla enumera varias propiedades de Exchange basadas en parámetros de cmdlet de PowerShell, su propósito y los valores en los que se deberían establecer.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Propiedad</th>
<th align="left">Descripción</th>
<th align="left">Valor</th>
<th align="left">Impacto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>El parámetro AutomateProcessing habilita o deshabilita el procesamiento de calendario en el buzón.</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>El Surface Hub podrá aceptar o rechazar automáticamente las convocatorias de reunión según su disponibilidad.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>El parámetro AddOrganizerToSubject especifica si el nombre del organizador de la reunión se usa como el asunto de la convocatoria de reunión.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>La pantalla de bienvenida no mostrará al organizador de la reunión dos veces (en lugar de mostrarlo tanto como el organizador como el asunto de la reunión).</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>El parámetro AllowConflicts especifica si se permiten convocatorias de reunión en conflicto.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>El Surface Hub rechazará las convocatorias de reunión que entren en conflicto con la hora de otra reunión.</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>El parámetro DeleteComments especifica si se quita o se mantiene cualquier texto en el cuerpo del mensaje de las convocatorias de reunión entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>El cuerpo del mensaje de las reuniones se puede conservar y recuperar desde un Surface Hub si lo necesitas durante una reunión.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>El parámetro DeleteSubject especifica si se debe quitar o mantener el asunto de las convocatorias de reunión entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Los temas de las convocatorias de reunión se puede mostrar en el Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>El parámetro RemovePrivateProperty especifica si se borra la marca privada para las convocatorias de reunión entrantes.</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Los temas de las reuniones privadas se mostrará como Privado en la pantalla de bienvenida.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>El parámetro AddAdditionalResponse especifica si se enviará información adicional desde el buzón de recursos al responder a las convocatorias de reunión.</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>Cuando se envía una respuesta a una convocatoria de reunión, se proporcionará texto personalizado en la respuesta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>El parámetro AdditionalResponse especifica la información adicional que se incluirá en las respuestas a las convocatorias de reunión.</p>
<div class="alert">
<strong>Nota: </strong> este texto no se enviará a menos que AddAdditionalResponse se establezca en $true.
</div>
<div>
 
</div></td>
<td align="left"><p>Tu elección: la respuesta adicional se puede usar para indicar a los usuarios cómo usar un Surface Hub o guiarlos a los recursos.</p></td>
<td align="left"><p>Al añadir un mensaje de respuesta adicional se puede proporcionar a los usuarios una introducción sobre cómo pueden usar un Surface Hub en su reunión.</p></td>
</tr>
</tbody>
</table>

 

 

 






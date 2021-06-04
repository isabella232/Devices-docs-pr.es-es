---
title: Cambiar la cuenta del dispositivo de Microsoft Surface Hub.
description: Puedes cambiar la cuenta del dispositivo en Configuración para agregar una cuenta si no había ya una aprovisionada o para cambiar las propiedades de una cuenta que ya estaba aprovisionada.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: cambiar la cuenta del dispositivo, cambiar las propiedades, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836753"
---
# Cambiar la cuenta del dispositivo de Microsoft Surface Hub.


Puedes cambiar la cuenta del dispositivo en Configuración para agregar una cuenta si no había ya una aprovisionada o para cambiar las propiedades de una cuenta que ya estaba aprovisionada.

##  <a name="details"></a>Detalles


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Valor</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Nombre principal del usuario</p></td>
<td align="left"><p>El nombre principal de usuario (UPN) de la cuenta del dispositivo.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Contraseña</p></td>
<td align="left"><p>La contraseña correspondiente a la cuenta del dispositivo.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Dominio</p></td>
<td align="left"><p>El dominio al que pertenece la cuenta del dispositivo. Este campo no tiene que proporcionarse en las cuentas de Office 365.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Nombre de usuario</p></td>
<td align="left"><p>El nombre de usuario de la cuenta del dispositivo. Este campo no tiene que proporcionarse en las cuentas de Office 365.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Dirección de Protocolo de inicio de sesión (SIP)</p></td>
<td align="left"><p>La dirección SIP de la cuenta del dispositivo.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Servidor Microsoft Exchange</p></td>
<td align="left"><p>Este es el servidor Exchange de la cuenta del dispositivo. El nombre de usuario y la contraseña de la cuenta del dispositivo deben poder autenticarse en el servidor Exchange especificado.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Habilitar los servicios Exchange</p></td>
<td align="left"><p>Cuando estén activados, se habilitarán todos los servicios de Exchange (por ejemplo, el calendario en la pantalla de bienvenida y el envío de pizarras por correo electrónico). Si no están activados, se deshabilitarán todos los servicios de Exchange y no será necesario proporcionar el servidor Exchange.</p></td>
</tr>
</tbody>
</table>

 

##  <a name="what-happened"></a>Qué sucede


El UPN y la contraseña se usan para validar la cuenta en AD o Azure AD. Si se produce un error en la validación, deberás proporcionar el dominio y el nombre de usuario.

Una vez proporcionadas las credenciales, intentaremos detectar la dirección SIP. Si no se encuentra una dirección SIP, Skype Empresarial usará el UPN como la dirección SIP. Si esta no es la dirección SIP de la cuenta, deberás proporcionar la dirección SIP.

Se deberá proporcionar la dirección del servidor Exchange si el dispositivo no puede encontrar un servidor asociado a las credenciales de inicio de sesión. Microsoft Surface Hub usará el servidor Exchange para comunicarse con ActiveSync, que habilita varias características clave en el dispositivo.

##  <a name="related-topics"></a>Temas relacionados


[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 






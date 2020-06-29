---
title: Hoja de cálculo del programa de instalación (Surface Hub)
description: Cuando hayas terminado la preinstalación y estés preparado para iniciar la primera instalación de tu Microsoft Surface Hub, asegúrate de que tienes toda la información que se muestra en esta sección.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: Hoja de cálculo del programa de instalación, antes de la instalación, primera instalación
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836449"
---
# Hoja de cálculo del programa de instalación (Surface Hub)


Cuando hayas terminado la preinstalación y estés preparado para iniciar la primera instalación de tu Microsoft Surface Hub, asegúrate de que tienes toda la información que se muestra en esta sección.

Debes rellenar una lista para cada Surface Hub que necesitas configurar, aunque cierta información se puede usar en todos los Surface Hubs, como la información de proxy o las credenciales de dominio. Parte de esta información puede no ser necesaria, en función de cómo hayas decidido configurar el dispositivo o según cómo esté configurado el entorno de la infraestructura de la organización.

<table>
<tr>
<th>Propiedad</th>
<th>Esto se usa para</th>
<th>Ejemplo</th>
<th>Valor real</th>
</tr>
<tr>
<td>
<p>Información de proxy</p>
</td>
<td>
<p>Si la red usa a un proxy para el acceso a la red o a Internet, debes proporcionar un script o información del servidor o el puerto.</p>
</td>
<td>
<p>Script de proxy: <code>http://contoso/proxy.pa</code> </br>
- O bien </br>
Información de servidor y puerto: 10.10.10.100, puerto 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Credenciales de red inalámbrica (nombre de usuario y contraseña)</p>
</td>
<td>
<p>Si decides conectar tu dispositivo a una red Wi-Fi y la red inalámbrica requiere credenciales de usuario.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>UPN de la cuenta del dispositivo o Dominio\nombre de usuario y la contraseña de la cuenta del dispositivo</p>
</td>
<td>
<p>Este es el nombre principal de usuario (UPN) o el dominio\nombre de usuario y la contraseña de la cuenta del dispositivo. El correo electrónico, el calendario y Skype Empresarial dependen de una cuenta del dispositivo compatible.</p>
</td>
<td>
<p> UPN: ConfRoom15@contoso.com, #Passw0rd1 </br>
- O bien <br> 
Dominio y nombre de usuario: CONTOSO\ConfRoom15, #Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Servidor Microsoft Exchange de la cuenta del dispositivo</p>
</td>
<td>
<p>Este es el servidor Exchange de la cuenta del dispositivo.
El correo electrónico, el calendario y Skype Empresarial dependen de una cuenta del dispositivo compatible.
Para que el correo electrónico y el calendario funcionen, la cuenta del dispositivo debe tener un servidor Exchange válido. El dispositivo intentará encontrar esto automáticamente.</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Dirección de Protocolo de inicio de sesión (SIP) de la cuenta del dispositivo</p>
</td>
<td>
<p>Esta es la dirección SIP de Skype Empresarial de la cuenta del dispositivo.
El correo electrónico, el calendario y Skype Empresarial dependen de una cuenta del dispositivo compatible.
Para que Skype Empresarial funcione, la cuenta del dispositivo debe tener una dirección SIP válida. El dispositivo intentará encontrar esto automáticamente.</p>
</td>
<td>
<p>sip: ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nombre descriptivo</p>
</td>
<td>
<p>El nombre descriptivo del dispositivo es el nombre de emisión que los usuarios verán cuando intenten conectarse de forma inalámbrica al Surface Hub. Este nombre se mostrará de forma destacada en la pantalla del Surface Hub.
Se recomienda que el nombre descriptivo que elijas sea reconocible y único para que los usuarios puedan distinguir un Surface Hub de otro al intentar conectarse.</p>
</td>
<td>
<p>Sala de conferencias 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Nombre de dispositivo</p>
</td>
<td>
<p>El nombre del dispositivo es el nombre que se usará para unirse a un dominio y es la identidad que verás en el proveedor MDM si el dispositivo está inscrito en el MDM.
El nombre del dispositivo que elijas no debe ser el mismo nombre que el de otro dispositivo que esté en el dominio de Active Directory del usuario (si decides unir el dispositivo a un dominio). El dispositivo no puede unir el dominio si su nombre no es único.
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VAS A UNIRTE A AZURE AD</b></p>
</td>
</tr>
<tr>
<td>
<p>Credenciales de usuario de inquilino de Azure AD (nombre de usuario y contraseña)</p>
</td>
<td>
<p>Si decides tener usuarios en la organización de Azure Active Directory (Azure AD) que se conviertan en administradores del dispositivo, tendrás que unirte a Azure AD.
Para unirte a Azure AD, necesitarás credenciales de usuario válidas.</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI VAS A UNIRTE A UN DOMINIO</b></p>
</td>
</tr>
<tr>
<td>
<p>Dominio al que unirse</p>
</td>
<td>
<p>Este es el dominio al que debes unirte para que un grupo de seguridad de tu elección pueda ser administrador del dispositivo.
Es posible que necesites el nombre de dominio completo (FQDN).</p>
</td>
<td>
<p>contoso (nombre corto) O contoso.corp.com (FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Credenciales de cuenta de dominio (nombre de usuario y contraseña)</p>
</td>
<td>
<p>No puedes unirte a un dominio a menos que proporciones las credenciales de cuenta suficientes para unirte al dominio. Una vez que proporciones un dominio al que unirte y las credenciales para unirte al dominio, un grupo de seguridad de tu elección podrá cambiar la configuración del dispositivo.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>Alias del grupo de seguridad de administrador</p>
</td>
<td>
<p>Este es un grupo de seguridad de tu Active Directory (AD); todos los miembros de este grupo de seguridad pueden cambiar la configuración del dispositivo.</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI ESTÁS USANDO UN ADMINISTRADOR LOCAL</b></p>
</td>
</tr>
<tr>
<td>
<p>Credenciales de cuenta de administrador local (nombre de usuario y contraseña)</p>
</td>
<td>
<p>Si no quieres unirte a un dominio de AD o a Azure AD, puedes crear una cuenta de administrador local en el dispositivo.</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>SI NECESITAS INSTALAR APLICACIONES O CERTIFICADOS</b></p>
</td>
</tr>
<tr>
<td>
<p>Unidad USB</p>
</td>
<td>
<p>Si ya sabes antes de la primera ejecución que quieres instalar certificados o aplicaciones universales, sigue los pasos descritos en <a href="provisioning-packages-for-certificates-surface-hub.md">Crear paquetes de aprovisionamiento</a>. Los paquetes de aprovisionamiento se crearán en una unidad USB.</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 






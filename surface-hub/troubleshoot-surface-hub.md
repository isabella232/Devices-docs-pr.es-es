---
title: Solucionar problemas de Microsoft Surface Hub
description: Solucionar problemas comunes, incluidos los problemas de instalación y errores de Exchange ActiveSync.
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: Solucionar problemas comunes, problemas de instalación y errores de Exchange ActiveSync
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834890"
---
# Solucionar problemas de Microsoft Surface Hub


Solucionar problemas comunes, incluidos los problemas de instalación y errores de Exchange ActiveSync.

La [herramienta Diagnóstico de hardware de SurfaceHub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) incluye pruebas interactivas que te permiten confirmar que la funcionalidad esencial del hub esté funcionando según lo previsto. Además de probar el hardware, el diagnóstico puede probar la cuenta de recursos para comprobar si está configurada correctamente para tu entorno. Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub. Para obtener información de uso, consulta [Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).

Los problemas comunes se enumeran en la siguiente tabla, junto con las causas y las posibles soluciones. La sección [Solución de problemas del programa de instalación](#setup-troubleshooting) contiene una lista de problemas en el dispositivo, junto con varios tipos de problemas que se pueden encontrar durante la experiencia de primera ejecución. La sección [Errores de Exchange ActiveSync](#exchange-activesync-errors) enumera errores comunes que el dispositivo puede encontrar al intentar sincronizarse con un servidor Microsoft Exchange ActiveSync.




## Solución de problemas del programa de instalación


Esta sección enumera las causas y posibles correcciones para ayudar a solucionar problemas que puedes encontrar al configurar el Microsoft Surface Hub.

### En el dispositivo

Posibles correcciones para los problemas del Surface Hub después de haber completado el programa de primera ejecución.

<table>
<tr>
<th>Problema</th>
<th>Causas</th>
<th>Posibles soluciones</th>
</tr>
<tr>
<td rowspan="2">
<p>No recibir mensajes de aceptar o rechazar automáticamente.</p>
</td>
<td>
<p>La cuenta del dispositivo no está configurada para aceptar o rechazar mensajes automáticamente.</p>
</td>
<td>
<p>Usar el cmdlet de PowerShell <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</p>
</td>
</tr>
<tr>
<td>
<p>La cuenta del dispositivo no está configurada para procesar convocatorias de reunión externas.</p>
</td>
<td>
<p>Usar el cmdlet de PowerShell <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</p>
</td>
</tr>
<tr>
<td>
<p>El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (ninguna cuenta aprovisionada)".</p>
</td>
<td>
<p>No hay ninguna cuenta del dispositivo configurada en este Surface Hub.</p>
</td>
<td>
<p>Proporcionar una cuenta del dispositivo a través Configuración.</p>
</td>
</tr>
<tr>
<td>
<p>El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (sobreaprovisionadas)".</p>
</td>
<td>
<p>La cuenta del dispositivo está aprovisionada en demasiados dispositivos.</p>
</td>
<td>
<p>Quitar la cuenta del dispositivo de otros dispositivos a los que esté aprovisionada. Esto se puede realizar mediante el portal de administración de Exchange.</p>
</td>
</tr>
<tr>
<td>
<p>El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (credenciales no válidas)".</p>
</td>
<td>
<p>La contraseña de la cuenta del dispositivo ha expirado y ya no es válida.</p>
</td>
<td>
<p>Actualizar la contraseña de la cuenta en Configuración. Consulta también <a href="password-management-for-surface-hub-device-accounts.md">Administración de contraseñas</a>.</p>
</td>
</tr>
<tr>
<td>
<p>El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (directiva de cuenta)".</p>
</td>
<td>
<p>La cuenta del dispositivo está usando una directiva de ActiveSync no válida.</p>
</td>
<td>
<p>Asegúrate de que la cuenta del dispositivo tiene una directiva de ActiveSync donde <code>PasswordEnabled == False</code>.</p>
</td>
</tr>
<tr>
<td>
<p>El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Las citas pueden estar desactualizadas".</p>
</td>
<td>
<p>Exchange no está habilitado.</p>
</td>
<td>Habilitar la cuenta del dispositivo para los servicios de Exchange mediante Configuración. Debes asegurarte de que tienes el conjunto de directivas de ActiveSync correcto y de que has instalado también los certificados necesarios para que los servicios de Exchange funcionen.</td>
</tr>
<tr>
<td>
<p>No se puede iniciar sesión en Skype Empresarial.</p>
</td>
<td>
<p>La cuenta del dispositivo no tiene una propiedad de dirección de Protocolo de inicio de sesión (SIP).</p>
</td>
<td>
<p>La cuenta no tiene una propiedad de dirección SIP y su Nombre principal de usuario (UPN) no coincide con la dirección SIP real. La cuenta debe tener su dirección SIP establecida, o bien debería agregarse la dirección SIP mediante la aplicación Configuración.</p>
</td>
</tr>
<tr>
<td>
<p>No se puede iniciar sesión en Skype Empresarial.</p>
</td>
<td>
<p>La cuenta del dispositivo requiere un certificado para autenticarse en Skype Empresarial.</p>
</td>
<td>
<p>Instalar el certificado apropiado mediante el aprovisionamiento de paquetes.</p>
</td>
</tr>
</table>
 

### Primera ejecución

Correcciones posibles para los problemas con el programa de primera ejecución de Surface Hub.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Posibles soluciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>No se encuentra la cuenta al pedir el dominio y el nombre de usuario.</p></td>
<td align="left"><p>El dominio debe ser el nombre de dominio completo (FQDN).</p></td>
<td align="left"><p>Debe proporcionarse el FQDN en el campo de dominio.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>Página de la cuenta del dispositivo, problemas de configuración de la cuenta nueva

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Posibles soluciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>No se pudo encontrar la cuenta proporcionada en Azure AD.</p></td>
<td align="left"><p>El Nombre principal de usuario (UPN) de la cuenta proporcionada tiene un inquilino con el que no se puede contactar en Azure AD.</p></td>
<td align="left"><p>Asegúrate de que tienes una conexión a Internet activa y de que el dispositivo puede contactar con Microsoft Online Services. Asegúrate de que las credenciales de cuenta se han escrito correctamente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>No se puede alcanzar el directorio especificado.</p></td>
<td align="left"><p>El dominio de la cuenta proporcionada especifica un dominio que no se puede alcanzar.</p></td>
<td align="left"><p>Asegúrate de que tienes una conexión de red en funcionamiento y de que el dispositivo puede alcanzar el controlador de dominio. Asegúrate de que las credenciales de cuenta se han escrito correctamente. También puedes intentar usar el FQDN en su lugar.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>No se puede detectar automáticamente el servidor Exchange.</p></td>
<td align="left"><p>El servidor Exchange no está configurado para la detección automática.</p></td>
<td align="left"><p>Habilita la detección automática del servidor Exchange para la cuenta del dispositivo o escribe la dirección del servidor Exchange de la cuenta manualmente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>No se pudo detectar la dirección SIP después de escribir las credenciales de cuenta.</p></td>
<td align="left"><p>No había ninguna entrada de dirección SIP en Active Directory o Azure AD.</p></td>
<td align="left"><p>Asegúrate de que la cuenta está habilitada con Skype Empresarial y de que tiene una dirección SIP. Si no es así, puedes escribir la dirección SIP de forma manual en el cuadro de texto.</p></td>
</tr>
</tbody>
</table>

 

### Página de la cuenta del dispositivo, problemas de configuración de cuentas existentes

<table>
<tr>
<th>Problema</th>
<th>Causas</th>
<th>Códigos de error</th>
<th>Posibles soluciones</th>
</tr>
<tr>
<td>
<p>No se pudo autenticar la cuenta con las credenciales especificadas.</p>
</td>
<td>
<p>La cuenta no está habilitada como un usuario en Active Directory (AD), necesita una contraseña para su autenticación o la contraseña es incorrecta.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Asegúrate de que las credenciales se han escrito correctamente. Habilita la cuenta como un usuario en AD y agrega una contraseña o establece RoomMailboxPassword</p>. </td>
</tr>
<tr>
<td>
<p>Se muestra el error 0x800C0019 al proporcionar un servidor Exchange.</p>
</td>
<td>
<p>La cuenta del dispositivo requiere un certificado para autenticarse.</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>Instalar el certificado apropiado mediante el aprovisionamiento de paquetes.</p>
</td>
</tr>
<tr>
<td>
<p>Las credenciales de cuenta del dispositivo no son válidas para el servidor Exchange proporcionado.</p>
</td>
<td>
<p>El servidor Exchange proporcionado no se encuentra donde se hospeda el buzón de la cuenta del dispositivo.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Asegúrate de que estás proporcionando el servidor de correo de Exchange correcto para la cuenta del dispositivo.</p>
</td>
</tr>
<tr>
<td>
<p>Se agotó el tiempo de espera HTTP al intentar alcanzar el servidor Exchange.</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>No se pudo encontrar el servidor Exchange proporcionado.</p>
</td>
<td>
<p>No se pudo encontrar el servidor Exchange proporcionado.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Asegúrate de que tienes una red en funcionamiento o conexión a Internet y de que el servidor Exchange que proporcionaste es correcto.</p>
</td>
</tr>
<tr>
<td>
<p>HTTP no compatible.</p>
</td>
<td>
<p>Se proporcionó un servidor Exchange con <i>http://</i> en lugar de <i>https://</i>.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Usar un servidor Exchange que usa https.</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>Los usuarios llegan a la página titulada "Hay un problema con esta cuenta" en relación con ActiveSync.</p>
</div>
<div> </div>
</td>
<td>
<p>La directiva PasswordEnabled de ActiveSync está establecida en True (o 1).</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Crear una nueva directiva de ActiveSync en la que PasswordEnabled esté establecida en False (o 0) y, a continuación, aplica esa directiva a la cuenta.</p>
</td>
</tr>
<tr>
<td>
<p>El Surface Hube no tiene una conexión con Exchange.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Asegúrate de que tienes una red en funcionamiento o conexión a Internet.</p>
</td>
</tr>
<tr>
<td>
<p>Exchange devuelva un código de estado que indique un error.</p>
</td>
<td>
<p>Ninguno</p>
</td>
<td>
<p>Asegúrate de que tienes una red en funcionamiento o conexión a Internet.</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>Primera ejecución, problemas de la página de unión a un dominio

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Posibles soluciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Al intentar unirte a un dominio, se muestra un error por el que la cuenta no se pudo autenticar con las credenciales especificadas.</p></td>
<td align="left"><p>Las credenciales proporcionadas no se pueden unir al dominio especificado.</p></td>
<td align="left"><p>Escribe las credenciales correctas de una cuenta que exista en el dominio especificado.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Al especificar un grupo desde un dominio, se muestra un error por el que no se encontró el grupo en el dominio.</p></td>
<td align="left"><p>Es posible que el grupo se haya quitado o que ya no exista.</p></td>
<td align="left"><p>Comprueba que el grupo existe en el dominio.</p></td>
</tr>
</tbody>
</table>

 

### Primera ejecución, página del servidor Exchange

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Posibles soluciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Los usuarios llegan a esta página y se les pide la dirección del servidor Exchange.</p></td>
<td align="left"><p>El servidor Exchange no está configurado para la detección automática.</p></td>
<td align="left"><p>Habilita la detección automática del servidor Exchange para la cuenta del dispositivo o escribe la dirección del servidor Exchange de la cuenta manualmente.</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>Primera ejecución, problemas en el dispositivo

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Problema</th>
<th align="left">Causas</th>
<th align="left">Códigos de error</th>
<th align="left">Posibles soluciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>No se pueden sincronizar el correo ni el calendario.</p></td>
<td align="left"><p>La cuenta no estableció el Surface Hub como un dispositivo permitido.</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p>Para agregar el identificador de dispositivo de Surface Hub a la lista de permitidos, establece la <strong> </strong> propiedad ActiveSyncAllowedDeviceIds para el buzón.</p></td>
</tr>
</tbody>
</table>

 



 

## Errores de Exchange ActiveSync


En esta sección se muestran los códigos de estado, la asignación, los mensajes de usuario y las acciones que un administrador puede realizar para solucionar errores de Exchange ActiveSync.

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Código hexadecimal</th>
<th align="left">Asignación</th>
<th align="left">Mensaje descriptivo</th>
<th align="left">Acciones que debe realizar el administrador</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>Se debe actualizar la contraseña.</p></td>
<td align="left"><p>Actualizar la contraseña.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento. Espera unos instantes y vuelve a intentarlo o comprueba la configuración de la cuenta.</p></td>
<td align="left"><p>Comprueba que el nombre del servidor es correcto y accesible. Comprueba que el dispositivo está conectado a la red.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (las directivas no coinciden)</p></td>
<td align="left"><p>La cuenta está configurada con directivas que no son compatibles con Surface Hub.</p></td>
<td align="left"><p>Deshabilitar la directiva <strong>PasswordEnabled</strong> para esta cuenta.</p>
<p>Se ha producido un error que se producía un error en la política si la cuenta no recibe notificaciones del servidor en el intervalo de actualización de la Directiva.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>La cuenta tiene demasiadas asociaciones de dispositivo.</p></td>
<td align="left"><p>Elimina una o más asociaciones en el servidor.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento.</p></td>
<td align="left"><p>Espera a que el servidor vuelva a estar conectado. Si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED (las credenciales expiraron y deben actualizarse)</p></td>
<td align="left"><p>Se debe actualizar la contraseña.</p></td>
<td align="left"><p>Actualizar la contraseña.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento. Espera un momento o verifica la configuración de la cuenta.</p></td>
<td align="left"><p>Esto suele ser un error transitorio, pero si el problema persiste, comprueba el número de dispositivos asociados con la cuenta y elimina algunos de ellos si el número es grande.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>El buzón se migró a un servidor diferente.</p></td>
<td align="left"><p>Nunca deberías ver este error. Si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento. Espera un momento e inténtalo de nuevo, o verifica la configuración de la cuenta.</p></td>
<td align="left"><p>Comprueba el nombre del servidor para asegurarse de que es correcto. Si la cuenta está usando una autenticación basada en certificados, asegúrate de que el certificado sigue siendo válido y actualízalo si no es el caso.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>Falta o no es válida la contraseña de la cuenta o el certificado de cliente.</p></td>
<td align="left"><p>Actualiza la contraseña o implementa el certificado de cliente.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>La cuenta está configurada con directivas que no son compatibles con Surface Hub.</p></td>
<td align="left"><p>Deshabilitar la directiva PasswordEnabled para esta cuenta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>Se debe actualizar la contraseña.</p></td>
<td align="left"><p>Actualizar la contraseña.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>La red no es compatible con el tiempo de espera mínimo de inactividad requerido para recibir la notificación del servidor o el servidor está desconectado.</p></td>
<td align="left"><p>Comprueba que el servidor se está ejecutando. Comprueba la configuración de NAT.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>Este error se usa para interrumpir hanging sync y no se mostrará a los usuarios. Se mostrará en los datos de diagnóstico si fuerzas una sincronización interactiva, eliminas la cuenta o actualizas su configuración.</p></td>
<td align="left"><p>Nada</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento. Espera un momento o verifica la configuración de la cuenta.</p></td>
<td align="left"><p>Comprueba el nombre del servidor para asegurarse de que es correcto. Espera a que el servidor vuelva a estar conectado. Si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>No se puede conectar al servidor en este momento. Espera un momento o verifica la configuración de la cuenta.</p></td>
<td align="left"><p>Comprueba el nombre del servidor para asegurarse de que es correcto. Espera a que el servidor vuelva a estar conectado. Si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>El servidor Exchange requiere un certificado.</p></td>
<td align="left"><p>Importar el certificado EAS apropiado en el Surface Hub.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>La cuenta está configurada con directivas que no son compatibles con Surface Hub.</p></td>
<td align="left"><p>Deshabilitar la directiva PasswordEnabled para esta cuenta.</p>
<p>Se ha producido un error que se producía un error en la política si la cuenta no recibe notificaciones del servidor en el intervalo de actualización de la Directiva.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>El nombre del servidor no es válido.</p></td>
<td align="left"><p>Comprueba el nombre del servidor para asegurarse de que es correcto. Si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>No se puede conectar al servidor.</p></td>
<td align="left"><p>Comprueba el nombre del servidor para asegurarse de que es correcto. Desencadena una sincronización y, si el problema persiste, vuelve a aprovisionar la cuenta.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>No se pudo resolver el nombre del servidor o la dirección.</p></td>
<td align="left"><p>Asegúrate de que el nombre del servidor está escrito correctamente.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>Durante la detección automática del servidor Exchange, se aplica una directiva que impide que el usuario que haya iniciado sesión inicie sesión en el servidor.</p></td>
<td align="left"><p>Se trata de un problema de temporización. Vuelve a comprobar las credenciales de cuenta. Intenta volver a aprovisionarlas cuando sean correctas.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>El certificado de seguridad necesario para acceder a este recurso no es válido.</p></td>
<td align="left"><p>Instala el certificado correcto de ActiveSync necesario para la cuenta del dispositivo proporcionada.</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>WININET_E_INVALID_CA</p></td>
<td align="left"><p>La entidad de certificación no es válida o es incorrecta. No se pudo detectar automáticamente el servidor Exchange porque falta un certificado.</p></td>
<td align="left"><p>Instala el certificado correcto de ActiveSync necesario para la cuenta del dispositivo proporcionada.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>No se encontró el dominio proporcionado. El servidor Exchange no se pudo detectar automáticamente y no se proporcionó en la configuración.</p></td>
<td align="left"><p>Asegúrate de que el dominio especificado es el FQDN y de que se ha especificado un servidor Exchange en el cuadro de texto del servidor Exchange.</p></td>
</tr>
</tbody>
</table>

## Ponerse en contacto con soporte técnico

Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).


 
## Contenidos relacionados

- [Solucionar problemas de conexión de Miracast a Surface Hub](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 






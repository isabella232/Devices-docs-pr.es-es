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
# <span data-ttu-id="c1da4-104">Solucionar problemas de Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c1da4-104">Troubleshoot Microsoft Surface Hub</span></span>


<span data-ttu-id="c1da4-105">Solucionar problemas comunes, incluidos los problemas de instalación y errores de Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="c1da4-105">Troubleshoot common problems, including setup issues, Exchange ActiveSync errors.</span></span>

<span data-ttu-id="c1da4-106">La [herramienta Diagnóstico de hardware de SurfaceHub](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) incluye pruebas interactivas que te permiten confirmar que la funcionalidad esencial del hub esté funcionando según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-106">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contains interactive tests which allow you to confirm essential functionality of your Hub is working as expected.</span></span> <span data-ttu-id="c1da4-107">Además de probar el hardware, el diagnóstico puede probar la cuenta de recursos para comprobar si está configurada correctamente para tu entorno.</span><span class="sxs-lookup"><span data-stu-id="c1da4-107">In addition to testing hardware, the diagnostic can test the resource account to verify that it is configured properly for your environment.</span></span> <span data-ttu-id="c1da4-108">Si surgen problemas, los resultados se pueden guardar y compartir con el equipo de soporte técnico de SurfaceHub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-108">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="c1da4-109">Para obtener información de uso, consulta [Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span><span class="sxs-lookup"><span data-stu-id="c1da4-109">For usage information, see [Using the Surface Hub Hardware Diagnostic Tool to test a device account](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span></span>

<span data-ttu-id="c1da4-110">Los problemas comunes se enumeran en la siguiente tabla, junto con las causas y las posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="c1da4-110">Common issues are listed in the following table, along with causes and possible fixes.</span></span> <span data-ttu-id="c1da4-111">La sección [Solución de problemas del programa de instalación](#setup-troubleshooting) contiene una lista de problemas en el dispositivo, junto con varios tipos de problemas que se pueden encontrar durante la experiencia de primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1da4-111">The [Setup troubleshooting](#setup-troubleshooting) section contains a listing of on-device problems, along with several types of issues that may be encountered during the first-run experience.</span></span> <span data-ttu-id="c1da4-112">La sección [Errores de Exchange ActiveSync](#exchange-activesync-errors) enumera errores comunes que el dispositivo puede encontrar al intentar sincronizarse con un servidor Microsoft Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="c1da4-112">The [Exchange ActiveSync errors](#exchange-activesync-errors) section lists common errors the device may encounter when trying to synchronize with an Microsoft Exchange ActiveSync server.</span></span>




## <span data-ttu-id="c1da4-113">Solución de problemas del programa de instalación</span><span class="sxs-lookup"><span data-stu-id="c1da4-113">Setup troubleshooting</span></span>


<span data-ttu-id="c1da4-114">Esta sección enumera las causas y posibles correcciones para ayudar a solucionar problemas que puedes encontrar al configurar el Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-114">This section lists causes, and possible fixes to help troubleshoot issues you might find when you set up your Microsoft Surface Hub.</span></span>

### <span data-ttu-id="c1da4-115">En el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c1da4-115">On-device</span></span>

<span data-ttu-id="c1da4-116">Posibles correcciones para los problemas del Surface Hub después de haber completado el programa de primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1da4-116">Possible fixes for issues on the Surface Hub after you've completed the first-run program.</span></span>

<table>
<tr>
<th><span data-ttu-id="c1da4-117">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-117">Issue</span></span></th>
<th><span data-ttu-id="c1da4-118">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-118">Causes</span></span></th>
<th><span data-ttu-id="c1da4-119">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-119">Possible fixes</span></span></th>
</tr>
<tr>
<td rowspan="2">
<p><span data-ttu-id="c1da4-120">No recibir mensajes de aceptar o rechazar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-120">Not receiving automatic accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-121">La cuenta del dispositivo no está configurada para aceptar o rechazar mensajes automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-121">The device account isn't configured to automatically accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-122">Usar el cmdlet de PowerShell <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span><span class="sxs-lookup"><span data-stu-id="c1da4-122">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-123">La cuenta del dispositivo no está configurada para procesar convocatorias de reunión externas.</span><span class="sxs-lookup"><span data-stu-id="c1da4-123">The device account isn't configured to process external meeting requests.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-124">Usar el cmdlet de PowerShell <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span><span class="sxs-lookup"><span data-stu-id="c1da4-124">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-125">El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (ninguna cuenta aprovisionada)".</span><span class="sxs-lookup"><span data-stu-id="c1da4-125">Calendar is not showing on the Welcome screen, or message "Appointments of date (no account provisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-126">No hay ninguna cuenta del dispositivo configurada en este Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-126">No device account is set up on this Surface Hub.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-127">Proporcionar una cuenta del dispositivo a través Configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-127">Provision a device account through Settings.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-128">El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (sobreaprovisionadas)".</span><span class="sxs-lookup"><span data-stu-id="c1da4-128">Calendar is not showing on the Welcome screen or message "Appointments of date (overprovisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-129">La cuenta del dispositivo está aprovisionada en demasiados dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c1da4-129">The device account is provisioned on too many devices.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-130">Quitar la cuenta del dispositivo de otros dispositivos a los que esté aprovisionada.</span><span class="sxs-lookup"><span data-stu-id="c1da4-130">Remove the device account from other devices that it's provisioned to.</span></span> <span data-ttu-id="c1da4-131">Esto se puede realizar mediante el portal de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-131">This can be done using the Exchange admin portal.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-132">El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (credenciales no válidas)".</span><span class="sxs-lookup"><span data-stu-id="c1da4-132">Calendar is not showing on the Welcome screen or message "Appointments of date (invalid credentials)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-133">La contraseña de la cuenta del dispositivo ha expirado y ya no es válida.</span><span class="sxs-lookup"><span data-stu-id="c1da4-133">The device account's password has expired and is no longer valid.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-134">Actualizar la contraseña de la cuenta en Configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-134">Update the account's password in Settings.</span></span> <span data-ttu-id="c1da4-135">Consulta también <a href="password-management-for-surface-hub-device-accounts.md">Administración de contraseñas</a>.</span><span class="sxs-lookup"><span data-stu-id="c1da4-135">Also see <a href="password-management-for-surface-hub-device-accounts.md">Password management</a>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-136">El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Citas de fecha (directiva de cuenta)".</span><span class="sxs-lookup"><span data-stu-id="c1da4-136">Calendar is not showing on the Welcome screen or message "Appointments of date (account policy)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-137">La cuenta del dispositivo está usando una directiva de ActiveSync no válida.</span><span class="sxs-lookup"><span data-stu-id="c1da4-137">The device account is using an invalid ActiveSync policy.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-138">Asegúrate de que la cuenta del dispositivo tiene una directiva de ActiveSync donde <code>PasswordEnabled == False</code>.</span><span class="sxs-lookup"><span data-stu-id="c1da4-138">Make sure the device account has an ActiveSync policy where <code>PasswordEnabled == False</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-139">El calendario no se muestra en la pantalla de bienvenida o se está mostrando el mensaje "Las citas pueden estar desactualizadas".</span><span class="sxs-lookup"><span data-stu-id="c1da4-139">Calendar is not showing on the Welcome screen or message "Appointments may be out of date" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-140">Exchange no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-140">Exchange is not enabled.</span></span></p>
</td>
<td><span data-ttu-id="c1da4-141">Habilitar la cuenta del dispositivo para los servicios de Exchange mediante Configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-141">Enable the device account for Exchange services through Settings.</span></span> <span data-ttu-id="c1da4-142">Debes asegurarte de que tienes el conjunto de directivas de ActiveSync correcto y de que has instalado también los certificados necesarios para que los servicios de Exchange funcionen.</span><span class="sxs-lookup"><span data-stu-id="c1da4-142">You need to make sure you have the right set of ActiveSync policies and have also installed any necessary certificates for Exchange services to work.</span></span></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-143">No se puede iniciar sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c1da4-143">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-144">La cuenta del dispositivo no tiene una propiedad de dirección de Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="c1da4-144">The device account does not have a Session Initiation Protocol (SIP) address property.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-145">La cuenta no tiene una propiedad de dirección SIP y su Nombre principal de usuario (UPN) no coincide con la dirección SIP real.</span><span class="sxs-lookup"><span data-stu-id="c1da4-145">The account does not have a SIP address property and its User Principal Name (UPN) does not match the actual SIP address.</span></span> <span data-ttu-id="c1da4-146">La cuenta debe tener su dirección SIP establecida, o bien debería agregarse la dirección SIP mediante la aplicación Configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-146">The account must have its SIP address set, or the SIP address should be added using the Settings app.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-147">No se puede iniciar sesión en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c1da4-147">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-148">La cuenta del dispositivo requiere un certificado para autenticarse en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c1da4-148">The device account requires a certificate to authenticate into Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-149">Instalar el certificado apropiado mediante el aprovisionamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="c1da4-149">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
</table>
 

### <span data-ttu-id="c1da4-150">Primera ejecución</span><span class="sxs-lookup"><span data-stu-id="c1da4-150">First run</span></span>

<span data-ttu-id="c1da4-151">Correcciones posibles para los problemas con el programa de primera ejecución de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-151">Possible fixes for issues with Surface Hub first-run program.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-152">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-152">Issue</span></span></th>
<th align="left"><span data-ttu-id="c1da4-153">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-153">Causes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-154">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-154">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-155">No se encuentra la cuenta al pedir el dominio y el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="c1da4-155">Cannot find account when asked for domain and user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-156">El dominio debe ser el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="c1da4-156">Domain needs to be the fully qualified domain name (FQDN).</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-157">Debe proporcionarse el FQDN en el campo de dominio.</span><span class="sxs-lookup"><span data-stu-id="c1da4-157">The FQDN should be provided in the domain field.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a><span data-ttu-id="c1da4-158">Página de la cuenta del dispositivo, problemas de configuración de la cuenta nueva</span><span class="sxs-lookup"><span data-stu-id="c1da4-158">Device account page, issues for new account settings</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-159">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-159">Issue</span></span></th>
<th align="left"><span data-ttu-id="c1da4-160">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-160">Causes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-161">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-161">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-162">No se pudo encontrar la cuenta proporcionada en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1da4-162">Unable to find the provided account in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-163">El Nombre principal de usuario (UPN) de la cuenta proporcionada tiene un inquilino con el que no se puede contactar en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1da4-163">The provided account's User Principal Name (UPN) has a tenant that can't be reached in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-164">Asegúrate de que tienes una conexión a Internet activa y de que el dispositivo puede contactar con Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="c1da4-164">Make sure that you have a working Internet connection, and that the device can reach Microsoft Online Services.</span></span> <span data-ttu-id="c1da4-165">Asegúrate de que las credenciales de cuenta se han escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-165">Make sure the account credentials are entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-166">No se puede alcanzar el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-166">Unable to reach the specified directory.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-167">El dominio de la cuenta proporcionada especifica un dominio que no se puede alcanzar.</span><span class="sxs-lookup"><span data-stu-id="c1da4-167">The provided account domain specifies a domain that can't be reached.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-168">Asegúrate de que tienes una conexión de red en funcionamiento y de que el dispositivo puede alcanzar el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="c1da4-168">Make sure that you have a working network connection, and that the device can reach the domain controller.</span></span> <span data-ttu-id="c1da4-169">Asegúrate de que las credenciales de cuenta se han escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-169">Make sure the account credentials are entered correctly.</span></span> <span data-ttu-id="c1da4-170">También puedes intentar usar el FQDN en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c1da4-170">You can also try using the FQDN instead.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-171">No se puede detectar automáticamente el servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-171">Can't auto-discover Exchange server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-172">El servidor Exchange no está configurado para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="c1da4-172">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-173">Habilita la detección automática del servidor Exchange para la cuenta del dispositivo o escribe la dirección del servidor Exchange de la cuenta manualmente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-173">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-174">No se pudo detectar la dirección SIP después de escribir las credenciales de cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-174">Could not discover the SIP address after entering the account credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-175">No había ninguna entrada de dirección SIP en Active Directory o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1da4-175">There was no SIP address entry in Active Directory or Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-176">Asegúrate de que la cuenta está habilitada con Skype Empresarial y de que tiene una dirección SIP.</span><span class="sxs-lookup"><span data-stu-id="c1da4-176">Make sure the account is enabled with Skype for Business and has a SIP address.</span></span> <span data-ttu-id="c1da4-177">Si no es así, puedes escribir la dirección SIP de forma manual en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-177">If not, you can enter the SIP address manually into the text box.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c1da4-178">Página de la cuenta del dispositivo, problemas de configuración de cuentas existentes</span><span class="sxs-lookup"><span data-stu-id="c1da4-178">Device account page, issues for existing account settings</span></span>

<table>
<tr>
<th><span data-ttu-id="c1da4-179">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-179">Issue</span></span></th>
<th><span data-ttu-id="c1da4-180">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-180">Causes</span></span></th>
<th><span data-ttu-id="c1da4-181">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="c1da4-181">Error codes</span></span></th>
<th><span data-ttu-id="c1da4-182">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-182">Possible fixes</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-183">No se pudo autenticar la cuenta con las credenciales especificadas.</span><span class="sxs-lookup"><span data-stu-id="c1da4-183">Account could not authenticate with the specified credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-184">La cuenta no está habilitada como un usuario en Active Directory (AD), necesita una contraseña para su autenticación o la contraseña es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-184">The account is not enabled as a user in Active Directory (AD), needs a password to authenticate, or the password is incorrect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-185">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-185">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-186">Asegúrate de que las credenciales se han escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-186">Make sure the credentials are entered correctly.</span></span> <span data-ttu-id="c1da4-187">Habilita la cuenta como un usuario en AD y agrega una contraseña o establece RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="c1da4-187">Enable the account as a user in AD and add a password, or set the RoomMailboxPassword</span></span></p><span data-ttu-id="c1da4-188">.</span><span class="sxs-lookup"><span data-stu-id="c1da4-188">.</span></span> </td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-189">Se muestra el error 0x800C0019 al proporcionar un servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-189">Error 0x800C0019 is displayed when providing an Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-190">La cuenta del dispositivo requiere un certificado para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="c1da4-190">The device account requires a certificate to authenticate.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-191">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="c1da4-191">0x800C0019</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-192">Instalar el certificado apropiado mediante el aprovisionamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="c1da4-192">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-193">Las credenciales de cuenta del dispositivo no son válidas para el servidor Exchange proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-193">Device account credentials are not valid for the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-194">El servidor Exchange proporcionado no se encuentra donde se hospeda el buzón de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1da4-194">The provided Exchange server is not where the device account's mailbox is hosted.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-195">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-195">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-196">Asegúrate de que estás proporcionando el servidor de correo de Exchange correcto para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1da4-196">Make sure you are providing the correct Exchange mail server for the device account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-197">Se agotó el tiempo de espera HTTP al intentar alcanzar el servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-197">HTTP timeout while trying to reach Exchange server.</span></span></p>
</td>
<td></td>
<td>
<p><span data-ttu-id="c1da4-198">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="c1da4-198">0x80072EE2</span></span></p>
</td>
<td></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-199">No se pudo encontrar el servidor Exchange proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-199">Couldn't find the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-200">No se pudo encontrar el servidor Exchange proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-200">The Exchange server provided could not be found.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-201">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-201">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-202">Asegúrate de que tienes una red en funcionamiento o conexión a Internet y de que el servidor Exchange que proporcionaste es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-202">Ensure that you have a working network or Internet connection, and that the Exchange server you provided is correct.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-203">HTTP no compatible.</span><span class="sxs-lookup"><span data-stu-id="c1da4-203">http not supported.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-204">Se proporcionó un servidor Exchange con <i>http://</i> en lugar de <i>https://</i>.</span><span class="sxs-lookup"><span data-stu-id="c1da4-204">An Exchange server with <i>http://</i> instead of <i>https://</i> was provided.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-205">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-205">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-206">Usar un servidor Exchange que usa https.</span><span class="sxs-lookup"><span data-stu-id="c1da4-206">Use an Exchange server that uses https.</span></span></p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p><span data-ttu-id="c1da4-207">Los usuarios llegan a la página titulada "Hay un problema con esta cuenta" en relación con ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="c1da4-207">People land on the page titled "There's a problem with this account" regarding ActiveSync.</span></span></p>
</div>
<div> </div>
</td>
<td>
<p><span data-ttu-id="c1da4-208">La directiva PasswordEnabled de ActiveSync está establecida en True (o 1).</span><span class="sxs-lookup"><span data-stu-id="c1da4-208">The ActiveSync policy PasswordEnabled is set to True (or 1).</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-209">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-209">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-210">Crear una nueva directiva de ActiveSync en la que PasswordEnabled esté establecida en False (o 0) y, a continuación, aplica esa directiva a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-210">Create a new ActiveSync policy where PasswordEnabled is set to False (or 0), and then apply that policy to the account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-211">El Surface Hube no tiene una conexión con Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-211">The Surface Hub doesn't have a connection to Exchange.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-212">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-212">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-213">Asegúrate de que tienes una red en funcionamiento o conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="c1da4-213">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c1da4-214">Exchange devuelva un código de estado que indique un error.</span><span class="sxs-lookup"><span data-stu-id="c1da4-214">Exchange returns a status code indicating an error.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-215">Ninguno</span><span class="sxs-lookup"><span data-stu-id="c1da4-215">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c1da4-216">Asegúrate de que tienes una red en funcionamiento o conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="c1da4-216">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a><span data-ttu-id="c1da4-217">Primera ejecución, problemas de la página de unión a un dominio</span><span class="sxs-lookup"><span data-stu-id="c1da4-217">First run, Domain join page issues</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-218">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-218">Issue</span></span></th>
<th align="left"><span data-ttu-id="c1da4-219">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-219">Causes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-220">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-220">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-221">Al intentar unirte a un dominio, se muestra un error por el que la cuenta no se pudo autenticar con las credenciales especificadas.</span><span class="sxs-lookup"><span data-stu-id="c1da4-221">When trying to join a domain, an error shows that the account couldn't authenticate using the specified credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-222">Las credenciales proporcionadas no se pueden unir al dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-222">The credentials provided are not capable of joining the specified domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-223">Escribe las credenciales correctas de una cuenta que exista en el dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-223">Enter correct credentials for an account that exists in the specified domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-224">Al especificar un grupo desde un dominio, se muestra un error por el que no se encontró el grupo en el dominio.</span><span class="sxs-lookup"><span data-stu-id="c1da4-224">When specifying a group from a domain, an error shows that the group couldn't be found on the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-225">Es posible que el grupo se haya quitado o que ya no exista.</span><span class="sxs-lookup"><span data-stu-id="c1da4-225">The group may have been removed or no longer exists.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-226">Comprueba que el grupo existe en el dominio.</span><span class="sxs-lookup"><span data-stu-id="c1da4-226">Verify that the group exists within the domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c1da4-227">Primera ejecución, página del servidor Exchange</span><span class="sxs-lookup"><span data-stu-id="c1da4-227">First run, Exchange server page</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-228">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-228">Issue</span></span></th>
<th align="left"><span data-ttu-id="c1da4-229">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-229">Causes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-230">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-230">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-231">Los usuarios llegan a esta página y se les pide la dirección del servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-231">People land on this page and are asked for the Exchange server address.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-232">El servidor Exchange no está configurado para la detección automática.</span><span class="sxs-lookup"><span data-stu-id="c1da4-232">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-233">Habilita la detección automática del servidor Exchange para la cuenta del dispositivo o escribe la dirección del servidor Exchange de la cuenta manualmente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-233">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a><span data-ttu-id="c1da4-234">Primera ejecución, problemas en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c1da4-234">First run, On-device issues</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-235">Problema</span><span class="sxs-lookup"><span data-stu-id="c1da4-235">Issue</span></span></th>
<th align="left"><span data-ttu-id="c1da4-236">Causas</span><span class="sxs-lookup"><span data-stu-id="c1da4-236">Causes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-237">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="c1da4-237">Error codes</span></span></th>
<th align="left"><span data-ttu-id="c1da4-238">Posibles soluciones</span><span class="sxs-lookup"><span data-stu-id="c1da4-238">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-239">No se pueden sincronizar el correo ni el calendario.</span><span class="sxs-lookup"><span data-stu-id="c1da4-239">Can't sync mail/calendar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-240">La cuenta no estableció el Surface Hub como un dispositivo permitido.</span><span class="sxs-lookup"><span data-stu-id="c1da4-240">The account has not allowed the Surface Hub as an allowed device.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-241">0x86000C1C</span><span class="sxs-lookup"><span data-stu-id="c1da4-241">0x86000C1C</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-242">Para agregar el identificador de dispositivo de Surface Hub a la lista de permitidos, establece la <strong> </strong> propiedad ActiveSyncAllowedDeviceIds para el buzón.</span><span class="sxs-lookup"><span data-stu-id="c1da4-242">Add the Surface Hub device ID to the allowed list by setting the <strong>ActiveSyncAllowedDeviceIds</strong> property for the mailbox.</span></span></p></td>
</tr>
</tbody>
</table>

 



 

## <span data-ttu-id="c1da4-243">Errores de Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="c1da4-243">Exchange ActiveSync errors</span></span>


<span data-ttu-id="c1da4-244">En esta sección se muestran los códigos de estado, la asignación, los mensajes de usuario y las acciones que un administrador puede realizar para solucionar errores de Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="c1da4-244">This section lists status codes, mapping, user messages, and actions an admin can take to solve Exchange ActiveSync errors.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c1da4-245">Código hexadecimal</span><span class="sxs-lookup"><span data-stu-id="c1da4-245">Hex Code</span></span></th>
<th align="left"><span data-ttu-id="c1da4-246">Asignación</span><span class="sxs-lookup"><span data-stu-id="c1da4-246">Mapping</span></span></th>
<th align="left"><span data-ttu-id="c1da4-247">Mensaje descriptivo</span><span class="sxs-lookup"><span data-stu-id="c1da4-247">User-Friendly Message</span></span></th>
<th align="left"><span data-ttu-id="c1da4-248">Acciones que debe realizar el administrador</span><span class="sxs-lookup"><span data-stu-id="c1da4-248">Action admin should take</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-249">0x85010002</span><span class="sxs-lookup"><span data-stu-id="c1da4-249">0x85010002</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-250">E_HTTP_DENIED</span><span class="sxs-lookup"><span data-stu-id="c1da4-250">E_HTTP_DENIED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-251">Se debe actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-251">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-252">Actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-252">Update the password.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-253">0x80072EFD</span><span class="sxs-lookup"><span data-stu-id="c1da4-253">0x80072EFD</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-254">WININET_E_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="c1da4-254">WININET_E_CANNOT_CONNECT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-255">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-255">Can't connect to the server right now.</span></span> <span data-ttu-id="c1da4-256">Espera unos instantes y vuelve a intentarlo o comprueba la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-256">Wait a while and try again, or check the account settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-257">Comprueba que el nombre del servidor es correcto y accesible.</span><span class="sxs-lookup"><span data-stu-id="c1da4-257">Verify that the server name is correct and reachable.</span></span> <span data-ttu-id="c1da4-258">Comprueba que el dispositivo está conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="c1da4-258">Verify that the device is connected to the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-259">0x86000C29</span><span class="sxs-lookup"><span data-stu-id="c1da4-259">0x86000C29</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (las directivas no coinciden)</span><span class="sxs-lookup"><span data-stu-id="c1da4-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (policies don't match)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-261">La cuenta está configurada con directivas que no son compatibles con Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-261">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-262">Deshabilitar la directiva <strong>PasswordEnabled</strong> para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-262">Disable the <strong>PasswordEnabled</strong> policy for this account.</span></span></p>
<p><span data-ttu-id="c1da4-263">Se ha producido un error que se producía un error en la política si la cuenta no recibe notificaciones del servidor en el intervalo de actualización de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="c1da4-263">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-264">0x86000C4C</span><span class="sxs-lookup"><span data-stu-id="c1da4-264">0x86000C4C</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span><span class="sxs-lookup"><span data-stu-id="c1da4-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-266">La cuenta tiene demasiadas asociaciones de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1da4-266">The account has too many device partnerships.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-267">Elimina una o más asociaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c1da4-267">Delete one or more partnerships on the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-268">0x86000C0A</span><span class="sxs-lookup"><span data-stu-id="c1da4-268">0x86000C0A</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span><span class="sxs-lookup"><span data-stu-id="c1da4-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-270">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-270">Can't connect to the server right now.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-271">Espera a que el servidor vuelva a estar conectado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-271">Wait until the server comes back online.</span></span> <span data-ttu-id="c1da4-272">Si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-272">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-273">0x85050003</span><span class="sxs-lookup"><span data-stu-id="c1da4-273">0x85050003</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-274">E_CREDENTIALS_EXPIRED (las credenciales expiraron y deben actualizarse)</span><span class="sxs-lookup"><span data-stu-id="c1da4-274">E_CREDENTIALS_EXPIRED (Credentials have expired and need to be updated)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-275">Se debe actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-275">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-276">Actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-276">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-277">0x8505000D</span><span class="sxs-lookup"><span data-stu-id="c1da4-277">0x8505000D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-278">E_AIRSYNC_RESET_RETRY</span><span class="sxs-lookup"><span data-stu-id="c1da4-278">E_AIRSYNC_RESET_RETRY</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-279">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-279">Can't connect to the server right now.</span></span> <span data-ttu-id="c1da4-280">Espera un momento o verifica la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-280">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-281">Esto suele ser un error transitorio, pero si el problema persiste, comprueba el número de dispositivos asociados con la cuenta y elimina algunos de ellos si el número es grande.</span><span class="sxs-lookup"><span data-stu-id="c1da4-281">This is normally a transient error but if the issue persists check the number of devices associated with the account and delete some of them if the number is large.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-282">0x86000C16</span><span class="sxs-lookup"><span data-stu-id="c1da4-282">0x86000C16</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span><span class="sxs-lookup"><span data-stu-id="c1da4-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-284">El buzón se migró a un servidor diferente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-284">The mailbox was migrated to a different server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-285">Nunca deberías ver este error.</span><span class="sxs-lookup"><span data-stu-id="c1da4-285">You should never see this error.</span></span> <span data-ttu-id="c1da4-286">Si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-286">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-287">0x85010004</span><span class="sxs-lookup"><span data-stu-id="c1da4-287">0x85010004</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-288">E_HTTP_FORBIDDEN</span><span class="sxs-lookup"><span data-stu-id="c1da4-288">E_HTTP_FORBIDDEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-289">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-289">Can't connect to the server right now.</span></span> <span data-ttu-id="c1da4-290">Espera un momento e inténtalo de nuevo, o verifica la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-290">Wait a while and try again, or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-291">Comprueba el nombre del servidor para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-291">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c1da4-292">Si la cuenta está usando una autenticación basada en certificados, asegúrate de que el certificado sigue siendo válido y actualízalo si no es el caso.</span><span class="sxs-lookup"><span data-stu-id="c1da4-292">If the account is using cert based authentication make sure the certificate is still valid and update it if not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-293">0x85030028</span><span class="sxs-lookup"><span data-stu-id="c1da4-293">0x85030028</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span><span class="sxs-lookup"><span data-stu-id="c1da4-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-295">Falta o no es válida la contraseña de la cuenta o el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-295">The account's password or client certificate are missing or invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-296">Actualiza la contraseña o implementa el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-296">Update the password and/or deploy the client certificate.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-297">0x86000C2A</span><span class="sxs-lookup"><span data-stu-id="c1da4-297">0x86000C2A</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span><span class="sxs-lookup"><span data-stu-id="c1da4-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-299">La cuenta está configurada con directivas que no son compatibles con Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-299">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-300">Deshabilitar la directiva PasswordEnabled para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-300">Disable the PasswordEnabled policy for this account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-301">0x85050002</span><span class="sxs-lookup"><span data-stu-id="c1da4-301">0x85050002</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-302">E_CREDENTIALS_UNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1da4-302">E_CREDENTIALS_UNAVAILABLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-303">Se debe actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-303">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-304">Actualizar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1da4-304">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-305">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="c1da4-305">0x80072EE2</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-306">WININET_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1da4-306">WININET_E_TIMEOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-307">La red no es compatible con el tiempo de espera mínimo de inactividad requerido para recibir la notificación del servidor o el servidor está desconectado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-307">The network doesn't support the minimum idle timeout required to receive server notification, or the server is offline.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-308">Comprueba que el servidor se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c1da4-308">Verify that the server is running.</span></span> <span data-ttu-id="c1da4-309">Comprueba la configuración de NAT.</span><span class="sxs-lookup"><span data-stu-id="c1da4-309">Verify the NAT settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-310">0x85002004</span><span class="sxs-lookup"><span data-stu-id="c1da4-310">0x85002004</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-311">E_FAIL_ABORT</span><span class="sxs-lookup"><span data-stu-id="c1da4-311">E_FAIL_ABORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-312">Este error se usa para interrumpir hanging sync y no se mostrará a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c1da4-312">This error is used to interrupt the hanging sync, and will not be exposed to users.</span></span> <span data-ttu-id="c1da4-313">Se mostrará en los datos de diagnóstico si fuerzas una sincronización interactiva, eliminas la cuenta o actualizas su configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-313">It will be shown in the diagnostic data if you force an interactive sync, delete the account, or update its settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-314">Nada</span><span class="sxs-lookup"><span data-stu-id="c1da4-314">Nothing.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-315">0x85010017</span><span class="sxs-lookup"><span data-stu-id="c1da4-315">0x85010017</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-316">E_HTTP_SERVICE_UNAVAIL</span><span class="sxs-lookup"><span data-stu-id="c1da4-316">E_HTTP_SERVICE_UNAVAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-317">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-317">Can't connect to the server right now.</span></span> <span data-ttu-id="c1da4-318">Espera un momento o verifica la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-318">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-319">Comprueba el nombre del servidor para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-319">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c1da4-320">Espera a que el servidor vuelva a estar conectado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-320">Wait until the server comes back online.</span></span> <span data-ttu-id="c1da4-321">Si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-321">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-322">0x86000C0D</span><span class="sxs-lookup"><span data-stu-id="c1da4-322">0x86000C0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span><span class="sxs-lookup"><span data-stu-id="c1da4-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-324">No se puede conectar al servidor en este momento.</span><span class="sxs-lookup"><span data-stu-id="c1da4-324">Can't connect to the server right now.</span></span> <span data-ttu-id="c1da4-325">Espera un momento o verifica la configuración de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-325">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-326">Comprueba el nombre del servidor para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-326">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c1da4-327">Espera a que el servidor vuelva a estar conectado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-327">Wait until the server comes back online.</span></span> <span data-ttu-id="c1da4-328">Si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-328">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-329">0x85030027</span><span class="sxs-lookup"><span data-stu-id="c1da4-329">0x85030027</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-330">E_ACTIVESYNC_GETCERT</span><span class="sxs-lookup"><span data-stu-id="c1da4-330">E_ACTIVESYNC_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-331">El servidor Exchange requiere un certificado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-331">The Exchange server requires a certificate.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-332">Importar el certificado EAS apropiado en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-332">Import the appropriate EAS certificate on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-333">0x86000C2B</span><span class="sxs-lookup"><span data-stu-id="c1da4-333">0x86000C2B</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span><span class="sxs-lookup"><span data-stu-id="c1da4-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-335">La cuenta está configurada con directivas que no son compatibles con Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="c1da4-335">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-336">Deshabilitar la directiva PasswordEnabled para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-336">Disable the PasswordEnabled policy for this account.</span></span></p>
<p><span data-ttu-id="c1da4-337">Se ha producido un error que se producía un error en la política si la cuenta no recibe notificaciones del servidor en el intervalo de actualización de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="c1da4-337">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-338">0x85010005</span><span class="sxs-lookup"><span data-stu-id="c1da4-338">0x85010005</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-339">E_HTTP_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c1da4-339">E_HTTP_NOT_FOUND</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-340">El nombre del servidor no es válido.</span><span class="sxs-lookup"><span data-stu-id="c1da4-340">The server name is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-341">Comprueba el nombre del servidor para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-341">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c1da4-342">Si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-342">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-343">0x85010014</span><span class="sxs-lookup"><span data-stu-id="c1da4-343">0x85010014</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-344">E_HTTP_SERVER_ERROR</span><span class="sxs-lookup"><span data-stu-id="c1da4-344">E_HTTP_SERVER_ERROR</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-345">No se puede conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="c1da4-345">Can't connect to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-346">Comprueba el nombre del servidor para asegurarse de que es correcto.</span><span class="sxs-lookup"><span data-stu-id="c1da4-346">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c1da4-347">Desencadena una sincronización y, si el problema persiste, vuelve a aprovisionar la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-347">Trigger a sync and, if the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-348">0x80072EE7</span><span class="sxs-lookup"><span data-stu-id="c1da4-348">0x80072EE7</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-349">WININET_E_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="c1da4-349">WININET_E_NAME_NOT_RESOLVED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-350">No se pudo resolver el nombre del servidor o la dirección.</span><span class="sxs-lookup"><span data-stu-id="c1da4-350">The server name or address could not be resolved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-351">Asegúrate de que el nombre del servidor está escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1da4-351">Make sure the server name is entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-352">0x8007052F</span><span class="sxs-lookup"><span data-stu-id="c1da4-352">0x8007052F</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-353">ERROR_ACCOUNT_RESTRICTION</span><span class="sxs-lookup"><span data-stu-id="c1da4-353">ERROR_ACCOUNT_RESTRICTION</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-354">Durante la detección automática del servidor Exchange, se aplica una directiva que impide que el usuario que haya iniciado sesión inicie sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c1da4-354">While auto-discovering the Exchange server, a policy is applied that prevents the logged-in user from logging in to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-355">Se trata de un problema de temporización.</span><span class="sxs-lookup"><span data-stu-id="c1da4-355">This is a timing issue.</span></span> <span data-ttu-id="c1da4-356">Vuelve a comprobar las credenciales de cuenta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-356">Re-verify the account's credentials.</span></span> <span data-ttu-id="c1da4-357">Intenta volver a aprovisionarlas cuando sean correctas.</span><span class="sxs-lookup"><span data-stu-id="c1da4-357">Try to re-provision when they're correct.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-358">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="c1da4-358">0x800C0019</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-359">INET_E_INVALID_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="c1da4-359">INET_E_INVALID_CERTIFICATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-360">El certificado de seguridad necesario para acceder a este recurso no es válido.</span><span class="sxs-lookup"><span data-stu-id="c1da4-360">Security certificate required to access this resource is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-361">Instala el certificado correcto de ActiveSync necesario para la cuenta del dispositivo proporcionada.</span><span class="sxs-lookup"><span data-stu-id="c1da4-361">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c1da4-362">0x80072F0D</span><span class="sxs-lookup"><span data-stu-id="c1da4-362">0x80072F0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-363">WININET_E_INVALID_CA</span><span class="sxs-lookup"><span data-stu-id="c1da4-363">WININET_E_INVALID_CA</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-364">La entidad de certificación no es válida o es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c1da4-364">The certificate authority is invalid or is incorrect.</span></span> <span data-ttu-id="c1da4-365">No se pudo detectar automáticamente el servidor Exchange porque falta un certificado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-365">Could not auto-discover the Exchange server because a certificate is missing.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-366">Instala el certificado correcto de ActiveSync necesario para la cuenta del dispositivo proporcionada.</span><span class="sxs-lookup"><span data-stu-id="c1da4-366">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c1da4-367">0x80004005</span><span class="sxs-lookup"><span data-stu-id="c1da4-367">0x80004005</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-368">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1da4-368">E_FAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-369">No se encontró el dominio proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c1da4-369">The domain provided couldn't be found.</span></span> <span data-ttu-id="c1da4-370">El servidor Exchange no se pudo detectar automáticamente y no se proporcionó en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c1da4-370">The Exchange server could not be auto-discovered and was not provided in the settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c1da4-371">Asegúrate de que el dominio especificado es el FQDN y de que se ha especificado un servidor Exchange en el cuadro de texto del servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1da4-371">Make sure that the domain entered is the FQDN, and that there is an Exchange server entered in the Exchange server text box.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="c1da4-372">Ponerse en contacto con soporte técnico</span><span class="sxs-lookup"><span data-stu-id="c1da4-372">Contact Support</span></span>

<span data-ttu-id="c1da4-373">Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).</span><span class="sxs-lookup"><span data-stu-id="c1da4-373">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


 
## <span data-ttu-id="c1da4-374">Contenidos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1da4-374">Related content</span></span>

- [<span data-ttu-id="c1da4-375">Solucionar problemas de conexión de Miracast a Surface Hub</span><span class="sxs-lookup"><span data-stu-id="c1da4-375">Troubleshooting Miracast connection to the Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 






---
title: Implementación híbrida (Surface Hub)
description: Una implementación híbrida requiere un procesamiento especial para configurar una cuenta del dispositivo para Microsoft Surface Hub.
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: implementación híbrida, cuenta del dispositivo para Surface Hub, Exchange hospedado de forma local, Exchange hospedado en línea
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836202"
---
# Implementación híbrida (Surface Hub)

Una implementación híbrida requiere un procesamiento especial para configurar una cuenta del dispositivo para Microsoft Surface Hub. Si estás usando una implementación híbrida, en la que la organización tenga una mezcla de servicios, algunos hospedados de forma local y algunos hospedados en línea, tu configuración dependerá de dónde esté hospedado cada servicio. Este tema se centra en las implementaciones híbridas para [Exchange hospedado de forma local](#exchange-on-premises), [Exchange hospedado en línea](#exchange-online), Skype Empresarial, Skype Empresarial Online y Skype Empresarial híbrido. Dado que hay muchas variaciones en este tipo de implementación, no es posible proporcionar instrucciones detalladas para todas ellas. El siguiente proceso funcionará en muchas configuraciones. Si el proceso no es adecuado para la instalación, te recomendamos que uses PowerShell (consulta [Apéndice: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) para lograr el mismo resultado final que se describe aquí y para ver otras opciones de implementación. A continuación, debes usar el script de PowerShell proporcionado para comprobar tu configuración de Surface Hub. (Consulta [Script de comprobación de cuenta](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)).

> [!NOTE]
> En un entorno híbrido de Exchange, siga los pasos para la [implementación local de Exchange](#exchange-on-premises). Para mover objetos de Exchange a Office 365, use el cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) .

## Exchange local

Usa este procedimiento si usas Exchange de forma local.

1. Para este procedimiento, usaremos las herramientas de administración de AD para agregar una dirección de correo electrónico para tu cuenta de dominio local. Esta cuenta se sincronizará con Office 365.

- En la herramienta de AD **Usuarios y equipos de Active Directory** , haz clic con el botón derecho en la carpeta o en la unidad organizativa en la que se crearán tus cuentas de Surface Hub, haz clic en **Nuevo**y **Usuario**.
- Escribe el nombre para mostrar del cmdlet anterior en el cuadro **Nombre completo** y, a continuación, el alias en el cuadro **Nombre de inicio de sesión de usuario** . Haz clic en **Siguiente**.<p>

![Cuadro de objeto nuevo para crear un nuevo usuario en Active Directory.](images/hybriddeployment-01a.png)

- Escribe la contraseña para esta cuenta. Debes escribirla de nuevo para su comprobación. Asegúrate de que la casilla **La contraseña nunca expira** sea la única opción seleccionada.

> **Importante** Seleccionar **La contraseña nunca expira** es un requisito de Skype Empresarial en Surface Hub. Las reglas de dominio pueden prohibir las contraseñas que no expiren. Si es así, debes crear una excepción para cada cuenta del dispositivo de Surface Hub.

![Imagen que muestra el cuadro de diálogo de contraseña.](images/hybriddeployment-02a.png)

-   Haz clic en **Finalizar** para crear la cuenta.

![Imagen con el nombre de la cuenta, el nombre de inicio de sesión y las opciones de contraseña para el nuevo usuario.](images/hybriddeployment-03a.png)

2. Habilitar el buzón remoto.

Abre el shell de administración de Exchange local con permisos de administrador y ejecuta este cmdlet.

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> Si no tienes un entorno de Exchange local para ejecutar este cmdlet, puedes realizar los mismos cambios directamente en el objeto de Active Directory para la cuenta.
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. Después de crear la cuenta, ejecuta una sincronización de directorios. Cuando haya finalizado, vaya a la página usuarios del centro de administración de Microsoft 365 y compruebe que la cuenta creada en los pasos anteriores se ha fusionado en línea.

4. Conéctate a Microsoft Exchange Online y establece algunas propiedades para la cuenta en Office 365.

Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange. Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.

Los siguientes pasos se ejecutarán en tu inquilino de Office 365.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. Crea una nueva directiva de Exchange ActiveSync o usa una directiva existente compatible.

Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False. Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).

Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs". Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Una vez que tenga una directiva compatible, tendrá que aplicar la Directiva a la cuenta del dispositivo. 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. Establecer las propiedades de Exchange.

Establecer propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. Conexión a Azure AD.

Primero debes instalar el módulo de Azure AD para PowerShell, versión 2. En un símbolo del sistema de PowerShell con privilegios elevados, ejecute el siguiente comando:

```PowerShell
Install-Module -Name AzureAD
```

Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta. Puedes ejecutar este cmdlet para conectarte.

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Asignar una licencia de Office 365.

La cuenta del dispositivo debe tener una licencia válida de Office 365 (O365); de otro modo, Exchange y Skype Empresarial no funcionarán. Si tienes la licencia, debes asignar una ubicación de uso a tu cuenta del dispositivo; esto determina los SKU de la licencia que están disponibles para tu cuenta.

Puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.

Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

A continuación, habilita la cuenta del dispositivo con [Skype Empresarial Online](#skype-for-business-online), [Skype Empresarial local](#skype-for-business-on-premises) o [Skype Empresarial híbrido](#skype-for-business-hybrid).

### Skype Empresarial Online

Para habilitar Skype Empresarial Online, los usuarios de inquilino deben tener buzones de Exchange (se requiere al menos un buzón de Exchange en el inquilino). En la siguiente tabla se explica qué planes o servicios adicionales necesitas.

| Escenario de sistema de sala de Skype | Si tiene Office 365 Premium, aplicaciones de Microsoft 365 para empresas o plan independiente 2 de Skype empresarial, necesitará lo siguiente: | Si tienes un plan de empresa, necesitas lo siguiente: | Si tiene Skype empresarial Server 2015 (local o híbrido), necesita: |
| --- | --- | --- | --- |
| Unirse a una reunión programada | Plan 1 independiente de Skype Empresarial | E1, 3, 4 o 5 | CAL estándar de Skype Empresarial Server |
| Iniciar una reunión ad-hoc | Plan 2 independiente de Skype Empresarial | E 1, 3, 4 o 5 | CAL estándar o CAL empresarial de Skype Empresarial Server |
| Iniciar una reunión ad hoc y marcar de una reunión a números de teléfono | Plan independiente 2 de Skype empresarial con audioconferencia</br></br>**Nota** La facturación de consumo RTC es opcional | E1 o E3 con audioconferencias o E5| CAL estándar o CAL empresarial de Skype Empresarial Server |
| Proporcionar a la sala un número de teléfono y realizar o recibir llamadas desde la sala, o unirse a una conferencia de acceso telefónico con un número de teléfono | Plan independiente 2 de Skype empresarial con sistema telefónico y un plan de llamadas de voz RTC | E1 o E3 con el sistema telefónico y un plan de llamadas de voz RTC, o E5 | CAL estándar o CAL Plus de Skype Empresarial Server |

En la siguiente tabla se indican los planes de Office 365 y las opciones de Skype Empresarial.

| Plan de O365 | Skype Empresarial | Sistema telefónico | Audioconferencia | Planes de llamadas |
| --- | --- | --- | --- | --- |
| O365 Empresa Essentials | Incluido |  |  |  |
| O365 Empresa Premium | Incluido |  |  |  |
| E1 | Incluido | Complemento | Complemento | Complemento (requiere el complemento del sistema telefónico) |
| E3 | Incluido | Complemento | Complemento | Complemento (requiere el complemento del sistema telefónico) |
| E5 | Incluido | Incluido | Incluido | Complemento  |

1. Para comenzar, crea una sesión remota de PowerShell desde un equipo al entorno de Skype Empresarial Online.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. Asigna la licencia de Skype Empresarial a tu cuenta de Surface Hub.

 Una vez que hayas completado los pasos anteriores para habilitar tu cuenta de Surface Hub en Skype Empresarial Online, debes asignar una licencia al Surface Hub. Con el portal administrativo de O365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.

- Inicia sesión como administrador de inquilinos, abre el portal de administración de O365 y haz clic en la aplicación de administración.

- Haz clic en **Usuarios y grupos locales** y después en **Agregar usuarios, restablecer contraseñas y más**.

- Haz clic en la cuenta de Surface Hub y, a continuación, haz clic en el icono de lápiz para editar la información de la cuenta.

- Haz clic en **Licencias**.

- En **asignar licencias**, seleccione Skype empresarial (plan 1) o Skype empresarial (plan 2), en función de sus requisitos de licencia y telefonía IP empresarial. Tendrá que usar una licencia de plan 2 Si desea usar la telefonía IP empresarial en su Surface Hub.

- Haz clic en **Guardar**.

> [!NOTE]
> También puedes usar el Módulo de Microsoft Azure Active Directory para Windows Powershell para ejecutar los cmdlets necesarios para asignar una de estas licencias, pero esto no se incluye aquí.

Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.

### Skype Empresarial local

Para ejecutar este cmdlet, tendrás que conectarte a uno de los front-end de Skype. Abre Skype PowerShell y ejecútalo:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype Empresarial híbrido

Si tu organización ha configurado la [conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](https://technet.microsoft.com/library/jj205403.aspx), las instrucciones para crear cuentas difiere de una implementación estándar de Surface Hub.

Surface Hub requiere una cuenta de Skype del tipo `meetingroom`, mientras que un usuario normal usaría una cuenta de tipo user en Skype. Si el servidor de Skype se configuró para conectividad híbrida donde puede haber usuarios en el servidor local de Skype, así como usuarios hospedados en Office 365, es posible que se produzcan problemas al intentar crear una cuenta de Surface Hub.

En el entorno híbrido de Skype empresarial Server 2015, todos los usuarios que desee en Skype empresarial online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory. Después, puede mover el usuario a Skype empresarial online. El movimiento de una cuenta de usuario de local a conectada se realiza mediante el cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Para mover un objeto Csmeetingroom, usa el cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Para usar el cmdlet Move-CsMeetingRoom, debe tener instalado [el paquete de actualización acumulativa de mayo de 2017 6.0.9319.281 para Skype empresarial Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) o [la actualización acumulativa de julio 2017 5.0.8308.992 para Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).


## Exchange en línea

Usa este procedimiento si usas Exchange en línea.

1. Crear una cuenta de correo electrónico en Office 365.

Inicia una sesión remota de PowerShell en un equipo y conéctate a Exchange. Asegúrate de que tienes los permisos adecuados establecidos para ejecutar los cmdlets asociados.

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. Configurar un buzón.

Después de establecer una sesión, podrás crear un nuevo buzón y habilitarlo como un RoomMailboxAccount o cambiar la configuración de un buzón existente de la sala. Esto permitirá autenticar la cuenta en el Surface Hub.

Si vas a cambiar un buzón de recursos existente:

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Si vas a crear un nuevo buzón de recursos:

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. Crear la directiva de Exchange ActiveSync.

Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

Los Surface Hubs solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en False. Si esto no se establece correctamente, los servicios de Exchange en Surface Hub (correo, calendario y Unión a reuniones) no estarán habilitados.

Si aún no has creado una directiva compatible, usa el siguiente cmdlet; este crea una directiva denominada "Surface Hubs". Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

Una vez que tenga una directiva compatible, tendrá que aplicar la Directiva a la cuenta del dispositivo. Sin embargo, las directivas solo se pueden aplicar a las cuentas de usuario y no a los buzones de recursos. Tienes que convertir el buzón en un tipo de usuario, aplicar la directiva y, a continuación, volver a convertirlo en un buzón; es posible que tengas que volver a habilitarlo y establecer la contraseña de nuevo también.

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. Establecer las propiedades de Exchange.

Se deben establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. Agregue una dirección de correo electrónico para su cuenta de dominio local.

Para este procedimiento, usaremos las herramientas de administración de AD para agregar una dirección de correo electrónico para tu cuenta de dominio local.

- En la herramienta de AD **Usuarios y equipos de Active Directory** , haz clic con el botón derecho en la carpeta o en la unidad organizativa en la que se crearán tus cuentas de Surface Hub, haz clic en **Nuevo**y **Usuario**.
- Escribe el nombre para mostrar del cmdlet anterior en el cuadro **Nombre completo** y, a continuación, el alias en el cuadro **Nombre de inicio de sesión de usuario** . Haz clic en **Siguiente**.

![Cuadro de objeto nuevo para crear un nuevo usuario en Active Directory.](images/hybriddeployment-01a.png)

- Escribe la contraseña para esta cuenta. Debes escribirla de nuevo para su comprobación. Asegúrate de que la casilla **La contraseña nunca expira** sea la única opción seleccionada.

> [!IMPORTANT]
> Seleccionar la **contraseña nunca vence** es un requisito para Skype empresarial en Surface Hub. Las reglas de dominio pueden prohibir las contraseñas que no expiren. Si es así, debes crear una excepción para cada cuenta del dispositivo de Surface Hub.

![Imagen que muestra el cuadro de diálogo de contraseña.](images/hybriddeployment-02a.png)

- Haz clic en **Finalizar** para crear la cuenta.

![Imagen con el nombre de la cuenta, el nombre de inicio de sesión y las opciones de contraseña para el nuevo usuario.](images/hybriddeployment-03a.png)

6. Ejecuta la sincronización de directorios.

Después de crear la cuenta, ejecuta una sincronización de directorios. Una vez completa, ve a la página de usuarios y comprueba que se combinaron las dos cuentas creadas en los pasos anteriores.

7. Conexión a Azure AD.

Primero debes instalar el módulo de Azure AD para PowerShell, versión 2. En un símbolo del sistema de PowerShell con privilegios elevados, ejecute el siguiente comando:

```PowerShell
Install-Module -Name AzureAD
```

Debes conectarte a Azure AD para aplicar algunas opciones de configuración de la cuenta. Puede ejecutar este cmdlet para conectarse:

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. Asignar una licencia de Office 365.

La cuenta del dispositivo debe tener una licencia válida de Office 365 (O365); de otro modo, Exchange y Skype Empresarial no funcionarán. Si tienes la licencia, debes asignar una ubicación de uso a tu cuenta del dispositivo; esto determina los SKU de la licencia que están disponibles para tu cuenta.

A continuación, puedes usar `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para tu inquilino de O365.

Una vez que enumeres las SKU, deberás asignar el SkuId que quieras a la variable `$License.SkuId`.

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

A continuación, habilita la cuenta del dispositivo con [Skype Empresarial Online](#skype-for-business-online), [Skype Empresarial local](#skype-for-business-on-premises) o [Skype Empresarial híbrido](#skype-for-business-hybrid).

### Skype Empresarial Online

Para habilitar Skype Empresarial, tu entorno deberá cumplir los [requisitos previos de Skype Empresarial Online](#skype-for-business-online).

1. Para comenzar, crea una sesión remota de PowerShell al entorno de Skype Empresarial Online desde un equipo.

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. Asigna la licencia de Skype Empresarial a tu cuenta de Surface Hub

Una vez que hayas completado los pasos anteriores para habilitar tu cuenta de Surface Hub en Skype Empresarial Online, debes asignar una licencia al Surface Hub. Con el portal administrativo de O365, asigne una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) al dispositivo.

- Inicia sesión como administrador de inquilinos, abre el portal de administración de O365 y haz clic en la aplicación de administración.

- Haz clic en **Usuarios y grupos locales** y después en **Agregar usuarios, restablecer contraseñas y más**.

- Haz clic en la cuenta de Surface Hub y, a continuación, haz clic en el icono de lápiz para editar la información de la cuenta.

- Haz clic en **Licencias**.

- En **Asignar licencias**, selecciona Skype Empresarial (Plan 2) o Skype Empresarial (Plan 3), según los requisitos de tu licencia y de Telefonía IP empresarial. Tendrás que usar una licencia de Plan 3 si quieres usar Telefonía IP empresarial en el Surface Hub.

- Haz clic en **Guardar**.

> [!NOTE]
> También puedes usar el Módulo Microsoft Azure Active Directory para Windows PowerShell para ejecutar los cmdlets necesarios para asignar una de estas licencias, pero esto no se incluye aquí.

Para la validación, podrás usar cualquier cliente de Skype Empresarial (PC, Android, etc.) para iniciar sesión en esta cuenta.

### Skype Empresarial local

Para ejecutar este cmdlet, tendrás que conectarte a uno de los front-end de Skype. Abre Skype PowerShell y ejecútalo:

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### Skype Empresarial híbrido

Si tu organización ha configurado la [conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](https://technet.microsoft.com/library/jj205403.aspx), las instrucciones para crear cuentas difiere de una implementación estándar de Surface Hub.

Surface Hub requiere una cuenta de Skype del tipo *meetingroom*, mientras que un usuario normal usaría una cuenta de tipo *user* en Skype. Si el servidor de Skype se configuró para conectividad híbrida donde puede haber usuarios en el servidor local de Skype, así como usuarios hospedados en Office 365, es posible que se produzcan problemas al intentar crear una cuenta de Surface Hub.

En el entorno híbrido de Skype empresarial Server 2015, todos los usuarios que desee en Skype empresarial online deben crearse en la implementación local, de modo que la cuenta de usuario se cree en servicios de dominio de Active Directory. Después, puede mover el usuario a Skype empresarial online. El movimiento de una cuenta de usuario de local a conectada se realiza mediante el cmdlet [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) . Para mover un objeto Csmeetingroom, usa el cmdlet [Move-Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) .

> [!NOTE]
> Para usar el cmdlet Move-CsMeetingRoom, debe tener instalado [el paquete de actualización acumulativa de mayo de 2017 6.0.9319.281 para Skype empresarial Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) o [la actualización acumulativa de julio 2017 5.0.8308.992 para Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).

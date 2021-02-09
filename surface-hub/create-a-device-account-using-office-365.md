---
title: Crear una cuenta de dispositivo mediante la interfaz de usuario (Surface Hub v1)
description: Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la Interfaz de usuario de Office 365 o el Centro de administración de Exchange.
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: crear cuenta del dispositivo, interfaz de usuario de Office 365, Centro de administración de Exchange, Centro de administración de Microsoft 365, Skype Empresarial, directiva de buzón de dispositivo móvil
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: dd19e2fd2417acd29e71c7555e94ee849fbc1bec
ms.sourcegitcommit: 32b6c25698479fa289f642c5b5761ff3be15b686
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "11318014"
---
# Crear una cuenta del dispositivo mediante la interfaz de usuario (Surface Hub v1)

 > [!NOTE]
 >Esta página incluye información sobre el Surface Hub original (v1). Para Surface Hub 2S, consulta [Crear cuenta del dispositivo Surface Hub 2S.](surface-hub-2s-account.md)

Si prefieres usar una interfaz gráfica de usuario, puedes crear una cuenta del dispositivo para tu Microsoft Surface Hub con la [Interfaz de usuario de Office 365](#create-device-acct-o365) o el [Centro de administración de Exchange](#create-device-acct-eac).

## <a href="" id="create-device-acct-o365"></a>Crear una cuenta del dispositivo mediante Office 365


1.  [Cree la cuenta en el Centro de administración de Microsoft 365.](#create-device-acct-o365-admin-ctr)
2.  [Crear una directiva de buzón (ActiveSync) de dispositivos móviles desde el Centro de administración de Microsoft Exchange](#create-device-acct-o365-mbx-policy).
3.  [Usar PowerShell para completar la creación de cuentas de dispositivo](#create-device-acct-o365-complete-acct).
4.  [Usar PowerShell para configurar las propiedades de Exchange de la cuenta](#create-device-acct-o365-configure-exch-prop).
5.  [Habilitar la cuenta con Skype Empresarial](#create-device-acct-o365-skype-for-business).

### <a href="" id="create-device-acct-o365-admin-ctr"></a>Crear la cuenta en el centro de administración

1.  Inicie sesión en Office 365 visitando [https://portal.office.com](https://portal.office.com) .

2.  Proporciona las credenciales de administrador para tu inquilino de Office 365. Esto le llevará al Centro de administración de Microsoft 365.

    > [!div class="mx-imgBorder"]
    > ![Centro de administración de Microsoft 365.](images/setupdeviceaccto365-02.png)

3. En el centro de administración, vaya a **Recursos** en el panel izquierdo y, a continuación, haga clic en Salas **& equipo.**

    > [!div class="mx-imgBorder"]
    > ![Salas & opción de equipamiento en el Centro de administración](images/room-equipment.png)

4. Haga clic en **Agregar** para crear una nueva cuenta de la sala. Introduce un nombre para mostrar y la dirección de correo electrónico y, a continuación, haz clic en **Agregar**.

    > [!div class="mx-imgBorder"]
    > ![Crear nueva ventana de cuenta de la sala](images/room-add.png)

5. Selecciona la cuenta de la sala que acabas de crear en la lista de usuarios activos. En el panel derecho, puedes ver las propiedades de la cuenta y varias acciones opcionales. Haz clic en **Restablecer contraseña** para cambiar la contraseña y anular la selección de **Make this user change their password when they first sign in**, porque no es posible cambiar la contraseña desde el flujo de inicio de sesión de Surface Hub.

6. Haz clic en **Editar** en la sección **Licencia asignada** y, luego, haz clic en la flecha desplegable situada junto a la licencia correspondiente para ampliar los detalles. Selecciona una ubicación del usuario y en la lista de licencias, activa **Skype Empresarial Online (Plan 2)** y, a continuación, haz clic en **Guardar**. La licencia puede variar en función de tu organización (por ejemplo, puedes tener Plan 2 o Plan 3).

### <a href="" id="create-device-acct-o365-mbx-policy"></a>Crear una directiva de buzón (ActiveSync) de dispositivo móvil desde el Centro de administración de Exchange

1.  En el panel izquierdo del centro de administración, haga clic en **ADMINISTRACIÓN**y, a continuación, haga clic **en Exchange.**

    > [!div class="mx-imgBorder"]
    > ![centro de administración, que muestra los usuarios activos de Exchange.](images/setupdeviceaccto365-08.png)

2.  Se abrirá otra ficha en el explorador que te llevará al Centro de administración de Exchange, donde puedes crear y establecer la configuración del buzón de Surface Hub.

    > [!div class="mx-imgBorder"]
    > ![Centro de administración de Exchange.](images/setupdeviceaccto365-09.png)

3.  Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**. Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta. De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.

    > [!div class="mx-imgBorder"]
    > ![Centro de administración de Exchange: creación de una directiva de buzón de dispositivo móvil.](images/setupdeviceaccto365-10.png)

4.  Para crear una nueva directiva de buzón de dispositivo móvil de Surface Hub, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva. En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*). Asegúrate de que la directiva no requiera una contraseña para los dispositivos a los que se ha asignado, de modo que asegúrate de que **Requerir una contraseña** permanezca sin marcar y, luego, haz clic en **Guardar**.

    ![Imagen que muestra la nueva directiva de dispositivo móvil.](images/setupdeviceaccto365-11.png)

5.  Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al **Centro de administración de Exchange** y verás la nueva directiva en la lista.

    > [!div class="mx-imgBorder"]
    > ![Imagen con la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>Usar PowerShell para completar la creación de cuentas de dispositivo

De ahora en adelante, debes finalizar el proceso de creación de cuenta mediante PowerShell para establecer una configuración.

Para poder ejecutar los cmdlets usados por estos scripts de PowerShell, se debe instalar lo siguiente en la consola de administración de PowerShell:

-   [Microsoft Online Services Sign-In asistente para profesionales de TI RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [Módulo de Windows Azure Active Directory para Windows PowerShell](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [Skype Empresarial Online, módulo de Windows PowerShell](https://www.microsoft.com/download/details.aspx?id=39366)

Instale el siguiente módulo en PowerShell.

```powershell
install-module AzureAD
Install-module MsOnline
```

### Conexión a servicios en línea

1.  Ejecutar Windows PowerShell como administrador.

    > [!div class="mx-imgBorder"]
    > ![Imagen que muestra cómo iniciar Windows PowerShell y ejecutarlo como administrador.](images/setupdeviceaccto365-17.png)

2.  Crea un objeto de credenciales y luego crea una nueva sesión que se conecte a Skype Empresarial y proporciona la cuenta de administrador de inquilinos global; luego, haz clic en **Aceptar**.

    ![Imagen de la solicitud de credenciales de Windows PowerShell.](images/setupdeviceaccto365-18.png)

3.  Para conectarte a Microsoft Online Services, ejecuta:

    ```powershell
    Connect-MsolService -Credential $Cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-19.png)

4.  Ahora, para conectarte a Skype Empresarial Online, ejecuta:

    ```powershell
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-20.png)

5.  Por último, para conectarte a Exchange Online Services, ejecuta:

    ```powershell
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-21.png)

6.  Ahora tienes que importar la sesión de Skype Empresarial Online y la sesión de Exchange Online que acabas de crear, que importará los comandos de Exchange y Skype para que puedas usarlos de forma local.

    ```powershell
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    Ten en cuenta que esto podría tardar un tiempo en completarse.

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-22.png)

7.  Una vez que estés conectado a los servicios en línea, debes ejecutar unos cmdlets más para configurar esta cuenta como una cuenta del dispositivo de Surface Hub.

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>Usar PowerShell para configurar las propiedades de Exchange de la cuenta

Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo. Usarás la dirección de correo electrónico de la cuenta del dispositivo para:

-   Cambiar el tipo de buzón de "normal" a "de sala".
-   Establecer la contraseña y habilitar la cuenta de buzón de la sala
-   Cambiar varias propiedades de Exchange
-   Establecer la contraseña de la cuenta de usuario para que nunca expire.

1.  Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Para almacenar el valor, obtenlo a partir del buzón:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprimir el valor:

    ```powershell
    $strEmail
    ```

    Verás la dirección de correo electrónico correcta.

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-23.png)

2. Ejecute el siguiente cmdlet:

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![Imagen que muestra el cmdlet de PowerShell.](images/setupdeviceaccto365-26.png)

5.  Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.

    ```powershell
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>Habilitar la cuenta con Skype Empresarial

Habilitar la cuenta del dispositivo con Skype Empresarial.

Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:

-   Necesitará tener Skype Empresarial Online plan independiente 2 o superior en su plan de O365. El plan debe admitir la funcionalidad de conferencia.
-   Si necesitas usar Telefonía IP empresarial (telefonía RTC) mediante proveedores de servicios de telefonía para Surface Hub, necesitas skype empresarial online plan independiente 3.
-   Los usuarios de inquilino deben tener buzones de Exchange.
-   Tu cuenta de Surface Hub requiere una licencia del Plan independiente 2 de Skype Empresarial Online o de Skype Empresarial Online Plan 3, pero no requiere una licencia de Exchange Online.

1.  Comienza creando una sesión de PowerShell remoto desde un equipo.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:

    ```powershell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

     Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:

    ```powershell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>Crear una cuenta del dispositivo mediante el Centro de administración de Exchange

>[!NOTE]
>Este método solo funcionará si está sincronizando desde un Active Directory local.

Puedes usar el Centro de administración de Exchange para crear una cuenta del dispositivo:

1.  [Crear una cuenta y un buzón mediante el Centro de administración de Exchange](#create-device-acct-exch-admin-ctr).
2.  [Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange](#create-device-acct-exch-mbx-policy).
3.  [Usar PowerShell para configurar la cuenta](#create-device-acct-exch-powershell-conf).
4.  [Habilitar la cuenta con Skype Empresarial](#create-device-acct-exch-skype-for-business).

### <a href="" id="create-device-acct-exch-admin-ctr"></a>Crear una cuenta y un buzón mediante el Centro de administración de Exchange

1.  Iniciar sesión en el Centro de administración de Exchange con las credenciales de administrador de Exchange.
2.  Una vez que estés en el Centro de administración de Exchange (CEF), ve a **Destinatarios** en el panel izquierdo.

    ![Imagen que muestra buzones en el Centro de administración de Exchange.](images/setupdeviceacctexch-01.png)

3.  En los controles situados encima de la lista de buzones, elige **+** para crear uno nuevo y proporcionar un **nombre para mostrar**, un **nombre** y un **nombre de inicio de sesión de usuario** y luego haz clic en **Guardar**.

    ![Imagen que muestra la creación de un nuevo buzón.](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>Crear una directiva de buzón de dispositivo móvil desde el Centro de administración de Exchange

>[!NOTE]
>Si desea crear y asignar una directiva a la cuenta que creó y usa Exchange 2010, busque la información correspondiente sobre la creación de directivas y la asignación de directivas al usar la EMC (consola de administración de Exchange).

 

1.  Ve al Centro de administración de Exchange.

    ![Imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-03.png)

2.  Para crear una directiva de buzón de dispositivo móvil, haz clic en **Móvil** desde el panel izquierdo y luego haz clic en **Directivas de buzón de dispositivo móvil**. Los Surface Hubs requieren una cuenta con una directiva de buzón de dispositivo móvil que no requiera una contraseña, por lo que si ya tienes una directiva que cumpla este requisito, puedes aplicar esa directiva a la cuenta. De lo contrario, sigue los siguientes pasos para crear una nueva solo para usarse en cuentas de dispositivo de Surface Hub.

    ![Imagen que muestra el Centro de administración de Exchange para crear una directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-05.png)

3.  Para crear una nueva directiva de buzón de cuenta del dispositivo móvil, haz clic en el botón **+** en los controles situados encima de la lista de directivas para agregar una nueva directiva. En cuanto al nombre, proporciona un nombre que te ayude a distinguir esta directiva de otras cuentas de dispositivo (por ejemplo, *SurfaceHubDeviceMobilePolicy*). La directiva no debe estar protegida por contraseña, por lo tanto, asegúrate de que **Requerir una contraseña** permanece sin marcar y , a continuación, haz clic en **Guardar**.

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil.](images/setupdeviceacctexch-06.png)

4.  Después de crear la nueva directiva de buzón de dispositivo móvil, vuelve al Centro de administración de Exchange y verás la nueva directiva en la lista.

    ![Imagen que muestra la nueva directiva de buzón de dispositivo móvil en el Centro de administración de Exchange.](images/setupdeviceacctexch-07.png)

5.  Para aplicar la directiva de ActiveSync sin usar PowerShell, puedes hacer lo siguiente:

    -   En el CEF, haz clic en **Destinatarios** &gt; **Buzones** y selecciona un buzón.

        ![imagen que muestra el Centro de administración de Exchange.](images/setupdeviceacctexch-08.png)

    -   En el panel **Detalles** desplázate a **Características de teléfono y voz** y haz clic en **Ver detalles** para mostrar la pantalla **Detalles del dispositivo móvil**.

        ![imagen que muestra los detalles de buzón de correo.](images/setupdeviceacctexch-09.png)

    -   Se muestra la directiva de buzón de dispositivo móvil que está asignada actualmente. Para cambiar la directiva de buzón de dispositivo móvil, haz clic en **Examinar**.

        ![imagen que muestra la directiva de buzón de dispositivo móvil asignada actualmente.](images/setupdeviceacctexch-10.png)

    -   Elige la directiva de buzón de dispositivo móvil adecuada en la lista, haz clic en **Aceptar** y, a continuación, haz clic en **Guardar**.

        ![imagen que muestra una lista de directivas de buzón de dispositivo móvil.](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>Usar PowerShell para configurar la cuenta

Ahora que estás conectado a los servicios en línea, puedes finalizar la configuración de la cuenta del dispositivo. Usarás la dirección de correo electrónico de la cuenta del dispositivo para:

-   Cambiar el tipo de buzón de "normal" a "de sala".
-   Cambiar varias propiedades de Exchange
-   Establecer la contraseña de la cuenta de usuario para que nunca expire.

1.  Deberás especificar la dirección de correo electrónico de la cuenta y crear una variable con ese valor:

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    Para almacenar el valor, obtenlo a partir del buzón:

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    Imprimir el valor ejecutando:

    ```powershell
    $strEmail
    ```

    Verás la dirección de correo electrónico correcta.

2.  Debe convertir la cuenta en un buzón de sala, por lo que ejecute:

    ```powershell
    Set-Mailbox $strEmail -Type Room
    ```

3.  Para autenticar la cuenta del dispositivo en un Surface Hub, debes habilitar la cuenta de buzón de la sala y establecer una contraseña para que la cuenta se pueda usar con el dispositivo para obtener información de la reunión mediante ActiveSync e iniciar sesión en Skype Empresarial.

    ```powershell
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  Se pueden establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades deben establecerse en la sección [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md).

    ```powershell
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  Ahora debemos establecer algunas propiedades en AD. Para ello, necesitas el alias de la cuenta (esta es la parte del UPN que aparece antes de "@").

    ```powershell
    $strAlias = “<your device account’s alias>”
    ```

6.  El usuario debe estar habilitado en AD antes de poder autenticarse con un Surface Hub. Ejecutar:

    ```powershell
    Set-ADUser $strAlias -Enabled $True
    ```

7.  Si decides que la contraseña no expire, puedes establecerlo con los cmdlets de PowerShell también. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más información.

    ```powershell
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>Habilitar la cuenta con Skype Empresarial

Habilitar la cuenta del dispositivo con Skype Empresarial.

Para habilitar Skype Empresarial, tu entorno deberá cumplir los siguientes requisitos previos:

- Necesitará tener Skype Empresarial Online plan independiente 2 o superior en su plan de O365. El plan debe admitir la funcionalidad de conferencia.
- Si necesitas usar Telefonía IP empresarial (telefonía RTC) con proveedores de servicios de telefonía para Surface Hub, necesitas skype empresarial online plan independiente 3.
- Los usuarios de inquilino deben tener buzones de Exchange.
- Tu cuenta de Surface Hub requiere una licencia del Plan independiente 2 de Skype Empresarial Online o skype empresarial Online plan independiente 3, pero no requiere una licencia de Exchange Online.

1. Comienza creando una sesión de PowerShell remoto desde un equipo.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. Recupera el grupo de registradores de cuentas de Surface Hub.

   Si no estás seguro de qué valor usar para el parámetro `RegistrarPool` en el entorno, puedes obtener el valor a partir de un usuario de Skype Empresarial con este cmdlet:

   ```PowerShell
   Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
   ```

3. Para habilitar la cuenta de Surface Hub para Skype Empresarial Server, ejecuta este cmdlet:

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```
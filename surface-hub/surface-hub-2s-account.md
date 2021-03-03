---
title: Crear cuenta del dispositivo para Surface Hub 2S
description: En esta página se describe el procedimiento para crear la cuenta del dispositivo Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385228"
---
# <a name="create-surface-hub-2s-device-account"></a>Crear cuenta del dispositivo para Surface Hub 2S

Crear una cuenta de dispositivo Surface Hub (también conocido como buzón de sala) permite a Surface Hub 2S recibir, aprobar o rechazar las solicitudes de reunión y unirse a reuniones. Configure la cuenta del dispositivo durante la configuración de la experiencia de salida (OOBE). Si es necesario, puede cambiarlo más adelante (sin pasar por la configuración de OOBE).

Puede crear la cuenta desde el Centro de administración de Microsoft 365 en combinación con Windows PowerShell: 

- **Crear cuenta a través del Centro de administración**. Para cumplir los requisitos mínimos, puede configurar todo lo que necesita para la cuenta directamente desde el Centro de administración [de Microsoft 365](https://admin.microsoft.com/AdminPortal). Algunas características como compartir pizarras directamente desde la aplicación de pizarra requieren usar PowerShell para configurar ActiveSync; consulta [Habilitar ActiveSync si el uso de la aplicación de correo electrónico es necesario](#enable-activesync-if-use-of-email-app-is-required) en esta página.

- **Crear cuenta a través de PowerShell**. Puede usar scripts de PowerShell para facilitar la creación de varias cuentas de dispositivo y configurar rápidamente características específicas, como:
    - Procesamiento de calendario para cada cuenta de dispositivo Surface Hub.
    - Respuestas automáticas personalizadas a solicitudes de programación.
    - Si la directiva de buzón de ActiveSync predeterminada ya ha sido modificada por otra persona o por otro proceso, es probable que tenga que crear y asignar una nueva directiva de buzón de ActiveSync.

> [!TIP]
> Para comprobar la configuración de la cuenta, ejecute el [script de comprobación de la cuenta que se muestra](#account-verification-script) a continuación.

> [!NOTE]  
> La cuenta del dispositivo Surface Hub no admite proveedores de identidades federadas (FIP) de terceros y debe ser una cuenta estándar de Active Directory o Azure Active Directory.

## <a name="create-account-via-admin-center"></a>Crear cuenta a través del Centro de administración

1. En el Centro de administración de Microsoft 365, vaya a **Recursos** y elija **Salas & Equipamiento** y, a continuación, seleccione + **Agregar recurso**.

2. Proporcione un nombre y una dirección de correo electrónico para la cuenta del dispositivo. Deje la configuración restante sin cambios en el estado predeterminado.

   ![Proporcionar un nombre y una dirección de correo electrónico](images/sh2-account2.png)

   ![Dejar la configuración restante sin cambios en el estado predeterminado](images/sh2-account3.png)

3. Establece la contraseña de la cuenta del dispositivo. Para establecer la contraseña, elija **Usuarios y,** a continuación, **seleccione Usuarios activos**. Ahora busque el usuario recién creado para establecer la contraseña. Asegúrese de que **no selecciona la** opción Hacer que este usuario cambie su contraseña cuando inicie sesión por primera **vez.**

   ![Establecer la contraseña de la cuenta del dispositivo](images/sh2-account4.png)

4. Asigne la sala con una licencia de Office 365. Se recomienda asignar la licencia de **** sala de reuniones de Office 365, que habilita automáticamente la cuenta para Microsoft Teams y Skype Empresarial.

   ![Asignar licencia de Office 365](images/sh2-account5.png)


> [!NOTE]  
> Si usa Skype Empresarial, tendrá que finalizar la instalación a través de PowerShell -- Skype Empresarial Calendar: Establecer el [autoprocesamiento](#set-calendar-auto-processing-skype-for-business-only) de calendario para esta cuenta. 

## <a name="create-account-via-powershell"></a>Crear cuenta a través de PowerShell

 El uso de PowerShell para automatizar rápidamente las tareas en Surface Hub no requiere necesariamente experiencia de PowerShell. Asegúrese de haber completado los requisitos previos de configuración antes de usar los scripts adecuados en esta página.

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>Requisitos previos para usar PowerShell para administrar Surface Hub 

1. Inicie PowerShell con privilegios de cuenta elevados **(Ejecutar**como administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell. Para obtener más información, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?). 
2. [Instalar el módulo de PowerShell de Azure](https://docs.microsoft.com/powershell/azure/install-az-ps).


### <a name="connect-to-exchange-online-powershell"></a>Conectarse a Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>Crear buzón

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>Establecer el procesamiento automático del calendario (solo Skype Empresarial)

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>Habilitar ActiveSync si se requiere el uso de la aplicación de correo electrónico

 La directiva de ActiveSync predeterminada funcionará si no se modifica. De lo contrario, cree una nueva directiva y asígnela.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>Conexión a Azure AD

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>Asignar una licencia

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>Buscar licencias disponibles

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>Script de verificación de cuenta

Después de crear la cuenta del dispositivo, puedes ejecutar el siguiente script de verificación. Este script valida una cuenta de dispositivo creada anteriormente y genera un informe de resumen. Por ejemplo:

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

No se mostrarán los detalles de la configuración específica.

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <a name="learn-more"></a>Más información

- [Crear cuentas locales de Surface Hub 2S con PowerShell](surface-hub-2s-onprem-powershell.md)
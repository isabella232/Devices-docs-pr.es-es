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
# <a name="create-surface-hub-2s-device-account"></a><span data-ttu-id="690d7-104">Crear cuenta del dispositivo para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="690d7-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="690d7-105">Crear una cuenta de dispositivo Surface Hub (también conocido como buzón de sala) permite a Surface Hub 2S recibir, aprobar o rechazar las solicitudes de reunión y unirse a reuniones.</span><span class="sxs-lookup"><span data-stu-id="690d7-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="690d7-106">Configure la cuenta del dispositivo durante la configuración de la experiencia de salida (OOBE).</span><span class="sxs-lookup"><span data-stu-id="690d7-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="690d7-107">Si es necesario, puede cambiarlo más adelante (sin pasar por la configuración de OOBE).</span><span class="sxs-lookup"><span data-stu-id="690d7-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="690d7-108">Puede crear la cuenta desde el Centro de administración de Microsoft 365 en combinación con Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="690d7-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="690d7-109">**Crear cuenta a través del Centro de administración**.</span><span class="sxs-lookup"><span data-stu-id="690d7-109">**Create account via Admin center**.</span></span> <span data-ttu-id="690d7-110">Para cumplir los requisitos mínimos, puede configurar todo lo que necesita para la cuenta directamente desde el Centro de administración [de Microsoft 365](https://admin.microsoft.com/AdminPortal).</span><span class="sxs-lookup"><span data-stu-id="690d7-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="690d7-111">Algunas características como compartir pizarras directamente desde la aplicación de pizarra requieren usar PowerShell para configurar ActiveSync; consulta [Habilitar ActiveSync si el uso de la aplicación de correo electrónico es necesario](#enable-activesync-if-use-of-email-app-is-required) en esta página.</span><span class="sxs-lookup"><span data-stu-id="690d7-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="690d7-112">**Crear cuenta a través de PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="690d7-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="690d7-113">Puede usar scripts de PowerShell para facilitar la creación de varias cuentas de dispositivo y configurar rápidamente características específicas, como:</span><span class="sxs-lookup"><span data-stu-id="690d7-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="690d7-114">Procesamiento de calendario para cada cuenta de dispositivo Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="690d7-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="690d7-115">Respuestas automáticas personalizadas a solicitudes de programación.</span><span class="sxs-lookup"><span data-stu-id="690d7-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="690d7-116">Si la directiva de buzón de ActiveSync predeterminada ya ha sido modificada por otra persona o por otro proceso, es probable que tenga que crear y asignar una nueva directiva de buzón de ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="690d7-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="690d7-117">Para comprobar la configuración de la cuenta, ejecute el [script de comprobación de la cuenta que se muestra](#account-verification-script) a continuación.</span><span class="sxs-lookup"><span data-stu-id="690d7-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="690d7-118">La cuenta del dispositivo Surface Hub no admite proveedores de identidades federadas (FIP) de terceros y debe ser una cuenta estándar de Active Directory o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="690d7-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <a name="create-account-via-admin-center"></a><span data-ttu-id="690d7-119">Crear cuenta a través del Centro de administración</span><span class="sxs-lookup"><span data-stu-id="690d7-119">Create account via admin center</span></span>

1. <span data-ttu-id="690d7-120">En el Centro de administración de Microsoft 365, vaya a **Recursos** y elija **Salas & Equipamiento** y, a continuación, seleccione + **Agregar recurso**.</span><span class="sxs-lookup"><span data-stu-id="690d7-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="690d7-121">Proporcione un nombre y una dirección de correo electrónico para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="690d7-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="690d7-122">Deje la configuración restante sin cambios en el estado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="690d7-122">Leave remaining settings unchanged in the default state.</span></span>

   ![Proporcionar un nombre y una dirección de correo electrónico](images/sh2-account2.png)

   ![Dejar la configuración restante sin cambios en el estado predeterminado](images/sh2-account3.png)

3. <span data-ttu-id="690d7-125">Establece la contraseña de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="690d7-125">Set the password for the device account.</span></span> <span data-ttu-id="690d7-126">Para establecer la contraseña, elija **Usuarios y,** a continuación, **seleccione Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="690d7-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="690d7-127">Ahora busque el usuario recién creado para establecer la contraseña.</span><span class="sxs-lookup"><span data-stu-id="690d7-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="690d7-128">Asegúrese de que **no selecciona la** opción Hacer que este usuario cambie su contraseña cuando inicie sesión por primera **vez.**</span><span class="sxs-lookup"><span data-stu-id="690d7-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![Establecer la contraseña de la cuenta del dispositivo](images/sh2-account4.png)

4. <span data-ttu-id="690d7-130">Asigne la sala con una licencia de Office 365.</span><span class="sxs-lookup"><span data-stu-id="690d7-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="690d7-131">Se recomienda asignar la licencia de \*\*\*\* sala de reuniones de Office 365, que habilita automáticamente la cuenta para Microsoft Teams y Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="690d7-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![Asignar licencia de Office 365](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="690d7-133">Si usa Skype Empresarial, tendrá que finalizar la instalación a través de PowerShell -- Skype Empresarial Calendar: Establecer el [autoprocesamiento](#set-calendar-auto-processing-skype-for-business-only) de calendario para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="690d7-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <a name="create-account-via-powershell"></a><span data-ttu-id="690d7-134">Crear cuenta a través de PowerShell</span><span class="sxs-lookup"><span data-stu-id="690d7-134">Create account via PowerShell</span></span>

 <span data-ttu-id="690d7-135">El uso de PowerShell para automatizar rápidamente las tareas en Surface Hub no requiere necesariamente experiencia de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="690d7-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="690d7-136">Asegúrese de haber completado los requisitos previos de configuración antes de usar los scripts adecuados en esta página.</span><span class="sxs-lookup"><span data-stu-id="690d7-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a><span data-ttu-id="690d7-137">Requisitos previos para usar PowerShell para administrar Surface Hub</span><span class="sxs-lookup"><span data-stu-id="690d7-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="690d7-138">Inicie PowerShell con privilegios de cuenta elevados **(Ejecutar**como administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="690d7-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="690d7-139">Para obtener más información, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="690d7-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="690d7-140">[Instalar el módulo de PowerShell de Azure](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="690d7-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <a name="connect-to-exchange-online-powershell"></a><span data-ttu-id="690d7-141">Conectarse a Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="690d7-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a><span data-ttu-id="690d7-142">Crear buzón</span><span class="sxs-lookup"><span data-stu-id="690d7-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a><span data-ttu-id="690d7-143">Establecer el procesamiento automático del calendario (solo Skype Empresarial)</span><span class="sxs-lookup"><span data-stu-id="690d7-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a><span data-ttu-id="690d7-144">Habilitar ActiveSync si se requiere el uso de la aplicación de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="690d7-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="690d7-145">La directiva de ActiveSync predeterminada funcionará si no se modifica.</span><span class="sxs-lookup"><span data-stu-id="690d7-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="690d7-146">De lo contrario, cree una nueva directiva y asígnela.</span><span class="sxs-lookup"><span data-stu-id="690d7-146">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a><span data-ttu-id="690d7-147">Conexión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="690d7-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a><span data-ttu-id="690d7-148">Asignar una licencia</span><span class="sxs-lookup"><span data-stu-id="690d7-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a><span data-ttu-id="690d7-149">Buscar licencias disponibles</span><span class="sxs-lookup"><span data-stu-id="690d7-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a><span data-ttu-id="690d7-150">Script de verificación de cuenta</span><span class="sxs-lookup"><span data-stu-id="690d7-150">Account verification script</span></span>

<span data-ttu-id="690d7-151">Después de crear la cuenta del dispositivo, puedes ejecutar el siguiente script de verificación.</span><span class="sxs-lookup"><span data-stu-id="690d7-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="690d7-152">Este script valida una cuenta de dispositivo creada anteriormente y genera un informe de resumen.</span><span class="sxs-lookup"><span data-stu-id="690d7-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="690d7-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="690d7-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="690d7-154">No se mostrarán los detalles de la configuración específica.</span><span class="sxs-lookup"><span data-stu-id="690d7-154">Details of specific settings will not be shown.</span></span>

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

## <a name="learn-more"></a><span data-ttu-id="690d7-155">Más información</span><span class="sxs-lookup"><span data-stu-id="690d7-155">Learn more</span></span>

- [<span data-ttu-id="690d7-156">Crear cuentas locales de Surface Hub 2S con PowerShell</span><span class="sxs-lookup"><span data-stu-id="690d7-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)
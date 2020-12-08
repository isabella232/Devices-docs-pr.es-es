---
title: Crear cuenta del dispositivo para Surface Hub 2S
description: Esta página describe el procedimiento para crear la cuenta del dispositivo Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196733"
---
# Crear cuenta del dispositivo para Surface Hub 2S

La creación de una cuenta de dispositivo de Surface Hub (también conocida como buzón de sala) permite a Surface Hub 2S recibir, aprobar o rechazar convocatorias de reunión y unirse a reuniones con Microsoft Teams o Skype empresarial. Configurar la cuenta del dispositivo al configurar la configuración rápida (OOBE). Si es necesario, puede cambiarlo más tarde (sin pasar por la configuración de OOBE).

A diferencia de los buzones de sala estándar que permanecen deshabilitados de forma predeterminada, debe habilitar la cuenta de dispositivo Surface Hub 2S para que inicie sesión en Microsoft Teams y Skype empresarial. Surface Hub 2S depende de Exchange ActiveSync, que requiere una directiva de buzón de ActiveSync en la cuenta del dispositivo. Aplicar la Directiva de buzón de correo predeterminada de ActiveSync que se incluye con Exchange Online.

Cree la cuenta con el centro de administración de Microsoft 365 o con PowerShell. Puede usar Exchange Online PowerShell para configurar características específicas, entre las que se incluyen:

- Procesamiento de calendario para todas las cuentas de dispositivos de Surface Hub.
- Respuestas automáticas personalizadas a solicitudes de programación.
- Si la Directiva de buzón predeterminada de ActiveSync ya ha sido modificada por otra persona u otro proceso, probablemente tendrá que crear y asignar una nueva Directiva de buzón de ActiveSync.

> [!NOTE]  
> La cuenta del dispositivo Surface Hub no admite proveedores de identidades federados de terceros (FIPs) y debe ser una cuenta estándar de Active Directory o de Azure Active Directory.

## Crear una cuenta con el centro de administración de Microsoft 365

1. En el centro de administración de Microsoft 365, vaya a **recursos** y elija **salas & equipo** y, a continuación, seleccione **+ sala**.

2. Proporcione un nombre y una dirección de correo electrónico para la cuenta del dispositivo. No cambie la configuración restante en el estado predeterminado.

   ![Proporcionar un nombre y una dirección de correo electrónico](images/sh2-account2.png)

   ![Dejar los valores restantes sin cambios en el estado predeterminado](images/sh2-account3.png)

3. Establezca la contraseña de la cuenta del dispositivo. Para establecer la contraseña, elija **usuarios** y, a continuación, seleccione **usuarios activos**. Ahora busque el usuario recién creado para establecer la contraseña. Asegúrese de **no** seleccionar la opción hacer que **este usuario cambie la contraseña la primera vez que inicie sesión.**

   ![Establecer la contraseña de la cuenta del dispositivo](images/sh2-account4.png)

4. Asigne el salón con una licencia de Office 365. Se recomienda asignar la licencia de la **sala de reuniones** de Office 365, una nueva opción que habilita automáticamente la cuenta de Skype empresarial online y Microsoft Teams.

   ![Asignar licencia de Office 365](images/sh2-account5.png)

### Finalizar la configuración a través de PowerShell

- **Microsoft Teams y calendario de Skype empresarial:** Establecer el [**procesamiento automático de calendario**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta cuenta.

## Crear una cuenta con PowerShell

En lugar de usar el portal del centro de administración de Microsoft, puede crear la cuenta con PowerShell.

### Conectarse a Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### Crear buzón

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### Establecer el procesamiento automático de los calendarios

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### Habilitar ActiveSync si se requiere el uso de la aplicación de correo electrónico

 La directiva predeterminada de ActiveSync funcionará si unchnaged. En caso contrario, crea una nueva Directiva y la asigna.

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### Conexión a Azure AD

```powershell
Connect-AzureAD
```

### Asignar una licencia

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### Comprobar si hay licencias disponibles

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```
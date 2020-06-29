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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836378"
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

- **Skype para empresas:** Solo para Skype empresarial (local o en línea), puede habilitar el objeto de Skype empresarial ejecutando **enable-CsMeetingRoom** para habilitar características como el aviso de la sala de reuniones para la suspensión de audio y recepción.

- **Microsoft Teams y calendario de Skype empresarial:** Establecer el [**procesamiento automático de calendario**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) para esta cuenta.

## Crear una cuenta con PowerShell

En lugar de usar el portal del centro de administración de Microsoft, puede crear la cuenta con PowerShell.

### Conectarse a Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### Crear un nuevo buzón de sala

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### Establecer el procesamiento automático de los calendarios

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### Asignar una licencia

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## Conectarse a Skype empresarial online con PowerShell

### Requisitos previos de instalación

- [Paquete redistribuible de Visual C++ 2017](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [Módulo de PowerShell de Skype empresarial online](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```

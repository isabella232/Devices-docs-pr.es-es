---
title: Características avanzadas de seguridad de UEFI para Surface Pro 3 (Surface)
description: En este artículo se describe cómo instalar y configurar la actualización de UEFI v3.11.760.0 para habilitar las opciones de seguridad adicionales para dispositivos Surface Pro 3.
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: seguridad, características, configurar, hardware, dispositivo, personalizado, script, actualizar
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163179"
---
# Características avanzadas de seguridad de UEFI para Surface Pro 3


En este artículo se describe cómo instalar y configurar la actualización de UEFI v3.11.760.0 para habilitar las opciones de seguridad adicionales para dispositivos Surface Pro 3.

Para abordar un control más detallado de la seguridad de dispositivos Surface, la actualización de UEFI v3.11.760.0 proporciona otras opciones de seguridad que te permiten deshabilitar dispositivos de hardware específicos o impedir el inicio desde esos dispositivos. Después de instalar la actualización de UEFI en un dispositivo, puedes configurarlo automáticamente o manualmente mediante la ejecución de un script.

##  <a name="manually-install-the-uefi-update"></a>Instalar manualmente la actualización de UEFI


Antes de configurar las características de seguridad avanzadas del dispositivo Surface, primero debes instalar la actualización de UEFI v3.11.760.0. Esta actualización se instalará automáticamente si recibes actualizaciones de Windows Update. Para obtener más información sobre cómo configurar Windows para actualizarse automáticamente mediante Windows Update, consulta [Cómo configurar y utilizar actualizaciones automáticas en Windows](https://support.microsoft.com/kb/306525).

Para actualizar la UEFI en Surface Pro 3, puedes descargar e instalar las actualizaciones de la UEFI de Surface como parte del firmware de Surface Pro 3 y el paquete de controladores. Este firmware y estos paquetes de controladores están disponibles en la [Página de Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826) en el Centro de descarga de Microsoft. Puedes encontrar más información sobre el firmware y los paquetes de controladores en [Descargar el firmware y los controladores más recientes para los dispositivos de Surface](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices). El firmware y los paquetes de controladores están disponibles en formatos Windows Installer (.msi) y de archivo (.zip) independientes. Puedes encontrar más información sobre estos dos formatos y cómo se pueden usar para actualizar los controladores en [Administrar actualizaciones de controladores y firmware de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).

##  <a name="manually-configure-additional-security-settings"></a>Configurar manualmente las opciones de seguridad adicionales


>[!NOTE]
>Para especificar la configuración de firmware en un dispositivo Surface, comienza con el dispositivo apagado, mantén presionado el botón **Subir el volumen**, presiona el botón **inicio/apagado** y suéltalo, y, luego, suelta el botón **Subir el volumen** después de que el dispositivo haya comenzado a arrancar.

Después de instalar la actualización de UEFI v3.11.760.0 en un dispositivo Surface, tendrás disponible un menú de UEFI adicional denominado **Seguridad avanzada del dispositivo**. Si haces clic en este menú, se muestran las siguientes opciones:

| Opción         | Descripción                                                                                                                                                                          | Opciones de configuración disponibles (las predeterminadas se indican con negrita) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| Arranque de red   | Habilita o deshabilita la capacidad del dispositivo Surface de arrancar desde la red (también conocida como el arranque PXE).                                                                            | **Habilitado**, No de arranque                   |
| USB lateral       | Habilita o deshabilita el puerto USB en el lateral del dispositivo Surface. Además, el puerto USB se puede habilitar, pero no permite arrancar.                                                | **Habilitado**, No de arranque, Deshabilitado         |
| Puerto de acoplamiento   | Habilita o deshabilita los puertos en la base de acoplamiento de Surface. Además, el puerto de acoplamiento se puede habilitar, pero bloquea el arranque desde cualquier puerto USB o Ethernet en la estación de acoplamiento. | **Habilitado**, No de arranque, Deshabilitado         |
| Cámara frontal   | Habilita o deshabilita la cámara en la parte frontal del dispositivo Surface.                                                                                                                   | **Habilitado**, Deshabilitado                       |
| Cámara trasera    | Habilita o deshabilita la cámara en la parte trasera del dispositivo Surface.                                                                                                                    | **Habilitado**, Deshabilitado                       |
| Audio integrado | Habilita o deshabilita el audio en el dispositivo Surface.                                                                                                                                     | **Habilitado**, Deshabilitado                       |
| microSD        | Habilita o deshabilita la ranura microSD en el dispositivo Surface.                                                                                                                          | **Habilitado**, Deshabilitado                       |
| Wi-Fi           | Habilita o deshabilita el transceptor Wi-Fi integrado en el dispositivo Surface. Esto deshabilita también Bluetooth.                                                                              | **Habilitado**, Deshabilitado                       |
| Bluetooth      | Habilita o deshabilita el transceptor Bluetooth integrado en el dispositivo Surface.                                                                                                        | **Habilitado**, Deshabilitado                       |

 

##  <a name="automate-additional-security-settings"></a>Automatizar la configuración de seguridad adicional


Como profesional de TI con privilegios administrativos, puedes automatizar la configuración de las opciones de UEFI aprovechando [Surface Pro 3 Firmware Tools (KB 476)](https://go.microsoft.com/fwlink/p/?LinkID=618038) disponible desde el Centro de descarga de Microsoft. Estas herramientas instalan a un ensamblado .NET que se puede llamar desde cualquier aplicación o script personalizados.

**Requisitos previos**

-   Los scripts de muestra a continuación aprovechan la extensión mencionada anteriormente y, por tanto, suponen que la herramienta se ha instalado en el dispositivo que se administra.
-   Los scripts se deben ejecutar con privilegios administrativos.
-   Se debe llamar al comando de Windows PowerShell [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) antes de ejecutar scripts de muestra si no están firmados digitalmente.

**Scripts de muestra**

> [!NOTE]
> La contraseña de UEFI usada en los scripts de muestra a continuación se presenta en texto sin cifrar. Te recomendamos encarecidamente guardar los scripts en un lugar protegido y los ejecutes en un entorno controlado.


Mostrar todas las opciones configurables:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

Establecer o cambiar la contraseña de UEFI:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

Comprobar el estado de los cambios propuestos:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

Revertir UEFI con valores predeterminados:

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

Interpretación del código de estado

-   00: La actualización propuesta se instaló correctamente
-   02: Uno de los valores propuestos tenía un valor no válido
-   03: Había un conjunto de valores propuesto que no se había reconocido
-   0F: La contraseña de desbloqueo no coincidió con la contraseña establecida actualmente

 

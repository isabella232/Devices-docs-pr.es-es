---
title: Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM (Surface)
description: Aprenda a administrar el modo de administración de Microsoft Surface Enterprise (SEMM) con el administrador de configuración de extremo.
keywords: inscribir, actualizar, scripts, configuración
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/13/2020
ms.openlocfilehash: bfd10df3bb7a7dd031c1719d4191ffc46418c4e3
ms.sourcegitcommit: 30c1eb469610dfd2ad9169c154ca07e565240fdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117856"
---
# Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM

La característica del modo de administración de Microsoft Surface (SEMM) de Surface UEFI permite a los administradores administrar y ayudar a proteger la configuración de la configuración de Surface UEFI. Para la mayoría de las organizaciones, este proceso se consigue creando paquetes de Windows Installer (. msi) con la herramienta de configurador Microsoft Surface UEFI. A continuación, estos paquetes se ejecutan o se implementan en los dispositivos Surface del cliente para inscribir los dispositivos en SEMM y para actualizar la configuración de la configuración de Surface UEFI.

Para las organizaciones con Microsoft Endpoint Configuration Manager, existe una alternativa al uso del proceso configurador Microsoft Surface UEFI. msi para implementar y administrar SEMM. Microsoft Surface UEFI Manager es un instalador ligero que hace que los ensamblados necesarios para la administración de SEMM estén disponibles en un dispositivo. Al instalar estos ensamblados con Microsoft Surface UEFI Manager en un cliente administrado, SEMM puede ser administrado por Configuration Manager con scripts de PowerShell, implementado como aplicaciones. Con este proceso, la administración de SEMM se realiza en Configuration Manager, que elimina la necesidad de la herramienta externa del configurador Microsoft Surface UEFI.

> [!Note]
> Aunque el proceso descrito en este artículo puede funcionar con versiones anteriores de Endpoint Configuration Manager o con otras soluciones de administración de terceros, la administración de SEMM con Microsoft Surface UEFI Manager y PowerShell solo se admite en la rama actual del administrador de configuración de extremo.

#### Requisitos previos

Antes de comenzar el proceso descrito en este artículo, familiarícese con las siguientes tecnologías y herramientas:

* [Superficie UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [Modo de administración de empresa de Surface (SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [Scripting de PowerShell](https://technet.microsoft.com/scriptcenter/dd742419)
* [Implementación de aplicaciones de System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* Administración de certificados

> [!Note]
> También necesitará acceso al certificado que pretende usar para proteger el SEMM. Para obtener más información sobre los requisitos para este certificado, consulte [requisitos de certificados del modo de administración de Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).
> 
> Es muy importante que este certificado se mantenga en un lugar seguro y se haga una copia de seguridad de él correctamente. Si este certificado se pierde o no se puede usar, no es posible restablecer Surface UEFI, cambiar la configuración de la superficie administrada UEFI o quitar SEMM de un dispositivo Surface inscrito.

#### Descargar Microsoft Surface UEFI Manager

La administración de SEMM con Configuration Manager requiere la instalación de Microsoft Surface UEFI Manager en cada dispositivo Surface del cliente. Puede descargar Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) desde la página [Surface Tools para ti](https://www.microsoft.com/download/details.aspx?id=46703) en el centro de descarga de Microsoft.

#### Descargar scripts SEMM para Configuration Manager

Después de instalar Microsoft Surface UEFI Manager en el dispositivo Surface del cliente, SEMM se implementa y administra con scripts de PowerShell. Puede descargar muestras de las [secuencias de comandos de administración de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) desde el centro de descarga.

## Implementar Microsoft Surface UEFI Manager

La implementación de Microsoft Surface UEFI Manager es una implementación de aplicaciones típica. El archivo instalador de Microsoft Surface UEFI Manager es un archivo de Windows Installer estándar que puede instalar con la [opción silencio estándar](https://msdn.microsoft.com/library/windows/desktop/aa367988).

El comando para instalar Microsoft Surface UEFI Manager es el siguiente.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

El comando para desinstalar Microsoft Surface UEFI Manager es el siguiente.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Para crear una nueva aplicación e implementarla en una colección que contiene los dispositivos de Surface, siga estos pasos:

1. Abra la consola de Configuration Manager desde la pantalla **Inicio** o desde el menú **Inicio** .
2. Seleccione **biblioteca de software** en la esquina inferior izquierda de la ventana.
3. Expanda el nodo **Administración de aplicaciones** de la biblioteca de software y, a continuación, seleccione **aplicaciones**.
4. Seleccione el botón **crear aplicación** en la pestaña **Inicio** , en la parte superior de la ventana. Esto inicia el Asistente para crear aplicaciones.
5. El Asistente para crear aplicaciones presenta una serie de pasos:

   * **General** : la opción **detectar automáticamente la información sobre esta aplicación desde los archivos de instalación** está seleccionada de forma predeterminada. En el campo **tipo** , **Windows Installer (archivo. msi)** también está seleccionado de forma predeterminada. Seleccione **examinar** para ir a y seleccione **SurfaceUEFIManagerSetup.msi**y, a continuación, seleccione **siguiente**.
   
      > [!Note]
      > La ubicación de SurfaceUEFIManagerSetup.msi debe estar en un recurso compartido de red y encontrarse en una carpeta que no contenga otros archivos. No se puede usar una ubicación de archivo local.

   * **Importar información** : el Asistente para crear aplicaciones analizará el archivo. msi y leerá el nombre de la **aplicación** y el **código de producto**. SurfaceUEFIManagerSetup.msi debe aparecer como el único archivo que está debajo de los **archivos de contenido**de línea, como se muestra en la ilustración 1. Seleccione **siguiente** para continuar.

      ![Se analiza automáticamente la información de la configuración de Surface UEFI Manager.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figura 1. La información de la configuración de Microsoft Surface UEFI Manager se analiza de forma automática*

   * **Información general** : puede modificar el nombre de la aplicación e información sobre el editor y la versión, o agregar comentarios en esta página. El comando de instalación de Microsoft Surface UEFI Manager se muestra en el campo del programa de instalación. El comportamiento de instalación predeterminada de instalar para el sistema permite que Microsoft Surface UEFI Manager Instale los ensamblados necesarios para SEMM incluso si un usuario no ha iniciado sesión en el dispositivo Surface. Seleccione **siguiente** para continuar.
   * **Resumen** : la información que se analizó en el paso **Importar información** y las selecciones del paso **información general** se muestra en esta página. Seleccione **siguiente** para confirmar las selecciones y crear la aplicación.
   * **Progreso** : muestra una barra de progreso y un estado a medida que se importa la aplicación y se agrega a la biblioteca de software.
   * **Finalización** : se muestra una confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación. Seleccione **cerrar** para finalizar el Asistente para crear aplicaciones.

Después de crear la aplicación en Configuration Manager, puede distribuirla a los puntos de distribución e implementarla en las colecciones, incluidos los dispositivos Surface. Esta aplicación no instalará ni habilitará SEMM en el dispositivo Surface. Solo proporciona los ensamblados necesarios para que SEMM se habilite con el script de PowerShell.

Si no desea instalar los ensamblados de Microsoft Surface UEFI Manager en dispositivos que no se administrarán con SEMM, puede configurar Microsoft Surface UEFI Manager como una dependencia de los scripts de SEMM Configuration Manager. Este escenario se trata en la sección [implementar SEMM de scripts de Configuration Manager](#deploy-semm-configuration-manager-scripts) más adelante en este artículo.

## Crear o modificar los scripts de SEMM Configuration Manager

Una vez instalados los ensamblados necesarios en los dispositivos, el proceso de inscribir los dispositivos en SEMM y configurar Surface UEFI se realiza con scripts de PowerShell y se implementa como una aplicación de scripts con Configuration Manager. Estas secuencias de comandos se pueden modificar para satisfacer las necesidades de la organización y el entorno. Por ejemplo, puede crear varias configuraciones para dispositivos de Surface administrados en diferentes departamentos o roles. Puede descargar ejemplos de las secuencias de comandos para SEMM y Configuration Manager desde el vínculo de la sección [requisitos previos](#prerequisites) al principio de este artículo.

Hay dos scripts principales que necesitará para realizar una implementación de SEMM con Configuration Manager:

* **ConfigureSEMM.ps1** : Use este script para crear paquetes de configuración para los dispositivos Surface con la configuración de Surface UEFI deseada para aplicar la configuración especificada a un dispositivo Surface, para inscribir el dispositivo en SEMM y para establecer una clave del registro usada para identificar la inscripción del dispositivo en SEMM.
* **ResetSEMM.ps1** : Use este script para restablecer SEMM en un dispositivo Surface, que anula su inscripción de semm y quita el control de la configuración de Surface UEFI.

Los scripts de ejemplo incluyen ejemplos de cómo establecer la configuración de Surface UEFI y cómo controlar los permisos de esa configuración. Esta configuración se puede modificar para la superficie segura UEFI y establecer la configuración de Surface UEFI según las necesidades de su entorno. En las siguientes secciones de este artículo, se explica el script de ConfigureSEMM.ps1 y se exploran las modificaciones que es necesario realizar en la secuencia de comandos para satisfacer sus necesidades.

> [!NOTE]
> Los scripts de SEMM Configuration Manager y el archivo de certificado SEMM exportado (. pfx) deben ubicarse en la misma carpeta sin otros archivos antes de que se agreguen a Configuration Manager.

### Especificar nombres de paquetes y certificados

La primera región de la secuencia de comandos que necesita modificar es la parte que especifica y carga el certificado SEMM, además de indicar SurfaceUEFIManager versión y los nombres del paquete de configuración de SEMM y SEMM restablecer paquete. El nombre del certificado y la versión de SurfaceUEFIManager se especifican en las líneas 56 a 73 en el script de ConfigureSEMM.ps1.

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

Reemplace el valor **FabrikamSEMMSample. pfx** de la variable **$certName** por el nombre del archivo de certificado SEMM en la línea 58. El script creará un directorio de trabajo (denominado configuración) en la carpeta en la que se encuentran los scripts y, a continuación, copiará el archivo de certificado en este directorio de trabajo.

El paquete de propietario y el paquete de restablecimiento también se crearán en el directorio config y conservarán la configuración de los permisos y la configuración de Surface UEFI generados por el script.

En la línea 73, reemplace el valor de la variable **$password** , de **1234** a la contraseña del archivo de certificado. Si no es necesaria una contraseña, elimine el texto de **1234** .

> [!Note]
> Los últimos dos caracteres de la huella digital del certificado son necesarios para inscribir un dispositivo en SEMM. Esta secuencia de comandos mostrará estos dígitos al usuario, lo que permite al usuario o al técnico grabar estos dígitos antes de que el sistema se reinicie para inscribir el dispositivo en SEMM. La secuencia de comandos usa el código siguiente, que se encuentra en las líneas 150-155, para hacerlo.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Los administradores con acceso al archivo de certificados (. pfx) pueden leer la huella digital en cualquier momento abriendo el archivo. pfx en CertMgr. Para ver la huella digital con CertMgr, siga este proceso:

1. Haga clic con el botón derecho en el archivo. pfx y, después, seleccione **abrir**.
2. Expanda la carpeta en el panel de navegación.
3. Seleccione **certificados**.
4. Haga clic con el botón derecho en el certificado en el panel principal y, a continuación, seleccione **abrir**.
5. Seleccione la pestaña **detalles** .
6. Solo se deben seleccionar **todas** **las propiedades** o en el menú desplegable **Mostrar** .
7. Seleccione la **huella digital**del campo.

> [!NOTE]
> El nombre de certificado y la contraseña de SEMM también deben escribirse en esta sección del script de ResetSEMM.ps1 para habilitar Configuration Manager para quitar SEMM del dispositivo con la acción de desinstalación.

### Configurar permisos

La primera región de la secuencia de comandos en la que especificará la configuración de Surface UEFI es la región de **permisos de configuración** . Esta región comienza en la línea 210 de la secuencia de comandos de ejemplo con el comentario **# configurar permisos** y continúa en la línea 247. El siguiente fragmento de código establece primero permisos para todos los ajustes de la superficie UEFI para que solo los pueda modificar SEMM, después agrega permisos explícitos que permiten al usuario local modificar la superficie UEFI contraseña, TPM, y cámaras frontal y trasera.

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

Cada variable **$uefiV 2** identifica una configuración de Surface UEFI mediante el establecimiento de nombre o identificador, y luego configura los permisos en uno de los siguientes valores:

* **$ownerOnly** : el permiso para modificar esta configuración solo se concede a SEMM.
* **$ownerAndLocalUser** : el permiso para modificar esta configuración se concede a un usuario local que arranca con Surface UEFI, así como a SEMM.

Puede encontrar información sobre los nombres e identificadores de configuración disponibles para Surface UEFI en la sección [nombres e identificadores de configuración](#settings-names-and-ids) de este artículo.

### Configurar opciones

La segunda región de la secuencia de comandos en la que especificará la configuración de Surface UEFI es el área **configurar opciones** del script de ConfigureSEMM.ps1, que establece si cada opción está habilitada o deshabilitada. El script de ejemplo incluye instrucciones para establecer toda la configuración en los valores predeterminados. La secuencia de comandos proporciona instrucciones explícitas para deshabilitar IPv6 para el arranque PXE y para dejar la contraseña de administrador de Surface UEFI sin cambios. Puede encontrar esta región empezando con el comentario de **Configuración # Configurar** en la línea 291 a la 335 en la secuencia de comandos de ejemplo. La región aparece de la siguiente manera.

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

Al igual que los permisos establecidos en la sección de configuración de **permisos** del script, la configuración de cada configuración de Surface UEFI se realiza definiendo la variable **$uefiV 2** . Para cada línea que define la variable **$uefiV 2** , se identifica la configuración de Surface UEFI mediante el nombre o el identificador de configuración, y el valor configurado se establece en **habilitado** o **deshabilitado**.

Si no desea alterar la configuración de una superficie UEFI, por ejemplo, asegúrese de que la contraseña de administrador de Surface UEFI no se limpie con la acción de restablecer la configuración de Surface UEFI a su valor predeterminado, puede usar **ClearConfiguredValue ()** para exigir que no se modifique esta configuración. En el script de ejemplo, se usa en la línea 323 para evitar que se borre la contraseña de administrador de Surface UEFI, identificada en el script de ejemplo según su identificador de configuración, **501**.

Puede encontrar información sobre los nombres e identificadores de configuración disponibles para Surface UEFI en la sección [nombres e identificadores de configuración,](#settings-names-and-ids) más adelante en este artículo.

### Configuración clave del registro

Para identificar sistemas inscritos para Configuration Manager, el script de ConfigureSEMM.ps1 graba las claves del registro que se pueden usar para identificar sistemas inscritos como instalados con el script de configuración SEMM. Estas claves se pueden encontrar en la siguiente ubicación.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

El siguiente fragmento de código, que se encuentra en las líneas 380-477, se usa para escribir estas claves de registro.

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### Nombres e identificadores de configuración

Para configurar la configuración de Surface UEFI o permisos para la configuración de Surface UEFI, debe hacer referencia a cada configuración mediante su nombre de configuración o el identificador de configuración. Con cada nueva actualización de Surface UEFI, se puede Agregar una nueva configuración. La mejor manera de obtener una lista completa de la configuración disponible en un dispositivo Surface, junto con el nombre de configuración y los identificadores de configuración, es usar la ShowSettingsOptions.ps1 script de SEMM_Powershell.zip en [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703) 

El equipo en el que se ejecuta ShowSettingsOptions.ps1 debe tener instalado Microsoft Surface UEFI Manager, pero el script no requiere un dispositivo Surface.

La mejor manera de ver los nombres e identificadores de configuración más actuales para los dispositivos es usar el script de ConfigureSEMM.ps1 o el ConfigureSEMM- <device name> . PS1 de la SEMM_Powershell.zip en [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703).

En el script ConfigureSEMM.ps1 se pueden ver los nombres e identificadores de todos los dispositivos.

La configuración de nombres e identificadores para dispositivos específicos se puede ver en los <device name> scripts ConfigureSEMM-. ps1. 

## Implementar SEMM scripts de Configuration Manager

Una vez que los scripts estén preparados para configurar y habilitar SEMM en el dispositivo cliente, el siguiente paso es agregar estos scripts como una aplicación en Configuration Manager. Antes de abrir el administrador de configuración, asegúrese de que los siguientes archivos están en una carpeta compartida que no incluye otros archivos:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* El certificado de SEMM (por ejemplo, SEMMCertificate. pfx)

Los scripts de Configuration Manager de SEMM se agregarán a Configuration Manager como una aplicación de script. El comando para instalar SEMM con ConfigureSEMM.ps1 es el siguiente.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

El comando para desinstalar SEMM con ResetSEMM.ps1 es el siguiente.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Para agregar los scripts del administrador de configuración de SEMM a Configuration Manager como una aplicación, use el siguiente proceso:

1. Inicie el Asistente para crear aplicaciones usando los pasos 1 a 5 de la sección [implementar Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) anteriormente en este artículo.

2. Continúe con el Asistente para crear aplicaciones de la siguiente manera:

   - **General** : seleccione **especificar manualmente la información de la aplicación**y, a continuación, seleccione **siguiente**.

   - **Información general** : escriba un nombre para la aplicación (por ejemplo, SEMM) y cualquier otra información que desee, como editor, versión o comentarios, en esta página. Seleccione **siguiente** para continuar.

   - **Catálogo de aplicaciones** : los campos de esta página se pueden dejar con los valores predeterminados. Selecciona **Siguiente**.

   - **Tipos de implementación** : seleccione **Agregar** para iniciar el Asistente para crear tipos de implementación.

   - Siga los pasos del Asistente para crear tipos de implementación, como se indica a continuación:

     * **General** : seleccione **instalador de script** en el menú desplegable **tipo** . La opción **especificar manualmente la información de tipo de implementación** se seleccionará automáticamente. Seleccione **siguiente** para continuar.
     * **Información general** : escriba un nombre para el tipo de implementación (por ejemplo, scripts de configuración de SEMM) y, a continuación, seleccione **siguiente** para continuar.
     * **Contenido** : seleccione **examinar** junto al campo **Ubicación de contenido** y, a continuación, seleccione la carpeta donde se encuentran los scripts de Configuration Manager de semm. En el campo **programa de instalación** , escriba el comando de [instalación](#deploy-semm-configuration-manager-scripts) que se encontró anteriormente en este artículo. En el campo **desinstalar programa** , escriba el [comando de desinstalación](#deploy-semm-configuration-manager-scripts) que se encuentra anteriormente en este artículo (que se muestra en la ilustración 2). Seleccione **siguiente** para ir a la página siguiente.
    
     ![Establecer los scripts de Configuration Manager de SEMM como comandos de instalación y desinstalación](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figura 2. Establecer los scripts de Configuration Manager de SEMM como comandos de instalación y desinstalación*

     * **Método de detección** : seleccione la **cláusula Add** para agregar la regla de detección de la clave de registro SEMM de Configuration Manager. Aparece la ventana **regla de detección** , como se muestra en la ilustración 3. Usa la configuración siguiente:

       - Seleccione **registro** en el menú desplegable **tipo de configuración** .
       - Seleccione **HKEY_LOCAL_MACHINE** en el menú desplegable **Hive (Hive** ).
       - Escriba **SOFTWARE\Microsoft\Surface\SEMM** en el campo **clave** .
       - Escriba **CertName** en el campo de **valor** .
       - Seleccione **cadena** en el menú desplegable **tipo de datos** .
       - Seleccione la **opción este registro debe cumplir con los siguientes pasos para indicar la presencia de esta aplicación** .
       - Escriba el nombre del certificado que ha introducido en la línea 58 del script en el campo de **valor** .
       - Seleccione **Aceptar** para cerrar la ventana de **regla de detección** .

     ![Usar una clave del registro para identificar los dispositivos inscritos en SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Figura 3. Usar una clave del registro para identificar los dispositivos inscritos en SEMM*

     * Seleccione **siguiente** para pasar a la página siguiente.
     
     * **Experiencia de usuario** : seleccione **instalar para el sistema** en el menú desplegable de **instalación** . Si quiere que los usuarios registren y escriban la huella digital del certificado, deje el requisito de inicio de sesión establecido en **solo cuando un usuario ha iniciado sesión**. Si desea que los administradores introduzcan la huella digital para los usuarios y los usuarios no necesiten ver la huella digital, seleccione **si un usuario ha iniciado sesión en** el menú desplegable de **requisitos de inicio de sesión** .

     * **Requisitos** : el script de ConfigureSEMM.ps1 comprueba automáticamente que el dispositivo es un dispositivo Surface antes de intentar habilitar SEMM. Sin embargo, si tiene previsto implementar esta aplicación de script en una colección con dispositivos distintos de los que se administrarán con SEMM, puede agregar requisitos aquí para asegurarse de que esta aplicación se ejecute solo en dispositivos Surface o dispositivos que desee administrar con SEMM. Seleccione **siguiente** para continuar.
     
     * **Dependencias** : seleccione **Agregar** para abrir la ventana **Agregar dependencia** .

       * Seleccione **Agregar** para abrir la ventana **especificar aplicación requerida** .

          - Escriba un nombre para las dependencias SEMM en el campo de **nombre del grupo de dependencias** (por ejemplo, *SEMM ensamblados*).

          - Seleccione **Microsoft Surface UEFI Manager** en la lista de **aplicaciones disponibles** y el tipo de implementación MSI y, a continuación, seleccione **Aceptar** para cerrar la ventana **especificar aplicación requerida** .
          
         *   Mantenga activada la casilla de verificación **instalación automática** si quiere que Microsoft Surface UEFI Manager se instale automáticamente en los dispositivos cuando intente habilitar SEMM con los scripts de Configuration Manager. Seleccione **Aceptar** para cerrar la ventana **Agregar dependencia** .

     * Seleccione **siguiente** para continuar.
     
     * **Resumen** : la información que ha introducido en el Asistente para crear tipos de implementación se muestra en esta página. Seleccione **siguiente** para confirmar las selecciones.
     
     * **Progreso** : se muestra una barra de progreso y un estado como tipo de implementación para la aplicación de script SEMM en esta página.
     
     * **Finalización** : la confirmación de la creación del tipo de implementación se muestra cuando se completa el proceso. Seleccione **cerrar** para finalizar el Asistente para crear tipos de implementación.

   - **Resumen** : se muestra la información introducida en el Asistente para crear aplicaciones. Seleccione **siguiente** para crear la aplicación.

   - **Progreso** : se muestra una barra de progreso y el estado como la aplicación en la biblioteca de software en esta página.

   - **Finalización** : se muestra una confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación. Seleccione **cerrar** para finalizar el Asistente para crear aplicaciones.

Una vez que la aplicación de scripts esté disponible en la biblioteca de software de Configuration Manager, puede distribuir e implementar SEMM con los scripts que preparó para dispositivos o colecciones. Si ha configurado los ensamblados de Microsoft Surface UEFI Manager como una dependencia que se instalará de forma automática, puede implementar SEMM en un solo paso. Si no ha configurado los ensamblados como dependencia, debe instalarlos en los dispositivos que desea administrar antes de habilitar SEMM.

Al implementar SEMM con esta aplicación de scripts y con una configuración visible para el usuario final, el script de PowerShell se iniciará y la ventana de PowerShell mostrará la huella digital para el certificado. Puede hacer que los usuarios registren esta huella digital y escribirla cuando se lo solicite la Surface UEFI después de que el dispositivo se reinicie.

Como alternativa, puede configurar la instalación de la aplicación para que se reinicie automáticamente y, de forma invisible para el usuario. En este caso, se requerirá que un técnico Introduzca la huella digital en cada dispositivo a medida que se reinicie. Cualquier técnico con acceso al archivo de certificado puede leer la huella digital viendo el certificado con CertMgr. Las instrucciones para ver la huella digital con CertMgr se encuentran en la sección [crear o modificar la Semm de las secuencias de comandos de Configuration Manager](#create-or-modify-the-semm-configuration-manager-scripts) de este artículo.

La eliminación de SEMM de un dispositivo implementado con Configuration Manager con estas secuencias de comandos es tan fácil como desinstalar la aplicación con Configuration Manager. Esta acción inicia el script de ResetSEMM.ps1 y anula la inscripción del dispositivo correctamente con el mismo archivo de certificado que se usó durante la implementación de SEMM.

> [!NOTE]
> Microsoft Surface recomienda que cree paquetes de restablecimiento solo cuando necesite anular la inscripción de un dispositivo. Normalmente, estos paquetes de restablecimiento son válidos para un solo dispositivo, identificados por su número de serie. Sin embargo, puede crear un paquete de restablecimiento universal que funcione para cualquier dispositivo inscrito en SEMM con este certificado.
> 
> Le recomendamos encarecidamente que proteja su paquete de restablecimiento universal tan detenidamente como el certificado que usó para inscribir dispositivos en SEMM. Recuerde que, al igual que el propio certificado, este paquete de restablecimiento universal se puede usar para anular la inscripción de cualquiera de los dispositivos Surface de su organización desde SEMM.
> 
> Al instalar un paquete de restablecimiento, el valor más bajo admitido (LSV) se restablece en el valor 1. Puede volver a inscribir un dispositivo con un paquete de configuración existente. El dispositivo solicitará la huella digital del certificado antes de que se realice la propiedad.
> 
> Por esta razón, la reinscripción de un dispositivo en SEMM requeriría la creación y la instalación de un nuevo paquete en ese dispositivo. Como esta acción es una inscripción nueva y no un cambio en la configuración en un dispositivo ya inscrito en SEMM, el dispositivo solicitará la huella digital del certificado antes de que se realice la propiedad.

---
title: Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM
description: Obtén información sobre cómo administrar Microsoft Surface Enterprise Management Mode (SEMM) con Endpoint Configuration Manager.
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
ms.date: 10/28/2020
ms.openlocfilehash: 9f3db9428e188aa20399d26c066507d76c90ba57
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708791"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM

La característica modo de administración de Microsoft Surface Enterprise (SEMM) de dispositivos UEFI de Surface permite a los administradores administrar y ayudar a proteger la configuración de la configuración de UEFI de Surface. Para la mayoría de las organizaciones, este proceso se lleva a cabo creando Windows Installer (.msi) con la herramienta Configurador UEFI de Microsoft Surface. A continuación, estos paquetes se ejecutan o implementan en los dispositivos Surface del cliente para inscribir los dispositivos en SEMM y actualizar la configuración de configuración de UEFI de Surface.

Para las organizaciones con Microsoft Endpoint Configuration Manager existe una alternativa al uso del proceso de configuración uefi de Microsoft Surface .msi implementar y administrar SEMM. Microsoft Surface UEFI Manager es un instalador ligero que hace que los ensamblados necesarios para la administración de SEMM estén disponibles en un dispositivo. Al instalar estos ensamblados con Microsoft Surface UEFI Manager en un cliente administrado, Configuration Manager puede administrar SEMM con scripts de PowerShell, implementados como aplicaciones. Con este proceso, la administración de SEMM se realiza en Configuration Manager, lo que elimina la necesidad de la herramienta externa de Microsoft Surface UEFI Configurator.

> [!Note]
> Aunque el proceso descrito en este artículo puede funcionar con versiones anteriores de Endpoint Configuration Manager o con otras soluciones de administración de terceros, la administración de SEMM con Microsoft Surface UEFI Manager y PowerShell solo se admite con la rama actual de Endpoint Configuration Manager.

#### <a name="prerequisites"></a>Requisitos previos

Antes de comenzar el proceso descrito en este artículo, familiarícese con las siguientes tecnologías y herramientas:

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Modo de administración de empresa de Surface (SEMM)](surface-enterprise-management-mode.md)
* [Scripting de PowerShell](/powershell)
* [Implementar aplicaciones con Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> También necesitarás acceso al certificado que quieres usar para proteger SEMM. Para obtener más información sobre los requisitos de este certificado, consulta Requisitos de certificado del modo de administración de [Surface Enterprise.](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)
> 
> Es muy importante mantener este certificado en una ubicación segura y realizar una copia de seguridad correctamente. Si este certificado se pierde o no se puede usar, no es posible restablecer la UEFI de Surface, cambiar la configuración de UEFI de Surface administrada o quitar SEMM de un dispositivo Surface inscrito.

#### <a name="download-microsoft-surface-uefi-manager"></a>Descargar Microsoft Surface UEFI Manager

La administración de SEMM con Configuration Manager requiere la instalación de Microsoft Surface UEFI Manager en cada dispositivo Surface cliente. Puedes descargar Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) desde la página [Herramientas de Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft.

#### <a name="download-semm-scripts-for-configuration-manager"></a>Descargar scripts DEMM para Configuration Manager

Después de instalar Microsoft Surface UEFI Manager en el dispositivo Surface cliente, SEMM se puede implementar y administrar con scripts de PowerShell. Obtén ejemplos de [scripts de administración de SEMM](https://www.microsoft.com/download/details.aspx?id=46703) descargando SEMM_PowerShell.zip de Surface Tools para TI.

## <a name="deploy-microsoft-surface-uefi-manager"></a>Implementar Microsoft Surface UEFI Manager

La implementación de Microsoft Surface UEFI Manager es una implementación típica de aplicaciones. El archivo de instalación de Microsoft Surface UEFI Manager es un archivo Windows Installer estándar que puedes instalar con la [opción silenciosa estándar.](https://msdn.microsoft.com/library/windows/desktop/aa367988)

El comando para instalar Microsoft Surface UEFI Manager es el siguiente.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

El comando para desinstalar Microsoft Surface UEFI Manager es el siguiente.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

Para crear una nueva aplicación e implementarla en una colección que contenga los dispositivos Surface, siga estos pasos:

1. Abra la Consola de Configuration Manager desde la **pantalla** Inicio o **el menú** Inicio.
2. Seleccione **Biblioteca de software** en la esquina inferior izquierda de la ventana.
3. Expanda el **nodo Administración de** aplicaciones de la biblioteca de software y, a continuación, seleccione **Aplicaciones**.
4. Seleccione el **botón Crear aplicación** debajo de la pestaña Inicio en la parte superior de la ventana. **** Esto inicia el Asistente para crear aplicaciones.
5. El Asistente para crear aplicaciones presenta una serie de pasos:

   * **General:** **la opción Detectar automáticamente información sobre esta aplicación** desde archivos de instalación está seleccionada de forma predeterminada. En el **campo** Tipo, **Windows installer (.msi archivo)** también está seleccionado de forma predeterminada. Seleccione **Examinar** para ir a y seleccionar **SurfaceUEFIManagerSetup.msi**y, a continuación, seleccione **Siguiente**.
   
      > [!Note]
      > La ubicación de SurfaceUEFIManagerSetup.msi debe estar en un recurso compartido de red y se encuentra en una carpeta que no contiene ningún otro archivo. No se puede usar una ubicación de archivo local.

   * **Importar información:** el Asistente para crear aplicación analizará el archivo .msi y leerá el **nombre de** la aplicación y el código **de producto**. SurfaceUEFIManagerSetup.msi debe aparecer como el único archivo debajo de la línea **Archivos de contenido**, como se muestra en la figura 1. Seleccione **Siguiente** para continuar.

      ![La información de la configuración de Surface UEFI Manager se analiza automáticamente](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figura 1. La información del programa de instalación de Microsoft Surface UEFI Manager se analiza automáticamente*

   * **Información general:** puede modificar el nombre de la aplicación y la información sobre el editor y la versión, o agregar comentarios en esta página. El comando de instalación de Microsoft Surface UEFI Manager se muestra en el campo Programa de instalación. El comportamiento de instalación predeterminado de Install for system permitirá a Microsoft Surface UEFI Manager instalar los ensamblados necesarios para SEMM incluso si un usuario no ha iniciado sesión en el dispositivo Surface. Seleccione **Siguiente** para continuar.
   * **Resumen:** la información analizada en el paso **Importar** información y las selecciones del paso Información **general** se muestra en esta página. Seleccione **Siguiente** para confirmar las selecciones y crear la aplicación.
   * **Progreso:** muestra una barra de progreso y el estado a medida que la aplicación se importa y se agrega a la biblioteca de software.
   * **Finalización:** se muestra la confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación. Seleccione **Cerrar** para finalizar el Asistente para crear aplicaciones.

Después de crear la aplicación en Configuration Manager, puedes distribuirla a los puntos de distribución e implementarla en las colecciones, incluidos los dispositivos Surface. Esta aplicación no instalará ni habilitará SEMM en el dispositivo Surface. Solo proporciona los ensamblados necesarios para que SEMM se habilite con el script de PowerShell.

Si no quieres instalar los ensamblados de Microsoft Surface UEFI Manager en dispositivos que no se administrarán con SEMM, puedes configurar Microsoft Surface UEFI Manager como una dependencia de los scripts de SEMM Configuration Manager. Este escenario se describe en la sección Implementar scripts de [Configuration Manager de SEMM](#deploy-semm-configuration-manager-scripts) más adelante en este artículo.

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>Crear o modificar los scripts de SEMM Configuration Manager

Una vez instalados los ensamblados necesarios en los dispositivos, el proceso de inscripción de los dispositivos en SEMM y la configuración de UEFI de Surface se realiza con scripts de PowerShell e se implementa como una aplicación de script con Configuration Manager. Estos scripts se pueden modificar para que se ajusten a las necesidades de su organización y entorno. Por ejemplo, puedes crear varias configuraciones para dispositivos Surface administrados en diferentes departamentos o roles. Puede descargar ejemplos de los scripts para SEMM y Configuration Manager desde el vínculo de la sección [Requisitos previos](#prerequisites) al principio de este artículo.

Hay dos scripts principales que necesitará para realizar una implementación de SEMM con Configuration Manager:

* **ConfigureSEMM.ps1: ** usa este script para crear paquetes de configuración para tus dispositivos Surface con la configuración UEFI de Surface deseada para aplicar la configuración especificada a un dispositivo Surface, inscribir el dispositivo en SEMM y establecer una clave del Registro usada para identificar la inscripción del dispositivo en SEMM.
* **ResetSEMM.ps1: ** usa este script para restablecer SEMM en un dispositivo Surface, que lo desanrolla de SEMM y quita el control sobre la configuración de UEFI de Surface.

Los scripts de ejemplo incluyen ejemplos de cómo establecer la configuración de UEFI de Surface y cómo controlar los permisos de dicha configuración. Esta configuración se puede modificar para proteger La UEFI de Surface y establecer la configuración de UEFI de Surface según las necesidades del entorno. En las secciones siguientes de este artículo se explica el ConfigureSEMM.ps1 script y se exploran las modificaciones que debe realizar en el script para ajustarse a sus requisitos.

> [!NOTE]
> Los scripts de SEMM Configuration Manager y el archivo de certificado semm exportado (.pfx) deben colocarse en la misma carpeta sin otros archivos antes de agregarlos a Configuration Manager.

### <a name="specify-certificate-and-package-names"></a>Especificar nombres de certificado y paquete

La primera región del script que debes modificar es la parte que especifica y carga el certificado SEMM, y también indica la versión de SurfaceUEFIManager y los nombres del paquete de configuración de SEMM y el paquete de restablecimiento de SEMM. El nombre del certificado y la versión de SurfaceUEFIManager se especifican en las líneas 56 a 73 del script ConfigureSEMM.ps1 usuario.

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

Reemplace el **valor FabrikamSEMMSample.pfx** de la variable **$certName** por el nombre del archivo de certificado SEMM en la línea 58. El script creará un directorio de trabajo (denominado Config) en la carpeta donde se encuentran los scripts y, a continuación, copiará el archivo de certificado en este directorio de trabajo.

El paquete propietario y el paquete de restablecimiento también se crearán en el directorio Config y mantendrán la configuración de la configuración de la UEFI de Surface y los permisos generados por el script.

En la línea 73, reemplace el valor de la variable **$password,** de **1234** a la contraseña del archivo de certificado. Si no es necesaria una contraseña, elimine el **texto 1234.**

> [!Note]
> Los dos últimos caracteres de la huella digital del certificado son necesarios para inscribir un dispositivo en SEMM. Este script mostrará estos dígitos al usuario, lo que permite al usuario o al técnico grabar estos dígitos antes de que el sistema se reinicie para inscribir el dispositivo en SEMM. El script usa el siguiente código, que se encuentra en las líneas 150-155, para lograrlo.

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Los administradores con acceso al archivo de certificado (.pfx) pueden leer la huella digital en cualquier momento abriendo el archivo .pfx en CertMgr. Para ver la huella digital con CertMgr, siga este proceso:

1. Haga clic con el botón secundario en el archivo .pfx y, a continuación, **seleccione Abrir**.
2. Expanda la carpeta en el panel de navegación.
3. Seleccione **Certificados**.
4. Haga clic con el botón secundario en el certificado en el panel principal y, a continuación, **seleccione Abrir**.
5. Seleccione la **pestaña** Detalles.
6. **All** o **Properties Only** deben seleccionarse en **el** menú desplegable Mostrar.
7. Seleccione el campo **Huella digital**.

> [!NOTE]
> El nombre y la contraseña del certificado SEMM también deben especificarse en esta sección del script de ResetSEMM.ps1 para permitir que Configuration Manager quite SEMM del dispositivo con la acción de desinstalación.

### <a name="configure-permissions"></a>Configurar permisos

La primera región del script donde especificará la configuración de UEFI de Surface es la **región Configurar permisos.** Esta región comienza en la línea 210 en el script de ejemplo con el comentario **# Configurar** permisos y continúa con la línea 247. En primer lugar, el siguiente fragmento de código establece permisos en todas las configuraciones de UEFI de Surface para que solo se puedan modificar por SEMM y, a continuación, agrega permisos explícitos para permitir al usuario local modificar la contraseña de UEFI de Surface, el TPM y las cámaras frontal y trasera.

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

Cada **variable $uefiV 2** identifica una configuración de UEFI de Surface estableciendo el nombre o id. y, a continuación, configura los permisos en uno de los siguientes valores:

* **$ownerOnly:** el permiso para modificar esta configuración solo se concede a SEMM.
* **$ownerAndLocalUser:** el permiso para modificar esta configuración se concede a un usuario local que inicia en Surface UEFI, así como a SEMM.

Puedes encontrar información sobre los nombres de configuración e IDs disponibles para UEFI de Surface en la sección Configuración nombres e [IDs](#settings-names-and-ids) de este artículo.

### <a name="configure-settings"></a>Configurar opciones

La segunda región del script donde especificará la configuración de UEFI de Surface es la región Configurar **Configuración** del script ConfigureSEMM.ps1, que configura si cada configuración está habilitada o deshabilitada. El script de ejemplo incluye instrucciones para establecer todas las opciones de configuración en sus valores predeterminados. A continuación, el script proporciona instrucciones explícitas para deshabilitar IPv6 para el arranque PXE y para dejar la contraseña del administrador de UEFI de Surface sin cambios. Puede encontrar esta región a partir del **comentario # Configure Configuración** en la línea 291 a la línea 335 en el script de ejemplo. La región aparece de la siguiente manera.

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

Al igual que los permisos establecidos en la sección **Configurar** permisos del script, la configuración de cada configuración de UEFI de Surface se realiza definiendo la **variable $uefiV 2.** Para cada línea que define la variable **$uefiV 2,** una configuración de UEFI de Surface se identifica estableciendo el nombre o id. y el valor configurado se establece en **Enabled** o **Disabled**.

Si no quieres modificar la configuración de una configuración de UEFI de Surface, por ejemplo, para asegurarte de que la contraseña de administrador de UEFI de Surface no se borra mediante la acción de restablecer todas las configuraciones de UEFI de Surface a su valor predeterminado, puedes usar **ClearConfiguredValue()** para exigir que esta configuración no se modifique. En el script de ejemplo, se usa en la línea 323 para evitar que se borra la contraseña del administrador de UEFI de Surface, identificada en el script de ejemplo por su identificador de configuración, **501**.

Puedes encontrar información sobre los nombres de configuración e IDs disponibles para UEFI de Surface en la sección Configuración Nombres e [IDs](#settings-names-and-ids) disponibles más adelante en este artículo.

### <a name="settings-registry-key"></a>Configuración clave del Registro

Para identificar los sistemas inscritos para Configuration Manager, el script ConfigureSEMM.ps1 escribe claves del Registro que se pueden usar para identificar los sistemas inscritos como instalados con el script de configuración de SEMM. Estas claves se pueden encontrar en la siguiente ubicación.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

El siguiente fragmento de código, que se encuentra en las líneas 380-477, se usa para escribir estas claves del Registro.

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

### <a name="settings-names-and-ids"></a>Configuración nombres e IDs

Para configurar la uefi de Surface o los permisos para la configuración de UEFI de Surface, debes hacer referencia a cada configuración por su nombre de configuración o id. de configuración. Con cada nueva actualización para Surface UEFI, se pueden agregar nuevas opciones de configuración. Ejecutar ShowSettingsOptions.ps1 script (desde SEMM_Powershell.zip en [Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703))proporciona detalles de la configuración disponible. El equipo donde ShowSettingsOptions.ps1 se ejecuta debe tener Instalado Microsoft Surface UEFI Manager, pero el script no requiere un dispositivo Surface.


## <a name="deploy-semm-configuration-manager-scripts"></a>Implementar scripts de CONFIGURATION Manager de SEMM

Después de que los scripts estén preparados para configurar y habilitar SEMM en el dispositivo cliente, el siguiente paso es agregar estos scripts como una aplicación en Configuration Manager. Antes de abrir Configuration Manager, asegúrese de que los siguientes archivos se encuentran en una carpeta compartida que no incluye otros archivos:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Su certificado SEMM (por ejemplo, SEMMCertificate.pfx)

Los scripts de SEMM Configuration Manager se agregarán a Configuration Manager como una aplicación de script. El comando para instalar SEMM con ConfigureSEMM.ps1 es el siguiente.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

El comando para desinstalar SEMM con ResetSEMM.ps1 es el siguiente.

`Powershell.exe -file ".\ResetSEMM.ps1"`

Para agregar los scripts de SEMM Configuration Manager a Configuration Manager como una aplicación, use el siguiente proceso:

1. Inicia el Asistente para crear aplicaciones con los pasos 1 y 5 de la sección [Implementar Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) anterior en este artículo.

2. Continúe con el Asistente para crear aplicaciones de la siguiente manera:

   - **General:** seleccione **Especificar manualmente la información de la**aplicación y, a continuación, seleccione **Siguiente**.

   - **Información general:** escriba un nombre para la aplicación (por ejemplo, SEMM) y cualquier otra información que desee, como editor, versión o comentarios en esta página. Seleccione **Siguiente** para continuar.

   - **Catálogo de aplicaciones:** los campos de esta página se pueden dejar con sus valores predeterminados. Selecciona **Siguiente**.

   - **Tipos de implementación:** seleccione **Agregar** para iniciar el Asistente para crear tipo de implementación.

   - Siga los pasos del Asistente para crear tipo de implementación, como se muestra a continuación:

     * **General:** seleccione **Instalador de scripts** en el menú desplegable Tipo. **** La **opción Especificar manualmente la información del tipo de** implementación se seleccionará automáticamente. Seleccione **Siguiente** para continuar.
     * **Información general:** escriba un nombre para el tipo de implementación (por ejemplo, Scripts de configuración de SEMM) y, a continuación, **seleccione Siguiente** para continuar.
     * **Contenido:** seleccione **Examinar junto** al campo **Ubicación** de contenido y, a continuación, seleccione la carpeta donde se encuentran los scripts de SEMM Configuration Manager. En el **campo Programa de** instalación, escriba el comando de [instalación](#deploy-semm-configuration-manager-scripts) que se encontró anteriormente en este artículo. En el **campo Desinstalar programa,** escriba el comando [de desinstalación](#deploy-semm-configuration-manager-scripts) que se encontró anteriormente en este artículo (que se muestra en la figura 2). Seleccione **Siguiente** para pasar a la página siguiente.
    
     ![Establecer los scripts de SEMM Configuration Manager como comandos de instalación y desinstalación](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figura 2. Establecer los scripts de SEMM Configuration Manager como comandos de instalación y desinstalación*

     * **Método Detection:** seleccione **Agregar cláusula** para agregar la regla de detección de claves de script de SEMM Configuration Manager. Se **muestra la ventana** Regla de detección, como se muestra en la figura 3. Usa la configuración siguiente:

       - Seleccione **Registro** en el **menú** desplegable Tipo de configuración.
       - Seleccione **HKEY_LOCAL_MACHINE** en el menú desplegable **Subárbol.**
       - Escriba **SOFTWARE\Microsoft\Surface\SEMM** en el **campo** Clave.
       - Escriba **CertName** en el **campo** Valor.
       - Seleccione **Cadena** en el **menú** desplegable Tipo de datos.
       - Seleccione la **opción Esta configuración del Registro debe cumplir la siguiente regla para indicar la presencia de este botón de** aplicación.
       - Escriba el nombre del certificado que escribió en la línea 58 del script en el **campo** Valor.
       - Seleccione **Aceptar** para cerrar la ventana **Regla de detección.**

     ![Usar una clave del Registro para identificar los dispositivos inscritos en SEMM](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *Figura 3. Usar una clave del Registro para identificar los dispositivos inscritos en SEMM*

     * Seleccione **Siguiente** para continuar con la página siguiente.
     
     * **Experiencia del usuario:** seleccione **Instalar para el sistema** en el menú desplegable Comportamiento de instalación. **** Si desea que los usuarios registren e introduzcan la huella digital del certificado por sí mismos, deje el requisito de inicio de sesión establecido en Solo cuando un usuario **haya iniciado sesión.** Si desea que los administradores escriban la huella digital de los usuarios y los usuarios no necesitan **** ver la huella digital, seleccione **Si** un usuario ha iniciado sesión o no en el menú desplegable Requisito de inicio de sesión.

     * **Requisitos:** ConfigureSEMM.ps1 script comprueba automáticamente que el dispositivo es un dispositivo Surface antes de intentar habilitar SEMM. Sin embargo, si quieres implementar esta aplicación de script en una colección con dispositivos distintos de los que se administrarán con SEMM, puedes agregar requisitos aquí para garantizar que esta aplicación se ejecute solo en dispositivos Surface o dispositivos que quieres administrar con SEMM. Seleccione **Siguiente** para continuar.
     
     * **Dependencias:** seleccione **Agregar** para abrir la **ventana Agregar dependencia.**

       * Seleccione **Agregar** para abrir la **ventana Especificar aplicación** necesaria.

          - Escriba un nombre para las dependencias de SEMM en el campo **Nombre** del grupo de dependencias (por ejemplo, Ensamblados *SEMM*).

          - Selecciona **Microsoft Surface UEFI Manager** en la lista de Aplicaciones disponibles y el tipo de implementación MSI y, a continuación, selecciona Aceptar para cerrar la ventana Especificar **aplicación** necesaria. **** ****
          
         *   Activa la **casilla Instalación** automática si quieres que Microsoft Surface UEFI Manager se instale automáticamente en dispositivos cuando intentes habilitar SEMM con los scripts de Configuration Manager. Seleccione **Aceptar** para cerrar la **ventana Agregar dependencia.**

     * Seleccione **Siguiente** para continuar.
     
     * **Resumen:** en esta página se muestra la información que ha escrito a lo largo del Asistente para crear tipo de implementación. Seleccione **Siguiente** para confirmar las selecciones.
     
     * **Progreso:** en esta página se muestra una barra de progreso y un estado como el tipo de implementación para la aplicación de script SEMM.
     
     * **Finalización:** se muestra la confirmación de la creación del tipo de implementación cuando se completa el proceso. Seleccione **Cerrar** para finalizar el Asistente para crear tipo de implementación.

   - **Resumen:** se muestra la información que ha especificado en el Asistente para crear aplicaciones. Seleccione **Siguiente** para crear la aplicación.

   - **Progreso:** en esta página se muestra una barra de progreso y el estado de la aplicación que se agrega a la biblioteca de software.

   - **Finalización:** se muestra la confirmación de la creación correcta de la aplicación cuando se completa el proceso de creación de la aplicación. Seleccione **Cerrar** para finalizar el Asistente para crear aplicaciones.

Después de que la aplicación de script esté disponible en la Biblioteca de software de Configuration Manager, puede distribuir e implementar SEMM con los scripts que preparó para dispositivos o colecciones. Si has configurado los ensamblados de Microsoft Surface UEFI Manager como una dependencia que se instalará automáticamente, puedes implementar SEMM en un solo paso. Si no ha configurado los ensamblados como dependencia, deben instalarse en los dispositivos que desea administrar antes de habilitar SEMM.

Al implementar SEMM con esta aplicación de script y con una configuración visible para el usuario final, se iniciará el script de PowerShell y la huella digital del certificado se mostrará en la ventana de PowerShell. Puedes hacer que los usuarios grabe esta huella digital e introdrásla cuando se lo pida Surface UEFI después de reiniciar el dispositivo.

Como alternativa, puede configurar la instalación de la aplicación para que se reinicie automáticamente y para que se instale de forma invisible para el usuario. En este escenario, se requiere que un técnico escriba la huella digital en cada dispositivo mientras se reinicia. Cualquier técnico con acceso al archivo de certificado puede leer la huella digital viendo el certificado con CertMgr. Las instrucciones para ver la huella digital con CertMgr se encuentran en la sección Crear o modificar los scripts de [SEMM Configuration Manager](#create-or-modify-the-semm-configuration-manager-scripts) de este artículo.

La eliminación de SEMM de un dispositivo implementado con Configuration Manager con estos scripts es tan fácil como desinstalar la aplicación con Configuration Manager. Esta acción inicia el script ResetSEMM.ps1 y desanrolla correctamente el dispositivo con el mismo archivo de certificado que se usó durante la implementación de SEMM.

> [!NOTE]
> Microsoft Surface recomienda crear paquetes de restablecimiento solo cuando necesites desenrollar un dispositivo. Estos paquetes de restablecimiento suelen ser válidos para un solo dispositivo, identificado por su número de serie. Sin embargo, puedes crear un paquete de restablecimiento universal que funcione para cualquier dispositivo inscrito en SEMM con este certificado.
> 
> Se recomienda encarecidamente proteger el paquete de restablecimiento universal con el mismo cuidado que el certificado que usó para inscribir dispositivos en SEMM. Recuerda que, al igual que el certificado en sí, este paquete de restablecimiento universal se puede usar para desenrollar cualquiera de los dispositivos Surface de la organización desde SEMM.
> 
> Al instalar un paquete de restablecimiento, el valor más bajo admitido (LSV) se restablece a un valor de 1. Puedes volver a realizar la inscripción de un dispositivo mediante un paquete de configuración existente. El dispositivo pedirá la huella digital del certificado antes de tomar posesión.
> 
> Por este motivo, la reenrollación de un dispositivo en SEMM requeriría que se creara e instalara un nuevo paquete en ese dispositivo. Dado que esta acción es una inscripción nueva y no un cambio en la configuración de un dispositivo que ya está inscrito en SEMM, el dispositivo solicitará la huella digital del certificado antes de tomar posesión.

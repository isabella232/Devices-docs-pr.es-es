---
title: Modo de administración de Surface Enterprise (Surface)
description: Consulta cómo esta característica de dispositivos Surface con UEFI de Surface te ayuda a proteger y administrar la configuración de firmware dentro de la organización.
keywords: uefi, configurar, firmware, seguro, semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271424"
---
# Modo de administración de Microsoft Surface Enterprise

El Modo de administración de Microsoft Surface Enterprise (SEMM) es una característica de dispositivos Surface con UEFI de Surface que te permite proteger y administrar la configuración de firmware dentro de la organización. Con SEMM, los profesionales de IT pueden preparar configuraciones de la configuración de UEFI e instalarlas en un dispositivo Surface. Además de la capacidad de configurar las opciones de UEFI, SEMM también usa un certificado para proteger la configuración contra alteraciones o eliminaciones no autorizadas. SEMM es un requisito para poder migrar un Surface Hub 2S a Windows 10 Pro y Enterprise.

>[!NOTE]
>SEMM solo está disponible en dispositivos con firmware de UEFI de Surface. Esto incluye la mayoría de los demás dispositivos Surface, incluidos Surface Pro 7+, Surface Pro X, Surface Hub 2S y LAS SKU comerciales de Surface Laptop 3 con un procesador Intel y Surface Laptop Go. SEMM no se admite en la SKU de Surface Laptop 3 de 15" con procesador AMD (solo disponible como SKU comercial). 

Cuando los dispositivos Surface se configuran mediante SEMM y se protegen con el certificado SEMM, se consideran *inscritos* en SEMM. Cuando se quita el certificado SEMM y se devuelve el control de la configuración de UEFI al usuario del dispositivo, el dispositivo Surface se considera no inscrito *en* SEMM.

Hay dos opciones administrativas que puedes usar para administrar SEMM e inscribir dispositivos Surface: una herramienta independiente o la integración con Microsoft Endpoint Configuration Manager. La herramienta independiente SEMM, denominada Microsoft Surface UEFI Configurator, se describe en este artículo. Para obtener más información sobre cómo administrar SEMM con Microsoft Endpoint Configuration Manager, consulta Usar Microsoft Endpoint Configuration Manager para administrar dispositivos [con SEMM.](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)


## Configurador de UEFI de Microsoft Surface

El área de trabajo principal de SEMM es microsoft Surface UEFI Configurator, como se muestra en la figura 1. Microsoft Surface UEFI Configurator es una herramienta que se usa para crear paquetes de Windows Installer (.msi) o imágenes de WinPE que se usan para inscribir, configurar y deshacer la inscripción de SEMM en un dispositivo Surface. Estos paquetes contienen un archivo de configuración donde se especifican las opciones de UEFI. Los paquetes SEMM también contienen un certificado, que se instala y almacena en firmware y se usa para comprobar la firma de los archivos de configuración antes de aplicar la configuración de UEFI.

>[!NOTE]
>Ahora puedes usar el Configurador de UEFI de Surface y SEMM para administrar puertos en Surface Dock 2. Para obtener más información, consulta [Puertos de Surface Dock 2 seguros con SEMM.](secure-surface-dock-ports-semm.md)

![Configurador de UEFI de Microsoft Surface](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figura 1. Configurador de UEFI de Microsoft Surface*


Puedes usar la herramienta Configurador de UEFI de Microsoft Surface en tres modos:

* [Paquete de configuración de UEFI de Surface.](#configuration-package) Usa este modo para crear un paquete de configuración de UEFI de Surface para inscribir un dispositivo Surface en SEMM y para configurar las opciones de UEFI en dispositivos inscritos.
* [Paquete de restablecimiento de UEFI de Surface.](#reset-package) Usa este modo para deshacer la inscripción de un dispositivo Surface de SEMM.
* [Surface UEFI Recovery Request](#recovery-request). Usa este modo para responder a una solicitud de recuperación para deshacer la inscripción de un dispositivo Surface desde SEMM donde una operación restablecer paquete no se realiza correctamente.


#### Descargar el Configurador de UEFI de Microsoft Surface

Puedes descargar el Configurador de UEFI de Microsoft Surface desde la página Herramientas [de Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft.

### Paquete de configuración

Los paquetes de configuración de UEFI de Surface son el mecanismo principal para implementar y administrar SEMM en dispositivos Surface. Estos paquetes contienen un archivo de configuración de las opciones de UEFI especificadas durante la creación del paquete en el Configurador de UEFI de Microsoft Surface y un archivo de certificado, como se muestra en la figura 2. Cuando se ejecuta un paquete de configuración por primera vez en un dispositivo Surface que aún no está inscrito en SEMM, aprovisiona el archivo de certificado en el firmware del dispositivo e inscribe el dispositivo en SEMM. Al inscribir un dispositivo en SEMM, se te pedirá que confirmes la operación proporcionando los dos últimos dígitos de la huella digital del certificado SEMM antes de que se almacene el archivo de certificado y se pueda completar la inscripción. Esta confirmación requiere que un usuario esté físicamente presente en el dispositivo en el momento de la inscripción para realizar la confirmación.

![Proteger un paquete de configuración de SEMM con un certificado](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figura 2. Proteger un paquete de configuración de SEMM con un certificado*

Consulta la sección [requisitos de](#surface-enterprise-management-mode-certificate-requirements) certificados del Modo de administración de Surface Enterprise de este artículo para obtener más información sobre los requisitos para el certificado SEMM.

>[!NOTE]
>También puedes especificar una contraseña de UEFI con SEMM necesaria **** para ver las páginas **Seguridad,** **Dispositivos,** Configuración de arranque o **Administración** empresarial de Surface UEFI.

Después de inscribir un dispositivo en SEMM, se lee el archivo de configuración y la configuración especificada en el archivo se aplica a UEFI. Cuando ejecutas un paquete de configuración en un dispositivo que ya está inscrito en SEMM, la firma del archivo de configuración se comprueba con el certificado almacenado en el firmware del dispositivo. Si la firma no coincide, no se aplican cambios al dispositivo.

### Habilitar o deshabilitar dispositivos en la UEFI de Surface con SEMM

En la siguiente lista se muestran todos los dispositivos disponibles que puede administrar en SEMM:

* Puerto USB de acoplamiento
* Audio integrado
* DGPU
* Funda con teclado
* Tarjeta Micro SD
* Cámara frontal
* Cámara trasera
* Cámara infrarroja, para Windows Hello
* Bluetooth solo
* Wi-Fi y Bluetooth
*              LTE           

 >[!NOTE]
>Los dispositivos integrados que aparecen en la página Dispositivos UEFI pueden variar según el dispositivo o el entorno corporativo. Por ejemplo, la página Dispositivos UEFI no se admite en Surface Pro X; LTE solo aparece en dispositivos equipados con LTE. 
### Configurar opciones avanzadas con SEMM
**Tabla 1. Configuración avanzada**

| Configuración                            | Descripción                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 para el arranque PXE                  | Te permite administrar la compatibilidad con IPv6 para el arranque PXE. Si no configuras esta opción, la compatibilidad con IPv6 para el arranque PXE está deshabilitada.                                                                               |
| Arranque alternativo                     | Permite administrar el uso de un orden de arranque alternativo para arrancar directamente en un dispositivo USB o Ethernet presionando el botón Bajar volumen y el botón De encendido durante el arranque. Si no configuras esta opción, se habilita el arranque alternativo. |
| Bloqueo de orden de arranque                    | Permite bloquear el orden de arranque para evitar cambios. Si no configuras esta opción, el bloqueo de orden de arranque está deshabilitado.                                                                                                        |
| Arranque desde USB                           | Permite administrar el arranque en dispositivos USB. Si no configuras esta opción, el arranque USB está habilitado.                                                                                                                 |
| Pila de red                      | Permite administrar la configuración de arranque de la pila de red. Si no configuras esta opción, se deshabilita la capacidad de administrar la configuración de arranque de la pila de red.                                                                                                           |
| Encendido automático                      | Te permite administrar la configuración de arranque de Inicio automático. Si no configura esta opción, se habilitará la opción De encendido automático.                                                                                                        |
| Multiproceso simultáneo (SMT) | Permite administrar el multiproceso simultáneo (SMT) para habilitar o deshabilitar el hyperthreading. Si no configura esta opción, SMT está habilitado.                                                  |
|Habilitar límite de batería| Permite administrar la funcionalidad de límite de batería. Si no configuras esta opción, el límite de batería está habilitado |
| Seguridad                           | Muestra la página Seguridad de UEFI **de** Surface. Si no configura esta opción, se mostrará la página Seguridad.                                                                                                                 |
| Dispositivos                            | Muestra la página Dispositivos UEFI **de** Surface. Si no configura esta opción, se mostrará la página Dispositivos.                                                                                                                     |
| Arranque                               | Muestra la página de arranque de LA UEFI **de** Surface. Si no configuras esta opción, se muestra la página de arranque.                                                                                                                                                            |
| DateTime                           | Muestra la página Fecha y hora de la UEFI **de** Surface. Si no configura esta opción, se mostrará la página DateTime.                                                                                                                |
| EnableOSMigration                          | Te permite migrar Surface Hub 2 de Windows 10 Team a Windows 10 Pro o Enterprise. Si no configuras esta opción, los dispositivos Surface Hub 2 solo podrán ejecutar el sistema operativo Windows 10 Team.   Nota: El arranque dual entre Windows 10 Team y Windows 10 Pro/Enterprise no está disponible en Surface Hub 2.                                                                                                           |


>[!NOTE]
>Al crear un paquete de configuración de SEMM, se muestran dos caracteres en la página Correcto, como se muestra en la figura 3. ****

![Visualización de huella digital del certificado](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figura 3. Visualización de los dos últimos caracteres de la huella digital del certificado en la página Correcto*

Estos caracteres son los dos últimos caracteres de la huella digital del certificado y deben escribirse o grabarse. Los caracteres son necesarios para confirmar la inscripción en SEMM en un dispositivo Surface, como se muestra en la figura 4.

![Confirmación de inscripción en SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figura 4. Confirmación de inscripción en SEMM con la huella digital del certificado SEMM*

>[!NOTE]
>Los administradores con acceso al archivo de certificado (.pfx) pueden leer la huella digital en cualquier momento abriendo el archivo .pfx en CertMgr. Para ver la huella digital con CertMgr, siga este proceso:
>1. Haga clic con el botón secundario en el archivo .pfx y, a continuación, haga clic en **Abrir**.
>2. Expanda la carpeta en el panel de navegación.
>3. Haga clic en **Certificados**.
>4. Haga clic con el botón secundario en el certificado en el panel principal y, a continuación, haga clic en **Abrir**.
>5. Haga clic en **la pestaña** Detalles.
>6. **En** el **menú** desplegable Mostrar **** deben seleccionarse todos o Solo propiedades.
>7. Seleccione el campo **Huella digital**.

Para inscribir un dispositivo Surface en SEMM o para aplicar la configuración de UEFI desde un paquete de configuración, lo único que debes hacer es ejecutar el archivo .msi con privilegios administrativos en el dispositivo Surface previsto. Puedes usar la implementación de aplicaciones o las tecnologías de implementación del sistema operativo, como [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) o Microsoft Deployment [Toolkit.](https://technet.microsoft.com/windows/dn475741) Cuando inscribes un dispositivo en SEMM, debes estar físicamente presente para confirmar la inscripción en el dispositivo. La interacción del usuario no es necesaria cuando se aplica una configuración a los dispositivos que ya están inscritos en SEMM.

Para obtener un tutorial paso a paso sobre cómo inscribir un dispositivo Surface en SEMM o aplicar una configuración de UEFI de Surface con SEMM, consulta Inscribir y configurar dispositivos Surface con [SEMM.](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)

### Restablecer paquete

Un paquete de restablecimiento de UEFI de Surface se usa para realizar solo una tarea: para deshacer la inscripción de un dispositivo Surface de SEMM. El paquete de restablecimiento contiene instrucciones firmadas para quitar el certificado SEMM del firmware del dispositivo y restablecer la configuración de UEFI a la configuración predeterminada de fábrica. Al igual que un paquete de configuración de UEFI de Surface, un paquete de restablecimiento debe estar firmado con el mismo certificado SEMM que se aprovisiona en el dispositivo Surface. Al crear un paquete de restablecimiento de SEMM, debes proporcionar el número de serie del dispositivo Surface que quieres restablecer. Los paquetes de restablecimiento de SEMM no son universales y son específicos de un dispositivo.

### Solicitud de recuperación

En algunos escenarios, puede que sea imposible usar un paquete de restablecimiento de UEFI de Surface. (Por ejemplo, si Windows se vuelve inutilizable en el dispositivo Surface). En estos escenarios, puedes deshacer la inscripción del **** dispositivo Surface desde SEMM a través de la página Administración empresarial de LA UEFI de Surface (que se muestra en la figura 5) con una operación de solicitud de recuperación.

![Iniciar una solicitud de recuperación de SEMM](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figura 5. Iniciar una solicitud de recuperación de SEMM en la página Administración empresarial*

Cuando usas el proceso en la página **Administración** empresarial para restablecer SEMM en un dispositivo Surface, se te proporciona una solicitud de restablecimiento. Esta solicitud de restablecimiento se puede guardar como un archivo en una unidad USB, copiarse como texto o leerse como código QR con un dispositivo móvil para que se pueda enviar un mensaje o correo electrónico fácilmente. Usa la opción Restablecimiento del configurador de UEFI de Microsoft Surface para cargar un archivo de solicitud de restablecimiento o escribir el texto de la solicitud de restablecimiento o el código QR. El Configurador de UEFI de Microsoft Surface generará un código de verificación que se puede especificar en el dispositivo Surface. Si escribes el código en el dispositivo Surface y haz clic en **Reiniciar,** el dispositivo se dará de baja de SEMM. 

>[!NOTE]
>Una solicitud de restablecimiento expira dos horas después de su creación.

Para obtener un tutorial paso a paso sobre cómo deshacer la inscripción de dispositivos Surface de SEMM, consulta La inscripción de dispositivos [Surface desde SEMM.](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)

## Requisitos de certificado del Modo de administración de Surface Enterprise
El uso de SEMM con microsoft Surface UEFI Configurator requiere un certificado para comprobar la firma de los archivos de configuración antes de aplicar la configuración de UEFI. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo se pueden usar paquetes creados con el certificado aprobado para modificar la configuración de UEFI.

>[!NOTE]
>El certificado SEMM es necesario para realizar cualquier modificación en la configuración de SEMM o UEFI de Surface en dispositivos Surface inscritos. Si el certificado SEMM está dañado o perdido, NO se puede quitar ni restablecer. Administre el certificado SEMM en consecuencia con una solución adecuada para la copia de seguridad y recuperación.

Los paquetes creados con la herramienta Configurador de UEFI de Microsoft Surface se firman con un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo se pueden usar paquetes creados con el certificado aprobado para modificar la configuración de UEFI. 
### Configuración de certificado recomendada
Se recomienda la siguiente configuración para el certificado SEMM:

* **Algoritmo de clave:** RSA 
* **Longitud de la** clave: 2048
* **Algoritmo hash** : SHA-256
* **Tipo:** autenticación de servidor SSL
* **Uso de clave:** firma digital, cifrado de clave
* **Proveedor:** proveedor de cifrado RSA y AES mejorado de Microsoft
* **Fecha de expiración:** 15 meses desde la creación del certificado
* **Directiva de exportación de claves:** exportable

También se recomienda que el certificado SEMM se autentique en una arquitectura de infraestructura de clave pública (PKI) de dos niveles en la que la entidad de certificación (CA) intermedia esté dedicada a SEMM, lo que permite la revocación de certificados. Para obtener más información acerca de una configuración de PKI de dos niveles, vea Test [Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).

### Certificado autofirmado 
Puede usar el siguiente script de PowerShell de ejemplo para crear un certificado autofirmado para usarlo en escenarios de prueba de concepto.
Para usar este script, copie el siguiente texto en el Bloc de notas y guarde el archivo como un script de PowerShell (.ps1). 

> [!NOTE]
> Este script crea un certificado con una contraseña de `12345678` . El certificado generado por este script no se recomienda para entornos de producción.
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>Para su uso con SEMM y Microsoft Surface UEFI Configurator, el certificado debe exportarse con la clave privada y con protección con contraseña. El Configurador de UEFI de Microsoft Surface te pedirá que selecciones el archivo de certificado SEMM (.pfx) y la contraseña del certificado cuando sea necesario.

1.  Cree una carpeta en la unidad C: donde guardará el script; por ejemplo, C:\SEMM.
2.  Copie el script de ejemplo en el Bloc de notas o en un editor de texto equivalente y guarde el archivo como un script de PowerShell (.ps1).
3.  Inicia sesión en el equipo con credenciales de administrador y abre una sesión de PowerShell con privilegios elevados.
4.  Asegúrese de que los permisos están establecidos para permitir la ejecución de scripts. De forma predeterminada, los scripts no se pueden ejecutar a menos que modifique la directiva de ejecución. Para obtener más información, vea [Acerca de las directivas de ejecución.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)
5.  En el símbolo del sistema, escriba la ruta de acceso completa del script y, a continuación, presione ENTRAR. El script crea un certificado de demostración denominado TempOwner.pfx.

Como alternativa, puede crear su propio certificado autofirmado con PowerShell. Para obtener más información, vea la siguiente documentación de PowerShell: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).




>[!NOTE]
>Para las organizaciones que usan una raíz sin conexión en su infraestructura de PKI, el Configurador de UEFI de Microsoft Surface debe ejecutarse en un entorno conectado a la CA raíz para autenticar el certificado SEMM. Los paquetes generados por el Configurador de UEFI de Microsoft Surface se pueden transferir como archivos y, por lo tanto, se pueden transferir fuera del entorno de red sin conexión con almacenamiento extraíble, como un stick USB.

### Preguntas más frecuentes sobre la administración de certificados

La longitud *mínima recomendada* es de 15 meses. Puede usar un certificado que expire en menos de 15 meses o usar un certificado que expire en más de 15 meses.

>[!NOTE] 
>Cuando un certificado expira, no se renueva automáticamente. 


**¿Afectará un certificado expirado a la funcionalidad de los dispositivos inscritos en SEMM?**<br><br>
No, un certificado solo afecta a las tareas de administración de administración de TI en SEMM y no tiene ningún efecto en la funcionalidad del dispositivo cuando expira.


**¿Es necesario actualizar el paquete y el certificado de SEMM en todas las máquinas que lo tengan?**

Si desea que el restablecimiento o recuperación de SEMM funcione, el certificado debe ser válido y no expirado. 

**¿Se pueden crear paquetes de restablecimiento masivo para cada superficie que ordenemos? ¿Se puede crear una que restablezca todas las máquinas de nuestro entorno?**

Los ejemplos de PowerShell que crean un paquete de configuración para un tipo de dispositivo específico también se pueden usar para crear un paquete de restablecimiento independiente del número de serie. Si el certificado sigue siendo válido, puedes crear un paquete de restablecimiento con PowerShell para restablecer SEMM.

## Historial de versiones

### Versión 2.79.139.0

Esta versión de SEMM incluye:
- Compatibilidad con Surface Pro 7+
- Mejoras en la experiencia del usuario


### Versión 2.78.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop Go y Surface Pro X
- Notificaciones para la nueva versión
- Capacidad de crear paquetes personalizados para cambiar la propiedad
- Correcciones de errores

### Versión 2.73.136.0

Esta versión de SEMM incluye:

- El audio ahora se puede deshabilitar en Surface Hub2S con SEMM
- Compatibilidad con Surface Pro X para Dock 2
- Compatibilidad con el administrador de UEFI para operaciones relacionadas con Dock 2
- Corrección de errores del paquete de restablecimiento de Surface Go
- Compatibilidad con la migración de dispositivos Surface Hub 2 desde el sistema operativo Windows 10 Team a Windows 10 Pro o Enterprise.

### Versión 2.71.139.0

Esta versión de SEMM agrega compatibilidad con las características de administración de Surface Dock 2 para Surface Book 3, Surface Laptop 3 y Surface Pro 7, que incluyen:

- Habilitación de audio (bloqueo/desbloqueo), puertos Ethernet y USB
- Capacidad de crear paquetes de acoplamiento para hosts autenticados y no autenticados

### Versión 2.70.130.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Go 2
- Compatibilidad con Surface Book 3
- Correcciones de errores


### Versión 2.59.139.0

* Compatibilidad con modelos Surface Pro 7, Surface Pro X y Surface Laptop 3 de 13,5" y 15" con procesador Intel. Nota: No se admite el procesador AMD Surface Laptop 3 de 15".

- Compatibilidad con la característica Activar en energía

### Versión 2.54.139.0
* Compatibilidad con Surface Hub 2S
* Correcciones de errores

### Versión 2.43.136.0
* Compatibilidad para habilitar o deshabilitar multitráfico simulado 
* Opciones independientes para WiFi y Bluetooth para algunos dispositivos 
* Límite de batería quitado para Surface Studio 

### Versión 2.26.136.0
* Agregar compatibilidad a Surface Studio 2
* Característica límite de batería

### Versión 2.21.136.0
* Agregar compatibilidad a Surface Pro 6
* Agregar compatibilidad a Surface Laptop 2

### Versión 2.14.136.0
* Agregar compatibilidad a Surface Go

### Versión 2.9.136.0
* Agregar compatibilidad a Surface Book 2
* Agregar compatibilidad a Surface Pro LTE
* Mejoras de accesibilidad

### Versión 1.0.74.0
* Agregar compatibilidad a Surface Laptop
* Agregar compatibilidad a Surface Pro
* Correcciones de errores y mejora general

## Temas relacionados

- [Inscribir y configurar los dispositivos Surface con SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Anular la inscripción de dispositivos Surface desde SEMM](unenroll-surface-devices-from-semm.md)
- [Proteger puertos de Surface Dock 2 con SEMM](secure-surface-dock-ports-semm.md)

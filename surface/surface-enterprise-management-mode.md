---
title: Modo de administración de empresa de Surface (Surface)
description: Descubra cómo esta característica de Surface Devices con la Surface UEFI le ayuda a proteger y administrar la configuración del firmware dentro de su organización.
keywords: UEFI, configurar, firmware, seguro, SEMM
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
ms.date: 05/26/2020
ms.openlocfilehash: 116aeb6d1d92f387efa34319f7852febda729207
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835609"
---
# Modo de administración de Microsoft Surface Enterprise

El modo de administración de Microsoft Surface Enterprise (SEMM) es una característica de los dispositivos Surface con Surface UEFI que le permite proteger y administrar la configuración del firmware dentro de su organización. Con SEMM, los profesionales de TI pueden preparar configuraciones de configuración de UEFI e instalarlas en un dispositivo Surface. Además de la capacidad para configurar las opciones de UEFI, SEMM también usa un certificado para proteger la configuración de las alteraciones o desinstalación no autorizadas.

>[!NOTE]
>SEMM solo está disponible en dispositivos con firmware de Surface UEFI. Esto incluye la mayoría de los dispositivos de Surface, incluidos Surface Pro 7, Surface Pro X y Surface Laptop 3 SKU comerciales con un procesador Intel. SEMM no es compatible con el "Surface Laptop 3 SKU de 15" con procesador AMD (solo disponible como SKU comercial). 

Cuando los dispositivos de superficie están configurados por SEMM y protegidos con el certificado de SEMM, se consideran *inscritos* en SEMM. Cuando se quita el certificado de SEMM y se devuelve el control de la configuración de UEFI al usuario del dispositivo, se considera que el dispositivo de superficie no está *inscrito* en SEMM.

Existen dos opciones administrativas que puede usar para administrar SEMM e inscritos dispositivos Surface: una herramienta independiente o integración con Microsoft Endpoint Configuration Manager. La herramienta independiente SEMM, llamada configurador Microsoft Surface UEFI, se describe en este artículo. Para obtener más información sobre cómo administrar SEMM con Microsoft Endpoint Configuration Manager, consulte [usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).


## Configurador UEFI de Surface de Microsoft

El área de trabajo principal de SEMM es el configurador UEFI de Surface de Microsoft, tal como se muestra en la figura 1. El configurador UEFI de Microsoft Surface es una herramienta que se usa para crear paquetes de Windows Installer (. msi) o imágenes de WinPE que se usan para inscribir, configurar y anular la inscripción de SEMM en un dispositivo Surface. Estos paquetes contienen un archivo de configuración donde se especifica la configuración para UEFI. Los paquetes de SEMM también contienen un certificado que se instala y se almacena en el firmware y se usa para verificar la firma de los archivos de configuración antes de aplicar la configuración de UEFI.

>[!NOTE]
>Ahora puede usar el configurador Surface UEFI y SEMM para administrar puertos en Surface Dock 2. Para obtener más información, consulte [puertos de seguridad de Surface Dock 2 con SEMM](secure-surface-dock-ports-semm.md).

![Configurador UEFI de Surface de Microsoft](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figura 1. Configurador UEFI de Surface de Microsoft*


Puede usar la herramienta Microsoft Surface UEFI configurador en tres modos:

* [Paquete de configuración de Surface UEFI](#configuration-package). Use este modo para crear un paquete de configuración de Surface UEFI para inscribir un dispositivo Surface en SEMM y para configurar las opciones de UEFI en dispositivos inscritos.
* [Paquete de restablecimiento de Surface UEFI](#reset-package). Usa este modo para anular la inscripción de un dispositivo Surface desde SEMM.
* [Solicitud de recuperación de Surface UEFI](#recovery-request). Use este modo para responder a una solicitud de recuperación para anular la inscripción de un dispositivo Surface de SEMM en el que no se haya realizado correctamente una operación de restablecimiento de paquetes.


#### Descargar el configurador UEFI de Surface de Microsoft

Puede descargar Microsoft Surface UEFI configurador desde la página [Surface Tools para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft.

### Paquete de configuración

Los paquetes de configuración de Surface UEFI son el mecanismo principal para implementar y administrar SEMM en dispositivos Surface. Estos paquetes contienen un archivo de configuración de la configuración de UEFI especificada durante la creación del paquete en Microsoft Surface UEFI Configurator y un archivo de certificado, como se muestra en la ilustración 2. Cuando un paquete de configuración se ejecuta por primera vez en un dispositivo Surface que aún no se ha inscrito en SEMM, suministra el archivo de certificado en el firmware del dispositivo e incluye el dispositivo en SEMM. Al inscribir un dispositivo en SEMM, se le pedirá que confirme la operación proporcionando los últimos dos dígitos de la huella digital del certificado SEMM antes de que se almacene el archivo de certificado y se pueda completar la inscripción. Esta confirmación requiere que el usuario esté presente en el dispositivo en el momento de la inscripción para realizar la confirmación.

![Proteger un paquete de configuración de SEMM con un certificado](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figura 2. Proteger un paquete de configuración de SEMM con un certificado*

Para obtener más información sobre los requisitos del certificado SEMM, consulte la sección [requisitos de certificados del modo de administración](#surface-enterprise-management-mode-certificate-requirements) de la empresa.

>[!NOTE]
>También puede especificar una contraseña de UEFI con SEMM necesaria para ver la **seguridad**, los **dispositivos**, la **configuración de arranque**o las páginas de **Administración de empresa** de Surface UEFI.

Después de que un dispositivo se ha inscrito en SEMM, el archivo de configuración se lee y la configuración especificada en el archivo se aplica a UEFI. Al ejecutar un paquete de configuración en un dispositivo que ya se ha inscrito en SEMM, la firma del archivo de configuración se compara con el certificado almacenado en el firmware del dispositivo. Si la firma no coincide, no se aplican cambios al dispositivo.

### Habilitar o deshabilitar dispositivos en Surface UEFI con SEMM

En la siguiente lista se muestran todos los dispositivos disponibles que puede administrar en SEMM:

* Puerto USB de acoplamiento
* Audio incorporado
* DGPU
* Funda con teclado
* Tarjeta micro SD
* Cámara frontal
* Cámara trasera
* Cámara de infrarrojos para Windows Hello
* Solo Bluetooth
* Wi-Fi y Bluetooth
*              LTE           

 >[!NOTE]
>Los dispositivos integrados que aparecen en la página dispositivos UEFI pueden variar según el dispositivo o el entorno corporativo. Por ejemplo, la página de dispositivos UEFI no es compatible con Surface Pro X; LTE solo aparece en dispositivos con LTE. 
### Establecer la configuración avanzada con SEMM
**Tabla 1. Configuración avanzada**

| Configuración                            | Descripción                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 para el arranque PXE                  | Le permite administrar la compatibilidad de IPv6 con el arranque PXE. Si no establece esta configuración, la compatibilidad con IPv6 para el arranque PXE está deshabilitada.                                                                               |
| Arranque alternativo                     | Le permite administrar el uso de un orden de arranque alternativo para arrancar directamente en un dispositivo USB o Ethernet pulsando el botón de volumen y de encendido durante el arranque. Si no establece esta configuración, el arranque alternativo estará habilitado. |
| Bloqueo de orden de arranque                    | Le permite bloquear el orden de inicio para evitar cambios. Si no establece esta configuración, el bloqueo de orden de arranque se deshabilitará.                                                                                                        |
| Arranque desde USB                           | Le permite administrar el arranque en dispositivos USB. Si no establece esta configuración, el arranque USB estará habilitado.                                                                                                                 |
| Pila de red                      | Le permite administrar la configuración de inicio de pila de red. Si no establece esta configuración, la capacidad de administrar la configuración de inicio de pila de red está deshabilitada.                                                                                                           |
| Encendido automático                      | Le permite administrar la configuración de encendido automática. Si no establece esta configuración, encendido automático estará habilitado.                                                                                                        |
| Subprocesamiento múltiple simultáneo (SMT) | Le permite administrar el subprocesamiento múltiple (SMT) simultáneo para habilitar o deshabilitar el hyperthreading. Si no estableces esta configuración, el SMT está habilitado.                                                  |
|Habilitar límite de batería| Le permite administrar la funcionalidad de límite de batería. Si no establece esta configuración, el límite de batería estará habilitado. |
| Seguridad                           | Muestra la página de **seguridad** de superficie UEFI. Si no establece esta configuración, se mostrará la página seguridad.                                                                                                                 |
| Dispositivos                            | Muestra la página de **dispositivos** de Surface UEFI. Si no establece esta configuración, se mostrará la página dispositivos.                                                                                                                     |
| Arranque                               | Muestra la página de **Inicio** de Surface UEFI. Si no establece esta configuración, se mostrará la página de inicio.                                                                                                                                                            |
| DateTime                           | Muestra la superficie de la página **DateTime** de UEFI. Si no establece esta configuración, se mostrará la página DateTime.                                                                                                                |



>[!NOTE]
>Al crear un paquete de configuración de SEMM, se muestran dos caracteres en la página **correcta** , como se muestra en la ilustración 3.

![Visualización de huella digital de certificado](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figura 3. Visualización de los últimos dos caracteres de la huella digital del certificado en la página correcta*

Estos caracteres son los dos últimos caracteres de la huella digital del certificado y deben escribirse o grabarse. Los caracteres son necesarios para confirmar la inscripción en SEMM en un dispositivo Surface, como se muestra en la figura 4.

![Confirmación de inscripción en SEMM](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figura 4. Confirmación de inscripción en SEMM con la huella digital de certificado SEMM*

>[!NOTE]
>Los administradores con acceso al archivo de certificados (. pfx) pueden leer la huella digital en cualquier momento abriendo el archivo. pfx en CertMgr. Para ver la huella digital con CertMgr, siga este proceso:
>1. Haga clic con el botón secundario en el archivo. pfx y haga clic en **abrir**.
>2. Expanda la carpeta en el panel de navegación.
>3. Haga clic en **Certificados**.
>4. Haga clic con el botón derecho en el certificado en el panel principal y, a continuación, haga clic en **abrir**.
>5. Haga clic en la pestaña **detalles** .
>6. Solo se deben seleccionar **todas** **las propiedades** o en el menú desplegable **Mostrar** .
>7. Seleccione la **huella digital**del campo.

Para inscribir un dispositivo Surface en SEMM o para aplicar la configuración de UEFI desde un paquete de configuración, todo lo que tiene que hacer es ejecutar el archivo. msi con privilegios de administrador en el dispositivo Surface previsto. Puede usar las tecnologías de implementación de aplicaciones o de implementación de sistemas operativos, como [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) o [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741). Cuando inscriba un dispositivo en SEMM, debe estar presente para confirmar la inscripción en el dispositivo. La interacción del usuario no es necesaria cuando se aplica una configuración a dispositivos que ya se han inscrito en SEMM.

Para obtener un tutorial paso a paso sobre cómo inscribir un dispositivo Surface en SEMM o aplicar una configuración de Surface UEFI con SEMM, consulte [inscribir y configurar dispositivos Surface con SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).

### Restablecer el paquete

Un paquete de restablecimiento de Surface UEFI se usa para realizar una sola tarea, para anular la inscripción de un dispositivo Surface desde SEMM. El paquete de restablecimiento contiene instrucciones firmadas para quitar el certificado SEMM del firmware del dispositivo y restablecer la configuración de UEFI a los valores predeterminados de fábrica. Al igual que un paquete de configuración de Surface UEFI, un paquete de restablecimiento debe estar firmado con el mismo certificado SEMM que se aprovisiona en el dispositivo Surface. Al crear un paquete de restablecimiento de SEMM, es necesario que suministre el número de serie del dispositivo Surface que desea restablecer. Los paquetes de restablecimiento de SEMM no son universales y son específicos de un dispositivo.

### Solicitud de recuperación

En algunos escenarios, es posible que no se pueda usar un paquete de restablecimiento de Surface UEFI. (Por ejemplo, si Windows no se puede usar en el dispositivo Surface). En estos escenarios, puede anular la inscripción del dispositivo Surface de SEMM a través de la página de **Administración de empresa** de la superficie UEFI (que se muestra en la figura 5) con una operación de solicitud de recuperación.

![Iniciar una solicitud de recuperación de SEMM](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figura 5. Iniciar una solicitud de recuperación de SEMM en la página Administración de empresa*

Cuando se usa el proceso en la página de **Administración de empresa** para restablecer SEMM en un dispositivo Surface, se le proporciona una solicitud de restablecimiento. Esta solicitud de restablecimiento se puede guardar como un archivo en una unidad USB, copiarla como texto, o leer como un código QR con un dispositivo móvil para que sea fácilmente correo electrónico o mensaje. Use la opción solicitud de restablecimiento de solicitud de restablecimiento de Microsoft Surface UEFI para cargar un archivo de solicitud de restablecimiento o escriba el texto de la solicitud de restablecimiento o el código QR. El configurador Microsoft Surface UEFI generará un código de verificación que puede introducirse en el dispositivo Surface. Si introduces el código en el dispositivo Surface y haz clic en **reiniciar**, el dispositivo se anulará de la inscripción de semm. 

>[!NOTE]
>Una solicitud de restablecimiento vence dos horas después de su creación.

Para obtener un tutorial paso a paso sobre cómo anular la inscripción de dispositivos de Surface desde SEMM, consulte [anulación de la inscripción de dispositivos de Surface desde SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).

## Requisitos de certificados del modo de administración empresarial de Surface

>[!NOTE]
>El certificado SEMM es necesario para realizar cualquier modificación en la configuración de Surface UEFI SEMM o Surface en dispositivos Surface inscritos. Si el certificado SEMM está dañado o se ha perdido, SEMM no se puede quitar ni restablecer. Administre su certificado SEMM según corresponda a una solución adecuada para realizar copias de seguridad y recuperación.

Los paquetes creados con la herramienta de configurador Microsoft Surface UEFI están firmados con un certificado. Este certificado garantiza que después de que un dispositivo se haya inscrito en SEMM, solo se podrán usar los paquetes creados con el certificado aprobado para modificar la configuración de UEFI. Se recomienda la siguiente configuración para el certificado SEMM:

* **Algoritmo de clave** : RSA 
* **Longitud** de la clave: 2048
* **Algoritmo hash** : SHA-256
* **Tipo** : autenticación de servidor SSL
* **Uso** de la clave: firma digital, cifrado de clave
* **Proveedor** : proveedor criptográfico RSA y AES mejorado de Microsoft
* **Fecha de expiración** : 15 meses desde la creación de certificados
* **Política de exportación de claves** : exportable

También se recomienda autenticar el certificado de SEMM en una arquitectura de infraestructura de clave pública (PKI) de dos niveles, en la que la entidad de certificación (CA) intermedia se dedica a SEMM, lo que habilita la revocación de certificados. Para obtener más información acerca de una configuración de PKI de dos niveles, consulte [Guía del entorno de pruebas: implementación de una jerarquía de PKI de dos niveles de AD CS](https://technet.microsoft.com/library/hh831348).

>[!NOTE]
>Puede usar el siguiente script de PowerShell para crear un certificado autofirmado para usarlo en escenarios de prueba de concepto.
 > Para usar este script, copie el siguiente texto en el Bloc de notas y guarde el archivo como un script de PowerShell (. PS1). Este script crea un certificado con la contraseña `12345678` .<br/><br/>El certificado generado por este script no se recomienda para entornos de producción.
  
   ```
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

Para usar con SEMM y el configurador Microsoft Surface UEFI, el certificado debe exportarse con la clave privada y con protección con contraseña. El configurador Microsoft Surface UEFI le pedirá que seleccione el archivo de certificados SEMM (. pfx) y la contraseña del certificado cuando sea necesario.

>[!NOTE]
>Para las organizaciones que usan una raíz sin conexión en su infraestructura PKI, Microsoft Surface UEFI Configurator debe ejecutarse en un entorno conectado a la entidad emisora raíz para autenticar el certificado SEMM. Los paquetes generados por el configurador Microsoft Surface UEFI se pueden transferir como archivos y, por lo tanto, se pueden transferir fuera del entorno de red sin conexión con almacenamiento extraíble, como un stick USB.

### Preguntas frecuentes sobre la administración de certificados

La longitud *mínima* recomendada es de 15 meses. Puede usar un certificado que expira en menos de 15 meses o usar un certificado que vence en más de 15 meses.

>[!NOTE] 
>Cuando un certificado vence, no se renueva automáticamente. 

**¿Las máquinas existentes seguirán aplicando la configuración del BIOS después de 15 meses?**

Sí, pero solo si el paquete en sí se firmó cuando el certificado era válido.

**¿Será** **necesario actualizar el certificado y el paquete de SEMM en todas las máquinas que lo tengan?**

Si desea que el restablecimiento o la recuperación de SEMM funcionen, el certificado debe ser válido y no haber expirado. 

**¿Se pueden crear paquetes de restablecimiento en masa para cada superficie que pedimos? ¿Se puede crear una que reestablezca todas las máquinas de nuestro entorno?**

Los ejemplos de PowerShell que crean un paquete de configuración para un tipo de dispositivo específico también se pueden usar para crear un paquete de restablecimiento que sea independiente de los números de serie. Si el certificado sigue siendo válido, puede crear un paquete de restablecimiento con PowerShell para restablecer SEMM.

## Historial de versiones

### Versión 2.71.139.0

Esta versión de SEMM agrega compatibilidad para las características de administración de Surface Dock 2 para Surface Book 3, Surface Laptop 3 y Surface Pro 7, entre las que se incluyen:

- Activación de audio (bloqueo/desbloqueo), puertos Ethernet y USB
- Capacidad de crear paquetes acoplados para hosts autenticados y no autenticados

### Versión 2.70.130.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Go 2
- Compatibilidad con Surface Book 3
- Correcciones de errores


### Versión 2.59.139.0

* Compatibilidad con Surface Pro 7, Surface Pro X y Surface Laptop 3 13,5 "y 15" modelos con procesador Intel. Nota: la superficie del equipo portátil 3 15 "AMD no es compatible.

- Compatibilidad con la característica Wake on Power

### Versión 2.54.139.0
* Compatibilidad con Surface Hub 2S
* Correcciones de errores

### Versión 2.43.136.0
* Compatibilidad para habilitar o deshabilitar simulatenous multiamenazas 
* Separar las opciones de WiFi y Bluetooth para algunos dispositivos 
* Límite de batería quitado para Surface Studio 

### Versión 2.26.136.0
* Agregar compatibilidad a Surface Studio 2
* Característica de límite de batería

### Versión 2.21.136.0
* Agregar compatibilidad a Surface Pro 6
* Agregar compatibilidad a un portátil Surface 2

### Versión 2.14.136.0
* Agregar compatibilidad a Surface Go

### Versión 2.9.136.0
* Agregar compatibilidad a Surface Book 2
* Agregar compatibilidad al LTE de Surface Pro
* Mejoras de accesibilidad

### Versión 1.0.74.0
* Agregar compatibilidad a un portátil Surface
* Agregar compatibilidad a Surface Pro
* Corrección de errores y mejora general

## Temas relacionados

- [Inscribir y configurar los dispositivos Surface con SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Anular la inscripción de dispositivos Surface desde SEMM](unenroll-surface-devices-from-semm.md)
- [Puertos 2 puertos de acoplamiento de superficies seguras con SEMM](secure-surface-dock-ports-semm.md)

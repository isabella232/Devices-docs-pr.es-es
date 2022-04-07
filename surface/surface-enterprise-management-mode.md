---
title: Modo de administración de empresa de Surface (SEMM)
description: Consulta cómo esta característica de dispositivos Surface con Surface UEFI te ayuda a proteger y administrar la configuración de firmware dentro de tu organización.
keywords: uefi, configure, firmware, secure, semm
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
ms.date: 12/08/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 9e08b3dd804b8b4ac6e2ee4dd4041ed2e684d5d7
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472649"
---
# <a name="microsoft-surface-enterprise-management-mode-semm"></a>Modo de administración de Microsoft Surface Enterprise (SEMM)

El modo de administración de Microsoft Surface Enterprise (SEMM) es una característica de los dispositivos Surface con surface unified extensible firmware interface (UEFI). Puede usar SEMM para:

- Proteja y administre la configuración de firmware en su organización.
- Prepare las configuraciones de configuración de UEFI e instálelas en un dispositivo Surface.

SEMM también usa un certificado para proteger la configuración frente a alteraciones o eliminaciones no autorizadas. Para migrar un Surface Hub 2S a Windows 10 Pro o Windows Enterprise, se requiere SEMM.

## <a name="supported-devices"></a>Dispositivos compatibles

SEMM solo está disponible en dispositivos con firmware UEFI de Surface, entre los que se incluyen: 

- Surface Pro 8 (solo SKU comerciales)
- Surface Pro 4 y versiones posteriores (todas las SKU)
- Surface Pro X (todas las SKU)
- Surface Laptop SE (todas las SKU)
- Surface Laptop Studio (solo SKU comerciales) 
- Surface Hub 2S
- Surface Laptop 4 (solo SKU comerciales)
- Surface Laptop 3 (solo procesadores Intel)
- Surface Laptop Go 
- Surface Book (todas las generaciones)
- Surface Go, Surface Go 2
- Surface Go 3 (solo SKU comerciales)
- Surface Studio 

>[!TIP]
> Las SKU comerciales (también conocidas como Surface para empresas) ejecutan Windows 10 Pro/Enterprise o Windows 11 Pro/Enterprise; las SKU de consumidor ejecutan Windows 10/Windows 11 Home. Para más información, consulte [Visualización de la información del sistema](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 


## <a name="getting-started"></a>Introducción 

Cuando los dispositivos Surface están configurados por SEMM y protegidos con el certificado SEMM, se consideran *inscritos* en SEMM. Cuando se quita el certificado SEMM y se devuelve el control de la configuración de UEFI al usuario del dispositivo, el dispositivo Surface se considera *no inscrito* en SEMM.

Hay dos opciones administrativas que puedes usar para administrar SEMM e inscribir dispositivos Surface:

- En este artículo se describe la herramienta independiente SEMM, Microsoft Surface UEFI Configurator.

- Integración con Microsoft Endpoint Configuration Manager. Para obtener información, consulte [Uso de Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM](use-system-center-configuration-manager-to-manage-devices-with-semm.md).

## <a name="microsoft-surface-uefi-configurator"></a>Configurador de UEFI de Microsoft Surface

El área de trabajo principal de SEMM es Microsoft Surface UEFI Configurator, como se muestra en la figura 1.

Puede usar Microsoft Surface UEFI Configurator para:

- Cree paquetes del instalador de Windows (.msi).
- Usa imágenes de WinPE para inscribir, configurar y anular la inscripción de SEMM en un dispositivo Surface.

Estos paquetes contienen un archivo de configuración que especifica la configuración de UEFI. Los paquetes SEMM también contienen un certificado que está instalado y almacenado en firmware y se usa para comprobar la firma de los archivos de configuración antes de aplicar la configuración de UEFI.

>[!TIP]
>Ahora puedes usar Surface UEFI Configurator y SEMM para administrar puertos en Surface Dock 2. Para obtener más información, consulta [Protección de puertos de Surface Dock 2 con SEMM](secure-surface-dock-ports-semm.md).

![Configurador UEFI de Microsoft Surface.](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figura 1. Configurador de UEFI de Microsoft Surface*

Puedes usar la herramienta Microsoft Surface UEFI Configurator en tres modos:

- [Paquete de configuración de UEFI de Surface](#configuration-package). Usa este modo para crear un paquete de configuración de UEFI de Surface para inscribir un dispositivo Surface en SEMM y configurar la configuración de UEFI en dispositivos inscritos.
- [Paquete de restablecimiento de UEFI de Surface](#reset-package). Usa este modo para anular la inscripción de un dispositivo Surface desde SEMM.
- [Solicitud de recuperación de SURFACE UEFI](#recovery-request). Usa este modo para responder a una solicitud de recuperación para anular la inscripción de un dispositivo Surface desde SEMM donde una operación restablecer paquete no se realiza correctamente.

### <a name="download-microsoft-surface-uefi-configurator"></a>Descarga de Microsoft Surface UEFI Configurator

Puedes descargar Microsoft Surface UEFI Configurator desde la página [Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) del Centro de descarga de Microsoft.

- Para dispositivos Intel/AMD, descargue: **SurfaceUEFI_Configurator_v2.94.139.0_x64.msi**
- Para dispositivos ARM, descargue: **SurfaceUEFI_Configurator_v2.94.139.0_x86.msi.**

### <a name="configuration-package"></a>Paquete de configuración

Los paquetes de configuración de UEFI de Surface son el mecanismo principal para implementar y administrar SEMM en dispositivos Surface. Estos paquetes contienen un archivo de configuración y un archivo de certificado, como se muestra en la figura 2. El archivo de configuración contiene la configuración de UEFI que se especifica cuando se crea el paquete en Microsoft Surface UEFI Configurator. Cuando un paquete de configuración se ejecuta por primera vez en un dispositivo Surface que aún no está inscrito en SEMM, aprovisiona el archivo de certificado en el firmware del dispositivo e inscribe el dispositivo en SEMM. Al inscribir un dispositivo en SEMM, y antes de que se almacene el certificado y finalice la inscripción, se le pedirá que confirme la operación proporcionando los dos últimos dígitos de la huella digital del certificado SEMM. Esta confirmación requiere que un usuario esté físicamente presente en el dispositivo durante la inscripción para realizar la confirmación.

![Proteja un paquete de configuración SEMM con un certificado.](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figura 2. Protección de un paquete de configuración SEMM con un certificado*

Para obtener más información sobre los requisitos del certificado SEMM, consulte la sección [Requisitos de certificados del modo de administración de Surface Enterprise](#surface-enterprise-management-mode-certificate-requirements) más adelante en este artículo.

>[!TIP]
>Tiene la opción de requerir una contraseña UEFI con SEMM. Si lo hace, la contraseña es necesaria para ver las páginas **Seguridad**, **Dispositivos**, **Configuración de arranque** y **Administración de Enterprise** de Surface UEFI.

Después de inscribir un dispositivo en SEMM, se lee el archivo de configuración y la configuración especificada en el archivo se aplica a UEFI. Al ejecutar un paquete de configuración en un dispositivo que ya está inscrito en SEMM, la firma del archivo de configuración se comprueba con el certificado almacenado en el firmware del dispositivo. Si la firma no coincide, no se aplica ningún cambio al dispositivo.

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>Habilitación o deshabilitación de dispositivos en Surface UEFI con SEMM

En la lista siguiente se muestran todos los dispositivos disponibles que puede administrar en SEMM:

- Acoplamiento del puerto USB
- Audio integrado
- Unidad de procesamiento de gráficos digitales
- Cubierta de tipo
- Tarjeta Micro SD
- Cámara frontal
- Cámara trasera
- Cámara infrarroja (para Windows Hello)
- solo Bluetooth
- Red inalámbrica y Bluetooth
- Evolución a largo plazo (LTE)

 >[!NOTE]
>En la página Dispositivos UEFI, los dispositivos integrados pueden variar, en función del dispositivo o del entorno corporativo. Por ejemplo, la página Dispositivos UEFI no se admite en Surface Pro X; LTE solo aparece en dispositivos equipados con LTE.

### <a name="configure-advanced-settings-with-semm"></a>Configuración de opciones avanzadas con SEMM

**Tabla 1. Configuración avanzada**

| Ajuste                            | Descripción                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 para el arranque PXE                  | Permite administrar la compatibilidad con IPv6 para el arranque PXE. Si no configura esta opción, la compatibilidad con IPv6 para el arranque PXE está deshabilitada.                                                                               |
| Arranque alternativo                     | Le permite administrar el uso de un orden de arranque alternativo para arrancar directamente en un dispositivo USB o Ethernet presionando el botón de bajar volumen y el botón de encendido durante el arranque. Si no configura esta configuración, el arranque alternativo está habilitado. |
| Bloqueo de orden de arranque                    | Permite bloquear el orden de arranque para evitar cambios. Si no configura esta opción, el bloqueo del pedido de arranque está deshabilitado.                                                                                                        |
| Arranque desde USB                           | Permite administrar el arranque en dispositivos USB. Si no configura esta opción, arranque USB está habilitado.                                                                                                                 |
| Pila de red                      | Permite administrar la configuración de arranque de Network Stack. Si no configura esta configuración, se deshabilita la capacidad de administrar la configuración de arranque de Network Stack.                                                                                                           |
| Encendido automático                      | Permite administrar la configuración de arranque automático de Power On. Si no configura esta opción, se habilita El encendido automático.                                                                                                        |
| Multiproceso simultáneo (SMT) | Permite administrar el multiproceso simultáneo (SMT) para habilitar o deshabilitar el hiperthreading. Si no configura esta configuración, SMT está habilitado.                                                  |
|Habilitar límite de batería| Permite administrar la funcionalidad de límite de batería. Si no configura esta opción, el límite de batería está habilitado. |
| Seguridad                           | Muestra la página Seguridad de UEFI **de** Surface. Si no configura esta opción, se muestra la página Seguridad.                                                                                                                 |
| Dispositivos                            | Muestra la página Dispositivos UEFI **de** Surface. Si no configura esta opción, se muestra la página Dispositivos.                                                                                                                     |
| Arranque                               | Muestra la página **De arranque** ueFI de Surface. Si no configura esta opción, se mostrará la página De arranque.                                                                                                                                                            |
| DateTime                           | Muestra la página Surface UEFI **DateTime** . Si no configura esta opción, se muestra la página DateTime.                                                                                                                |
| EnableOSMigration                          | Permite migrar Surface Hub 2 de Windows 10 Team a Windows 10/11 Pro o Enterprise. Si no configura esta configuración, Surface Hub 2 dispositivos solo pueden ejecutar el sistema operativo Windows 10 Team. Nota: El arranque dual entre Windows 10 Team y Windows 10/11 Pro/Enterprise no está disponible en Surface Hub 2.                                                                                                           |

>[!TIP]
>Al crear un paquete de configuración SEMM, se muestran dos caracteres en la página **Correcto** , como se muestra en la figura 3.

![Pantalla de huella digital del certificado.](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figura 3. Presentación de los dos últimos caracteres de la huella digital del certificado en la página Correcto*

Estos caracteres son los dos últimos caracteres de la huella digital del certificado y deben escribirse o grabarse. Los caracteres son necesarios para confirmar la inscripción en SEMM en un dispositivo Surface, como se muestra en la figura 4.

![Confirmación de inscripción en SEMM.](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figura 4. Confirmación de inscripción en SEMM con la huella digital del certificado SEMM*

>[!TIP]
>Los administradores con acceso al archivo de certificado (.pfx) pueden leer la huella digital en cualquier momento abriendo el archivo .pfx en CertMgr. Para ver la huella digital con CertMgr:
>
>1. Seleccione y mantenga presionado (o haga clic con el botón derecho) el archivo .pfx y, a continuación, seleccione **Abrir**.
>2. En el panel de navegación, expanda la carpeta .
>3. Seleccione **Certificados**.
>4. En el panel principal, seleccione y mantenga presionado (o haga clic con el botón derecho) el certificado y, a continuación, seleccione **Abrir**.
>5. Seleccione la pestaña **Detalles** .
>6. En el menú desplegable **Mostrar****,** solo todas o **propiedades** deben seleccionarse.
>7. Seleccione el campo **Huella digital** .

Para inscribir un dispositivo Surface en SEMM o aplicar la configuración de UEFI desde un paquete de configuración, ejecute el archivo .msi con privilegios administrativos en el dispositivo Surface previsto. Puede usar tecnologías de implementación de aplicaciones o de implementación del sistema operativo, como [Microsoft Endpoint Configuration Manager](/mem/configmgr) o la [Toolkit de implementación de Microsoft](/mem/configmgr/mdt). Al inscribir un dispositivo en SEMM, debe estar físicamente presente para confirmar la inscripción en el dispositivo. Cuando se aplica una configuración a dispositivos que ya están inscritos en SEMM, no se requiere la interacción del usuario.

Para ver un tutorial paso a paso sobre cómo inscribir un dispositivo Surface en SEMM o aplicar una configuración de UEFI de Surface con SEMM, consulta [Inscribir y configurar dispositivos Surface con SEMM](enroll-and-configure-surface-devices-with-semm.md).

### <a name="reset-package"></a>Restablecer paquete

Un paquete de restablecimiento de UEFI de Surface se usa para realizar solo una tarea, para anular la inscripción de un dispositivo Surface desde SEMM. El paquete de restablecimiento contiene instrucciones firmadas para quitar el certificado SEMM del firmware del dispositivo y restablecer la configuración de UEFI a la configuración predeterminada de fábrica. Al igual que un paquete de configuración de UEFI de Surface, se debe firmar un paquete de restablecimiento con el mismo certificado SEMM aprovisionado en el dispositivo Surface. Cuando creas un paquete de restablecimiento de SEMM, debes proporcionar el número de serie del dispositivo Surface que quieres restablecer. Los paquetes de restablecimiento de SEMM no son universales, son específicos de un dispositivo.

### <a name="recovery-request"></a>Solicitud de recuperación

En algunos escenarios, podría ser imposible usar un paquete de restablecimiento de UEFI de Surface. (Por ejemplo, si Windows se vuelve inutilizable en el dispositivo Surface). En estos escenarios, puedes anular la inscripción del dispositivo Surface desde SEMM a través de la página **administración de Enterprise** de Surface UEFI (que se muestra en la figura 5) con una operación de solicitud de recuperación.

> [!div class="mx-imgBorder"]
> ![Inicie una solicitud de recuperación de SEMM.](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figura 5. Iniciar una solicitud de recuperación de SEMM en la página administración de Enterprise*

Cuando usas el proceso en la página **Administración de Enterprise** para restablecer SEMM en un dispositivo Surface, se te da una solicitud de restablecimiento. Esta solicitud de restablecimiento se puede guardar como un archivo en una unidad USB, copiarse como texto o leerse como un código QR con un dispositivo móvil para que se envíe fácilmente por correo electrónico o se le envíe un mensaje. Usa la opción Solicitud de restablecimiento del configurador UEFI de Microsoft Surface para cargar un archivo de solicitud de restablecimiento o para escribir el texto de la solicitud de restablecimiento o el código QR. Microsoft Surface UEFI Configurator genera un código de verificación que se puede escribir en el dispositivo Surface. Si escribes el código en el dispositivo Surface y **seleccionas Reiniciar**, el dispositivo no se inscribirá en SEMM.

>[!NOTE]
>Una solicitud de restablecimiento expira dos horas después de su creación.

Para ver un tutorial paso a paso sobre cómo anular la inscripción de dispositivos Surface desde SEMM, consulta [Anular la inscripción de dispositivos Surface desde SEMM](unenroll-surface-devices-from-semm.md).

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Requisitos de certificado del modo de administración de Surface Enterprise

Cuando se usa SEMM con Microsoft Surface UEFI Configurator y se quiere aplicar la configuración de UEFI, se requiere un certificado para comprobar la firma de los archivos de configuración. Este certificado garantiza que, una vez que un dispositivo se inscribe en SEMM, solo se pueden usar los paquetes creados con el certificado aprobado para modificar la configuración de UEFI.

>[!NOTE]
>Para realizar cualquier modificación en la configuración de SEMM o Surface UEFI en dispositivos Surface inscritos, se requiere el certificado SEMM. Si el certificado SEMM está dañado o perdido, no se puede quitar o restablecer SEMM. Administre el certificado SEMM en consecuencia con una solución adecuada para la copia de seguridad y recuperación.

Los paquetes creados con la herramienta Microsoft Surface UEFI Configurator están firmados con un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo se pueden usar paquetes creados con el certificado aprobado para modificar la configuración de UEFI.

### <a name="recommended-certificate-settings"></a>Configuración de certificado recomendada

Se recomienda la siguiente configuración para el certificado SEMM:

- **Algoritmo de clave** : RSA
- **Longitud de clave** : 2048
- **Algoritmo hash** : SHA-256
- **Tipo** : autenticación de servidor SSL
- **Uso de claves** : firma digital, cifrado de claves
- **Proveedor** : proveedor criptográfico RSA mejorado de Microsoft y AES
- **Fecha de expiración** : 15 meses a partir de la creación del certificado
- **Directiva de exportación de claves** : exportable

También se recomienda autenticar el certificado SEMM en una arquitectura de infraestructura de clave pública (PKI) de dos niveles donde la entidad de certificación intermedia (CA) esté dedicada a SEMM, lo que permite la revocación de certificados. Para obtener más información sobre una configuración de PKI de dos niveles, consulte [Guía del laboratorio de pruebas: Implementación de una jerarquía de PKI de AD CS Two-Tier](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11)).

### <a name="self-signed-certificate"></a>Certificado autofirmado

Puede usar el siguiente script de PowerShell de ejemplo para crear un certificado autofirmado para usarlo en escenarios de prueba de concepto.
Para usar este script, copie el texto siguiente en Bloc de notas y, a continuación, guarde el archivo como script de PowerShell (.ps1).

> [!NOTE]
> Este script crea un certificado con una contraseña de `12345678`. El certificado generado por este script no se recomienda para entornos de producción.
  
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
>Para su uso con SEMM y Microsoft Surface UEFI Configurator, el certificado debe exportarse con la clave privada y con la protección con contraseña. Microsoft Surface UEFI Configurator le pide que seleccione el archivo de certificado SEMM (.pfx) y la contraseña del certificado.

Para crear un certificado autofirmado:

1. En la unidad C:, cree la carpeta donde guardará el script; por ejemplo, C:\SEMM.
2. Copie el script de ejemplo en Bloc de notas (o editor de texto equivalente) y, a continuación, guarde el archivo como script de PowerShell (.ps1).
3. Inicie sesión en el equipo con credenciales de administrador y abra una sesión de PowerShell con privilegios elevados.
4. Asegúrese de que los permisos están establecidos para permitir la ejecución de scripts. De forma predeterminada, los scripts no se pueden ejecutar a menos que modifique la directiva de ejecución. Para más información, consulte [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5. En el símbolo del sistema, escriba la ruta de acceso completa del script y presione **Entrar**. El script crea un certificado de demostración denominado TempOwner.pfx.

Como alternativa, puede crear su propio certificado autofirmado mediante PowerShell. Para obtener más información, consulte [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate).

>[!NOTE]
>Para las organizaciones que usan una raíz sin conexión en su infraestructura PKI, Microsoft Surface UEFI Configurator debe ejecutarse en un entorno conectado a la CA raíz para autenticar el certificado SEMM. Los paquetes generados por Microsoft Surface UEFI Configurator se pueden transferir como archivos, por lo que se pueden transferir fuera del entorno de red sin conexión con almacenamiento extraíble, como un stick USB.

### <a name="managing-certificates-faq"></a>Preguntas más frecuentes sobre la administración de certificados

La longitud *mínima* recomendada es de 15 meses. Puede usar un certificado que expire en menos de 15 meses o usar un certificado que expire en más de 15 meses.

>[!NOTE]
>Cuando un certificado expira, no se renueva automáticamente.

**¿Afectará un certificado expirado a la funcionalidad de los dispositivos inscritos en SEMM?**<br><br>
No, un certificado solo afecta a las tareas de administración de administración de TI en SEMM y no tiene ningún efecto en la funcionalidad del dispositivo cuando expira.

**¿Será necesario actualizar el paquete y el certificado SEMM en todas las máquinas que lo tengan?**<br><br>
Si desea que el restablecimiento o la recuperación de SEMM funcionen, el certificado debe ser válido y no expirado.

**¿Se pueden crear paquetes de restablecimiento masivo para cada superficie que pidamos? ¿Se puede crear uno que restablezca todas las máquinas de nuestro entorno?**<br><br>
Los ejemplos de PowerShell que crean un paquete de configuración para un tipo de dispositivo específico también se pueden usar para crear un paquete de restablecimiento independiente del número de serie. Si el certificado sigue siendo válido, puede crear un paquete de restablecimiento mediante PowerShell para restablecer SEMM.

## <a name="version-history"></a>Historial de versiones

### <a name="version-2941390"></a>Versión 2.94.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop Studio, Surface Pro 8 y Surface Go 3

### <a name="version-2831390"></a>Versión 2.83.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop 4
- Compatibilidad con la opción multithreading simultánea para Surface Pro 7
- Eliminación de la configuración de SEMM obsoleta  
- Se ha mejorado la firma de MSI

### <a name="version-2791390"></a>Versión 2.79.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Pro 7+.
- Mejoras en la experiencia del usuario.

### <a name="version-2781390"></a>Versión 2.78.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop Go y Surface Pro X.
- Notificaciones para nuevas versiones.
- La capacidad de crear paquetes personalizados para cambiar la propiedad.
- Correcciones.

### <a name="version-2731360"></a>Versión 2.73.136.0

Esta versión de SEMM incluye:

- La capacidad de deshabilitar el audio en Surface Hub2S mediante SEMM.
- Compatibilidad con Surface Pro X para Dock 2.
- Compatibilidad con UEFI Manager para operaciones relacionadas con Dock 2.
- Corrección de errores del paquete de restablecimiento de Surface Go.
- Compatibilidad con la migración de Surface Hub 2 dispositivos desde Windows 10 Team sistema operativo a Windows 10 Pro o Enterprise.

### <a name="version-2711390"></a>Versión 2.71.139.0

Esta versión de SEMM agrega compatibilidad con las características de administración de Surface Dock 2 para Surface Book 3, Surface Laptop 3 y Surface Pro 7. Incluye:

- La capacidad de habilitar el audio (bloqueo/desbloqueo) y los puertos Ethernet y USB.
- La capacidad de crear paquetes de acoplamiento para hosts autenticados y no autenticados.

### <a name="version-2701300"></a>Versión 2.70.130.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Go 2.
- Compatibilidad con Surface Book 3.
- Correcciones.

### <a name="version-2591390"></a>Versión 2.59.139.0

Esta versión de SEMM incluye:

- Compatibilidad con modelos de Surface Pro 7, Surface Pro X y Surface Laptop modelos de 3 13,5" y 15" con procesador Intel.
    >[!NOTE]
    >Surface Laptop no se admite el procesador AMD de 3 15".
- Compatibilidad con la característica Wake on Power.

### <a name="version-2541390"></a>Versión 2.54.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Hub 2S.
- Correcciones.

### <a name="version-2431360"></a>Versión 2.43.136.0

Esta versión de SEMM incluye:

- Compatibilidad para habilitar o deshabilitar el multithreading simultáneo.
- Opciones independientes para redes inalámbricas y Bluetooth para algunos dispositivos.
- Límite de batería eliminado para Surface Studio.

### <a name="version-2261360"></a>Versión 2.26.136.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Studio 2.
- Característica límite de batería.

### <a name="version-2211360"></a>Versión 2.21.136.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Pro 6.
- Compatibilidad con Surface Laptop 2.

### <a name="version-2141360"></a>Versión 2.14.136.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Go.

### <a name="version-291360"></a>Versión 2.9.136.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Book 2.
- Compatibilidad con Surface Pro LTE.
- Mejoras de accesibilidad.

### <a name="version-10740"></a>Versión 1.0.74.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop.
- Compatibilidad con Surface Pro.
- Correcciones de errores y mejoras generales.

## <a name="related-topics"></a>Temas relacionados

- [Inscribir y configurar los dispositivos Surface con SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Anular la inscripción de dispositivos Surface desde SEMM](unenroll-surface-devices-from-semm.md)
- [Proteger puertos de Surface Dock 2 con SEMM](secure-surface-dock-ports-semm.md)

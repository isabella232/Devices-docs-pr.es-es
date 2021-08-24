---
title: Surface Enterprise Management Mode (Surface)
description: Consulta cómo esta característica de dispositivos Surface con UEFI de Surface te ayuda a proteger y administrar la configuración de firmware en tu organización.
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
ms.date: 04/16/2021
ms.openlocfilehash: 8e30234e72b6533da3d36ca38188c7e199beeeac
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910995"
---
# <a name="microsoft-surface-enterprise-management-mode"></a>Modo de administración Enterprise Microsoft Surface

Microsoft Surface Enterprise Management Mode (SEMM) es una característica de dispositivos Surface con La interfaz de firmware extensible unificada (UEFI) de Surface. Puede usar SEMM para:

- Proteja y administre la configuración de firmware en su organización.
- Preparar configuraciones de configuración de UEFI e instalarlas en un dispositivo Surface.

SEMM también usa un certificado para proteger la configuración de manipulaciones o eliminaciones no autorizadas. Para migrar un Surface Hub 2S a Windows 10 Pro o Windows Enterprise, se requiere SEMM.

>[!NOTE]
>SEMM solo está disponible en dispositivos con firmware uefi de Surface. Esto incluye la mayoría de los otros dispositivos Surface, incluidos Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 SKU comerciales con procesador Intel, Surface Laptop 4 SKU comerciales con procesador AMD, Surface Laptop 3 SKU comerciales con un procesador Intel y Surface Laptop Go. SEMM no se admite en la SKU de 15" Surface Laptop 3 con procesador AMD (disponible solo como SKU comercial).

Cuando los dispositivos Surface están configurados por SEMM y protegidos con el certificado SEMM, se consideran *inscritos* en SEMM. Cuando se quita el certificado SEMM y se devuelve el control de la configuración de UEFI al usuario del dispositivo, el dispositivo Surface se considera no inscrito *en* SEMM.

Hay dos opciones administrativas que puedes usar para administrar SEMM e inscribir dispositivos Surface:

- La herramienta independiente SEMM, Microsoft Surface UEFI Configurator, se describe en este artículo.

- Integración con Microsoft Endpoint Configuration Manager. Para obtener información, [vea Usar Microsoft Endpoint Configuration Manager para administrar dispositivos con SEMM](use-system-center-configuration-manager-to-manage-devices-with-semm.md).

> [!NOTE]
> SEMM solo se admite Surface Pro X a través del Administrador de UEFI. Puedes descargar uefi manager de [Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703). Para obtener más información, consulte [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).

## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI Configurator

El área de trabajo principal de SEMM es Microsoft Surface UEFI Configurator, como se muestra en la figura 1.

Puedes usar Microsoft Surface UEFI Configurator para:

- Cree Windows installer (.msi).
- Usa imágenes de WinPE para inscribir, configurar y desenrollar SEMM en un dispositivo Surface.

Estos paquetes contienen un archivo de configuración que especifica la configuración de UEFI. Los paquetes SEMM también contienen un certificado que está instalado y almacenado en el firmware y se usa para comprobar la firma de los archivos de configuración antes de aplicar la configuración de UEFI.

>[!TIP]
>Ahora puedes usar Surface UEFI Configurator y SEMM para administrar puertos en Surface Dock 2. Para obtener más información, [consulta Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).

![Configurador UEFI de Microsoft Surface.](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*Figura 1. Microsoft Surface UEFI Configurator*

Puedes usar la herramienta Configurador UEFI de Microsoft Surface en tres modos:

- [Paquete de configuración de UEFI de Surface](#configuration-package). Usa este modo para crear un paquete de configuración de UEFI de Surface para inscribir un dispositivo Surface en SEMM y para configurar la configuración de UEFI en dispositivos inscritos.
- [Paquete de restablecimiento de UEFI de Surface](#reset-package). Usa este modo para desenrollar un dispositivo Surface desde SEMM.
- [Solicitud de recuperación de UEFI de Surface](#recovery-request). Usa este modo para responder a una solicitud de recuperación para desenrollar un dispositivo Surface desde SEMM donde una operación restablecer paquete no se realiza correctamente.

### <a name="download-microsoft-surface-uefi-configurator"></a>Descargar Microsoft Surface UEFI Configurator

Puedes descargar Microsoft Surface UEFI Configurator desde la página [Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) en el Centro de descarga de Microsoft.

### <a name="configuration-package"></a>Paquete de configuración

Los paquetes de configuración de UEFI de Surface son el mecanismo principal para implementar y administrar SEMM en dispositivos Surface. Estos paquetes contienen un archivo de configuración y un archivo de certificado, como se muestra en la figura 2. El archivo de configuración contiene las opciones de UEFI que se especifican cuando se crea el paquete en Microsoft Surface UEFI Configurator. Cuando un paquete de configuración se ejecuta por primera vez en un dispositivo Surface que aún no está inscrito en SEMM, aprovisiona el archivo de certificado en el firmware del dispositivo e inscribe el dispositivo en SEMM. Al inscribir un dispositivo en SEMM, y antes de almacenar el certificado y finalizar la inscripción, se te pedirá que confirmes la operación proporcionando los dos últimos dígitos de la huella digital del certificado SEMM. Esta confirmación requiere que un usuario esté físicamente presente en el dispositivo durante la inscripción para realizar la confirmación.

![Proteger un paquete de configuración de SEMM con un certificado.](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*Figura 2. Proteger un paquete de configuración de SEMM con un certificado*

Para obtener más información acerca de los requisitos para el certificado SEMM, consulta la sección Requisitos del certificado del modo de administración de [Surface Enterprise](#surface-enterprise-management-mode-certificate-requirements) más adelante en este artículo.

>[!TIP]
>Tiene la opción de requerir una contraseña UEFI con SEMM. Si lo haces, la contraseña es necesaria para ver las páginas **Seguridad,** **Dispositivos,** **** Configuración de arranque y Enterprise **administración** de Surface UEFI.

Después de inscribir un dispositivo en SEMM, se lee el archivo de configuración y la configuración especificada en el archivo se aplica a UEFI. Cuando ejecutas un paquete de configuración en un dispositivo que ya está inscrito en SEMM, la firma del archivo de configuración se comprueba con el certificado almacenado en el firmware del dispositivo. Si la firma no coincide, no se aplican cambios al dispositivo.

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>Habilitar o deshabilitar dispositivos en Surface UEFI con SEMM

En la siguiente lista se muestran todos los dispositivos disponibles que puede administrar en SEMM:

- Puerto USB de acoplamiento
- Audio integrado
- Unidad de procesamiento de gráficos digitales
- Portada de tipo
- Tarjeta Micro SD
- Cámara frontal
- Cámara trasera
- Cámara de infrarrojos (para Windows Hello)
- Bluetooth solo
- Red inalámbrica y Bluetooth
- Evolución a largo plazo (LTE)

 >[!NOTE]
>En la página Dispositivos UEFI, los dispositivos integrados pueden variar según el dispositivo o el entorno corporativo. Por ejemplo, la página Dispositivos UEFI no se admite en Surface Pro X; LTE solo aparece en dispositivos equipados con LTE.

### <a name="configure-advanced-settings-with-semm"></a>Configurar opciones avanzadas con SEMM

**Tabla 1. Configuración avanzada**

| Configuración                            | Descripción                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 para el arranque PXE                  | Permite administrar la compatibilidad con IPv6 para el arranque PXE. Si no configura esta configuración, la compatibilidad con IPv6 para el arranque PXE está deshabilitada.                                                                               |
| Arranque alternativo                     | Permite administrar el uso de un orden de arranque alternativo para arrancar directamente en un dispositivo USB o Ethernet presionando el botón Bajar volumen y el botón De encendido durante el arranque. Si no configura esta opción, el arranque alternativo está habilitado. |
| Bloqueo de orden de arranque                    | Permite bloquear el orden de arranque para evitar cambios. Si no configura esta opción, el bloqueo de orden de arranque está deshabilitado.                                                                                                        |
| Arranque desde USB                           | Permite administrar el arranque en dispositivos USB. Si no configura esta opción, el arranque USB está habilitado.                                                                                                                 |
| Pila de red                      | Permite administrar la configuración de arranque de la pila de red. Si no configura esta configuración, la capacidad de administrar la configuración de arranque de la pila de red está deshabilitada.                                                                                                           |
| Encendido automático                      | Permite administrar la configuración de arranque de Auto Power On. Si no configura esta opción, se habilita La opción De encendido automático.                                                                                                        |
| Multiproceso simultáneo (SMT) | Permite administrar multiproceso simultáneo (SMT) para habilitar o deshabilitar el hyperthreading. Si no configura esta opción, SMT está habilitado.                                                  |
|Habilitar límite de batería| Permite administrar la funcionalidad límite de batería. Si no configuras esta configuración, el límite de batería está habilitado |
| Seguridad                           | Muestra la página Seguridad uefi **de** Surface. Si no configura esta configuración, se mostrará la página Seguridad.                                                                                                                 |
| Dispositivos                            | Muestra la página Dispositivos UEFI **de** Surface. Si no configura esta opción, se mostrará la página Dispositivos.                                                                                                                     |
| Arranque                               | Muestra la página De arranque de UEFI **de** Surface. Si no configura esta opción, se mostrará la página De arranque.                                                                                                                                                            |
| DateTime                           | Muestra la página **DateTime** de UEFI de Surface. Si no configura esta configuración, se mostrará la página DateTime.                                                                                                                |
| EnableOSMigration                          | Permite migrar Surface Hub 2 de Windows 10 Team a Windows 10 Pro o Enterprise. Si no configuras esta configuración, Surface Hub 2 dispositivos solo pueden ejecutar el sistema operativo Windows 10 Team usuario. Nota: El arranque dual entre Windows 10 Team y Windows 10 Pro/Enterprise no está disponible en Surface Hub 2.                                                                                                           |

>[!TIP]
>Al crear un paquete de configuración de SEMM, se muestran dos caracteres en la página **Correcto,** como se muestra en la figura 3.

![Presentación de huella digital del certificado.](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*Figura 3. Mostrar los dos últimos caracteres de la huella digital del certificado en la página Correcto*

Estos caracteres son los dos últimos caracteres de la huella digital del certificado y deben escribirse o grabarse. Los caracteres son necesarios para confirmar la inscripción en SEMM en un dispositivo Surface, como se muestra en la figura 4.

![Confirmación de inscripción en SEMM.](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*Figura 4. Confirmación de inscripción en SEMM con la huella digital del certificado SEMM*

>[!TIP]
>Los administradores con acceso al archivo de certificado (.pfx) pueden leer la huella digital en cualquier momento abriendo el archivo .pfx en CertMgr. Para ver la huella digital con CertMgr:
>
>1. Seleccione y mantenga presionado (o haga clic con el botón secundario) en el archivo .pfx y, a continuación, **seleccione Abrir**.
>2. En el panel de navegación, expanda la carpeta.
>3. Seleccione **Certificados**.
>4. En el panel principal, seleccione y mantenga presionado (o haga clic con el botón secundario) en el certificado y, a continuación, **seleccione Abrir**.
>5. Seleccione la **pestaña** Detalles.
>6. En el **menú** desplegable Mostrar, **** deben seleccionarse **Todas** o Solo propiedades.
>7. Seleccione el **campo Huella** digital.

Para inscribir un dispositivo Surface en SEMM o aplicar la configuración uefi desde un paquete de configuración, ejecute el archivo .msi con privilegios administrativos en el dispositivo Surface previsto. Puede usar tecnologías de implementación de aplicaciones o de sistema operativo, como [Microsoft Endpoint Configuration Manager](/mem/configmgr) o microsoft [deployment Toolkit](/mem/configmgr/mdt). Al inscribir un dispositivo en SEMM, debes estar físicamente presente para confirmar la inscripción en el dispositivo. Al aplicar una configuración a dispositivos que ya están inscritos en SEMM, no es necesaria la interacción del usuario.

Para obtener un tutorial paso a paso sobre cómo inscribir un dispositivo Surface en SEMM o aplicar una configuración de UEFI de Surface con SEMM, consulta Inscribir y configurar dispositivos Surface con [SEMM.](enroll-and-configure-surface-devices-with-semm.md)

### <a name="reset-package"></a>Restablecer paquete

Un paquete de restablecimiento de UEFI de Surface se usa para realizar una sola tarea: para desenrollar un dispositivo Surface de SEMM. El paquete de restablecimiento contiene instrucciones firmadas para quitar el certificado SEMM del firmware del dispositivo y restablecer la configuración de UEFI a la configuración predeterminada de fábrica. Al igual que un paquete de configuración de UEFI de Surface, un paquete de restablecimiento debe firmarse con el mismo certificado SEMM que se aprovisiona en el dispositivo Surface. Cuando creas un paquete de restablecimiento de SEMM, debes proporcionar el número de serie del dispositivo Surface que quieres restablecer. Los paquetes de restablecimiento de SEMM no son universales, son específicos de un dispositivo.

### <a name="recovery-request"></a>Solicitud de recuperación

En algunos escenarios, es posible que sea imposible usar un paquete de restablecimiento de UEFI de Surface. (Por ejemplo, si Windows se vuelve inutilizable en el dispositivo Surface). En estos escenarios, puedes desenrollar el dispositivo Surface desde SEMM a través de la página de administración de **Enterprise** de Surface UEFI (que se muestra en la figura 5) con una operación de solicitud de recuperación.

> [!div class="mx-imgBorder"]
> ![Inicie una solicitud de recuperación de SEMM.](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*Figura 5. Iniciar una solicitud de recuperación de SEMM en la página Enterprise administración*

Cuando usas el proceso en la **página Enterprise administración** de archivos para restablecer SEMM en un dispositivo Surface, se te da una solicitud de restablecimiento. Esta solicitud de restablecimiento se puede guardar como un archivo en una unidad USB, copiarse como texto o leerse como un código QR con un dispositivo móvil para que se envíe un mensaje o un correo electrónico fácilmente. Usa la opción Restablecimiento del configurador UEFI de Microsoft Surface para cargar un archivo de solicitud de restablecimiento o para escribir el texto Restablecer solicitud o código QR. Microsoft Surface UEFI Configurator genera un código de verificación que se puede especificar en el dispositivo Surface. Si escribes el código en el dispositivo Surface y **seleccionas Reiniciar,** el dispositivo se desanscribe desde SEMM.

>[!NOTE]
>Una solicitud de restablecimiento expira dos horas después de su creación.

Para obtener un tutorial paso a paso sobre cómo desenrollar dispositivos Surface desde SEMM, consulta [Desenrollar](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)dispositivos Surface de SEMM.

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Requisitos de Enterprise de modo de administración de Surface

Cuando usas SEMM con Microsoft Surface UEFI Configurator y quieres aplicar la configuración de UEFI, se requiere un certificado para comprobar la firma de los archivos de configuración. Este certificado garantiza que, después de que un dispositivo se inscribe en SEMM, solo se pueden usar paquetes creados con el certificado aprobado para modificar la configuración de UEFI.

>[!NOTE]
>Para realizar cualquier modificación en la configuración de SEMM o Surface UEFI en dispositivos Surface inscritos, se requiere el certificado SEMM. Si el certificado SEMM está dañado o perdido, NO se puede quitar ni restablecer SEMM. Administrar el certificado SEMM según corresponda con una solución adecuada para la copia de seguridad y la recuperación

Los paquetes creados con la herramienta Configurador UEFI de Microsoft Surface se firman con un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo se pueden usar paquetes creados con el certificado aprobado para modificar la configuración de UEFI.

### <a name="recommended-certificate-settings"></a>Configuración de certificado recomendada

Se recomiendan las siguientes opciones para el certificado SEMM:

- **Algoritmo clave** : RSA
- **Longitud de** clave – 2048
- **Algoritmo hash** : SHA-256
- **Tipo:** autenticación de servidor SSL
- **Uso de clave:** firma digital, cifrado de claves
- **Proveedor:** Microsoft Enhanced RSA and AES Cryptographic Provider
- **Fecha de expiración:** 15 meses desde la creación de certificados
- **Directiva de exportación clave:** exportable

También se recomienda autenticar el certificado SEMM en una arquitectura de infraestructura de clave pública (PKI) de dos niveles en la que la entidad de certificación intermedia (CA) esté dedicada a SEMM, lo que habilita la revocación de certificados. Para obtener más información acerca de una configuración de PKI de dos niveles, vea Guía del laboratorio de pruebas: Implementación de una jerarquía de [PKI de AD CS Two-Tier PKI](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11)).

### <a name="self-signed-certificate"></a>Certificado autofirmado

Puede usar el siguiente script de PowerShell de ejemplo para crear un certificado autofirmado para usarlo en escenarios de prueba de concepto.
Para usar este script, copie el texto siguiente en Bloc de notas y, a continuación, guarde el archivo como un script de PowerShell (.ps1).

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
>Para usarlo con SEMM y Microsoft Surface UEFI Configurator, el certificado debe exportarse con la clave privada y con protección con contraseña. Microsoft Surface UEFI Configurator te pide que selecciones el archivo de certificado SEMM (.pfx) y la contraseña del certificado.

Para crear un certificado autofirmado:

1. En la unidad C:, cree la carpeta donde guardará el script; por ejemplo, C:\SEMM.
2. Copie el script de ejemplo en Bloc de notas (o editor de texto equivalente) y, a continuación, guarde el archivo como un script de PowerShell (.ps1).
3. Inicie sesión en el equipo con credenciales de administrador y, a continuación, abra una sesión de PowerShell con privilegios elevados.
4. Asegúrese de que los permisos están configurados para permitir la ejecución de scripts. De forma predeterminada, los scripts están bloqueados para que no se ejecuten a menos que modifique la directiva de ejecución. Para obtener más información, vea [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5. En el símbolo del sistema, escriba la ruta de acceso completa del script y, a continuación, presione **Entrar**. El script crea un certificado de demostración denominado TempOwner.pfx.

Como alternativa, puede crear su propio certificado autofirmado con PowerShell. Para obtener más información, [vea New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate).

>[!NOTE]
>Para las organizaciones que usan una raíz sin conexión en su infraestructura de PKI, Microsoft Surface UEFI Configurator debe ejecutarse en un entorno conectado a la CA raíz para autenticar el certificado SEMM. Los paquetes generados por Microsoft Surface UEFI Configurator se pueden transferir como archivos, por lo que se pueden transferir fuera del entorno de red sin conexión con almacenamiento extraíble, como un stick USB.

### <a name="managing-certificates-faq"></a>Preguntas más frecuentes sobre la administración de certificados

La longitud *mínima recomendada* es de 15 meses. Puede usar un certificado que expire en menos de 15 meses o usar un certificado que expire en más de 15 meses.

>[!NOTE]
>Cuando un certificado expira, no se renueva automáticamente.

**¿Afectará un certificado expirado a la funcionalidad de los dispositivos inscritos en SEMM?**<br><br>
No, un certificado solo afecta a las tareas de administración de TI en SEMM y no tiene ningún efecto en la funcionalidad del dispositivo cuando expira.

**¿El paquete y el certificado SEMM tendrán que actualizarse en todas las máquinas que lo tengan?**<br><br>
Si desea que funcione el restablecimiento o la recuperación de SEMM, el certificado debe ser válido y no expirado.

**¿Se pueden crear paquetes de restablecimiento masivo para cada superficie que se ordene? ¿Se puede crear una que restablezca todas las máquinas de nuestro entorno?**<br><br>
Los ejemplos de PowerShell que crean un paquete de configuración para un tipo de dispositivo específico también se pueden usar para crear un paquete de restablecimiento independiente de número de serie. Si el certificado sigue siendo válido, puede crear un paquete de restablecimiento con PowerShell para restablecer SEMM.

## <a name="version-history"></a>Historial de versiones

### <a name="version-2831390"></a>Versión 2.83.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop 4
- Compatibilidad con la opción de multithreading simultánea para Surface Pro 7
- Eliminación de la configuración de SEMM obsoleta  
- Firma MSI mejorada

### <a name="version-2791390"></a>Versión 2.79.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Pro 7+.
- Mejoras en la experiencia del usuario.

### <a name="version-2781390"></a>Versión 2.78.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Laptop Go y Surface Pro X.
- Notificaciones para las versiones nuevas.
- La capacidad de crear paquetes personalizados para cambiar la propiedad.
- Correcciones de errores.

### <a name="version-2731360"></a>Versión 2.73.136.0

Esta versión de SEMM incluye:

- La capacidad para que el audio se deshabilite en Surface Hub2S con SEMM.
- Compatibilidad con Surface Pro X para dock 2.
- Compatibilidad con el Administrador de UEFI para operaciones relacionadas con Dock 2.
- Una corrección de errores del paquete de restablecimiento de Surface Go.
- Compatibilidad con la migración de Surface Hub 2 dispositivos desde Windows 10 Team sistema operativo a Windows 10 Pro o Enterprise.

### <a name="version-2711390"></a>Versión 2.71.139.0

Esta versión de SEMM agrega compatibilidad con las características de administración de Surface Dock 2 para Surface Book 3, Surface Laptop 3 y Surface Pro 7. Incluye:

- La capacidad de habilitar el audio (bloqueo/desbloqueo) y los puertos Ethernet y USB.
- La capacidad de crear paquetes de acoplamiento para hosts autenticados y no autenticados.

### <a name="version-2701300"></a>Versión 2.70.130.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Go 2.
- Compatibilidad con Surface Book 3.
- Correcciones de errores.

### <a name="version-2591390"></a>Versión 2.59.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Pro 7, Surface Pro X y Surface Laptop modelos de 3 13,5" y 15" con procesador Intel.
    >[!NOTE]
    >Surface Laptop no se admite el procesador AMD de 3 15".
- Compatibilidad con la característica Activar energía.

### <a name="version-2541390"></a>Versión 2.54.139.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Hub 2S.
- Correcciones de errores.

### <a name="version-2431360"></a>Versión 2.43.136.0

Esta versión de SEMM incluye:

- Compatibilidad para habilitar o deshabilitar el multithreading simultáneo.
- Opciones independientes para redes inalámbricas y Bluetooth para algunos dispositivos.
- Límite de batería eliminado para Surface Studio.

### <a name="version-2261360"></a>Versión 2.26.136.0

Esta versión de SEMM incluye:

- Compatibilidad con Surface Studio 2.
- Característica Límite de batería.

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

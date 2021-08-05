---
title: Puertos seguros de Surface Dock 2 con surface Enterprise management mode (SEMM)
description: Este documento proporciona instrucciones para configurar las opciones de puerto UEFI para Surface Dock 2 cuando se conectan a dispositivos Surface compatibles, incluidos Surface Book 3, Surface Laptop 3 y Surface Pro 7.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: Solucionar problemas comunes, problemas de configuración
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 08/02/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9a98eb9bab9b0be7f225dedf00ee6cfe7944b05e
ms.sourcegitcommit: 657d0d73a51f0dd35ad60740ed523164a55d2e04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2021
ms.locfileid: "11720934"
---
# <a name="secure-surface-dock-2-ports-with-surface-enterprise-management-mode-semm"></a>Puertos seguros de Surface Dock 2 con surface Enterprise management mode (SEMM)

## <a name="introduction"></a>Introducción

El modo de administración de Surface Enterprise (SEMM) permite a los administradores de TI proteger y administrar puertos de Surface Dock 2 mediante la configuración de UEFI en un paquete de configuración de instalador de Windows (archivo .msi) implementado en dispositivos Surface compatibles en un entorno corporativo.

### <a name="supported-devices"></a>Dispositivos compatibles

La administración de Surface Dock 2 con SEMM está disponible para docks conectados a Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Laptop Go, Surface Pro 7+, Surface Pro 7 y Surface Pro X. Estos dispositivos Surface compatibles se conocen comúnmente como **dispositivos host.** Un paquete se aplica a los dispositivos host en función de si un dispositivo host está **autenticado** o **no autenticado.** La configuración reside en la capa UEFI en dispositivos host que te permiten, el administrador de TI, administrar Surface Dock 2 como cualquier otro periférico integrado, como la cámara.

>[!NOTE]
>Solo puedes administrar puertos de Surface Dock 2 cuando la base de datos esté conectada a uno de los siguientes dispositivos compatibles: Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7+y Surface Pro 7. Cualquier dispositivo que no reciba la configuración de directiva autenticada uefi es inherentemente un dispositivo no autenticado.

### <a name="scenarios"></a>Escenarios

Restringir Surface Dock 2 a las personas autorizadas que han iniciado sesión en un dispositivo host corporativo proporciona otra capa de protección de datos. Esta capacidad de bloquear Surface Dock 2 es fundamental para clientes específicos en entornos altamente seguros que desean las ventajas de funcionalidad y productividad de la base de datos mientras se mantiene el cumplimiento de protocolos de seguridad estrictos. Prevemos que SEMM usado con Surface Dock 2 será especialmente útil en oficinas abiertas y espacios compartidos, especialmente para los clientes que desean bloquear puertos USB por motivos de seguridad. Para ver una demostración de vídeo, echa un vistazo [a SEMM para Surface Dock 2](https://youtu.be/VLV19ISvq_s).

## <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>Configurar e implementar la configuración de UEFI para Surface Dock 2

En esta sección se proporcionan instrucciones paso a paso para las siguientes tareas:

1. Instalar **Surface UEFI Configurator** desde [Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703).
1. Crear u obtener certificados de clave pública.
1. Cree un .msi de configuración.
   1. Agregue los certificados.
   1. Escribe el número de RN de 16 dígitos para tus dispositivos Surface Dock 2.
   1. Configurar las opciones de UEFI.
1. Crear y aplicar el paquete de configuración a dispositivos Surface de destino (Surface Book 3, Surface Laptop 3 o Surface Pro 7).

>[!NOTE]
>El **número aleatorio (RN)** es un identificador de código hexadecimal de 16 dígitos único que se aprovisiona en la fábrica y se imprime en un tipo pequeño en la parte inferior del dock. El RN difiere de la mayoría de los números de serie en que no se puede leer electrónicamente. Esto garantiza que la prueba de propiedad se establece principalmente solo mediante la lectura de la RN al acceder físicamente al dispositivo. El RN también puede obtenerse durante la transacción de compra y se registra en sistemas de inventario de Microsoft.

### <a name="install-semm-and-surface-uefi-configurator"></a>Instalar SEMM y Surface UEFI Configurator

Instale SEMM ejecutando **SurfaceUEFI_Configurator_v2.83.139.0.msi.** Este es un instalador independiente y contiene todo lo que necesitas para crear y distribuir paquetes de configuración para Surface Dock 2.

- Descargar **Surface UEFI Configurator** de [Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703).

## <a name="create-public-key-certificates"></a>Crear certificados de clave pública

En esta sección se proporcionan especificaciones para crear los certificados necesarios para administrar puertos para Surface Dock 2.

### <a name="prerequisites"></a>Requisitos previos

En este artículo se supone que obtiene certificados de un proveedor de terceros o que ya tiene experiencia en servicios de certificados de PKI y sabe cómo crear los suyos propios.  Debes familiarizarte con las recomendaciones generales para crear certificados, como se describe en la documentación del Modo de administración de [Surface Enterprise (SEMM),](surface-enterprise-management-mode.md) con una excepción. Los certificados documentados en esta página requieren plazos de expiración de 30 años para la entidad de certificación de acoplamiento **y**20 años para el certificado de autenticación **de host**.

Para obtener más información, vea la documentación de arquitectura de [servicios](/windows/win32/seccrypto/certificate-services-architecture) de certificados y revise los capítulos correspondientes en [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)o Windows Server [2008 PKI y Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) disponibles en Microsoft Press.

### <a name="root-and-host-certificate-requirements"></a>Requisitos de certificados raíz y host

Antes de crear el paquete de configuración, debes preparar certificados de clave pública que autentiquen la propiedad de Surface Dock 2 y facilitar los cambios posteriores en la propiedad durante el ciclo de vida del dispositivo. Los certificados de host y aprovisionamiento requieren escribir identificadores de EKU que se conocen como identificadores de objeto **(OID)** de autenticación de cliente mejorada (EKU).

Los valores de EKU requeridos se enumeran en las tablas 1 y 2.

#### <a name="table-1-root-and-dock-certificate-requirements"></a>Tabla 1. Requisitos de certificados raíz y de acoplamiento

|Certificado|Algoritmo|Descripción|Expiración|EKU OID|
|---|---|---|---|---|
|Entidad de certificación raíz|ECDSA_P384|- Certificado raíz con algoritmo de firma digital de curva elíptica de 384 bits (ECDSA)<br>- Uso de clave SHA 256:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 años|N/A
|Entidad de certificación dock|Curva ECC P256|- Certificado de host con criptografía de curva elíptica de 256 bits (ECC)<br>- Uso de clave SHA 256:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- Restricción de longitud de ruta = 0|20 años|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >La CA de acoplamiento debe exportarse como un archivo .p7b.

### <a name="provisioning-administration-certificate-requirements"></a>Requisitos de certificado de administración de aprovisionamiento

Cada dispositivo host debe tener la ca de documento y dos certificados, como se muestra en la tabla 2.

#### <a name="table-2-provisioning-administration-certificate-requirements"></a>Tabla 2. Requisitos de certificado de administración de aprovisionamiento

|Certificado|Algoritmo|Descripción|EKU OID|
|---|---|---|---|
|Certificado de autenticación de host|ECC P256<br>SHA 256|Prueba la identidad del dispositivo host.|1.3.6.1.4.1.311.76.9.21.2|
|Certificado de administración de aprovisionamiento|ECC P256<br>SHA256|Permite cambiar la propiedad del acoplamiento o la configuración de directiva, ya que le permite reemplazar la ca que está instalada actualmente en el dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >Los certificados de aprovisionamiento y autenticación de host deben exportarse como archivos .pfx.

### <a name="create-configuration-package"></a>Crear paquete de configuración

Cuando haya obtenido o creado los certificados, estará listo para crear el paquete de configuración .msi que se aplicará a los dispositivos Surface de destino.

1. Ejecute El **Configurador uefi de**Surface .

   ![Ejecutar Surface UEFI Configurator](images/secure-surface-dock-ports-semm-1.png)

1. Selecciona **Surface Dock**.

   ![Seleccionar Surface Dock](images/secure-surface-dock-ports-semm-2.png)

1. Escriba los certificados **adecuados**  en la página del certificado. Los certificados de demostración están disponibles en [Surface Tools para](https://www.microsoft.com/download/details.aspx?id=46703) ** TI: ** descargueSEMM_PowerShell.zipy consulte **CreateSurfaceDock2Certificates.ps1**. Asegúrese de instalar **SurfaceDock2_WmiInstanceProvider** antes de ejecutar los scripts de demostración.

   ![escriba los certificados adecuados](images/secure-surface-dock-ports-semm-3.png)

1. Agregue los RN de acoplamiento adecuados a la lista.

   >[!TIP]
   >Cuando creas un paquete de configuración para varios dispositivos Surface Dock 2, en lugar de escribir cada RN manualmente, puedes usar un archivo .csv que contenga una lista de RN.

1. Especifica la configuración de la directiva para los puertos USB, Ethernet y Audio. UEFI Configurator le permite configurar las opciones de directiva para usuarios autenticados (directiva autenticada) y usuarios no autenticados (directiva no autenticada). En la siguiente figura se muestra el acceso de puerto activado para usuarios autenticados y desactivado para usuarios no autenticados.

   ![Elija qué componentes desea activar o desactivar.](images/secure-surface-dock-ports-semm-4.png)

   - El usuario autenticado hace referencia a un dispositivo Surface que tiene instalados los certificados adecuados, tal como se configura en el paquete de configuración .msi que aplicaste a los dispositivos de destino. Se aplica a cualquier usuario autenticado que inicia sesión en el dispositivo.
   - El usuario no autenticado hace referencia a cualquier otro dispositivo.
   - Seleccione **Restablecer** para crear un paquete especial de "restablecimiento" que quitará cualquier paquete de configuración anterior que el dock hubiera aceptado.

1. Seleccione **Generar** para crear el paquete según lo especificado.

### <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>Aplicar el paquete de configuración a Surface Dock 2

1. Toma el .msi que generó el Configurador de UEFI de Surface e instállo en un dispositivo host de Surface. Los dispositivos host compatibles Surface Book 3, Surface Laptop 3 o Surface Pro 7.
1. Conectar el dispositivo host a Surface Dock 2. Al conectar la configuración de directiva UEFI de acoplamiento se aplica.

## <a name="verify-managed-state-using-the-surface-app"></a>Comprobar el estado administrado con Surface App

Una vez aplicado el paquete de configuración, puedes comprobar rápidamente el estado de directiva resultante de la base de datos directamente desde Surface App, instalado de forma predeterminada en todos los dispositivos Surface. Si Surface App no está presente en el dispositivo, puedes descargarlo e instalarlo desde el Microsoft Store.

### <a name="test-scenario"></a>Escenario de prueba

Objetivo: configurar las opciones de directiva para permitir el acceso de puertos solo a los usuarios autenticados.

1. Active todos los puertos para usuarios autenticados y desconéctelos para usuarios no autenticados.

   ![Habilitar puertos para usuarios autenticados](images/secure-surface-dock-ports-semm-4.png)

1. Aplica el paquete de configuración al dispositivo de destino y, a continuación, conecta Surface Dock 2.

1. Abre **Surface App** y selecciona Surface **Dock** para ver el estado resultante de la directiva de Surface Dock. Si se aplica la configuración de directiva, Surface App indicará que los puertos están disponibles.

   ![La aplicación Surface muestra todos los puertos disponibles para usuarios autenticados](images/secure-surface-dock-ports-semm-5.png)

1. Ahora debe comprobar que la configuración de directiva ha desactivado correctamente todos los puertos para usuarios no autenticados. Conectar Surface Dock 2 para un dispositivo no administrado, es decir, cualquier dispositivo Surface fuera del ámbito de administración del paquete de configuración que creaste.

1. Abre **Surface App** y selecciona Surface **Dock**. El estado de directiva resultante indicará que los puertos están desactivados.

   ![Aplicación surface que muestra puertos desactivados para usuarios no autenticados ](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>Si quieres mantener la propiedad del dispositivo, pero permitir el acceso completo a todos los usuarios, puedes crear un nuevo paquete con todo activado. Si quieres quitar por completo las restricciones y la propiedad del dispositivo (que no esté administrado), selecciona **Restablecer** en Surface UEFI Configurator para crear un paquete que se aplique a los dispositivos de destino.

¡Enhorabuena! Has administrado correctamente los puertos de Surface Dock 2 en dispositivos host de destino.

## <a name="learn-more"></a>Obtén más información

- [Documentación Enterprise modo de administración de Surface (SEMM)](surface-enterprise-management-mode.md)
- [Arquitectura de servicios de certificados](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Servidor 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows PKI de Server 2008 y seguridad de certificados](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)

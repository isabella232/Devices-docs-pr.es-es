---
title: Puertos 2 puertos acoplados de Surface con el modo de administración de empresa de Surface (SEMM)
description: Este documento proporciona instrucciones para configurar ajustes de puertos UEFI para Surface Dock 2 cuando se conecta a dispositivos de Surface compatibles, incluidos Surface Book 3, Surface Laptop 3 y Surface Pro 7.
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
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114698"
---
# Puertos 2 puertos acoplados de Surface con el modo de administración de empresa de Surface (SEMM)

## Introducción

El modo de administración de empresa de Surface (SEMM) permite a los administradores de ti proteger y administrar los puertos del acoplamiento de superficies 2 al configurar la configuración de UEFI en un paquete de configuración de Windows Installer (. MSI) se implementó en dispositivos de Surface compatibles en un entorno corporativo.

### Dispositivos compatibles

La administración de Surface Dock 2 con SEMM está disponible para los muelles conectados a Surface Book 3, Surface Laptop 3, Surface portátiles Go, Surface Pro 7 y Surface Pro X. Estos dispositivos de Surface compatibles suelen denominarse **dispositivos host**. Se aplica un paquete a los dispositivos de hospedaje en función de si se **autentica** **o no se autentica a**un dispositivo de hospedaje. La configuración configurada reside en el nivel UEFI en dispositivos hosts, lo que permite que el administrador de TI administre Surface Dock 2 como cualquier otro periférico incorporado, como la cámara.

>[!NOTE]
>Puede administrar puertos de Surface Dock 2 solo cuando el Dock está conectado a uno de los siguientes dispositivos compatibles: Surface Book 3, Surface Laptop 3 y Surface Pro 7. Cualquier dispositivo que no reciba la configuración de directiva autenticada UEFI es por naturaleza un dispositivo no autenticado.

### Escenarios

La restricción de Surface Dock 2 a personas autorizadas que han iniciado sesión en un dispositivo de host corporativo ofrece otro nivel de protección de datos. Esta capacidad de bloquear Surface Dock 2 es crítica para clientes específicos en entornos de alta seguridad que desean los beneficios de productividad y funcionalidad del Dock al mismo tiempo que mantienen el cumplimiento de los estrictos protocolos de seguridad. Anticipamos que SEMM se usa con Surface Dock 2 será especialmente útil en oficinas abiertas y espacios compartidos, especialmente para los clientes que deseen bloquear puertos USB por razones de seguridad. Para obtener una demostración en video, consulta [SEMM para Surface docking 2](https://youtu.be/VLV19ISvq_s).

## Configuración e implementación de la configuración de UEFI para Surface Dock 2

Esta sección proporciona instrucciones paso a paso para las siguientes tareas:

1. Instale [**Surface configurador UEFI**](https://www.microsoft.com/download/details.aspx?id=46703).
1. Crear u obtener certificados de clave pública.
1. Crear un. Paquete de configuración de MSI.
   1. Agregue los certificados.
   1. Introduce el número de 16 dígitos de RN para los dispositivos de Surface Dock 2.
   1. Establezca la configuración de UEFI.
1. Compilar y aplicar el paquete de configuración a los dispositivos Surface de destino (Surface Book 3, Surface Laptop 3 o Surface Pro 7).

>[!NOTE]
>El **número aleatorio (RN)** es un identificador de código hexadecimal único de 16 dígitos que se suministra en la fábrica y se imprime en tipo pequeño en la parte inferior del Dock. RN se diferencia de la mayoría de los números de serie en que no se puede leer electrónicamente. Esto garantiza que la prueba de propiedad se establece principalmente mediante la lectura de RN cuando se accede físicamente al dispositivo. También puede obtenerse el RN durante la transacción de compra y se registra en sistemas de Microsoft Inventory.

### Instalar SEMM y el configurador UEFI de Surface

Instale SEMM ejecutando **SurfaceUEFI_Configurator_v2.71.139.0.msi**. Este es un instalador independiente y contiene todo lo que necesitas para crear y distribuir paquetes de configuración para Surface Dock 2.

- Descarga el **configurador de Surface UEFI** desde [herramientas de Surface para ti](https://www.microsoft.com/en-us/download/details.aspx?id=46703).

## Crear certificados de clave pública

Esta sección proporciona especificaciones para crear los certificados necesarios para administrar los puertos de Surface Dock 2.

### Requisitos previos

En este artículo se supone que obtiene certificados de un proveedor de terceros o que ya tiene experiencia en servicios de certificados PKI y que sabe cómo crear los suyos propios.  Debe estar familiarizado con las recomendaciones generales para crear certificados, como se describe en la documentación del [modo de administración de empresas (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) , con una excepción. Los certificados documentados en esta página requieren condiciones de expiración de 30 años para la **entidad emisora de certificados**y 20 años para el **certificado de autenticación de host**.

Para obtener más información, consulte la documentación de la [arquitectura de servicios de Certificate](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) Server y revise los capítulos correspondientes de [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)o la [PKI de Windows Server 2008 y la seguridad de certificados](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) disponible en Microsoft Press.

### Requisitos de certificados raíz y de host

Antes de crear el paquete de configuración, debe preparar los certificados de clave pública que autentican la propiedad de Surface Dock 2 y facilitar cualquier cambio posterior en la propiedad durante el ciclo de vida del dispositivo. Los certificados de host y de aprovisionamiento requieren que se introduzcan identificadores EKU, de lo contrario, se denominan **identificadores de objetos (OID**) de autenticación de cliente (EKU).

Los valores de EKU obligatorios se muestran en la tabla 1 y la tabla 2.

#### Tabla 1. Requisitos de certificados raíz y de acoplamiento

|Certificado|Algoritmo|Descripción|Expiración|OID DEL EKU|
|---|---|---|---|---|
|Entidad emisora raíz|ECDSA_P384|-Certificado raíz con el algoritmo de firma digital de curva elíptica de 384 bits (ECDSA)<br>-Uso de claves SHA 256:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 años|N/D
|Entidad emisora de certificados|Curva P256 ECC|-Certificado de host con criptografía de curva elíptica de 256 bits (ECC)<br>-Uso de claves SHA 256:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-Restricción de longitud de ruta = 0|20 años|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >La entidad de certificación Dock debe exportarse como un archivo. p7b.

### Requisitos de certificados de administración de aprovisionamiento

Cada dispositivo host debe tener la CA de documento y dos certificados, tal como se muestra en la tabla 2.

#### Tabla 2. Requisitos de certificados de administración de aprovisionamiento

|Certificado|Algoritmo|Descripción|OID DEL EKU|
|---|---|---|---|
|Certificado de autenticación de host|P256 ECC<br>SHA 256|Prueba la identidad del dispositivo de hospedaje.|1.3.6.1.4.1.311.76.9.21.2|
|Certificado de administración de aprovisionamiento|P256 ECC<br>SHA256|Le permite cambiar la configuración de la Directiva o de la propiedad del Dock al permitirle reemplazar la entidad que está instalada actualmente en el Dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >Los certificados de autenticación y aprovisionamiento de host deben exportarse como archivos. pfx.

### Crear paquete de configuración

Cuando haya obtenido o creado los certificados, estará listo para crear el paquete de configuración de MSI que se aplicará a los dispositivos Surfaces de destino.

1. Ejecute el **configurador UEFI**de Surface.

   ![Configurador UEFI de superficie](images/secure-surface-dock-ports-semm-1.png)

1. Seleccione **muelle de superficie**.

   ![Seleccionar el Dock de Surface](images/secure-surface-dock-ports-semm-2.png)

1. En la página certificado, escriba los **certificados**apropiados.

   ![escribe los certificados apropiados](images/secure-surface-dock-ports-semm-3.png)

1. Agregue la RNs del Dock correspondiente a la lista.

   >[!NOTE]
   >Al crear un paquete de configuración para varios dispositivos de Surface Dock 2, en lugar de escribir cada RN manualmente, puede usar un archivo. csv que contiene una lista de RNs.

1. Especifique la configuración de la Directiva para los puertos de datos USB, Ethernet y de audio. El configurador UEFI le permite establecer la configuración de la Directiva para usuarios autenticados (Directiva autenticada) y los usuarios no autenticados (Directiva no autenticada). La siguiente ilustración muestra el acceso a puertos activado para usuarios autenticados y desactivado para usuarios no autenticados.

   ![Elija qué componentes desea activar o desactivar.](images/secure-surface-dock-ports-semm-4.png)

   - El usuario autenticado hace referencia a un dispositivo Surface que tiene instalados los certificados apropiados, según se haya configurado en el. Paquete de configuración MSI que aplicó a los dispositivos de destino. Se aplica a cualquier usuario autenticado por el usuario que inicia sesión en el dispositivo. 
   - El usuario no autenticado se refiere a cualquier otro dispositivo.
   - Seleccione **restablecer** para crear un paquete de "restablecimiento" especial en el que se eliminará cualquier paquete de configuración anterior que haya aceptado el Dock.

1. Seleccione **compilación** para crear el paquete como se especifica.

### Aplicar el paquete de configuración a un muelle de superficie 2

1. Tome el archivo MSI que el configurador de Surface UEFI ha generado e instálelo en un dispositivo de host de Surface. Los dispositivos host compatibles son Surface Book 3, Surface Laptop 3 o Surface Pro 7.
1. Conecte el dispositivo de hospedaje al muelle de superficie 2. Cuando se conecta la configuración de directiva de Dock UEFI, se aplican.

## Comprobar el estado administrado con la aplicación Surface

Una vez que haya aplicado el paquete de configuración, puede verificar rápidamente el estado de la Directiva resultante del muelle directamente desde la aplicación de Surface, instalado de forma predeterminada en todos los dispositivos de la superficie. Si Surface App no está presente en el dispositivo, puede descargarlo e instalarlo desde Microsoft Store.

### Escenario de prueba

Objetivo: configurar las opciones de directiva para permitir el acceso por parte de los usuarios autenticados únicamente.

1. Activar todos los puertos para usuarios autenticados y desactivarlos para los usuarios no autenticados.

   ![Habilitar puertos para usuarios autenticados](images/secure-surface-dock-ports-semm-4.png)

1. Aplique el paquete de configuración a su dispositivo de destino y, a continuación, conecte Surface docking 2.

1. Abra la **aplicación Surface** y seleccione **acoplar superficie** para ver el estado de la Directiva resultante de su base de superficie. Si se aplica la configuración de la Directiva, Surface App indicará que hay puertos disponibles.

   ![Surface App muestra que todos los puertos están disponibles para los usuarios autenticados](images/secure-surface-dock-ports-semm-5.png)

1. Ahora debe comprobar que la configuración de la Directiva ha desactivado correctamente todos los puertos para los usuarios no autenticados. Conecte Surface Dock 2 a un dispositivo no gestionado (es decir, cualquier dispositivo Surface) fuera del ámbito de administración para el paquete de configuración que ha creado.

1. Abra la **aplicación Surface** y seleccione **muelle de superficie**. El estado de la Directiva resultante indicará que los puertos están desactivados.

   ![Aplicación Surface que muestra los puertos desactivados para los usuarios no autenticados ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>Si desea mantener la propiedad del dispositivo, pero permitir que todos los usuarios tengan acceso completo, puede hacer un nuevo paquete con todo activado. Si desea quitar por completo las restricciones y la propiedad del dispositivo (hacerlo no administrado), seleccione **restablecer** en Surface configurador UEFI para crear un paquete que se aplicará a los dispositivos de destino.

¡Enhorabuena! Ha administrado correctamente los puertos de Surface Dock 2 en dispositivos host de destino.

## Obtén más información

- [Documentación del modo de administración de Enterprise Surface (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [Arquitectura de servicios de Certificate Server](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI y seguridad de certificados](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)

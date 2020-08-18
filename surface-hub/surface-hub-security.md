---
title: Introducción a la seguridad de Surface Hub
description: En esta página, se explica el diseño de Defensa en profundidad de Surface Hub y se describen las mejoras de seguridad de Surface Hub 2S, las protecciones de seguridad inalámbrica y otras características relacionadas.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/27/2020
ms.localizationpriority: High
ms.openlocfilehash: f6022c4fd16cd8afbbea892e73ad831f12b10eaa
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934860"
---
# Introducción a la seguridad de Surface Hub

Surface Hub ofrece un dispositivo informático bloqueado con un firmware de plataforma personalizado que ejecuta el sistema operativo Windows 10 Team. El dispositivo resultante adopta la filosofía tradicional de quiosco seguro de "uso único" en el que "solo ejecuta lo que necesita" y ofrece un enfoque moderno al respecto. Diseñado para dar soporte a una experiencia de usuario colaborativa rica, Surface Hub se protege frente a las amenazas de seguridad en constante evolución.

Creado a partir de Windows10, Surface Hub ofrece seguridad moderna a nivel empresarial, lo que permite a los administradores de TI aplicar la protección de datos con BitLocker, el Módulo de plataforma segura 2.0 (TPM), además de seguridad con tecnología de la nube con Windows Defender (también conocido como Microsoft Defender).

## Seguridad de Defensa en profundidad

Los protocolos de seguridad se ponen en marcha en cuanto se enciende Surface Hub. Empezando por el nivel de firmware, Surface Hub solo cargará el sistema operativo y sus componentes en respuesta a las múltiples comprobaciones de seguridad. Surface Hub emplea una estrategia denominada Defensa en profundidad que involucra organizar en capas subcomponentes de defensa independientes para proteger todo el sistema en caso de fallo parcial. Esta práctica del sector ha demostrado ser muy eficaz en la mitigación de posibles ataques unilaterales y de puntos débiles en los subcomponentes.

La moderna modernización unificada de extensible firmware (UEFI) está configurada de forma estática y segura por Microsoft para que solo arranque un sistema operativo de equipo Windows 10 autenticado desde el almacenamiento interno.  La firma de todas las líneas de código que se ejecuten en Surface Hub se comprueba antes de su ejecución. Solo las aplicaciones firmadas por Microsoft, ya sea como parte del sistema operativo o instaladas desde la Microsoft Store, pueden ejecutarse en Surface Hub. El código o las aplicaciones que no cumplan estos requisitos se bloquearán.

Los sistemas de seguridad de Surface Hub incluyen lo siguiente:

- **Defensas durante el arranque.** Solo se cargan los componentes del sistema operativo de confianza de Surface Hub.
- **Defensas de sistema operativo.** Se protege contra la ejecución de código o software no intencionado o malintencionado.
- **Defensas de la interfaz de usuario.** Se ofrece una interfaz de usuario segura para los usuarios finales, lo que les impide el acceso a actividades potencialmente peligrosas como iniciar archivos ejecutables desde la línea de comandos.

### Defensas durante el arranque

El SoC tiene un procesador de seguridad independiente de cualquier otro núcleo. La primera vez que inicie Surface Hub, solo se iniciará el procesador de seguridad antes de que se pueda cargar cualquier otro elemento.

![Fases de inicio de SurfaceHub en las que se muestran las protecciones del procesador de seguridad](images/hub-sec-1.png)

#### Arranque seguro

El Arranque seguro se usa para comprobar que los componentes del proceso de inicio, incluidos los controladores y el sistema operativo, se validan con una base de datos de firmas válidas y conocidas. En Surface Hub, debe validarse primero una firma específica de la plataforma antes de que se pueda cargar el sistema operativo de WindowsTeam autorizado. Esto ayuda a evitar que se produzcan ataques de un sistema clonado o modificado en el que se ejecuta código malintencionado oculto en lo que parece ser una experiencia de usuario normal.  Para obtener más información, consulte [Información sobre el arranque seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).

### Defensas de sistema operativo

Una vez que se comprueba el sistema operativo como originario de Microsoft y Surface Hub completa satisfactoriamente el proceso de inicio, el dispositivo inspecciona el código ejecutable. Nuestro método para proteger el sistema operativo consiste en identificar la firma de código de todos los archivos ejecutables, de modo que solo los que superen las restricciones se carguen en tiempo de ejecución. Este método de firma de código permite al sistema operativo comprobar el autor y confirmar que el código no se ha modificado antes de ejecutarse en el dispositivo.

Surface Hub usa una característica de firma de código conocida como Integridad de código del modo usuario (UMCI) en el Control de aplicaciones de Windows (anteriormente conocido como Device Guard). Se configuran las opciones de la directiva de tal modo que solo admita aplicaciones que cumplan uno de estos requisitos:

- Aplicaciones de Plataforma universal de Windows (Microsoft Store) que están [certificadas oficialmente](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process).
- Las aplicaciones firmadas con la exclusiva entidad de certificación (CA) raíz de producción de Microsoft, que solo pueden firmar los empleados de Microsoft con el acceso autorizado a estos certificados.
- Aplicaciones firmadas con la exclusiva Raíz C de producción de Surface Hub.

El archivo de configuración se firma con la entidad de certificación de raíz de producción de Microsoft diseñada para evitar que un tercero pueda quitar o modificar las restricciones. En este momento dado, los demás archivos ejecutables simplemente se bloquean en el nivel de tiempo de ejecución del sistema operativo y se evita que utilicen recursos de procesamiento. Esta reducción de la superficie de ataque ofrece las siguientes protecciones:

- Ningún modo de documento heredado
- Ningún motor de scripts heredado
- Ningún lenguaje de marcado de vectores
- Ningún objeto auxiliar de explorador
- Ningún control de ActiveX

Además de bloquear el código sin firma o firmado de forma incorrecta mediante UMCI, Surface Hub usa el Control de aplicaciones de Windows para bloquear componentes de Windows como el Símbolo del sistema, PowerShell y el Administrador de tareas. Este sistema de seguridad refleja una característica de diseño clave de Surface Hub como dispositivo de computación seguro. Para obtener más información, consulte:

- [Introducción al control de aplicaciones](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Control de aplicaciones de Windows Defender y protección basada en la virtualización de la integridad del código](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### Defensas de la interfaz de usuario

Aunque las defensas en tiempo de arranque y las protecciones de bloqueo del sistema operativo proporcionan seguridad fundamental, la interfaz de usuario ofrece un nivel adicional que se ha diseñado para reducir los riesgos. Para impedir que algún código malintencionado llegue al dispositivo a través de los controladores, Surface Hub no descarga controladores avanzados para dispositivos Plug and Play (PnP). Los dispositivos que aprovechan los controladores básicos, como las unidades flash USB o los periféricos de Surface Hub certificados (altavoces, micrófonos y cámaras) funcionan como se espera, pero los sistemas avanzados, como las impresoras, no lo harán.

Las defensas de la interfaz de usuario también simplifican la interfaz de usuario y evitan la ejecución de código o software malintencionado. Los siguientes elementos de la interfaz de usuario de Surface Hub separan por capas la seguridad principal proporcionada por la firma de código:

- **Explorador de archivos.** Surface Hub tiene un Explorador de archivos personalizado que permite acceder rápidamente a las carpetas Música, Vídeos, Documentos, Imágenes y Descargas, sin tener que revelar a los usuarios los archivos de programa o del sistema. No se puede acceder a otras ubicaciones de la unidad de disco duro local a través del Explorador de archivos. Además, muchos tipos de archivos ejecutables, como. exe y. msi, no se pueden ejecutar, lo que proporciona otro nivel de seguridad frente a ejecutables potencialmente maliciosos.

- **Inicio y Todas las aplicaciones.** Los componentes Inicio y Todas las aplicaciones de Surface Hub no exponen el acceso al Símbolo del sistema, PowerShell u otros componentes de Windows bloqueados mediante el Control de aplicaciones. Además, la funcionalidad de ejecución de Windows, a la que generalmente se accede en equipos PC desde el cuadro de búsqueda, está desactivada para Surface Hub.

## Mejoras en la seguridad de Surface Hub 2S

Aunque Surface Hub y Surface Hub 2S ejecutan el mismo sistema operativo, algunas características exclusivas de Surface Hub 2S proporcionan capacidades de administración y seguridad adicionales que permiten a los administradores de TI realizar las siguientes tareas:

- Administrar la configuración de UEFI con SEMM
- Recuperar Hub con un USB de arranque
- Reforzar la cuenta del dispositivo mediante la rotación de contraseñas

### Administrar la configuración de UEFI con SEMM

UEFI es una interfaz situada entre las partes de la plataforma de hardware subyacente y el sistema operativo. En Surface Hub, una implementación personalizada de UEFI permite tener control específico sobre esta configuración y evita que cualquier entidad que no sea de Microsoft cambie la configuración de UEFI del dispositivo, o el arranque desde una unidad extraíble para modificar o cambiar el sistema operativo.

En un nivel superior, durante el proceso de aprovisionamiento de fábrica, la UEFI de Surface Hub se configura previamente para que permita el arranque seguro y se establece que arranque únicamente desde una unidad interna de estado sólido (SSD), con el acceso a los menús de UEFI bloqueado y los accesos directos eliminados. Esto sella el acceso a la UEFI y garantiza que el dispositivo solo pueda arrancar en el sistema operativo WindowsTeam instalado en Surface Hub.

Cuando se administra a través del Surface Enterprise Management Mode (SEMM) de Microsoft, los administradores de TI pueden implementar la configuración de UEFI en los dispositivos Hub de toda una organización. Esto incluye la posibilidad de habilitar o deshabilitar los componentes de hardware integrados, evitar que los usuarios no autorizados cambien la configuración de UEFI y ajustar la configuración de arranque.

![Configuración de UEFI de Surface Hub](images/hub-sec-2.png)

Los administradores pueden implementar SEMM y los dispositivos inscritos en Surface Hub 2S con el [Configurador de UEFI de Surface de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703) descargable. Para obtener más información, consulte [Proteger y administrar Surface Hub 2S con SEMM y UEFI](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm).
SEMM, que está protegido por un certificado para salvaguardar la configuración frente a la alteración o eliminación no autorizadas, permite la administración de los siguientes componentes:

- LAN de cable
- Cámara
- Bluetooth
- Wi-Fi
- Sensor de ocupación
- IPv6 para el arranque PXE
- Arranque alternativo
- Bloqueo de orden de arranque
- Arranque desde USB
- Interfaz de página de información de UEFI
    - Dispositivos
    - Arranque
    - Fecha y hora

    
### Recuperar Hub con un USB de arranque

Surface Hub 2S permite a los administradores devolver el dispositivo a la configuración de fábrica con una imagen de recuperación en tan solo 20 minutos. Normalmente, solo sería necesario llevar a cabo esta acción si Surface Hub deja de funcionar. La recuperación también es útil si ha perdido la clave de BitLocker o ya no tiene credenciales de administrador para la aplicación Configuración.

### Reforzar la cuenta del dispositivo mediante la rotación de contraseñas

Surface Hub usa una cuenta de dispositivo, también denominada "cuenta de sala", para autenticar con Exchange, Microsoft Teams y otros servicios. Cuando se habilita la rotación de contraseñas, Hub 2S genera automáticamente una nueva contraseña cada 7 días, que se compone de entre 15 y 32 caracteres con una combinación de letras mayúsculas y minúsculas, números y caracteres especiales. Como nadie conoce la contraseña, la rotación de contraseñas de la cuenta del dispositivo mitiga eficazmente el riesgo asociado a errores humanos y posibles ataques de seguridad mediante ingeniería social.

## Seguridad empresarial de Windows10

Además de las configuraciones y características específicas de Surface Hub que se tratan en este documento, Surface Hub también usa las características de seguridad estándares de Windows10. Entre ellos se incluyen los siguientes:

- **BitLocker**. El SSD de Surface Hub está equipado con BitLocker para proteger los datos en el dispositivo. Su configuración sigue los estándares del sector. Para obtener más información, consulte [Introducción a BitLocker](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).
- **Windows Defender.** El motor antimalware de Windows Defender se ejecuta de forma continua en Surface Hub y corrige automáticamente las amenazas que se encuentren en Surface Hub. El motor de Windows Defender recibe actualizaciones automáticamente y se administra mediante herramientas de administración remota para administradores de TI. El motor de Windows Defender es un ejemplo perfecto de nuestro enfoque de Defensa en profundidad: si el malware puede encontrar una manera de evitar nuestra solución básica de seguridad basada en código firmado, se detectará aquí. Para obtener más información, consulte [Control de aplicaciones de Windows Defender y protección basada en la virtualización de la integridad del código](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control).
- **Controladores Plug and Play.** Para impedir que un código malintencionado llegue al dispositivo a través de los controladores, Surface Hub no descarga controladores avanzados para dispositivos PnP. Esto permite que los dispositivos que usan controladores básicos, como las unidades flash USB, funcionen como se espera, a la vez que se bloquean sistemas más avanzados como impresoras.
- **Módulo de plataforma segura 2.0** Surface Hub tiene un módulo de plataforma segura diferenciado (dTPM) estándar del sector para generar y almacenar claves criptográficas y hashes. El dTPM protege las claves que se usan para la comprobación de las fases de arranque, la clave maestra de BitLocker, la clave de inicio de sesión sin contraseña y mucho más. El dTPM cumple la certificación [FIPS 140-2 de nivel 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation), el estándar de seguridad de equipos de la administración de Estados Unidos, y cumple con la certificación de [criterios comunes](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria) usada en todo el mundo.

## Seguridad inalámbrica para Surface Hub

Surface Hub usa la tecnología Wi-Fi Direct o Miracast y los estándares 802.11, Acceso protegido Wi-Fi (WPA2) y Wireless Protected Setup (WPS) asociados. Dado que el dispositivo solo admite WPS (en lugar de clave precompartida de WPA2 (PSK) o WPA2 Enterprise), los problemas que se asociaban tradicionalmente con el cifrado 802.11 se simplificaron por diseño.

Miracast pertenece al estándar de Wi-Fi Display, que también es compatible con el protocolo de Wi-Fi Direct. Estos estándares son compatibles con dispositivos móviles modernos para colaboración y uso compartido de pantalla.

Wi-Fi Direct o Wi-Fi "Punto a punto" (P2P) es un estándar publicado por Wi-Fi Alliance para las redes "ad hoc". Esto permite que los dispositivos compatibles se puedan comunicar directamente y creen grupos de redes sin necesidad de un punto de acceso Wi-Fi tradicional o una conexión a Internet.

La seguridad de Wi-Fi Direct la proporciona WPA2 con el estándar WPS. Los dispositivos pueden autenticarse con un PIN numérico, un botón de comando físico o virtual, o un mensaje fuera de banda mediante transmisión de datos en proximidad. Surface Hub es compatible de forma predeterminada con el botón de comando y con métodos PIN. Para obtener más información, consulte [Cómo gestiona Surface Hub los problemas de seguridad de Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct).

## Obtén más información

- [Introducción al arranque seguro](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [Introducción a BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [Introducción al control de aplicaciones](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Proteger y administrar Surface Hub 2S con SEMM y UEFI](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Cómo gestiona Surface Hub los problemas de seguridad de Wi-Fi Direct](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Control de aplicaciones de Windows Defender y protección basada en la virtualización de la integridad del código](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 nivel 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [Certificación de criterios comunes](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)

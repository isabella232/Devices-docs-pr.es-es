---
title: Conceptos básicos del sistema operativo (Surface Hub)
description: En este tema se explican aspectos únicos del Windows 10 Team operativo y cómo difiere de Windows 10 Enterprise.
keywords: historial de cambios
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/23/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 57fd7ea11e19902d2a94c1be998052739875afaf
ms.sourcegitcommit: 38e98402ab1380521029e792a83c00391997e1fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2021
ms.locfileid: "12089302"
---
# <a name="operating-system-essentials-surface-hub"></a>Conceptos básicos del sistema operativo (Surface Hub)

El sistema operativo de Surface Hub, Windows 10 Team, se basa en Windows 10 Enterprise y proporciona compatibilidad enriquecida para la administración empresarial, la seguridad y otras características. Sin embargo, hay importantes diferencias entre las dos versiones. Si bien la edición Enterprise está diseñada para equipos PC, Windows 10 Team está diseñado desde el principio para pantallas de gran tamaño y salas de reuniones. Al evaluar los requisitos de seguridad y administración de Surface Hub, es mejor considerarlo como un nuevo sistema operativo. Este artículo está diseñado para ayudar a destacar las diferencias clave entre Windows 10 Team en Surface Hub y Windows 10 Enterprise y qué significan las diferencias para las organizaciones.

A partir de septiembre de 2020, los clientes tienen la opción de migrar a Windows 10 Pro o Enterprise en Surface Hub 2S. Para conocer más, consulta lo siguiente:

- [Anuncio de la disponibilidad de Windows 10 Pro y Enterprise en Surface Hub 2](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107).

- [Migrar a Windows 10 Pro o Enterprise en Surface Hub 2](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>Interfaz de usuario

### <a name="shell-os-user-interface"></a>Shell (interfaz de usuario del sistema operativo)

El shell de Surface Hub está diseñado desde el principio de modo optimizado para pantallas de gran tamaño y táctiles. No usa el mismo shell que Windows 10 Enterprise.

*Directivas de la organización que esto puede afectar:* 

- La configuración relacionada con los controles el shell de Windows 10 Enterprise no se aplica s Surface Hub.

### <a name="lock-screen-and-screensaver"></a>Protector de pantalla y pantalla de bloqueo

Surface Hub no tiene pantalla de bloqueo ni protector de pantalla, pero tiene una característica similar denominada la pantalla de inicio de sesión. La pantalla de inicio muestra las reuniones programadas el calendario de la cuenta del dispositivo y puntos de entrada fácil a las aplicaciones principales de Surface Hub - Skype Empresarial, la Pizarra interactiva y Conectar.

*Directivas de la organización que esto puede afectar:* 

- La configuración de la pantalla de bloqueo, el tiempo de espera de pantalla y el protector de pantalla no se aplican a Surface Hub.

### <a name="user-sign-in"></a>Inicio de sesión de usuario

Surface Hub está diseñado para usarse en espacios comunes, como las salas de reunión. A diferencia de los equipos con Windows, cualquier persona puede acercarse y usar Surface Hub sin iniciar sesión. Para habilitar esta funcionalidad común, Surface Hub no admite el inicio de sesión de Windows, mientras que Windows 10 Enterprise sí lo permite (por ejemplo, iniciar sesión con un usuario en el sistema operativo y usar esas credenciales en todo el sistema operativo). En su lugar, siempre hay un usuario local conectado automáticamente y con privilegios bajos que ha iniciado sesión en Surface Hub. No es compatible con el inicio de sesión de cualquier usuario adicional, incluyendo los usuarios administradores (por ejemplo, cuando un usuario administrador inicia sesión, no han iniciado sesión en el sistema operativo).

Los usuarios pueden iniciar sesión en Surface Hub, pero no iniciarán sesión en el sistema operativo. Por ejemplo, cuando un usuario inicia sesión en Aplicaciones o Mi reuniones y archivos, solo tiene acceso a las aplicaciones o servicios, no al sistema operativo. Como resultado, el usuario que inició sesión es capaz de recuperar sus archivos y reuniones personales almacenadas de la nube, y estas credenciales se descartan al activar **Finalizar sesión**.

*Directivas de la organización que esto puede afectar:* 

- Por lo general, Surface Hub usa características de bloqueo en lugar del control de acceso de usuario para aplicar la seguridad. Las directivas relacionadas con los requisitos de contraseña, el inicio de sesión interactivo, las cuentas de usuario y el control de acceso no se aplican a Surface Hub.

### <a name="saving-and-browsing-files"></a>Guardar y explorar archivos

Los usuarios tienen acceso a un conjunto limitado de directorios en Surface Hub:
- Música
- Vídeos
- Documentos
- Imágenes
- Descargas

Los archivos que se guardan localmente en estos directorios se eliminan cuando los usuarios presionen **Terminar la sesión**. Para guardar contenido creado durante una reunión, los usuarios deben guardar los archivos en una unidad USB o en OneDrive.

*Directivas de la organización que esto puede afectar:* - Las directivas relacionadas con los permisos de acceso y la propiedad de archivos y carpetas no se aplican a Surface Hub. Los usuarios no pueden explorar ni guardar archivos en directorios del sistema ni carpetas de red.

## <a name="applications"></a>Aplicaciones

### <a name="default-applications"></a>Aplicaciones predeterminadas

Con pocas excepciones, las aplicaciones predeterminadas para la Plataforma universal de Windows (UWP) de Surface Hub también están disponibles en los equipos con Windows 10.

Aplicaciones para UWP instaladas previamente en Surface Hub:

- Alarmas y reloj
- Calculadora
- Conectar
- Excel Mobile
- Centro de opiniones
- Explorador de archivos
- Introducción
- Mapas
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- Fotos
- PowerPoint Mobile
- Configuración
- Tienda
- Sugerencias
- Word Mobile

*Directivas de la organización que esto puede afectar:* 

- Usa las directrices de Windows 10 Enterprise para determinar las características y los requisitos de red de las aplicaciones predeterminadas en Surface Hub.

### <a name="installing-apps-drivers-and-services"></a>Instalar aplicaciones, controladores y servicios

Para ayudar a mantener la naturaleza del dispositivo, Surface Hub solo admite la instalación de aplicaciones para la Plataforma universal de Windows (UWP) y no admite la instalación de aplicaciones, servicios ni controladores clásicos de Win32. Asimismo, solo los administradores tienen acceso para instalar aplicaciones para UWP.

*Directivas de la organización que esto puede afectar:* 

- Los empleados solo pueden usar las aplicaciones que hayan instalado los administradores, lo que ayuda a mitigar contra un uso no intencionado. Surface Hub no admite la instalación de los agentes de Win32 que la mayoría de las herramientas de administración y supervisión de PC tradicionales.

## <a name="security-and-lockdown"></a>Seguridad y bloqueo

Para que Surface Hub se use en espacios comunes, como reuniones de las salas, su sistema operativo personalizado implementa muchas de las características de seguridad y bloqueo disponibles en Windows 10. Para obtener más información, vea [Surface Hub de seguridad](surface-hub-security.md)

Surface Hub implementa las siguientes características de seguridad de Windows 10:

- [Arranque seguro](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Control de aplicaciones de Windows Defender y protección basada en la virtualización de la integridad del código](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Directivas de restricción de aplicaciones con AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [Cifrado de unidad BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Módulo de plataforma de confianza (TPM)] (/security/information-protection/tpm/trusted-platform-module-overview
- [Antivirus de Microsoft Defender en Windows](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- [Control de cuentas de usuario (UAC)](/windows/security/identity-protection/user-account-control/user-account-control-overview) para acceder a la aplicación Configuración

Las siguientes características de Surface Hub proporcionan seguridad adicional:

- Firmware UEFI personalizado
- El shell y el menú Inicio personalizados limitan al dispositivo a las funciones de reunión
- El Explorador de archivos personalizado solo concede acceso a los archivos y las carpetas de Mis documentos
- La aplicación Configuración personalizada solo permite a los administradores modificar la configuración del dispositivo
- La descarga de controladores Plug and Play avanzados está deshabilitada

*Directivas de la organización que esto puede afectar:*

- Ten en cuenta las siguientes características al realizar la evaluación de seguridad de Surface Hub.

## <a name="management"></a>Administración

### <a name="device-settings"></a>Configuración de dispositivo

Las opciones del dispositivo se pueden configurar a través de la aplicación Configuración. La aplicación Configuración está personalizada para Surface Hub, pero también contiene muchas de las opciones de configuración familiares de Windows 10 Escritorio. Un mensaje de Control de cuentas de usuario (UAC) aparece en la pantalla cuando se abre la aplicación Configuración para comprobar las credenciales del administrador, pero este proceso no inicia la sesión del administrador.

*Directivas de la organización que esto puede afectar:* 

- Los empleados pueden usar Surface Hub para reuniones, pero no pueden modificar las opciones de configuración del dispositivo. Además de las características de bloqueo, esto garantiza que los empleados solo usarán el dispositivo para las funciones de reunión.

### <a name="administrative-features"></a>Características de administración

Las características administrativas de Windows 10 Enterprise, como Microsoft Management Console, Ejecutar, Símbolo del sistema, PowerShell, Editor del registro, Visor de eventos y Administrador de tareas administrativas, no se admiten en Surface Hub. La aplicación Configuración contiene todas las características administrativas disponibles localmente en Surface Hub.

### <a name="remote-management-and-monitoring"></a>Administración y supervisión remotas

Surface Hub admite la administración remota a través de soluciones [](/mem/intune/) de administración de dispositivos móviles (MDM), como Microsoft Intune y supervisión a través [de Azure Monitor.](/azure/azure-monitor/) 

*Directivas de la organización que esto puede afectar:* 

- Surface Hub no admite la instalación de los agentes de Win32 que requiere la mayoría de las herramientas de administración y supervisión de equipos tradicionales, como System Center Operations Manager.

### <a name="group-policy"></a>Directiva de grupo

Surface Hub no admite Windows de grupo, incluida la auditoría. En su lugar, usa MDM para aplicar directivas a Surface Hub. Para obtener más información sobre MDM, consulta [Administrar la configuración con un proveedor de MDM (Surface Hub)](manage-settings-with-mdm-for-surface-hub.md).

*Directivas de la organización que esto puede afectar:* 

- Usa MDM para administrar Surface Hub en lugar de directivas de grupo.

### <a name="remote-assistance"></a>Asistencia remota

Surface Hub no admite la asistencia remota.

*Directivas de la organización que esto puede afectar:* 

- Las directivas relacionadas con la asistencia remota no se aplican a Surface Hub.

## <a name="network"></a>Red

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>Unirse a un dominio y unirse Azure Active Directory (Azure AD) 

Surface Hub usa la unión a un dominio y la unión a Azure AD principalmente para proporcionar un grupo de administradores respaldados por el directorio. No se admite la combinación híbrida. Los usuarios no pueden iniciar sesión con una cuenta de dominio. Para obtener más información, consulta [Administración del grupo de administradores](admin-group-management-for-surface-hub.md).

*Directivas de la organización que esto puede afectar:* 

- La configuración de directiva de grupo no se aplica cuando Surface Hub se une al dominio. La configuración de directiva relacionada con la pertenencia a un dominio no se aplica a Surface Hub.

### <a name="accessing-domain-resources"></a>Acceder a los recursos de dominio

Los usuarios pueden iniciar sesión en Microsoft Edge para acceder a sitios de intranet y recursos en línea (como Office 365). Si Surface Hub está configurado con una cuenta de dispositivo, el sistema la usa para acceder a Exchange y Skype Empresarial. Sin embargo, Surface Hub no admite el acceso a recursos de dominio, como recursos compartidos de archivos e impresoras.

*Directivas de la organización que esto puede afectar:* 

- Las directivas relacionadas con el acceso a objetos de dominio no se aplican a Surface Hub.

### <a name="diagnostic-data"></a>Datos de diagnóstico

El sistema de operativo de Surface Hub usa el componente Experiencia del usuario y telemetría asociadas de Windows 10 para recopilar y transmitir datos de diagnóstico. Para obtener más información, consulta [Configurar los datos de diagnóstico de Windows en la organización](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

*Directivas de la organización que esto puede afectar:* 

- Configura los niveles de datos de diagnóstico de Surface Hub de la misma manera que lo harías para Windows 10 Enterprise.

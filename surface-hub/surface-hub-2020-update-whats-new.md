---
title: Novedades de las actualizaciones de Windows 10 Team 2020
description: Consulte las novedades de la actualización más reciente del sistema operativo Surface Hub, Windows 10 Team actualización de 2020.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: 995766eb216051de270a387c15c96ee42dd008a3
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497963"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Novedades de las actualizaciones de Windows 10 Team 2020

Surface Hub ventajas de las actualizaciones periódicas que ofrecen nuevas características y funcionalidad. La actualización de 2020 (20H2) para Windows 10 Team y, posteriormente, la actualización 1 & update 2, ofrecen mejoras significativas en la implementación y la capacidad de administración de dispositivos junto con las características de Windows más recientes.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team 2020 Update 2 

### <a name="gcc-high-support"></a>compatibilidad con GCC alta

Después de instalar esta actualización ([KB5010415](https://support.microsoft.com/help/5010415) o un Windows CU posterior), los Surface Hubs se admiten en entornos de GCC High. En este momento, se necesitan [pasos adicionales ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) para que el cliente de Salas de Teams se conecte correctamente a GCC inquilinos altos.

### <a name="support-for-surface-hub-2-smart-camera"></a>Compatibilidad con Surface Hub 2 cámaras inteligentes

La cámara inteligente Surface Hub 2 con tecnología de inteligencia artificial está optimizada para equipos híbridos, lo que permite a los participantes remotos ver a las personas interactuar con el contenido en el Surface Hub mientras ven a todos los demás en la sala.  Para más información, consulte [Instalar y administrar Surface Hub cámara inteligente 2](surface-hub-2-smart-camera.md). 

### <a name="support-for-progressive-web-apps-pwas"></a>Compatibilidad con la Web Apps progresiva (PPA)

Los administradores pueden instalar PPA de forma remota en Surface Hubs mediante un proveedor de administración de dispositivos móviles (MDM) que aplique un paquete de aprovisionamiento. Para más información, consulte [Instalación de Web Apps progresiva en Surface Hub](install-pwa-surface-hub.md). 

### <a name="ease-of-access-updates"></a>Actualizaciones de facilidad de acceso

Los usuarios pueden ajustar la configuración de facilidad de acceso durante una sesión de Surface Hub y cerrar las aplicaciones como lo hacen en otras versiones de Windows 10 o Windows 11. 

- **Facilidad de acceso**. Los usuarios pueden ajustar la siguiente configuración sin iniciar sesión: Pantalla, Cursor de texto, Lupa, Contraste alto, Narrador, Subtítulos y Teclado. 
- **Interfaz de usuario familiar para aplicaciones**. Los usuarios pueden cerrar aplicaciones en Surface Hub seleccionando el botón Cerrar de la esquina superior derecha de la aplicación. Esto elimina la necesidad de cerrar las aplicaciones arrastrándolas a la parte inferior de la pantalla de Surface Hub. (Nota: Esta funcionalidad estará disponible en el explorador Edge como parte de la próxima actualización de Edge, programada para marzo de 2022). 

Para obtener más información, consulte [Ajustar la configuración de facilidad de acceso en Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Actualizaciones del administrador

- **Visor de eventos**. Los administradores pueden acceder a la Windows Visor de eventos directamente desde la aplicación de Configuración. 
- **Nueva configuración de directiva de administración de dispositivos móviles (MDM).** Los nuevos proveedores de servicios de configuración (CSP) incluyen:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Para más información, consulte [Configuración de cuentas de administrador no globales en Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team 2020 Update 1

### <a name="support-for-new-teams-rooms-application"></a>Compatibilidad con la nueva aplicación de Salas de Teams

Después de instalar esta actualización ([KB5005101](https://support.microsoft.com/help/5005101) o un Windows CU posterior), Surface Hubs admite una actualización automática al nuevo [cliente de Salas de Teams](surface-hub-teams-rooms.md) a través de Windows Update.

### <a name="support-for-new-whiteboard-application"></a>Compatibilidad con la nueva aplicación whiteboard

Después de instalar esta actualización, Surface Hubs admite una actualización automática (cuando esté disponible) a la nueva [aplicación pizarra](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) a través de Microsoft Store actualizaciones.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Nuevo explorador Microsoft Edge instalado de forma predeterminada

Después de instalar esta actualización, Surface Hubs reemplazará automáticamente su explorador Microsoft Edge (versión anterior) por el nuevo explorador Edge basado en Chromium.  Para más información, consulte [Administración de Microsoft Edge en Surface Hub](surface-hub-install-chromium-edge.md). Edge Legacy ya no está disponible en Windows 10 Team después de la instalación de esta actualización o un Windows CU posterior.


## <a name="windows-10-team-2020-update-20h2"></a>Actualización de Windows 10 Team 2020 (20H2)

### <a name="deployment-and-manageability"></a>Implementación y capacidad de administración

- **Autenticación moderna para cuentas de dispositivo en la nube**. Surface Hub admite la autenticación basada en servicios web de Exchange (EWS) y la biblioteca de autenticación de Active Directory (ADAL) para conectarse a Exchange, lo que permite a los clientes dejar de usar la autenticación básica. Para más información, consulte [Autenticación moderna en Surface Hub](surface-hub-modern-auth.md).
- **Más de 20 configuraciones de directiva MDM nuevas y actualizadas**.  Esta configuración de directiva proporciona a los administradores de TI un control mejorado sobre varias configuraciones de dispositivo, incluidas las actualizaciones de aplicaciones de la Microsoft Store, la configuración de proyección inalámbrica, como Miracast a través de la infraestructura, la configuración de red, como la calidad del servicio y la autenticación por cable 802.1x, y la nueva configuración relacionada con la privacidad y el RGPD. Los nuevos CSP incluyen:

  - [Cuentas de CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Csp de Wifi](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Para obtener más información, consulte:

- [Los CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>dispositivos unidos a Azure Active Directory

- **Inicio de sesión único (SSO) para dispositivos unidos a Azure AD**. Cuando los usuarios inician sesión con sus credenciales de Microsoft 365 en **Mis reuniones y archivos**, sus credenciales fluyen sin problemas de aplicación a aplicación, incluidas Microsoft 365 experiencias en el explorador.
- **Acceso condicional (CA) para dispositivos unidos a Azure AD**. Los administradores de TI pueden controlar el acceso de los usuarios a los recursos de la organización desde Azure AD Surface Hubs unidos mediante la asignación de directivas de dispositivo según sus requisitos de cumplimiento y seguridad corporativos.
- **Compatibilidad con administradores no globales para dispositivos unidos a Azure AD**. Los clientes pueden elegir un conjunto más granular de administradores dentro de su jerarquía de administración para administrar Surface Hub. Para más información, consulte [Configuración de cuentas de administrador no globales en Surface Hub](surface-hub-2s-nonglobal-admin.md).

### <a name="inking-improvements"></a>Mejoras de entrada manuscrita

- **Compatibilidad con la entrada de lápiz dual en Surface Hub 2S**.  Use la pizarra y colabore en paralelo en Surface Hub 2S con dos Surface Hub 2 plumas. Cualquier actualización de hardware del sistema instalada después de actualizar a Windows 10 Team 2020 agregará compatibilidad con firmware para este escenario.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado de forma predeterminada**. Microsoft Teams es la aplicación predeterminada para reuniones, llamadas y colaboración en nuevos dispositivos Surface Hub, que se pueden cambiar o configurar a través de MDM o directamente en Surface Hub mediante la aplicación Configuración. Para más información, consulte [Implementación de Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Compatibilidad con la unión por proximidad con Microsoft Teams**.  Unirse a proximidad permite a los usuarios realizar llamadas Microsoft Teams programadas en un Surface Hub cercano mediante su portátil o teléfono.  También permite a los usuarios realizar la transición de una reunión en curso a una Surface Hub cercana. Windows 10 Team actualización de 2020 agrega compatibilidad con mobile Administración de dispositivos (MDM) para configurar la combinación de proximidad. Para obtener más información, consulte:

  - [blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Administrar la configuración de Microsoft Teams en Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Compatibilidad con reuniones coordinadas con Microsoft Teams**. En las salas de reuniones que cuentan con un Surface Hub y un dispositivo Microsoft Teams Room, o espacios con dos dispositivos Surface Hub, las reuniones coordinadas permiten a los usuarios aprovechar rápidamente ambos dispositivos durante una reunión de Microsoft Teams. Los usuarios pueden unirse a una reunión desde cualquier dispositivo con un solo toque y maximizar el espacio real de pantalla mostrando fuentes de vídeo en un dispositivo y una pizarra digital o contenido en el otro. Windows 10 Team actualización de 2020 agrega compatibilidad con mobile Administración de dispositivos (MDM) para configurar reuniones coordinadas y la característica se publicará posteriormente como una actualización Microsoft Teams a través de Microsoft Store. Para más información, consulte [Configurar reuniones coordinadas con Salas de Microsoft Teams y Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>Seguridad

- **Inicio de sesión sin contraseña mediante claves de seguridad FIDO2** Con las claves de seguridad FIDO2, los usuarios pueden iniciar sesión rápidamente en Surface Hub sin escribir nombres de usuario y contraseñas. En combinación con Single Sign-On (SSO), esta característica proporciona una autenticación rápida y sin problemas a archivos, aplicaciones y sitios web durante una reunión. Para más información, consulte [Configuración del inicio de sesión sin contraseña en Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Mejoras en el inicio de sesión sin contraseña mediante Microsoft Authenticator**.  En el caso de las organizaciones que usan Azure AD, los usuarios pueden iniciar sesión con la aplicación Microsoft Authenticator. Además, los usuarios pueden iniciar sesión con sus alias de correo electrónico preferidos en Azure AD o su nombre principal de usuario (UPN). Para más información, consulte [Inicio de sesión en Surface Hub con Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Obtén más información

- [Windows 10 Team actualización 1 de 2020 publicada en todos los Surface Hubs](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team actualización de 2020 disponible el 27 de octubre](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Instalar la actualización 2020 de Windows 10 Team](surface-hub-2020-update.md)

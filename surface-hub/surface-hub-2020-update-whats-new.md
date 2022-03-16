---
title: Novedades de las actualizaciones Windows 10 Team 2020
description: Echa un vistazo a las novedades de la última actualización del sistema operativo Surface Hub, Windows 10 Team 2020 Update.
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
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448274"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Novedades de las actualizaciones Windows 10 Team 2020

Surface Hub ventajas de las actualizaciones periódicas que ofrecen nuevas características y funcionalidades. La actualización de 2020 (20H2) a Windows 10 Team y, posteriormente, la actualización 1 & Update 2, proporcionan mejoras significativas en la implementación y la facilidad de administración de dispositivos junto con las características Windows 10 más recientes.

## <a name="windows-10-team-2020-update-2"></a>Windows 10 Team 2020 Update 2 

### <a name="gcc-high-support"></a>GCC alta compatibilidad

Después de la instalación de esta actualización ([KB5010415](https://support.microsoft.com/help/5010415) o una Windows CU posterior), los Surface Hub se admiten en GCC entornos high. En este momento, [se necesitan pasos ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) adicionales para que Salas de Teams cliente se conecte correctamente a GCC inquilinos high.

### <a name="ease-of-access-updates"></a>Actualizaciones de facilidad de acceso

Los usuarios pueden ajustar la configuración de facilidad de acceso durante una sesión Surface Hub sesión y cerrar aplicaciones como lo hacen en otras versiones de Windows 10. 

- **Facilidad de acceso**. Los usuarios pueden ajustar la siguiente configuración sin iniciar sesión: Pantalla, Cursor de texto, Lupa, Contraste alto, Narrador, Títulos cerrados y Teclado. 
- **Interfaz de usuario familiar para aplicaciones**. Los usuarios pueden cerrar aplicaciones en Surface Hub seleccionando el botón Cerrar en la esquina superior derecha de la aplicación. Esto elimina la necesidad de cerrar aplicaciones arrastrándolas a la parte inferior de la pantalla Surface Hub pantalla. (Nota: Esta funcionalidad estará disponible en el explorador perimetral como parte de la próxima actualización perimetral, programada para marzo de 2022). 

Para obtener más información, consulta [Ajustar la configuración de acceso fácil en Surface Hub](accessibility-surface-hub.md).

### <a name="administrator-updates"></a>Actualizaciones de administrador

- **Visor de eventos**. Los administradores pueden acceder al Windows de eventos directamente desde la Configuración aplicación. 
- **Nueva configuración de directiva de administración de dispositivos móviles (MDM**). Los nuevos proveedores de servicios de configuración (SPC) incluyen:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

Para obtener más información, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).


## <a name="windows-10-team-2020-update-1"></a>Windows 10 Team 2020 Update 1

### <a name="support-for-new-teams-rooms-application"></a>Compatibilidad con nueva Salas de Teams aplicación

Después de la instalación de esta actualización ([KB5005101](https://support.microsoft.com/help/5005101) o una Windows CU posterior), Surface Hubs admite una actualización automática al nuevo cliente [Salas de Teams](surface-hub-teams-rooms.md) a través de Windows Update.

### <a name="support-for-new-whiteboard-application"></a>Compatibilidad con nueva aplicación de pizarra

Después de instalar esta actualización, los Surface Hub admiten una actualización automática (cuando esté disponible) a la nueva aplicación [Pizarra](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) a través de Microsoft Store actualizaciones.

### <a name="new-microsoft-edge-browser-installed-by-default"></a>Nuevo explorador Microsoft Edge instalado de forma predeterminada

Después de la instalación de esta actualización, Surface Hubs reemplazará automáticamente su Microsoft Edge (versión anterior) por el nuevo explorador perimetral Chromium basado en dispositivos perimetrales.  Para obtener más información, consulte [Manage Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md). Edge Legacy ya no está disponible en Windows 10 Team después de la instalación de esta actualización o una Windows CU posterior.


## <a name="windows-10-team-2020-update-20h2"></a>Actualización de Windows 10 Team 2020 (20H2)

### <a name="deployment-and-manageability"></a>Implementación y facilidad de administración

- **Autenticación moderna para cuentas de dispositivos en la nube**. Surface Hub admite la autenticación basada en Exchange Web Services (EWS) y la biblioteca de autenticación de Active Directory (ADAL) para conectarse a Exchange, lo que permite a los clientes dejar de usar la autenticación básica. Para obtener más información, consulte [Modern authentication on Surface Hub](surface-hub-modern-auth.md).
- **Más de 20 configuraciones de directiva MDM nuevas y actualizadas**.  Estas configuraciones de directiva dan a los administradores de TI un control mejorado sobre la configuración de varios dispositivos, incluidas las actualizaciones de aplicaciones de Microsoft Store, la configuración de proyección inalámbrica, como Miracast sobre la infraestructura, la configuración de red, como la calidad del servicio y la autenticación por cable 802.1x, y la nueva configuración relacionada con la privacidad y el RGPD. Los nuevos SPC incluyen:

  - [Cuentas de CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

Para obtener más información, vea:

- [CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory unidos

- **Inicio de sesión único (SSO) para dispositivos Azure AD unidos**. Cuando los usuarios inician sesión con sus Microsoft 365 a Mis **** reuniones y los archivos sus credenciales fluyen sin problemas de la aplicación a la aplicación, incluidas Microsoft 365 experiencias en el explorador.
- **Acceso condicional (CA) para Azure AD dispositivos unidos**. Los administradores de TI pueden controlar el acceso de los usuarios a los recursos de la organización Azure AD dispositivos Surface Hub unidos mediante la asignación de directivas de dispositivo según sus requisitos de seguridad y cumplimiento corporativos.
- **Compatibilidad con administradores no globales para Azure AD dispositivos unidos**. Los clientes pueden elegir un conjunto más detallado de administradores dentro de su jerarquía de administración para administrar Surface Hub. Para obtener más información, consulte [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

### <a name="inking-improvements"></a>Mejoras de entrada en la entrada

- **Compatibilidad con la entrada de lápiz dual en Surface Hub 2S**.  Use la pizarra y colabore en paralelo en Surface Hub 2S con dos Surface Hub 2 lápices. Cualquier actualización de hardware del sistema instalada después de actualizar a Windows 10 Team 2020 agregará compatibilidad de firmware para este escenario.

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado de forma predeterminada**. Microsoft Teams se incluye como la aplicación predeterminada para reuniones, llamadas y colaboración en nuevos dispositivos Surface Hub, que se pueden cambiar o configurar a través de MDM o directamente en Surface Hub mediante la aplicación Configuración. Para obtener más información, vea [Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Compatibilidad con la unión de proximidad con Microsoft Teams**.  La unión de proximidad permite a los usuarios realizar llamadas Microsoft Teams en un equipo Surface Hub con su portátil o teléfono.  También permite a los usuarios realizar la transición de una reunión en curso a una reunión Surface Hub. Windows 10 Team 2020 Update agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar la unión de proximidad. Para obtener más información, vea:

  - [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Administrar la configuración de Microsoft Teams en Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Compatibilidad con reuniones coordinadas con Microsoft Teams**. En las salas de reuniones que cuentan con un Surface Hub y un dispositivo de sala de Microsoft Teams, o espacios con dos dispositivos Surface Hub, las reuniones coordinadas permiten a los usuarios aprovechar rápidamente ambos dispositivos durante una Microsoft Teams reunión. Los usuarios pueden unirse a una reunión desde cualquier dispositivo con un solo toque y maximizar la propiedad de pantalla mostrando fuentes de vídeo en un dispositivo y una pizarra digital o contenido en el otro. Windows 10 Team actualización de 2020 agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar reuniones coordinadas y la característica se lanzará posteriormente como una actualización Microsoft Teams a través de Microsoft Store. Para obtener más información, vea [Set up Coordinated Meetings with Salas de Microsoft Teams and Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### <a name="security"></a>Seguridad

- **Inicio de sesión sin contraseña con claves de seguridad FIDO2** Con las claves de seguridad FIDO2, los usuarios pueden iniciar sesión rápidamente en Surface Hub sin escribir nombres de usuario y contraseñas. Combinada con single Sign-On (SSO), esta característica proporciona una autenticación rápida y sin problemas a archivos, aplicaciones y sitios web durante una reunión. Para obtener más información, vea [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Mejoras en el inicio de sesión sin contraseña mediante Microsoft Authenticator**.  Para las organizaciones que usan Azure AD, los usuarios pueden iniciar sesión con la Microsoft Authenticator aplicación. Además, los usuarios pueden iniciar sesión con sus alias de correo electrónico preferidos en Azure AD, así como su nombre principal de usuario (UPN). Para obtener más información, vea [Iniciar sesión para Surface Hub con Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Obtén más información

- [Windows 10 Team 2020 Update 1 lanzado a todos los Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team actualización de 2020 disponible el 27 de octubre](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [Instalar la actualización 2020 de Windows 10 Team](surface-hub-2020-update.md)

---
title: Novedades de la actualización Windows 10 Team 2020
description: Consulte las novedades de la última actualización del sistema operativo Surface Hub, Windows 10 Team 2020 Update.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: fcd7df80615e406a1dab061b473ef7f3dbd065e1
ms.sourcegitcommit: 38e98402ab1380521029e792a83c00391997e1fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2021
ms.locfileid: "12089272"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Novedades de la actualización Windows 10 Team 2020

Windows 10 Team 2020 Update ofrece mejoras importantes en la implementación y la facilidad de administración de dispositivos, junto con las características Windows 10 más recientes.

## <a name="deployment-and-manageability"></a>Implementación y facilidad de administración

- **Autenticación moderna para cuentas de dispositivo en la nube.** Surface Hub admite la autenticación basada en Exchange Web Services (EWS) y la biblioteca de autenticación de Active Directory (ADAL) para conectarse a Exchange, lo que permite a los clientes dejar de usar la autenticación básica. Para obtener más información, vea [Modern authentication on Surface Hub](surface-hub-modern-auth.md).
- **Más de 20 configuraciones**de directiva de administración de dispositivos móviles (MDM) nuevas y actualizadas.  Estas configuraciones de directiva dan a los administradores de TI un control mejorado sobre la configuración de varios dispositivos, incluidos: actualizaciones de aplicaciones de Microsoft Store, configuración de proyección inalámbrica como Miracast sobre infraestructura, configuración de red como calidad de servicio y autenticación por cable 802.1x y nueva configuración relacionada con la privacidad y el RGPD. Los nuevos proveedores de servicios de configuración (SPC) incluyen: 

  - [Cuentas de CSP](/windows/client-management/mdm/accounts-csp) 
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp) 

Para obtener más información, vea: 
- [CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md)

## <a name="azure-active-directory-joined-devices"></a>Azure Active Directory Dispositivos unidos

- **Inicio de sesión único (SSO) para Azure AD dispositivos unidos.** Cuando los usuarios inician sesión con sus credenciales de Microsoft 365 en "Mis reuniones y archivos", sus credenciales de usuario fluyen sin problemas de una aplicación a otra, incluidas Microsoft 365 experiencias en el explorador.
- **Acceso condicional (CA) para Azure AD dispositivos unidos.** Los administradores de TI pueden controlar el acceso de los usuarios a los recursos de la organización Azure AD surface hubs unidos mediante la asignación de directivas de dispositivos de acuerdo con sus requisitos de seguridad y cumplimiento corporativos.
- **Compatibilidad con administradores no globales para Azure AD dispositivos unidos.** Los clientes pueden elegir un conjunto más detallado de administradores dentro de su jerarquía de administración para administrar Surface Hub. Para obtener más información, vea [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

## <a name="browser-and-pen"></a>Explorador y lápiz

- **Compatibilidad con el nuevo Microsoft Edge**. Microsoft Edge se ha reconstruido para lograr un rendimiento de compatibilidad óptimo, seguridad y privacidad. Para obtener más información, vea [Install and configure the new Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md).
- **Entrada de lápiz dual en Surface Hub 2S**.   Los usuarios pueden hacer pizarras y colaborar en paralelo en Surface Hub 2S con dos Surface Hub 2 lápices. Las actualizaciones de firmware necesarias para habilitar la entrada de lápiz dual se liberarán con una actualización posterior.

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams instalado de forma predeterminada**.        Microsoft Teams se incluye como la aplicación predeterminada reuniones, llamadas y colaboración en nuevos dispositivos Surface Hub que se pueden cambiar o configurar a través de MDM o directamente en Surface Hub mediante la aplicación Configuración. Para obtener más información, [vea Microsoft Teams introducción a la implementación.](/microsoftteams/deploy-overview)
- **Compatibilidad con la unión de proximidad con Microsoft Teams**.  Proximity Join permite a los usuarios realizar llamadas de Microsoft Teams programadas en un Surface Hub cercano con su portátil o teléfono, o bien realizar una transición sin problemas de una reunión en curso a un Surface Hub. Windows 10 Team actualización de 2020 agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar la unión de proximidad. Para obtener más información, vea: 

  - [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Administrar la configuración de Microsoft Teams en Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Compatibilidad con reuniones coordinadas con Microsoft Teams**. En las salas de reuniones que cuentan con un Surface Hub y un dispositivo de sala de Microsoft Teams, o espacios con dos dispositivos Surface Hub, las reuniones coordinadas permiten a los usuarios aprovechar fácilmente ambos dispositivos durante una reunión Microsoft Teams. Con un solo toque, los usuarios pueden unirse a una reunión desde cualquier dispositivo y maximizar la propiedad de pantalla mostrando fuentes de vídeo en un dispositivo y una pizarra digital o contenido en el otro. Windows 10 Team 2020 Update agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar reuniones coordinadas y la característica se lanzará posteriormente como una actualización Microsoft Teams a través de Microsoft Store. Para obtener más información, vea [Set up Coordinated Meetings with Salas de Microsoft Teams and Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

## <a name="security"></a>Seguridad

- **Inicio de sesión sin contraseña con claves de seguridad FIDO2**     Con las claves de seguridad fido2, los clientes pueden iniciar sesión de forma rápida y Surface Hub sin tener que escribir nombres de usuario y contraseñas. Combinada con single Sign-On (SSO), esta característica proporciona una autenticación rápida y sin problemas a archivos, aplicaciones y sitios web durante una reunión. Para obtener más información, vea [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Mejoras en el inicio de sesión sin contraseña mediante Microsoft Authenticator**.  Para las organizaciones que usan Azure AD, los usuarios pueden usar la aplicación Microsoft Authenticator para iniciar sesión sin tener que escribir nombres de usuario y contraseñas. Además, los usuarios pueden iniciar sesión con sus alias de correo electrónico preferidos en Azure AD además de su nombre principal de usuario (UPN). Para obtener más información, vea [Sign in to Surface Hub with Microsoft Authenticator](surface-hub-authenticator-app.md).

## <a name="learn-more"></a>Obtén más información

- [Windows 10 Team actualización 2020 1 publicada en todos los Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Instalar la actualización 2020 de Windows 10 Team](surface-hub-2020-update.md)  
 
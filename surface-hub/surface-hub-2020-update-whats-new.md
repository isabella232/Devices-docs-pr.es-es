---
title: Novedades de Windows10 Team 2020
description: Echa un vistazo a las novedades de la actualización más reciente del sistema operativo Surface Hub, Windows 10 Team 2020 Update.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312056"
---
# Novedades de Windows10 Team 2020

La actualización de Windows 10 Team 2020 ofrece mejoras importantes en la implementación y la capacidad de administración de dispositivos, junto con las últimas características de Windows 10.

##  Implementación y capacidad de administración

- **Autenticación moderna para cuentas de dispositivo en la nube.** Surface Hub admite la autenticación basada en los servicios Web Exchange (EWS) y la Biblioteca de autenticación de Active Directory (ADAL) para conectarse a Exchange, lo que permite a los clientes dejar de usar la autenticación básica. Para obtener más información, consulta [Autenticación moderna en Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)
- **Más de 20 directivas de administración de dispositivos móviles (MDM) nuevas y actualizadas.**      Estas directivas dan a los administradores de TI un control mejorado sobre la configuración de varios dispositivos, como las actualizaciones de aplicaciones de Microsoft Store, la configuración de proyección inalámbrica como Miracast sobre la infraestructura, la configuración de red como la calidad de servicio y la autenticación por cable 802.1x, y la nueva configuración relacionada con la privacidad y el RGPD. Para obtener más información, consulte: 
- [Administrar Surface Hub 2S con Microsoft Intune.](surface-hub-2s-manage-intune.md)
- [CSP de directivas admitidas por Microsoft Surface Hub](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  Dispositivos unidos a Azure Active Directory

- **Inicio de sesión único (SSO) para dispositivos unidos a Azure AD.** Cuando los usuarios inician sesión con sus credenciales de Microsoft 365 en "Mis reuniones y archivos", sus credenciales de usuario fluyen sin problemas de una aplicación a otra, incluidas las experiencias de Microsoft 365 en el explorador.
- **Acceso condicional (CA) para dispositivos unidos a Azure AD.**       Los administradores de TI pueden implementar directivas de seguridad de nivel de dispositivo en su Surface Hub unido a Azure AD para controlar el acceso a los recursos de la organización de acuerdo con los requisitos de seguridad y cumplimiento corporativos.
- **Compatibilidad con administradores no globales para dispositivos unidos a Azure AD.** Los clientes pueden elegir un conjunto de administradores más granular dentro de su jerarquía de administradores para administrar Surface Hub. Para obtener más información, consulta [Configurar cuentas de administrador no globales en Surface Hub 2S.](surface-hub-2s-nonglobal-admin.md)


## Explorador y lápiz

- **Compatibilidad con el nuevo Microsoft Edge**. Microsoft Edge se ha reconstruido para obtener un rendimiento de compatibilidad óptimo, seguridad y privacidad. Para obtener más información, consulta [Instalar y configurar el nuevo Microsoft Edge en Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)
- - **Entrada de lápiz dual en Surface Hub 2S.**   Los usuarios pueden pizarrar y colaborar en paralelo en Surface Hub 2S con dos lápices de Surface Hub 2. Las actualizaciones de firmware necesarias para habilitar la entrada de lápiz dual se lanzarán con una actualización posterior.

## Microsoft Teams  

- **Microsoft Teams instalado de forma predeterminada.**        Microsoft Teams se incluye como la aplicación predeterminada reuniones, llamadas y colaboración en nuevos dispositivos Surface Hub que se pueden cambiar o configurar a través de MDM o directamente en Surface Hub mediante la aplicación Configuración. Para obtener más información, vea [Implementar Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)
- **Soporte técnico para unirse a la proximidad con Microsoft Teams.**  La unión a la proximidad permite a los usuarios realizar llamadas programadas de Microsoft Teams en un Surface Hub cercano con su portátil o teléfono, o realizar una transición sin problemas de una reunión en curso a un Surface Hub cercano. Windows 10 Team 2020 Update agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar la unión de proximidad. Para obtener más información, consulte: 

  - [Blog de Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833). 
  - [Administrar la configuración de Microsoft Teams en Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **Soporte técnico para reuniones coordinadas con Microsoft Teams.** En las salas de reuniones que cuentan con un dispositivo Surface Hub y una sala de Microsoft Teams, o espacios con dos dispositivos Surface Hub, las reuniones coordinadas permiten a los usuarios aprovechar fácilmente ambos dispositivos durante una reunión de Microsoft Teams. Con una sola pulsación, los usuarios pueden unirse a una reunión desde cualquier dispositivo y maximizar el espacio de la pantalla mostrando fuentes de vídeo en un dispositivo y una pizarra digital o contenido en el otro. Windows 10 Team 2020 Update agrega compatibilidad con administración de dispositivos móviles (MDM) para configurar reuniones coordinadas y la característica se lanzará posteriormente como una actualización de Microsoft Teams a través de Microsoft Store.To obtenga más información, consulta Configurar reuniones coordinadas con salas de Microsoft Teams y [Surface Hub.](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)

## Seguridad

- **Inicio de sesión sin contraseña con claves de seguridad FIDO2**     Con las claves de seguridad FIDO2, los clientes pueden iniciar sesión de forma rápida y sencilla en Surface Hub sin tener que escribir nombres de usuario y contraseñas. Combinada con single Sign-On (SSO), esta característica proporciona una autenticación rápida y sin problemas a archivos, aplicaciones y sitios web durante una reunión. Para obtener más información, consulta Configurar el inicio de sesión sin [contraseña en Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)
- **Mejoras en el inicio de sesión sin contraseña con Microsoft Authenticator**.  Para las organizaciones que usan Azure AD, los usuarios pueden usar la aplicación Microsoft Authenticator para iniciar sesión sin tener que escribir nombres de usuario y contraseñas. Además, los usuarios pueden iniciar sesión con sus alias de correo electrónico preferidos en Azure AD además de su nombre principal de usuario (UPN). Para obtener más información, consulta [Iniciar sesión en Surface Hub con Microsoft Authenticator.](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## Más información

- [Actualización al lanzamiento de Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [Instalar la actualización 2020 de Windows10Team](surface-hub-2020-update.md)  
 
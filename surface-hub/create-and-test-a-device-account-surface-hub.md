---
title: Crear y probar una cuenta del dispositivo (Surface Hub)
description: Este tema explica cómo crear y probar una cuenta del dispositivo que use Microsoft Surface Hub para comunicarse con Microsoft Exchange y Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: crear y probar una cuenta del dispositivo, cuenta del dispositivo, Surface Hub y Microsoft Exchange, Surface Hub y Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: c925cb952c7fd04a86d824dfba99a373c07b313e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472629"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Crear y probar una cuenta del dispositivo (Surface Hub)

La creación de una cuenta de dispositivo Surface Hub (también conocida como cuenta de recursos o buzón de sala) permite que el Surface Hub reciba, apruebe o rechace las convocatorias de reunión y se una a las reuniones.

Una vez aprovisionada la cuenta del dispositivo en un Surface Hub, los usuarios pueden agregar esta cuenta a una invitación a una reunión de la misma manera que invitarían a una sala de conferencias. 

Puede configurar la cuenta de dispositivo durante la [configuración de la experiencia rápida (OOBE).](first-run-program-surface-hub.md) Si es necesario, también puede cambiarlo más adelante en **Configuración** >  **Surface Hub** >  **Accounts**.

## <a name="configuration-overview"></a>Introducción a la configuración

Esta tabla explica los pasos principales y las decisiones de configuración cuando se crea una cuenta del dispositivo.
 
| Paso | Descripción                     |  Propósito                             |
|------|---------------------------------|--------------------------------------|
| 1    | Crear un buzón de sala habilitado para inicio de sesión (Exchange Online o Exchange Server 2016 y versiones posteriores) | Este tipo de buzón permite al dispositivo mantener un calendario de reuniones, recibir convocatorias de reunión y enviar correo. Debe estar habilitado para el inicio de sesión para poder usarse con un Surface Hub. |
| 2    | Configurar las propiedades de buzón de correo | El buzón de correo debe estar configurado con las propiedades correctas para obtener la mejor experiencia de reunión en Surface Hub. Para obtener más información acerca de las propiedades del buzón de correo, consulta [Propiedades del buzón](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Asegúrese de que Exchange servicios web (EWS) está habilitado y que la autenticación multifactor (MFA) está deshabilitada. | El Surface Hub usa EWS para sincronizar su calendario. Si no permite EWS en su entorno de forma predeterminada, el buzón de concentrador tendría que habilitarlo explícitamente. Como el Surface Hub inicia sesión en Exchange en segundo plano sin interacción del usuario, no puede responder a ninguna solicitud interactiva, como MFA. La cuenta de dispositivo que cree debe excluirse de dichos requisitos de autenticación. De lo contrario, Surface Hub no podrá sincronizar el correo ni la información de calendario. |
| 4    | Habilitar la cuenta para Teams o Skype Empresarial (Skype Empresarial Server 2015 y versiones posteriores) | Skype Empresarial o Teams deben estar habilitados para usar características de conferencia, como videollamadas y uso compartido de pantalla. Para obtener más información sobre las licencias que habilitan Teams, consulte [Teams Sala de reuniones licencias](/MicrosoftTeams/rooms/rooms-licensing) y [Teams descripción del servicio](/office365/servicedescriptions/teams-service-description). Las aplicaciones Teams y SfB en el Surface Hub no son compatibles con [las directivas de acceso condicional de Azure AD](/azure/active-directory/conditional-access/concept-conditional-access-policies) que requieren información del dispositivo (por ejemplo, cumplimiento). La cuenta de dispositivo que cree debe excluirse de dichas directivas de CA. De lo contrario, Surface Hub no puede usar ninguna característica de conferencia. |
| 5    | (Opcional) Deshabilitar la caducidad de contraseña | Para simplificar la administración, puedes desactivar la caducidad de contraseña para la cuenta del dispositivo y permitir que Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo. Para obtener más información acerca de la administración de contraseñas, consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md).  |

> [!NOTE]  
> La cuenta de dispositivo Surface Hub no admite proveedores de identidades federados (IDP) de terceros y debe autenticarse a través de Active Directory o Azure Active Directory.

## <a name="detailed-configuration-steps"></a>Pasos detallados de la configuración 

Los pasos de configuración de la cuenta de dispositivo pueden diferir en función del entorno. Seleccione el escenario de implementación de la tabla siguiente para encontrar los pasos adecuados y anote la columna "Formato de uso" para configurar Surface Hubs una vez aprovisionadas las cuentas.

| Implementación de la organización             |  Descripción                  |        Formato que se va a usar durante Surface Hub configuración
|---------------------------------|--------------------------------------|
| [Implementación en línea (Microsoft 365)](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |El entorno de la organización se implementa completamente en Microsoft 365. | nombreusuario@dominio.com |
| [Implementación híbrida (Exchange local)](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | Su organización tiene una combinación de servicios, con Exchange Server hospedados en el entorno local y Microsoft Teams en línea. | username@domain.com si la [autenticación moderna híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) está habilitada en Exchange, DOMAIN\username en caso contrario |
| [Implementación híbrida (Exchange Online)](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | Su organización tiene una combinación de servicios, con Skype Empresarial Server hospedados en el entorno local y Exchange Online. | username@domain.com si la [autenticación moderna híbrida](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) está habilitada en SfB, DOMINIO\nombre de usuario en caso contrario |
| [Implementación local (bosque único)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | La organización tiene servidores que controla, donde Active Directory, Exchange y Skype Empresarial Server se hospedan en un entorno de bosque único.  | DOMINIO\nombre de usuario |
| [Implementación local (varios bosques)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | La organización tiene servidores que controla, donde Active Directory, Exchange y Skype Empresarial Server se hospedan en un entorno de varios bosques. | ACCOUNTFOREST\username |

En el caso de las implementaciones en línea, también hay un [asistente de implementación disponible para Microsoft 365 administradores](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide) directamente en el Centro de administración de M365. Este asistente puede ayudar a crear nuevas cuentas de dispositivo o validar las cuentas de recursos existentes que tenga con el fin de ayudarle a convertirlas en cuentas de dispositivo Surface Hub compatibles.

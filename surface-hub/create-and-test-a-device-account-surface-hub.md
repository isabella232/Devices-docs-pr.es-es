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
ms.openlocfilehash: 9d2214453c8cb4c8d03f526dd4ac83264d2a16ad
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676384"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>Crear y probar una cuenta del dispositivo (Surface Hub)

La creación de una cuenta de dispositivo Surface Hub (también conocida como cuenta de recurso/buzón de sala) permite al Surface Hub recibir, aprobar o rechazar solicitudes de reunión y unirse a reuniones.

Una vez que la cuenta del dispositivo se aprovisiona en un Surface Hub, los usuarios pueden agregar esta cuenta a una invitación a una reunión del mismo modo que invitarían a una sala de conferencias. 

Puedes configurar la cuenta del dispositivo durante la configuración de la experiencia de salida [(OOBE).](first-run-program-surface-hub.md) Si es necesario, también puede cambiarlo más adelante **en Configuración**  >  **Surface Hub**  >  **Accounts**.

## <a name="configuration-overview"></a>Introducción a la configuración

Esta tabla explica los pasos principales y las decisiones de configuración cuando se crea una cuenta del dispositivo.
 
| Paso | Descripción                     |  Propósito                             |
|------|---------------------------------|--------------------------------------|
| 1    | Crear un buzón de sala habilitado para inicio de sesión (Exchange Online o Exchange Server 2016 y versiones posteriores) | Este tipo de buzón permite al dispositivo mantener un calendario de reuniones, recibir solicitudes de reunión y enviar correo. Debe estar habilitado para el inicio de sesión para poder usarse con un Surface Hub. |
| 2    | Configurar las propiedades de buzón de correo | El buzón de correo debe estar configurado con las propiedades correctas para obtener la mejor experiencia de reunión en Surface Hub. Para obtener más información acerca de las propiedades del buzón de correo, consulta [Propiedades del buzón](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Asegúrese de Exchange web Services (EWS) está habilitado y de que la autenticación multifactor (MFA) está deshabilitada | El Surface Hub usa EWS para sincronizar su calendario. Si no permite EWS en el entorno de forma predeterminada, el buzón de concentradores tendría que tenerla habilitada explícitamente. Como el Surface Hub inicia sesión Exchange en segundo plano sin la interacción del usuario, no puede responder a ningún mensaje interactivo, como MFA. La cuenta de dispositivo que cree debe excluirse de dichos requisitos de autenticación. De lo contrario, Surface Hub no podrá sincronizar el correo ni la información de calendario. |
| 4    | Habilitar la cuenta para Teams o Skype Empresarial (Skype Empresarial Server 2015 y versiones posteriores) | Skype Empresarial o Teams deben habilitarse para usar características de conferencia como videollamadas y uso compartido de pantalla. Para obtener más información sobre las licencias que Teams, vea Teams Sala de reuniones [licensing](/MicrosoftTeams/rooms/rooms-licensing) and [Teams service description](/office365/servicedescriptions/teams-service-description). Las aplicaciones Teams y SfB de la Surface Hub no son compatibles con las directivas de acceso condicional de [Azure AD](/azure/active-directory/conditional-access/concept-conditional-access-policies) que requieren información del dispositivo (por ejemplo, cumplimiento). La cuenta de dispositivo que cree debe excluirse de dichas directivas de CA. De lo contrario, Surface Hub no puede usar ninguna función de conferencia. |
| 5    | (Opcional) Deshabilitar la caducidad de contraseña | Para simplificar la administración, puedes desactivar la caducidad de contraseña para la cuenta del dispositivo y permitir que Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo. Para obtener más información acerca de la administración de contraseñas, consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md).  |
| 6    | (Opcional) Configurar Exchange directivas para permitir ActiveSync | Con determinadas implementaciones Exchange Server & de Active Directory locales, ActiveSync se usará para sincronizar el correo de la cuenta del dispositivo y la información del calendario. Para obtener más información acerca de las directivas que se configurarán, vea Directivas de [ActiveSync para Surface Hub cuentas](apply-activesync-policies-for-surface-hub-device-accounts.md). |

> [!NOTE]  
> La Surface Hub de dispositivo no admite proveedores de identidades federados (IDP) de terceros y debe autenticarse a través de Active Directory o Azure Active Directory.

## <a name="detailed-configuration-steps"></a>Pasos detallados de la configuración 

Se recomienda configurar las cuentas Surface Hub dispositivo mediante el uso de Windows PowerShell. Microsoft proporciona [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script que ayudará a crear nuevas cuentas de recursos o validar cuentas de recursos existentes que tenga para ayudarle a convertirlos en cuentas de dispositivo Surface Hub compatibles. Si lo prefiere, puede elegir una opción de la tabla siguiente y seguir los pasos detallados de PowerShell en función de la implementación de la organización.

| Implementación de la organización             |  Descripción                  |        Formato que se usará durante Surface Hub instalación
|---------------------------------|--------------------------------------|
| [Implementación en línea (Microsoft 365 o Office 365)](/MicrosoftTeams/rooms/with-office-365) |El entorno de la organización se implementa completamente en Microsoft 365 o Office 365. | nombreusuario@dominio.com |
| [Implementación híbrida (Exchange local)](/MicrosoftTeams/rooms/with-exchange-on-premises) | Su organización tiene una combinación de servicios, con Exchange Server local y Microsoft Teams en línea. | username@domain.com si [la autenticación moderna híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) está habilitada en Exchange, DOMAIN\username en caso contrario |
| [Implementación híbrida (Exchange Online)](/MicrosoftTeams/rooms/with-exchange-online) | Su organización tiene una combinación de servicios, con Skype Empresarial Server local y Exchange Online. | username@domain.com si [la autenticación moderna híbrida](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) está habilitada en SfB, DOMAIN\username de lo contrario |
| [Implementación local (bosque único)](/MicrosoftTeams/rooms/with-skype-for-business-server-2015) | Su organización tiene servidores que controla, donde Active Directory, Exchange y Skype Empresarial Server se hospedan en un entorno de bosque único.  | DOMINIO\nombre de usuario |
| [Implementación local (varios bosques)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Su organización tiene servidores que controla, donde Active Directory, Exchange y Skype Empresarial Server se hospedan en un entorno de varios bosques. | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>Verificación y prueba de cuentas

Hay dos métodos disponibles que puedes usar para validar y probar una cuenta Surface Hub [dispositivo:](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1y la aplicación Surface Hub de diagnóstico [de hardware](https://www.microsoft.com/store/apps/9nblggh51f2g). El script de aprovisionamiento de cuenta puede validar una cuenta de dispositivo creada previamente con PowerShell desde el equipo. La aplicación Diagnóstico de hardware de Surface Hub se instala en Surface Hub y proporciona información detallada acerca de los errores de inicio de sesión y comunicación. Ambas son herramientas valiosas para probar las cuentas del dispositivo recién creadas y deben usarse para garantizar una óptima disponibilidad de las cuentas.

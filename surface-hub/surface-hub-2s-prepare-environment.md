---
title: Preparar el entorno para Surface Hub 2S
description: Obtenga información sobre lo que tiene que hacer para preparar su entorno para Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: af66449806c9aa525fa3f5df84012d3daeed96ba
ms.sourcegitcommit: dbd14649442ad039aeb265cd60ed029d483a4bb0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2020
ms.locfileid: "11251457"
---
# Preparar el entorno para Surface Hub 2S

## Preparación de Office 365

Si usa Exchange Online, Skype empresarial online, Microsoft Teams o pizarra de Microsoft, y tiene la intención de administrar Surface Hub 2S con Intune, revise primero los [requisitos de Office 365 para los puntos de conexión](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Los puntos de conexión de Office 365 ayudan a optimizar la red mediante el envío de todas las solicitudes de red de Office 365 de confianza directamente a través del firewall, omitiendo la inspección o el procesamiento adicionales a nivel de paquete. Esta característica reduce la latencia y los requisitos de capacidad del perímetro.

Microsoft actualiza regularmente el servicio de Office 365 con nuevas características y funciones, que pueden modificar los puertos, direcciones URL y direcciones IP requeridos. Para evaluar, configurar y mantenerse al día con los cambios, suscríbase a la [dirección IP y el servicio Web](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)de la dirección IP de Office 365.

> [!NOTE]
> Surface Hub funciona con Microsoft Teams, Skype empresarial Server 2019, Skype empresarial Server 2015 o Skype empresarial online.
Las plataformas anteriores, como Lync Server 2013, no son compatibles. Surface Hub no es compatible en entornos GCC-High o DoD.


## Afiliación del dispositivo

Use la pertenencia a dispositivos para administrar el acceso de los usuarios a la aplicación configuración en Surface Hub 2S.
Con el sistema operativo Windows 10 Team (que se ejecuta en Surface Hub 2S), solo los usuarios autorizados pueden ajustar la configuración con la aplicación configuración. Como la elección de la afiliación puede afectar a la disponibilidad de las características, debe asegurarse de que los usuarios puedan obtener acceso a las características como se pretende.

> [!NOTE]
> Solo puedes establecer la afiliación a dispositivos durante la configuración inicial de la configuración rápida (OOBE). Si necesita restablecer la afiliación a dispositivos, tendrá que repetir el programa de instalación de OOBE.

## Sin afiliación

Ninguna afiliación es como tener Surface Hub 2S en un grupo de trabajo con una cuenta de administrador local diferente en cada Surface Hub 2S. Si elige no afiliación, debe guardar localmente la [clave de BitLocker en una unidad USB](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq). Aún puede inscribir el dispositivo con Intune; sin embargo, solo el administrador local puede acceder a la aplicación configuración con las credenciales de cuenta configuradas durante OOBE. Puede cambiar la contraseña de la cuenta Administrador desde la aplicación configuración.

## Active Directory Domain Services

Si afilia Surface Hub 2 con servicios de dominio de Active Directory local, tendrá que administrar el acceso a la aplicación configuración con un grupo de seguridad en su dominio. Esto ayuda a garantizar que todos los miembros del grupo de seguridad tienen permisos para cambiar la configuración en Surface Hub 2S. Además, tenga en cuenta lo siguiente:

- Cuando Surface Hub 2S a empresas afiliadas con los servicios de dominio de Active Directory local, la clave de BitLocker se puede guardar en el esquema de Active Directory. Para obtener más información, vea [preparar la organización para BitLocker: Planeación y directivas](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Las entidades de certificación raíz de confianza de su organización se envían al mismo contenedor de Surface Hub 2S, lo que significa que no es necesario importarlas con un paquete de aprovisionamiento.

- Aún puede inscribir el dispositivo con Intune para administrar de forma centralizada la configuración de Surface Hub 2S.

## Azure Active Directory

Cuando elige afiliar a su Surface Hub 2 con Azure Active Directory (Azure AD), todos los usuarios del grupo de seguridad de administradores globales pueden iniciar sesión en la aplicación configuración de Surface Hub 2S. En este momento, no se puede delegar ningún otro grupo para iniciar sesión en la aplicación configuración de Surface Hub 2S.

Si ha habilitado la inscripción automática de su organización, Surface Hub 2S se inscribirá automáticamente con Intune. La clave de BitLocker del dispositivo se guarda automáticamente en Azure AD. Al afiliar Surface Hub 2S con Azure AD, el inicio de sesión único y la autenticación simple no funcionarán.

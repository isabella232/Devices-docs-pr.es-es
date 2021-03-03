---
title: Preparar el entorno para Surface Hub 2S
description: Obtén información sobre lo que debes hacer para preparar el entorno para Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385148"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>Preparar el entorno para Surface Hub 2S

## <a name="office-365-readiness"></a>Preparación de Office 365

Si usa Exchange Online, Skype Empresarial Online, Microsoft Teams o Microsoft Whiteboard y tiene la intención de administrar Surface Hub 2S con Intune, revise primero los requisitos de [Office 365](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)para puntos de conexión.

Los puntos de conexión de Office 365 ayudan a optimizar la red enviando todas las solicitudes de red de confianza de Office 365 directamente a través del firewall, omitiendo toda inspección o procesamiento de nivel de paquete adicional. Esta característica reduce la latencia y los requisitos de capacidad perimetral.

Microsoft actualiza regularmente el servicio de Office 365 con nuevas características y funcionalidades, que pueden modificar los puertos, direcciones URL y direcciones IP necesarios. Para evaluar, configurar y mantenerse al día con los cambios, suscríbete al servicio web dirección IP y [dirección URL de Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

> [!NOTE]
> Surface Hub funciona con Microsoft Teams, Skype Empresarial Server 2019, Skype Empresarial Server 2015 o Skype Empresarial Online.
No se admiten plataformas anteriores, como Lync Server 2013. Surface Hub no es compatible con GCC-High o entornos DoD.


## <a name="device-affiliation"></a>Afiliación de dispositivos

Usa la afiliación a dispositivos para administrar el acceso de los usuarios a la aplicación Configuración en Surface Hub 2S.
Con el sistema operativo Windows 10 Team (que se ejecuta en Surface Hub 2S), solo los usuarios autorizados pueden ajustar la configuración con la aplicación Configuración. Dado que elegir la afiliación puede afectar a la disponibilidad de las características, planee correctamente para garantizar que los usuarios puedan acceder a las características según lo previsto.

> [!NOTE]
> Solo puedes establecer la afiliación de dispositivos durante la configuración inicial de la experiencia de inicio de la caja (OOBE). Si necesitas restablecer la afiliación a dispositivos, tendrás que repetir la configuración de OOBE.

## <a name="no-affiliation"></a>Sin afiliación

Ninguna afiliación es como tener Surface Hub 2S en un grupo de trabajo con una cuenta de administrador local diferente en cada Surface Hub 2S. Si eliges Sin afiliación, debes guardar localmente la clave [de BitLocker en una unidad usb.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq) Todavía puedes inscribir el dispositivo con Intune; sin embargo, solo el administrador local puede acceder a la aplicación Configuración con las credenciales de cuenta configuradas durante OOBE. Puedes cambiar la contraseña de la cuenta de administrador desde la aplicación Configuración.

## <a name="active-directory-domain-services"></a>Active Directory Domain Services

Si afilias Surface Hub 2S con los Servicios de dominio de Active Directory locales, debes administrar el acceso a la aplicación Configuración mediante un grupo de seguridad de tu dominio. Esto ayuda a garantizar que todos los miembros del grupo de seguridad tengan permisos para cambiar la configuración en Surface Hub 2S. También tenga en cuenta lo siguiente:

- Cuando las filiales de Surface Hub 2S con los Servicios de dominio de Active Directory locales, la clave de BitLocker se puede guardar en el esquema de Active Directory. Para obtener más información, vea [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Las CA raíz de confianza de la organización se insertan en el mismo contenedor de Surface Hub 2S, lo que significa que no es necesario importarlas con un paquete de aprovisionamiento.

- Aún puedes inscribir el dispositivo con Intune para administrar la configuración de forma centralizada en Surface Hub 2S.

## <a name="azure-active-directory"></a>Azure Active Directory

Cuando eliges asociar Surface Hub 2S con Azure Active Directory (Azure AD), cualquier usuario del Grupo de seguridad de administradores globales puede iniciar sesión en la aplicación Configuración de Surface Hub 2S. También puedes configurar cuentas de administrador no globales que limiten los permisos a la administración de la aplicación Configuración en Surface Hub 2S. Esto te permite tener en cuenta los permisos de administrador solo para Surface Hub 2S e impedir el acceso de administrador potencialmente no deseado en todo un dominio de Azure AD. 

Si habilitaste la inscripción automática de Intune para tu organización, Surface Hub 2S se inscribirá automáticamente en Intune. La clave BitLocker del dispositivo se guarda automáticamente en Azure AD. 

Para obtener más información sobre cómo administrar Surface Hub con Azure AD, consulta: 

 - [Administración del grupo de administradores](admin-group-management-for-surface-hub.md)
 - [Configurar cuentas de administrador no global en Surface Hub 2S](surface-hub-2s-nonglobal-admin.md)


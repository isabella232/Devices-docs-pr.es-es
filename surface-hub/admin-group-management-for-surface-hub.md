---
title: Administración del grupo de administradores
description: Cada Microsoft Surface Hub se puede configurar individualmente abriendo la aplicación Configuración en el dispositivo.
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: administración del grupo de administradores, aplicación Configuración, configurar Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d634a4045327cb826e519c7e5097d946991f5d0
ms.sourcegitcommit: d9c413f1c50908a81e5489aca2c6023eab573148
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "12093037"
---
# <a name="admin-group-management-for-surface-hub"></a>Administración de grupos de administración para Surface Hub

Cada Surface Hub se puede configurar localmente mediante la aplicación Configuración en el dispositivo. Para impedir que usuarios no autorizados cambien la configuración, la aplicación Configuración requiere credenciales de administrador para abrir la aplicación.

## <a name="admin-group-management"></a>Administración del grupo de administradores

Puedes configurar cuentas de administrador para el dispositivo de las siguientes maneras:

- [Crear una cuenta de administrador local](#create-a-local-admin-account)
- [Unir el dispositivo a Active Directory](#domain-join-the-device-to-active-directory)
- [Azure AD unirse al dispositivo](#azure-ad-join-the-device)
- [Configurar cuentas de administrador no globales en Azure AD unidos (Surface Hub 2S)](#configure-non-global-admin-accounts-on-azure-ad-joined-devices)

### <a name="create-a-local-admin-account"></a>Crear una cuenta de administrador local

Para crear un administrador local, [elige usar un administrador local durante la primera ejecución](first-run-program-surface-hub.md). De este modo, se creará una cuenta de administrador local única en Surface Hub con el nombre de usuario y la contraseña de tu elección. Usa estas credenciales para abrir la aplicación Configuración.

Ten en cuenta que la información de cuenta de administrador local no está respaldada por ningún servicio de directorio. Te recomendamos que elijas solo un administrador local si el dispositivo no tiene acceso a Active Directory (AD) o Azure Active Directory (Azure AD). Si decides cambiar la contraseña del administrador local, puedes hacerlo en Configuración. Sin embargo, si quieres cambiar de una cuenta de administrador local a un grupo de tu dominio o inquilino de Azure AD, tendrás que [restablecer el dispositivo](device-reset-surface-hub.md) y volver a ejecutar el programa como la primera vez.

### <a name="domain-join-the-device-to-active-directory"></a>Unir el dispositivo a Active Directory

Puedes unir Surface Hub a tu dominio de AD para permitir que los usuarios de un grupo de seguridad especificado puedan configurar los parámetros. Durante la primera ejecución, elige usar [los servicios de dominio de Active Directory](first-run-program-surface-hub.md#active-directory-domain-services). Deberás proporcionar las credenciales que son capaces de unir el dominio de tu elección y el nombre de un grupo de seguridad existente. Cualquier persona que sea miembro de ese grupo de seguridad puede escribir sus credenciales y desbloquear Configuración.

#### <a name="what-happens-when-you-domain-join-your-surface-hub"></a>¿Qué sucede cuando unes tu Surface Hub a un dominio?

Los Surface Hubs usan unión a un dominio para:

- Conceder derechos de administrador a los miembros de un grupo de seguridad especificado en AD.
- Copia de seguridad de la clave de recuperación de BitLocker del dispositivo, almacenándola en el objeto del equipo en AD. Consulta [Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md) para obtener más información.
- Sincronizar el reloj del sistema con el controlador de dominio para la comunicación cifrada

Surface Hub no admite la aplicación de directivas de grupo o certificados desde el controlador de dominio.

> [!NOTE]
> Si el Surface Hub pierde confianza en el dominio (por ejemplo, si se quita el Surface Hub del dominio cuando esté unido a este), no podrás autenticarte en el dispositivo ni abrir Configuración. Si decides quitar la relación de confianza entre el Surface Hub y tu dominio, [restablece el dispositivo](device-reset-surface-hub.md) en primer lugar.

### <a name="azure-ad-join-the-device"></a>Azure AD unirse al dispositivo

Puede Azure Active Directory (Azure AD) unirse a la Surface Hub para permitir que los profesionales de TI de su inquilino Azure AD configurar la configuración. Durante la primera ejecución, elige usar [Microsoft Azure Active Directory](first-run-program-surface-hub.md#microsoft-azure-active-directory). Deberás proporcionar las credenciales que se pueden unir al inquilino de Azure AD de tu elección. Después de unirte a Azure AD correctamente, se concederán los derechos de administrador a las personas adecuadas en el dispositivo.

De manera predeterminada, se concederán derechos de administrador a todos los **administradores globales** en un Surface Hub unido a Azure AD. Con **Azure AD Premium** o **Enterprise Mobility Suite (EMS)**, puedes agregar administradores adicionales:

1. En el [portal de Azure clásico](https://portal.azure.com/), haz clic en **Active Directory** y, a continuación, haz clic en el nombre del directorio de la organización.
2. En la página **Configurar**, en **Dispositivos** > **Administradores adicionales en los dispositivos unidos a Azure AD**, haz clic en **Seleccionados**.
3. Haz clic en **Agregar** y selecciona los usuarios que quieres agregar como administradores en tu Surface Hub y en otros dispositivos unidos a Azure AD.
4. Cuando hayas terminado, haz clic en el botón de marca de verificación para guardar el cambio.

#### <a name="what-happens-when-you-azure-ad-join-your-surface-hub"></a>¿Qué sucede al unir el Surface Hub a Azure AD?

Los Surface Hubs usan la unión a Azure AD para:

- Conceder derechos de administrador a los usuarios adecuados en el inquilino de Azure AD.
- Copia de seguridad de la clave de recuperación de BitLocker del dispositivo, almacenándola en la cuenta que se usó para unir el dispositivo a Azure AD. Consulta [Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md) para obtener más información.

#### <a name="automatic-enrollment-via-azure-active-directory-join"></a>Inscripción automática a través Azure Active Directory unirse

Surface Hub ahora admite la capacidad de inscribirse automáticamente en Intune uniendo el dispositivo a Azure Active Directory.

Para obtener más información, vea [Enable Windows 10 automatic enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment).

#### <a name="which-should-i-choose"></a>¿Cuál debo elegir?

Si tu organización usa AD o Azure AD, te recomendamos que te unas a un dominio o a Azure AD, principalmente por motivos de seguridad. Las personas podrán autenticarse y desbloquear Configuración con sus propias credenciales y se pueden mover dentro o fuera de los grupos de seguridad asociados a tu dominio.

| Opción                                            | Requisitos                            | ¿Qué credenciales se pueden usar para acceder a la aplicación Configuración?  |
|---------------------------------------------------|-----------------------------------------|-------|
| Crear una cuenta de administrador local                      | Ninguna                                    | El nombre de usuario y contraseña especificados durante la primera ejecución |
| Unión a un dominio de Active Directory (AD)              | Tu organización usa AD               | Cualquier usuario de AD de un grupo de seguridad específico de tu dominio |
| Unir el dispositivo a Azure Active Directory (Azure AD) | Tu organización usa Azure AD Basic   | Solo los administradores globales |
| &nbsp;                                            | Tu organización usa Azure AD Premium o Enterprise Mobility Suite (EMS) | Los administradores globales y los administradores adicionales |

### <a name="configure-non-global-admin-accounts-on-azure-ad-joined-devices"></a>Configurar cuentas de administración no globales en Azure AD dispositivos unidos

Para Surface Hub v1 y Surface Hub dispositivos 2S unidos a Azure AD, Windows 10 Team 2020 Update te permite limitar los permisos de administrador a la administración de la aplicación Configuración en Surface Hub. Esto le permite tener en cuenta los permisos de administración Surface Hub y evitar el acceso de administrador potencialmente no deseado a un dominio Azure AD usuario. Para obtener más información, vea [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

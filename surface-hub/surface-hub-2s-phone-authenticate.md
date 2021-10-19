---
title: Configurar el inicio de sesión sin contraseña en Surface Hub
description: Obtenga información sobre cómo simplificar el inicio de sesión Surface Hub.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101204"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>Configurar el inicio de sesión sin contraseña en Surface Hub

 
El inicio de sesión sin contraseña simplifica el acceso a sus aplicaciones, reuniones y archivos. Surface Hub permite iniciar sesión con la aplicación Microsoft Authenticator y las claves de seguridad fido2 proporcionadas por la organización.

**Importante:** Este contenido está destinado a los usuarios. Para usar el inicio de sesión sin contraseña, el administrador de TI debe habilitar la autenticación sin contraseña para su organización. Para más información, consulta lo siguiente:

- [Habilitar el inicio de sesión de teléfono sin contraseña](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Habilitar el inicio de sesión con clave de seguridad sin contraseña](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>Configurar el inicio de sesión con Microsoft Authenticator aplicación

**Nota:** A partir de Windows 10 Team actualización de 2020, los usuarios pueden usar sus alias de correo electrónico preferidos en Azure AD, así como su nombre principal de usuario (UPN), para iniciar sesión con Microsoft Authenticator. Por ejemplo, un usuario puede usar su alias preferido (John.Doe@contoso.com) o su UPN (jdoe@contoso.com) para iniciar sesión.
 
La Microsoft Authenticator te ayuda a iniciar sesión en Surface Hub usar el dispositivo móvil. Para configurar el inicio de sesión con Microsoft Authenticator:


1. En el dispositivo móvil, descarga la Microsoft Authenticator aplicación.
    - Google Android: en tu dispositivo Android, ve a Google Play para descargar e [instalar la Microsoft Authenticator aplicación](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: en tu dispositivo Apple iOS, ve a la App Store para descargar e instalar la [Microsoft Authenticator aplicación](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. En el equipo, [configura la aplicación Microsoft Authenticator desde la](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) página Información de seguridad de tu cuenta laboral o educativa.
3. Desde la Microsoft Authenticator en tu dispositivo móvil, activa y usa el inicio de sesión [del](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) teléfono para tu cuenta laboral o educativa.

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>Configurar el inicio de sesión con claves de seguridad FIDO2

> [!NOTE]
>  El inicio de sesión sin contraseña Surface Hub con claves de seguridad FIDO2 requiere la actualización Windows 10 Team 2020.

> [!IMPORTANT]
> Surface Hub solo admite claves de seguridad USB.
 
También puede iniciar sesión en Surface Hub con una clave de seguridad FIDO2 proporcionada por su organización. 

### <a name="to-configure-sign-in-using-a-security-key"></a>Para configurar el inicio de sesión con una clave de seguridad:


1. En el equipo, vaya a la página e inicie sesión en su cuenta laboral [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) o educativa.
2. Selecciona **Información de seguridad** en el panel **** de navegación izquierdo o en el vínculo del bloque Información de seguridad y, a continuación, selecciona **Agregar** método en la página **Información de** seguridad.
3. En la **página Agregar un método,** seleccione Clave **de seguridad** de la lista desplegable y, a continuación, **seleccione Agregar**.
4. En la **página Clave de** seguridad, elija Dispositivo **USB**.
5. Tenga la clave de seguridad lista y seleccione **Siguiente**.
6. En el cuadro de diálogo que aparece, siga las instrucciones para insertar la clave de seguridad, crear o escribir un PIN y realizar el gesto necesario (ya sea biométrico o táctil).
7. En la **página Clave de** seguridad, asigne un nombre a la clave de seguridad y, a continuación, seleccione **Siguiente**.
8. Seleccione **Listo** para completar el proceso.

## <a name="sign-in-to-surface-hub"></a>Inicie sesión en Surface Hub

Una vez que hayas configurado el inicio de sesión sin contraseña, puedes usarlo para facilitar el acceso a tus aplicaciones, reuniones y archivos en el Surface Hub:

- Únase rápidamente a sus reuniones y abra archivos Microsoft 365 recientes. Para obtener más información, vea [**Iniciar sesión para ver sus reuniones y archivos.**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)
- Inicie sesión rápidamente en aplicaciones de Microsoft como Whiteboard, PowerPoint, Word, Excel, OneDrive y Power BI.
- Inicie sesión rápidamente en el nuevo Microsoft Edge para acceder a sus preferencias de navegación y favoritos. Para obtener más información, vea [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).
- Una vez que hayas iniciado sesión Surface Hub, puedes usar otras aplicaciones sin tener que volver a iniciar sesión hasta que **selecciones Finalizar sesión**. Al seleccionar **Finalizar sesión,** se eliminan las credenciales, los archivos y los datos personales del dispositivo. Para obtener más información, vea [End session](finishing-your-surface-hub-meeting.md).


## <a name="learn-more"></a>Obtén más información

- [Opciones de autenticación sin contraseña para Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [Inicio de sesión sin contraseña con la Microsoft Authenticator aplicación](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Inicio de sesión sin contraseña con claves de seguridad FIDO2](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


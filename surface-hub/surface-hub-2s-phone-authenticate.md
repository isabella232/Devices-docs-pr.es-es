---
title: Configurar el inicio de sesión sin contraseña en Surface Hub
description: Aprenda a simplificar el inicio de sesión en Surface Hub.
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
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893052"
---
# Configurar el inicio de sesión sin contraseña en Surface Hub

 
El inicio de sesión sin contraseña simplifica el acceso a tus aplicaciones, reuniones y archivos. Surface HUB permite iniciar sesión con la aplicación Microsoft Authenticator y las claves de seguridad de FIDO2 proporcionadas por su organización.

**Importante:** Este contenido va dirigido a los usuarios. Para usar el inicio de sesión sin contraseña, su administrador de TI debe habilitar la autenticación sin contraseña para su organización. Para más información, consulta lo siguiente:

- [Habilitar el inicio de sesión de teléfono sin contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Habilitar el inicio de sesión con una clave de seguridad sin contraseñas](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


##  <a name="configure-sign-in-using-microsoft-authenticator-app"></a>Configurar el inicio de sesión con la aplicación Microsoft Authenticator

**Nota:** A partir de la actualización de Windows 10 Team 2020, los usuarios pueden usar sus alias de correo electrónico preferidos en Azure AD, así como su nombre principal de usuario (UPN), para iniciar sesión con Microsoft Authenticator. Por ejemplo, un usuario puede usar su alias preferido (John.Doe@contoso.com) o su UPN (jdoe@contoso.com) para iniciar sesión.
 
La aplicación Microsoft Authenticator le ayuda a iniciar sesión en Surface Hub con el dispositivo móvil. Para configurar el inicio de sesión con Microsoft Authenticator:


1. En su dispositivo móvil, descargue la aplicación Microsoft Authenticator.
    - Google Android: en su dispositivo Android, vaya a Google Play para [Descargar e instalar la aplicación Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - IOS de Apple: en el dispositivo Apple iOS, vaya a App Store para [Descargar e instalar la aplicación Microsoft Authenticator](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. En su equipo, [Configure la aplicación Microsoft Authenticator desde la página información de seguridad](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) de su cuenta profesional o educativa.
3. Desde la aplicación Microsoft Authenticator en su dispositivo móvil, [Active y use el inicio de sesión](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) para su cuenta profesional o educativa.

 
##  <a name="configure-sign-in-using-fido2-security-keys"></a>Configurar el inicio de sesión con las claves de seguridad de FIDO2

> [!NOTE]
>  El inicio de sesión sin contraseñas en Surface Hub con claves de seguridad FIDO2 requiere la actualización de Windows 10 Team 2020.

> [!IMPORTANT]
> Surface Hub solo admite claves de seguridad USB.
 
También puede iniciar sesión en Surface Hub con una clave de seguridad FIDO2 proporcionada por su organización. 

###  <a name="to-configure-sign-in-using-a-security-key"></a>Para configurar el inicio de sesión con una clave de seguridad:


1. En su equipo, vaya a la [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) página e inicie sesión con su cuenta profesional o educativa.
2. Seleccione **información de seguridad** en el panel de navegación izquierdo o en el vínculo del bloque de **información de seguridad** y, a continuación, seleccione **Agregar método** en la página **información de seguridad** .
3. En la página **Agregar un método** , seleccione **clave de seguridad** en la lista desplegable y, a continuación, seleccione **Agregar**.
4. En la página **clave de seguridad** , elija **dispositivo USB**.
5. Prepare su clave de seguridad y seleccione **siguiente**.
6. En el cuadro de diálogo que aparece, siga las instrucciones para insertar la clave de seguridad, cree o escriba un PIN y realice el gesto necesario (ya sea biométrico o táctil).
7. En la página **clave de seguridad** , asigne un nombre a la clave de seguridad y, a continuación, seleccione **siguiente**.
8. Seleccione **listo** para completar el proceso.

##  <a name="sign-in-to-surface-hub"></a>Iniciar sesión en Surface Hub

Una vez que haya configurado el inicio de sesión sin contraseñas, puede usarlo para facilitar el acceso a sus aplicaciones, reuniones y archivos en Surface Hub:

- Únase rápidamente a sus reuniones y abra archivos recientes de Microsoft 365. Para obtener más información, consulte [**iniciar sesión para ver sus reuniones y archivos**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Inicie sesión rápidamente en aplicaciones de Microsoft, como whiteboard, PowerPoint, Word, Excel, OneDrive y Power BI.
- Inicia sesión rápidamente en el nuevo Microsoft Edge para acceder a tus preferencias de navegación y favoritos. Para obtener más información, vea [instalar y configurar el nuevo Microsoft Edge](surface-hub-install-chromium-edge.md).
- Una vez que haya iniciado sesión en Surface Hub, puede usar otras aplicaciones sin tener que iniciar sesión de nuevo hasta que seleccione **finalizar sesión**. Al seleccionar **finalizar sesión** , se eliminan las credenciales, los archivos y los datos personales del dispositivo. Para obtener más información, consulte [finalizar sesión](finishing-your-surface-hub-meeting.md).


##  <a name="learn-more"></a>Obtén más información

- [Opciones de autenticación no de contraseña para Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [Inicio de sesión sin contraseña con la aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Inicio de sesión sin contraseñas con las claves de seguridad FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)


---
title: Iniciar sesión en Surface Hub con Microsoft Authenticator
description: Usa Microsoft Authenticator en tu dispositivo móvil para iniciar sesión en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: 11768488d2ef7509af6a592b9e4ac945a7e35650
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835257"
---
# Iniciar sesión en Surface Hub con Microsoft Authenticator

Las personas de tu organización pueden iniciar sesión en un dispositivo Surface Hub sin una contraseña con la aplicación Microsoft Authenticator, disponible en Android e iOS.

## Requisitos previos de la organización

Para permitir que las personas de tu organización inicien sesión en Surface Hub con sus teléfonos y otros dispositivos en lugar de una contraseña, tendrás que asegúrate de que la organización cumple estos requisitos previos: 

- La organización debe tener un entorno híbrido o solo en la nube, respaldada por la solución Azure Active Directory (Azure AD). Para más información, consulta [¿Qué es Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).

- Asegúrate de tener como mínimo una suscripción a Office 365 E3. 

- [Configurar la autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings). Asegúrate de que la opción **Notificación a través de aplicación móvil** está seleccionada. 

    ![opciones de autenticación multifactor](images/mfa-options.png)

- Habilitar el hospedaje de contenido en servicios de Azure AD como Office, SharePoint, etc. 

- Surface Hub debe ejecutar Windows 10, versión 1703 o posterior.

- Surface Hub está configurado con una cuenta local o unida a un dominio.

Actualmente, no puedes usar Microsoft Authenticator para iniciar sesión en los Surface Hub que estén unidos a Azure AD.

## Requisitos previos individuales

- Un teléfono Android que ejecuta 6.0 o versión posterior, o un iPhone o iPad que ejecuta iOS9 o versión posterior 

- La versión más reciente de la aplicación Microsoft Authenticator de la tienda de aplicaciones adecuada

    >[!NOTE]
    >En iOS, la versión de la aplicación debe ser 5.4.0 o superior.
    >
    >La aplicación Microsoft Authenticator en teléfonos con un sistema operativo Windows no pueden usarse para iniciar sesión en Surface Hub.

- El código de acceso o pantalla de bloqueo están habilitados en el dispositivo

- Una dirección de correo electrónico SMTP estándar (ejemplo: jose@contoso.com). Actualmente, las direcciones de correo electrónico SMTP no estándares o personalizadas (ejemplo: nombre.apellido@contoso.com) no funcionan.

## Cómo configurar la aplicación Microsoft Authenticator

>[!NOTE]
>Si el Portal de empresa está instalado en tu dispositivo Android, desinstálalo antes de configurar Microsoft Authenticator. Después de configurar la aplicación, puedes reinstalar Portal de empresa.
>
>Si ya has configurado Microsoft Authenticator en tu teléfono y has registrado tu dispositivos, ve a las instrucciones de inicio de sesión.

1. Agrega tu cuenta profesional o educativa a Microsoft Authenticator para la autenticación multifactor. Necesitarás un código QR proporcionado por el departamento de TI. Para obtener ayuda, consulta [Introducción a la aplicación Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).
2. Ve a **Configuración** y registrar tu dispositivo.
3. Vuelve a la página de cuentas y elige **Habilitar el inicio de sesión en el teléfono** en el menú desplegable Cuenta.

## Cómo iniciar sesión en Surface Hub durante una reunión

1. Después de configurar una reunión, ve a Surface Hub y selecciona **Inicia sesión para ver las reuniones y los archivos**.

    >[!NOTE]
    >Si no está seguro cómo programar una reunión en Surface Hub, consulta [Programar un Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).

    ![captura de pantalla de la opción de inicio de sesión en Surface Hub](images/sign-in.png)

2. Verás una lista de las personas invitadas a la reunión. Selecciónate a ti mismo (o selecciona la persona que quiere iniciar sesión, asegurándote de que esta persona haya realizado los pasos para configurar su dispositivo antes de la reunión) y luego selecciona **Continuar**.

    ![captura de pantalla de la lista de personas que asistirán a una reunión](images/attendees.png)

    Verás un código en el dispositivo Surface Hub.

    ![captura de pantalla del código de aprobación de inicio de sesión](images/approve-signin.png)

3. Para aprobar el inicio de sesión, abre la aplicación Authenticator, escribe el código de cuatro dígitos que se muestra en Surface Hub y selecciona **Aprobar**. Se te pedirá que especifiques el PIN o que uses tu huella digital para completar el inicio de sesión. 

    ![captura de pantalla de la pantalla de inicio de sesión de aprobación en Microsoft Authenticator](images/approve-signin2.png)

Ahora puedes acceder a todos los archivos a través de la aplicación OneDrive.
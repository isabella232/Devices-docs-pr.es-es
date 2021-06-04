---
title: Configurar el perfil de trabajo de Android Enterprise para Surface Duo
description: En este artículo se explica cómo configurar el perfil de trabajo en Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326265"
---
# Configurar el perfil de trabajo de Android Enterprise para Surface Duo

Destinados a implementaciones byod, los perfiles de trabajo proporcionan un espacio independiente en Duo para las aplicaciones y los datos de trabajo, lo que proporciona a las organizaciones un control total de sus datos, aplicaciones y directivas de seguridad sin impedir que los empleados utilicen su dispositivo para aplicaciones y datos personales.

###  <a name="set-up-android-enterprise-work-profile"></a>Configurar el perfil de trabajo de Android Enterprise

Usa perfiles de trabajo para administrar datos corporativos y aplicaciones en dispositivos Android de propiedad del usuario. De forma predeterminada, la inscripción de dispositivos de perfil de trabajo de propiedad personal está habilitada y no requiere ninguna otra configuración de administrador.  

**Para habilitar el perfil de trabajo empresarial:**

- En Endpoint Manager, seleccione **Dispositivos para**la inscripción de Android y, a  >  ****  >  **** continuación, seleccione **Dispositivos personales con perfil de trabajo.**
<br><br>
 ![Habilitar perfil de trabajo empresarial](images/enroll-start.png)

 
**Iniciar sesión en Surface Duo con el perfil de trabajo de Android Enterprise**

1. Instala la aplicación Portal de empresa desde Google Play Store e inicia sesión con tu cuenta de Microsoft trabajo o escuela.<br><br>
![Iniciar sesión en Surface Duo](images/duo-wp-1.png)
 
2. En la página Configuración de Access, seleccione **Comenzar**.<br><br>
![Begin](images/duo-wp-2.png)

3. Revise la información de la página de privacidad y seleccione **Continuar.**<br><br>
 ![Continuar](images/duo-wp-3.png)
<br><br>
 ![Seleccionar continuar](images/duo-wp-4.png)
 
4. Cuando se complete la configuración del perfil de trabajo, seleccione **Continuar** para activar y registrar el dispositivo.<br><br>
 ![Seleccionar continuar para activar y registrar el dispositivo](images/duo-wp-5.png)

5. Selecciona **Continuar**.<br><br>
 ![Seleccionar continuar de nuevo](images/duo-wp-6.png)

6. Cuando haya activado el perfil de trabajo, seleccione **Continuar** para actualizar la configuración del dispositivo. En este ejemplo, el perfil de trabajo aplica una configuración MDM para requerir una contraseña alfanumérica de 6 dígitos más segura. <br><br>

     ![Ejemplo de contraseña alfanumérica](images/duo-wp-7.png)<br><br>
7. Seleccione **Resolver para** especificar la autenticación necesaria y, a continuación, seleccione **Continuar** para completar la configuración del perfil de trabajo. <br><br>
     ![Seleccionar continuar para completar la configuración](images/duo-wp-8.png)<br><br>
     ![completar la configuración](images/duo-wp-9.png)<br><br>

##  <a name="learn-more"></a>Más información

- [Configurar la inscripción de dispositivos de perfiles de trabajo de Android Enterprise](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)


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
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911205"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>Configurar el perfil de trabajo de Android Enterprise para Surface Duo

Dirigidos a implementaciones BYOD, los perfiles de trabajo proporcionan un espacio independiente en Duo para aplicaciones y datos de trabajo, lo que proporciona a las organizaciones un control total de sus datos, aplicaciones y directivas de seguridad sin impedir que los empleados utilicen su dispositivo para aplicaciones y datos personales.

### <a name="set-up-android-enterprise-work-profile"></a>Configurar el perfil de trabajo Enterprise Android

Usa perfiles de trabajo para administrar aplicaciones y datos corporativos en dispositivos Android de propiedad del usuario. De forma predeterminada, la inscripción de dispositivos de perfil de trabajo de propiedad personal está habilitada y no requiere ninguna configuración de administrador adicional.  

**Para habilitar Enterprise de trabajo:**

- En Endpoint Manager, seleccione **Dispositivos**android inscripción  >  ****  >  **y,** a continuación, seleccione **Dispositivos personales con perfil de trabajo**.
<br><br>
 ![Habilite Enterprise de trabajo.](images/enroll-start.png)

 
**Iniciar sesión en Surface Duo con Android Enterprise de trabajo**

1. Instala la Portal de empresa de Google Play Store e inicia sesión con tu cuenta de trabajo o escuela de Microsoft.<br><br>
![Inicia sesión en Surface Duo.](images/duo-wp-1.png)
 
2. En la página Configuración de Access, seleccione **Comenzar**.<br><br>
![Comenzar.](images/duo-wp-2.png)

3. Revise la información de la página de privacidad y seleccione **Continuar**.<br><br>
 ![Continúe.](images/duo-wp-3.png)
<br><br>
 ![Seleccione continuar.](images/duo-wp-4.png)
 
4. Cuando se complete la configuración del perfil de trabajo, **seleccione Continuar** para activar y registrar el dispositivo.<br><br>
 ![Selecciona Continuar para activar y registrar el dispositivo.](images/duo-wp-5.png)

5. Selecciona **Continuar**.<br><br>
 ![Seleccione continuar de nuevo.](images/duo-wp-6.png)

6. Cuando haya activado el perfil de trabajo, **seleccione Continuar para** actualizar la configuración del dispositivo. En este ejemplo, el perfil de trabajo aplica una configuración MDM para requerir una contraseña alfanumérica de 6 dígitos más fuerte. <br><br>

     ![Contraseña alfanumérica de ejemplo.](images/duo-wp-7.png)<br><br>
7. Seleccione **Resolver** para especificar la autenticación necesaria y, a continuación, **seleccione Continuar** para completar la configuración del perfil de trabajo. <br><br>
     ![Seleccione continuar para completar la instalación.](images/duo-wp-8.png)<br><br>
     ![completar la configuración.](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>Obtén más información

- [Configurar la inscripción de dispositivos Enterprise de perfil de trabajo de Android](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)


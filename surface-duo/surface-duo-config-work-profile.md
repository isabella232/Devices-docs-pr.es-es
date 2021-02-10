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
# <span data-ttu-id="5deb6-103">Configurar el perfil de trabajo de Android Enterprise para Surface Duo</span><span class="sxs-lookup"><span data-stu-id="5deb6-103">Configure Android Enterprise Work Profile for Surface Duo</span></span>

<span data-ttu-id="5deb6-104">Destinados a implementaciones byod, los perfiles de trabajo proporcionan un espacio independiente en Duo para las aplicaciones y los datos de trabajo, lo que proporciona a las organizaciones un control total de sus datos, aplicaciones y directivas de seguridad sin impedir que los empleados utilicen su dispositivo para aplicaciones y datos personales.</span><span class="sxs-lookup"><span data-stu-id="5deb6-104">Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.</span></span>

### <span data-ttu-id="5deb6-105">Configurar el perfil de trabajo de Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="5deb6-105">Set up Android Enterprise Work Profile</span></span>

<span data-ttu-id="5deb6-106">Usa perfiles de trabajo para administrar datos corporativos y aplicaciones en dispositivos Android de propiedad del usuario.</span><span class="sxs-lookup"><span data-stu-id="5deb6-106">Use work profiles to manage corporate data and apps on user-owned Android devices.</span></span> <span data-ttu-id="5deb6-107">De forma predeterminada, la inscripción de dispositivos de perfil de trabajo de propiedad personal está habilitada y no requiere ninguna otra configuración de administrador.</span><span class="sxs-lookup"><span data-stu-id="5deb6-107">By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.</span></span>  

**<span data-ttu-id="5deb6-108">Para habilitar el perfil de trabajo empresarial:</span><span class="sxs-lookup"><span data-stu-id="5deb6-108">To enable Enterprise Work Profile:</span></span>**

- <span data-ttu-id="5deb6-109">En Endpoint Manager, seleccione **Dispositivos para**la inscripción de Android y, a  >  \*\*\*\*  >  \*\*\*\* continuación, seleccione **Dispositivos personales con perfil de trabajo.**</span><span class="sxs-lookup"><span data-stu-id="5deb6-109">In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.</span></span>
<br><br>
 ![Habilitar perfil de trabajo empresarial](images/enroll-start.png)

 
**<span data-ttu-id="5deb6-111">Iniciar sesión en Surface Duo con el perfil de trabajo de Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="5deb6-111">Sign into Surface Duo with Android Enterprise Work Profile</span></span>**

1. <span data-ttu-id="5deb6-112">Instala la aplicación Portal de empresa desde Google Play Store e inicia sesión con tu cuenta de Microsoft trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="5deb6-112">Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.</span></span><br><br>
![Iniciar sesión en Surface Duo](images/duo-wp-1.png)
 
2. <span data-ttu-id="5deb6-114">En la página Configuración de Access, seleccione **Comenzar**.</span><span class="sxs-lookup"><span data-stu-id="5deb6-114">On the Access Setup page, select **Begin**.</span></span><br><br>
![Begin](images/duo-wp-2.png)

3. <span data-ttu-id="5deb6-116">Revise la información de la página de privacidad y seleccione **Continuar.**</span><span class="sxs-lookup"><span data-stu-id="5deb6-116">Review the information on the privacy page and select **Continue**.</span></span><br><br>
 ![Continuar](images/duo-wp-3.png)
<br><br>
 ![Seleccionar continuar](images/duo-wp-4.png)
 
4. <span data-ttu-id="5deb6-119">Cuando se complete la configuración del perfil de trabajo, seleccione **Continuar** para activar y registrar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5deb6-119">When the work profile setup completes, select **Continue** to activate and register the device.</span></span><br><br>
 ![Seleccionar continuar para activar y registrar el dispositivo](images/duo-wp-5.png)

5. <span data-ttu-id="5deb6-121">Selecciona **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="5deb6-121">Select **Continue**.</span></span><br><br>
 ![Seleccionar continuar de nuevo](images/duo-wp-6.png)

6. <span data-ttu-id="5deb6-123">Cuando haya activado el perfil de trabajo, seleccione **Continuar** para actualizar la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5deb6-123">When you have activated the work profile, select **Continue** to update device settings.</span></span> <span data-ttu-id="5deb6-124">En este ejemplo, el perfil de trabajo aplica una configuración MDM para requerir una contraseña alfanumérica de 6 dígitos más segura.</span><span class="sxs-lookup"><span data-stu-id="5deb6-124">In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password.</span></span> <br><br>

     ![Ejemplo de contraseña alfanumérica](images/duo-wp-7.png)<br><br>
7. <span data-ttu-id="5deb6-126">Seleccione **Resolver para** especificar la autenticación necesaria y, a continuación, seleccione **Continuar** para completar la configuración del perfil de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5deb6-126">Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup.</span></span> <br><br>
     ![Seleccionar continuar para completar la configuración](images/duo-wp-8.png)<br><br>
     ![completar la configuración](images/duo-wp-9.png)<br><br>

## <span data-ttu-id="5deb6-129">Más información</span><span class="sxs-lookup"><span data-stu-id="5deb6-129">Learn more</span></span>

- [<span data-ttu-id="5deb6-130">Configurar la inscripción de dispositivos de perfiles de trabajo de Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="5deb6-130">Set up enrollment of Android Enterprise work profile devices</span></span>](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)


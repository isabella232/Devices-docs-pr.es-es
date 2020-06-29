---
title: Implementar aplicaciones en Surface Hub 2S con Intune
description: Obtenga información sobre cómo puede implementar aplicaciones en Surface Hub 2S con Intune.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835689"
---
# <span data-ttu-id="7a8af-104">Implementar aplicaciones en Surface Hub 2S con Intune</span><span class="sxs-lookup"><span data-stu-id="7a8af-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="7a8af-105">Puede instalar aplicaciones adicionales para satisfacer las necesidades de su equipo o de la organización.</span><span class="sxs-lookup"><span data-stu-id="7a8af-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="7a8af-106">Pautas para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="7a8af-106">Developer guidelines</span></span>

- <span data-ttu-id="7a8af-107">Surface Hub solo puede ejecutar [aplicaciones de la Plataforma universal de Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span><span class="sxs-lookup"><span data-stu-id="7a8af-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="7a8af-108">Las aplicaciones creadas con [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) no se ejecutarán en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7a8af-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="7a8af-109">Las aplicaciones deben elegirse para la [familia de dispositivos universales](https://msdn.microsoft.com/library/windows/apps/dn894631) o la familia de dispositivos del Equipo de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a8af-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="7a8af-110">Surface Hub solo admite [aplicaciones con licencia sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de [Microsoft Store para empresas](https://businessstore.microsoft.com/store).</span><span class="sxs-lookup"><span data-stu-id="7a8af-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="7a8af-111">De manera predeterminada, deben ser aplicaciones firmadas por la Store para poder instalarse.</span><span class="sxs-lookup"><span data-stu-id="7a8af-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="7a8af-112">Durante la fase de desarrollo y prueba, también puedes elegir ejecutar aplicaciones para UWP firmadas por el desarrollador colocando el dispositivo en modo de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="7a8af-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="7a8af-113">Al desarrollar y enviar aplicaciones a Microsoft Store, establezca disponibilidad de familia de dispositivos y opciones de licencia organizacional para asegurarse de que las aplicaciones estén disponibles para su ejecución en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7a8af-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="7a8af-114">Necesita credenciales de administrador para instalar aplicaciones en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="7a8af-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="7a8af-115">Diseñado para su uso en salas de reuniones y otros espacios compartidos, Surface Hub impide que los usuarios normales tengan acceso a Microsoft Store para descargar e instalar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7a8af-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="7a8af-116">Instrucciones de implementación</span><span class="sxs-lookup"><span data-stu-id="7a8af-116">Deployment guidelines</span></span>

<span data-ttu-id="7a8af-117">Puedes implementar aplicaciones de la plataforma universal de Windows (UWP) en Surface Hub 2S con Intune, lo que facilita la implementación de aplicaciones en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7a8af-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="7a8af-118">Para implementar aplicaciones, habilite MDM para su organización.</span><span class="sxs-lookup"><span data-stu-id="7a8af-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="7a8af-119">En el portal de Intune, seleccione **Intune** como su autoridad de MDM (recomendado).</span><span class="sxs-lookup"><span data-stu-id="7a8af-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![Elegir la autoridad de MDM](images/sh2-set-intune5.png)

2. <span data-ttu-id="7a8af-121">Habilitar Microsoft Store para empresas en Intune.</span><span class="sxs-lookup"><span data-stu-id="7a8af-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="7a8af-122">Abra Intune, seleccione **aplicaciones**  >  **de cliente Microsoft Store para empresas.**</span><span class="sxs-lookup"><span data-stu-id="7a8af-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![Habilitar tienda para empresas](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="7a8af-124">En Intune, Abra **Microsoft Store para empresas** y seleccione **configuración**  >  **distribuir**  >  **herramientas de administración**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="7a8af-125">Elija **Microsoft Intune** como la herramienta de administración.</span><span class="sxs-lookup"><span data-stu-id="7a8af-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![Agregar Intune como herramienta de administración](images/sh2-set-intune8.png)

4. <span data-ttu-id="7a8af-127">En Microsoft Store para empresas, seleccione **configuración**evaluación de la  >  **Shop**  >  **compra**y, a continuación, seleccione **Mostrar aplicaciones sin conexión**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="7a8af-128">Las aplicaciones sin conexión hacen referencia a las aplicaciones que se pueden sincronizar a Intune y a implementar de forma centralizada en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a8af-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="7a8af-129">Después de habilitar las compras sin conexión, puede adquirir licencias sin conexión para las aplicaciones que puede sincronizar con Intune e implementar como licencias de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7a8af-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="7a8af-130">En aplicaciones cliente de **Intune**  >  **Client apps**  >  ,**Microsoft Store para empresas**, seleccione **sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="7a8af-131">En la página aplicaciones cliente, busque la aplicación en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7a8af-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="7a8af-132">Asigne las aplicaciones al grupo o grupos de dispositivos que desee.</span><span class="sxs-lookup"><span data-stu-id="7a8af-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="7a8af-133">Seleccione **tareas**  >  **Agregar grupo**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* Asignar aplicaciones a grupos \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="7a8af-135">En tipo de asignación, elija **obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-135">Under assignment type, choose **Required**.</span></span> <br>

![\* Asignar aplicaciones a grupos \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="7a8af-137">Para los grupos seleccionados, elija **licencias de dispositivo** y, después, haga clic en **Aceptar** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="7a8af-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* Asignar aplicaciones a grupos \*](images/sh2-apps-assign.png)

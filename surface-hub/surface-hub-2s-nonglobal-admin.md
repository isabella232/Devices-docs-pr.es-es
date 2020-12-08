---
title: Configurar cuentas de administrador no global en Surface Hub 2S
description: En este artículo se describe cómo configurar cuentas de administrador que no son globales para administrar Surface Hub 2S.
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196834"
---
# <span data-ttu-id="f45dc-104">Configurar cuentas de administrador no global en Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="f45dc-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="f45dc-105">Cuando se une a Surface Hub 2S a un dominio de Azure AD, puede configurar cuentas de administrador no globales que limiten los permisos para la administración de la aplicación de configuración en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f45dc-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="f45dc-106">Esto le permite conceder permisos de administrador de ámbito solo para Surface Hub 2S e impedir el acceso de administrador potencialmente no deseado a todo un dominio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="f45dc-107">Antes de empezar, asegúrese de que Surface Hub 2S esté unido a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="f45dc-108">Si no es así, tendrá que restablecer Surface Hub 2S y completar el programa de configuración de instalación fuera de servicio (OOBE) por primera vez, eligiendo la opción de unirse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="f45dc-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="f45dc-109">Summary</span></span> 

<span data-ttu-id="f45dc-110">El proceso de creación de cuentas de administrador que no sean globales implica los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="f45dc-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="f45dc-111">En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f45dc-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="f45dc-112">Obtén el SID de grupo de Azure AD con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f45dc-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="f45dc-113">Crear un archivo XML que contenga el SID de grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="f45dc-114">Cree un grupo de seguridad que contenga los dispositivos Surface Hub 2S que administrará el grupo de seguridad administradores no globales.</span><span class="sxs-lookup"><span data-stu-id="f45dc-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="f45dc-115">Crear un perfil de configuración personalizado dirigido al grupo de seguridad que contiene los dispositivos Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f45dc-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="f45dc-116">Crear grupos de seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="f45dc-116">Create Azure AD security groups</span></span>

<span data-ttu-id="f45dc-117">En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador.</span><span class="sxs-lookup"><span data-stu-id="f45dc-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="f45dc-118">A continuación, cree otro grupo de seguridad para los dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="f45dc-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="f45dc-119">Crear un grupo de seguridad para cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="f45dc-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="f45dc-120">Inicie sesión en Intune a través del [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), seleccione **grupos**  >  **nuevo grupo** > y en tipo de grupo, seleccione **seguridad.**</span><span class="sxs-lookup"><span data-stu-id="f45dc-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="f45dc-121">Escriba un nombre de grupo, por ejemplo, **administrador local de Surface Hub** y, a continuación, seleccione **crear.**</span><span class="sxs-lookup"><span data-stu-id="f45dc-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Crear un grupo de seguridad para administradores de concentradores](images/sh-create-sec-group.png)

3. <span data-ttu-id="f45dc-123">Abra el grupo, seleccione **miembros**y, a continuación, elija **Agregar miembros** para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f45dc-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="f45dc-124">Para obtener más información sobre la creación de grupos en Intune, vea  [agregar grupos para organizar usuarios y dispositivos](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="f45dc-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="f45dc-125">Crear un grupo de seguridad para dispositivos Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="f45dc-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="f45dc-126">Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos de concentrador; por ejemplo, **dispositivos Surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Crear un grupo de seguridad para dispositivos concentradores](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="f45dc-128">Obtener el SID de grupo de Azure AD con PowerShell</span><span class="sxs-lookup"><span data-stu-id="f45dc-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="f45dc-129">Inicie PowerShell con privilegios de cuenta elevados (**Ejecutar como administrador**) y asegúrese de que su sistema está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f45dc-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="f45dc-130">Para obtener más información, consulte [acerca de las directivas de ejecución](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="f45dc-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="f45dc-131">[Instale el módulo de Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="f45dc-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="f45dc-132">Inicie sesión en su inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="f45dc-133">Cuando haya iniciado sesión en su inquilino, ejecute el siguiente commandlet.</span><span class="sxs-lookup"><span data-stu-id="f45dc-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="f45dc-134">Le pedirá que escriba el identificador de objeto de su grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f45dc-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="f45dc-135">En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="f45dc-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copiar el identificador de objeto del grupo de seguridad](images/sh-objectid.png)

6. <span data-ttu-id="f45dc-137">Ejecute los siguientes commandlet para obtener el SID del grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="f45dc-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="f45dc-138">Pegue el identificador de objeto en la commandlet de PowerShell, presione **entrar**y, a continuación, copie el **SID de grupo de Azure ad** en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="f45dc-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="f45dc-139">Crear un archivo XML que contenga el SID de grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="f45dc-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="f45dc-140">Copie lo siguiente en un editor de texto:</span><span class="sxs-lookup"><span data-stu-id="f45dc-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="f45dc-141">Reemplace el marcador de posición SID (que comienza con S-1-12-1) por el SID de su **grupo de Azure ad** y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="f45dc-142">Crear Perfil de configuración personalizado</span><span class="sxs-lookup"><span data-stu-id="f45dc-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="f45dc-143">En Endpoint Manager, seleccione perfiles de configuración de **dispositivos**  >  **Configuration profiles**  >  **crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="f45dc-144">En plataforma **, seleccione Windows 10 y versiones posteriores.**</span><span class="sxs-lookup"><span data-stu-id="f45dc-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="f45dc-145">En perfil, seleccione **personalizado**y, a continuación, haga clic en **crear.**</span><span class="sxs-lookup"><span data-stu-id="f45dc-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="f45dc-146">Agregue un nombre y una descripción y, después, seleccione **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="f45dc-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="f45dc-147">En **configuración**  >  **de configuración OMA-URI**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="f45dc-148">En el panel Agregar fila, agregue un nombre y, en     **OMA-URI**, agregue la siguiente cadena:</span><span class="sxs-lookup"><span data-stu-id="f45dc-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="f45dc-149">En tipo de datos, seleccione **cadena XML** y examinar para abrir el archivo XML que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="f45dc-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![Cargar archivo de configuración XML de administración local](images/sh-local-admin-config.png)

7. <span data-ttu-id="f45dc-151">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-151">Click **Save**.</span></span>
8. <span data-ttu-id="f45dc-152">Haga clic en **seleccionar grupos para incluir** y elija el [grupo de seguridad que creó anteriormente](#create-security-group-for-surface-hub-2s-devices) (**dispositivos Surface Hub**).</span><span class="sxs-lookup"><span data-stu-id="f45dc-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="f45dc-153">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-153">Click **Next.**</span></span>
9. <span data-ttu-id="f45dc-154">En reglas de aplicabilidad, agregue una regla si lo desea.</span><span class="sxs-lookup"><span data-stu-id="f45dc-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="f45dc-155">En caso contrario, seleccione **siguiente** y, después, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="f45dc-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="f45dc-156">Para obtener más información sobre los perfiles de configuración personalizados que usan cadenas OMA-URI, consulte [usar la configuración personalizada para dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="f45dc-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="f45dc-157">Administradores no globales que administran Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="f45dc-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="f45dc-158">Ahora, los miembros del grupo de seguridad de **Surface Hub local** se pueden iniciar sesión en la aplicación configuración en Surface Hub 2s y administrar la configuración.</span><span class="sxs-lookup"><span data-stu-id="f45dc-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>

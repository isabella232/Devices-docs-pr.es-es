---
title: Configurar cuentas de administrador no global en Surface Hub 2S
description: En este artículo se describe cómo configurar cuentas de administrador no globales para administrar Surface Hub 2S.
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
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385178"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a><span data-ttu-id="8ece3-104">Configurar cuentas de administrador no global en Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8ece3-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="8ece3-105">Cuando unes Surface Hub 2S a un dominio de Azure AD, puedes configurar cuentas de administrador no globales que limiten los permisos a la administración de la aplicación Configuración en Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="8ece3-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="8ece3-106">Esto te permite tener en cuenta los permisos de administrador solo para Surface Hub 2S e impedir el acceso de administrador potencialmente no deseado en todo un dominio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ece3-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="8ece3-107">Antes de empezar, asegúrate de que Surface Hub 2S esté unido a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ece3-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="8ece3-108">Si no es así, deberás restablecer Surface Hub 2S y completar el programa de configuración de la primera vez y lista para usar (OOBE), eligiendo la opción de unirte a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ece3-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="8ece3-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="8ece3-109">Summary</span></span> 

<span data-ttu-id="8ece3-110">El proceso de creación de cuentas de administración no globales implica los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8ece3-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="8ece3-111">En Microsoft Intune, crea un grupo de seguridad que contenga los administradores designados para administrar Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="8ece3-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="8ece3-112">Obtener SID de grupo de Azure AD con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ece3-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="8ece3-113">Cree un archivo XML que contenga sid de grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ece3-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="8ece3-114">Crea un grupo de seguridad que contenga los dispositivos Surface Hub 2S que administrará el grupo seguridad de administradores no globales.</span><span class="sxs-lookup"><span data-stu-id="8ece3-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="8ece3-115">Crea un perfil de configuración personalizado destinado al grupo de seguridad que contiene tus dispositivos Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="8ece3-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="8ece3-116">Crear grupos de seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ece3-116">Create Azure AD security groups</span></span>

<span data-ttu-id="8ece3-117">En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador.</span><span class="sxs-lookup"><span data-stu-id="8ece3-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="8ece3-118">A continuación, crea otro grupo de seguridad para dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="8ece3-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="8ece3-119">Crear grupo de seguridad para cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="8ece3-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="8ece3-120">Inicie sesión en Intune a través \*\*\*\* del Centro de administración de [Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)seleccione Grupos nuevos > y, en Tipo de  >  \*\*\*\* grupo, seleccione **Seguridad.**</span><span class="sxs-lookup"><span data-stu-id="8ece3-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="8ece3-121">Escribe un nombre de grupo (por ejemplo, Administradores locales de **Surface Hub)** y, a continuación, selecciona **Crear.**</span><span class="sxs-lookup"><span data-stu-id="8ece3-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Crear grupo de seguridad para administradores de concentradores](images/sh-create-sec-group.png)

3. <span data-ttu-id="8ece3-123">Abre el grupo, selecciona **Miembros**y, a continuación, elige Agregar miembros para escribir las cuentas de administrador que quieras designar como administradores no globales en Surface Hub 2S. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="8ece3-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="8ece3-124">Para obtener más información sobre cómo crear grupos en Intune, consulte [Agregar grupos para organizar usuarios y dispositivos.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="8ece3-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-2s-devices"></a><span data-ttu-id="8ece3-125">Crear grupo de seguridad para dispositivos Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8ece3-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="8ece3-126">Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos concentradores; por ejemplo, **dispositivos Surface Hub**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Crear grupo de seguridad para dispositivos concentradores](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="8ece3-128">Obtener SID de grupo de Azure AD con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ece3-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="8ece3-129">Inicie PowerShell con privilegios de cuenta elevados **(Ejecutar**como administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ece3-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="8ece3-130">Para obtener más información, consulte [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="8ece3-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="8ece3-131">[Instalar el módulo de PowerShell de Azure](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="8ece3-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="8ece3-132">Inicie sesión en el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8ece3-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="8ece3-133">Cuando haya iniciado sesión en el inquilino, ejecute el siguiente commandlet.</span><span class="sxs-lookup"><span data-stu-id="8ece3-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="8ece3-134">Se le pedirá que "Escriba el identificador de objeto de su grupo de Azure AD".</span><span class="sxs-lookup"><span data-stu-id="8ece3-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="8ece3-135">En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="8ece3-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copy Object id. del grupo de seguridad](images/sh-objectid.png)

6. <span data-ttu-id="8ece3-137">Ejecute el siguiente commandlet para obtener el SID del grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="8ece3-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="8ece3-138">Pegue el id. de objeto en el commandlet de PowerShell, presione **Entrar**y, a continuación, copie el **SID** de grupo de Azure AD en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8ece3-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="8ece3-139">Crear archivo XML que contenga sid de grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8ece3-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="8ece3-140">Copie lo siguiente en un editor de texto:</span><span class="sxs-lookup"><span data-stu-id="8ece3-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="8ece3-141">Reemplace el SID de marcador de posición (empezando por S-1-12-1) por su **SID** de grupo de Azure AD y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="8ece3-142">Crear perfil de configuración personalizado</span><span class="sxs-lookup"><span data-stu-id="8ece3-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="8ece3-143">En Endpoint Manager, seleccione **Perfiles**  >  **de configuración de dispositivos Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="8ece3-144">En Plataforma, **selecciona Windows 10 y versiones posteriores.**</span><span class="sxs-lookup"><span data-stu-id="8ece3-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="8ece3-145">En Perfil, seleccione **Personalizado**y, a continuación, **seleccione Crear.**</span><span class="sxs-lookup"><span data-stu-id="8ece3-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="8ece3-146">Agregue un nombre y una descripción y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="8ece3-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="8ece3-147">En **Configuración**  >  **OMA-URI Settings**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="8ece3-148">En el panel Agregar fila, agregue un nombre y, en     **OMA-URI,** agregue la siguiente cadena:</span><span class="sxs-lookup"><span data-stu-id="8ece3-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="8ece3-149">En Tipo de datos, seleccione **String XML** y busque para abrir el archivo XML que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8ece3-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![cargar archivo de configuración xml de administración local](images/sh-local-admin-config.png)

7. <span data-ttu-id="8ece3-151">Haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-151">Click **Save**.</span></span>
8. <span data-ttu-id="8ece3-152">Haz **clic en Seleccionar grupos para incluir** y elegir el grupo de seguridad que [creaste anteriormente](#create-security-group-for-surface-hub-2s-devices) (**dispositivos Surface Hub**).</span><span class="sxs-lookup"><span data-stu-id="8ece3-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="8ece3-153">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-153">Click **Next.**</span></span>
9. <span data-ttu-id="8ece3-154">En Reglas de aplicabilidad, agregue una regla si lo desea.</span><span class="sxs-lookup"><span data-stu-id="8ece3-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="8ece3-155">De lo contrario, **seleccione Siguiente** y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="8ece3-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="8ece3-156">Para obtener más información sobre los perfiles de configuración personalizados con cadenas OMA-URI, consulta Usar la configuración personalizada para dispositivos [Windows 10 en Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="8ece3-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub-2s"></a><span data-ttu-id="8ece3-157">Administradores no globales que administran Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="8ece3-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="8ece3-158">Los miembros del grupo seguridad de **administradores** locales de Surface Hub ahora pueden iniciar sesión en la aplicación Configuración de Surface Hub 2S y administrar la configuración.</span><span class="sxs-lookup"><span data-stu-id="8ece3-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>

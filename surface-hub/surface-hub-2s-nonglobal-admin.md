---
title: Configurar cuentas de administrador no globales en Surface Hub
description: En este artículo se describe cómo configurar cuentas de administrador que no son globales para administrar Surface Hub y Surface Hub 2S.
keywords: Surface Hub, Surface Hub v1, Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/22/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 11170f6c202faef7aa3dddcb8aa8c6fa84bea80f
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643866"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a><span data-ttu-id="d5774-104">Configurar cuentas de administrador no globales en Surface Hub</span><span class="sxs-lookup"><span data-stu-id="d5774-104">Configure non Global admin accounts on Surface Hub</span></span>

<span data-ttu-id="d5774-105">La actualización de Windows 10 Team 2020 agrega compatibilidad para configurar cuentas de administrador no globales que limiten los permisos a la administración de la aplicación Configuración en dispositivos Surface Hub unidos a un dominio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5774-105">The Windows 10 Team 2020 Update adds support for configuring non Global admin accounts that limit permissions to management of the Settings app on Surface Hub devices joined to an Azure AD domain.</span></span> <span data-ttu-id="d5774-106">Esto le permite tener en cuenta los permisos de administración Surface Hub y evitar el acceso de administrador potencialmente no deseado en todo un dominio de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5774-106">This enables you to scope admin permissions for Surface Hub only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="d5774-107">Antes de comenzar, asegúrese de que el Surface Hub está unido a Azure AD e Intune autoinscribirse.</span><span class="sxs-lookup"><span data-stu-id="d5774-107">Before you begin, make sure your Surface Hub is joined to Azure AD and Intune auto-enrolled.</span></span> <span data-ttu-id="d5774-108">Si no es así, tendrá que restablecer Surface Hub y completar el programa de instalación de la primera vez y sin necesidad de usar (OOBE), eligiendo la opción de unirse a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5774-108">If not, you will need to reset Surface Hub and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="d5774-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="d5774-109">Summary</span></span> 

<span data-ttu-id="d5774-110">El proceso de creación de cuentas de administración no globales implica los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="d5774-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="d5774-111">En Microsoft Intune, cree un grupo de seguridad que contenga los administradores designados para administrar Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="d5774-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub.</span></span>
2. <span data-ttu-id="d5774-112">Obtener SID de grupo de Azure AD con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5774-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="d5774-113">Cree un archivo XML que contenga sid de grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5774-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="d5774-114">Cree un grupo de seguridad que contenga los Surface Hub que administrará el grupo seguridad de administradores no globales.</span><span class="sxs-lookup"><span data-stu-id="d5774-114">Create a Security Group containing the Surface Hub devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="d5774-115">Crea un perfil de configuración personalizado destinado al grupo de seguridad que contiene los Surface Hub dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5774-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="d5774-116">Crear grupos de seguridad de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d5774-116">Create Azure AD security groups</span></span>

<span data-ttu-id="d5774-117">En primer lugar, cree un grupo de seguridad que contenga las cuentas de administrador.</span><span class="sxs-lookup"><span data-stu-id="d5774-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="d5774-118">A continuación, cree otro grupo de seguridad para Surface Hub dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5774-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="d5774-119">Crear grupo de seguridad para cuentas de administrador</span><span class="sxs-lookup"><span data-stu-id="d5774-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="d5774-120">Inicie sesión en Intune a [través Microsoft Endpoint Manager centro](https://go.microsoft.com/fwlink/?linkid=2109431)de administración, seleccione Grupos nuevos grupos > y, en Tipo de \*\*\*\*  >  \*\*\*\* grupo, seleccione **Seguridad.**</span><span class="sxs-lookup"><span data-stu-id="d5774-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="d5774-121">Escriba un nombre de grupo (por ejemplo, **Surface Hub administradores locales)** y, a continuación, **seleccione Crear.**</span><span class="sxs-lookup"><span data-stu-id="d5774-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![Crear grupo de seguridad para administradores de concentradores](images/sh-create-sec-group.png)

3. <span data-ttu-id="d5774-123">Abra el grupo, seleccione **Miembros**y, a continuación, elija Agregar miembros para especificar las cuentas de administrador que desea designar como administradores no globales en Surface Hub. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d5774-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub.</span></span> <span data-ttu-id="d5774-124">Para obtener más información sobre cómo crear grupos en Intune, consulte [Agregar grupos para organizar usuarios y dispositivos.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="d5774-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-devices"></a><span data-ttu-id="d5774-125">Crear grupo de seguridad para Surface Hub dispositivos</span><span class="sxs-lookup"><span data-stu-id="d5774-125">Create security group for Surface Hub devices</span></span>

1. <span data-ttu-id="d5774-126">Repita el procedimiento anterior para crear un grupo de seguridad independiente para dispositivos concentradores; por ejemplo, **Surface Hub dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="d5774-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![Crear grupo de seguridad para dispositivos concentradores](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="d5774-128">Obtener SID de grupo de Azure AD con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5774-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="d5774-129">Inicie PowerShell con privilegios de cuenta elevados **(Ejecutar**como administrador) y asegúrese de que el sistema está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5774-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="d5774-130">Para obtener más información, consulte [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span><span class="sxs-lookup"><span data-stu-id="d5774-130">To learn more, refer to [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="d5774-131">[Instalar Azure PowerShell módulo](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="d5774-131">[Install Azure PowerShell module](/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="d5774-132">Inicie sesión en el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5774-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="d5774-133">Cuando haya iniciado sesión en el inquilino, ejecute el siguiente commandlet.</span><span class="sxs-lookup"><span data-stu-id="d5774-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="d5774-134">Se le pedirá que "Escriba el identificador de objeto de su grupo de Azure AD".</span><span class="sxs-lookup"><span data-stu-id="d5774-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="d5774-135">En Intune, seleccione el grupo que creó anteriormente y copie el identificador de objeto, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="d5774-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![Copy Object id. del grupo de seguridad](images/sh-objectid.png)

6. <span data-ttu-id="d5774-137">Ejecute el siguiente commandlet para obtener el SID del grupo de seguridad:</span><span class="sxs-lookup"><span data-stu-id="d5774-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="d5774-138">Pegue el id. de objeto en el commandlet de PowerShell, presione **Entrar**y, a continuación, copie el **SID** de grupo de Azure AD en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="d5774-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="d5774-139">Crear archivo XML que contenga sid de grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d5774-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="d5774-140">Copie lo siguiente en un editor de texto:</span><span class="sxs-lookup"><span data-stu-id="d5774-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "S-1-5-32-544">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```
      > [!IMPORTANT]
      > <span data-ttu-id="d5774-141">Es posible que deba usar el [nombre localizado para la cuenta de administrador](https://social.technet.microsoft.com/wiki/contents/articles/13813.localized-names-for-administrator-account-in-windows.aspx).</span><span class="sxs-lookup"><span data-stu-id="d5774-141">You may need to use the [localized name for the Administrator account](https://social.technet.microsoft.com/wiki/contents/articles/13813.localized-names-for-administrator-account-in-windows.aspx).</span></span> <span data-ttu-id="d5774-142">No quite el miembro de administrador predeterminado del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d5774-142">Do not remove the default Administrator member from the XML file.</span></span>

2. <span data-ttu-id="d5774-143">Reemplace el SID de marcador de posición (empezando por S-1-12-1) por su **SID** de grupo de Azure AD y, a continuación, guarde el archivo como XML; por ejemplo, **aad-local-admin.xml**.</span><span class="sxs-lookup"><span data-stu-id="d5774-143">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="d5774-144">Aunque los grupos deben especificarse a través de su SID, si desea agregar usuarios de Azure directamente, se pueden agregar especificando su nombre principal de usuario (UPN) en este formato:</span><span class="sxs-lookup"><span data-stu-id="d5774-144">While groups should be specified via their SID, if you would like to add Azure users directly, they can be added by specifying their User Principal Name (UPN) in this format:</span></span> `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="d5774-145">Crear perfil de configuración personalizado</span><span class="sxs-lookup"><span data-stu-id="d5774-145">Create Custom configuration profile</span></span>

1. <span data-ttu-id="d5774-146">En Endpoint Manager, seleccione **Perfiles**  >  **de configuración de dispositivos Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="d5774-146">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="d5774-147">En Plataforma, **seleccione Windows 10 y versiones posteriores.**</span><span class="sxs-lookup"><span data-stu-id="d5774-147">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="d5774-148">En Perfil, seleccione **Personalizado**y, a continuación, **seleccione Crear.**</span><span class="sxs-lookup"><span data-stu-id="d5774-148">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="d5774-149">Agregue un nombre y una descripción y, a continuación, **seleccione Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="d5774-149">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="d5774-150">En **Configuración**  >  **OMA-URI Configuración**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5774-150">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="d5774-151">En el panel Agregar fila, agregue un nombre y, en     **OMA-URI,** agregue la siguiente cadena:</span><span class="sxs-lookup"><span data-stu-id="d5774-151">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="d5774-152">En Tipo de datos, seleccione **String XML** y busque para abrir el archivo XML que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d5774-152">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![cargar archivo de configuración xml de administración local](images/sh-local-admin-config.png)

7. <span data-ttu-id="d5774-154">Haz clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d5774-154">Click **Save**.</span></span>
8. <span data-ttu-id="d5774-155">Haga **clic en Seleccionar grupos para incluir** y elegir el grupo de seguridad que [creó anteriormente](#create-security-group-for-surface-hub-devices) ( Surface Hub**dispositivos**).</span><span class="sxs-lookup"><span data-stu-id="d5774-155">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="d5774-156">Haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d5774-156">Click **Next.**</span></span>
9. <span data-ttu-id="d5774-157">En Reglas de aplicabilidad, agregue una regla si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d5774-157">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="d5774-158">De lo contrario, **seleccione Siguiente** y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="d5774-158">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="d5774-159">Para obtener más información sobre los perfiles de configuración personalizados con cadenas OMA-URI, vea Usar la configuración personalizada para Windows 10 [dispositivos en Intune](/mem/intune/configuration/custom-settings-windows-10).</span><span class="sxs-lookup"><span data-stu-id="d5774-159">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub"></a><span data-ttu-id="d5774-160">Administradores no globales que administran Surface Hub</span><span class="sxs-lookup"><span data-stu-id="d5774-160">Non Global admins managing Surface Hub</span></span>

<span data-ttu-id="d5774-161">Los miembros del **Surface Hub seguridad** de administradores locales ahora pueden iniciar sesión en la aplicación Configuración en Surface Hub y administrar la configuración.</span><span class="sxs-lookup"><span data-stu-id="d5774-161">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub and manage settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5774-162">Se quita el acceso predeterminado de los administradores globales a Configuración aplicación (a menos que también sean miembros de este nuevo grupo de seguridad).</span><span class="sxs-lookup"><span data-stu-id="d5774-162">The default access of global admins to the Settings app is removed (unless they are also members of this new security group).</span></span>

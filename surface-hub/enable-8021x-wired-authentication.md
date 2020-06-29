---
title: Habilitar la autenticación por cable 802.1x
description: Se han habilitado políticas MDM de autenticación por cable 802.1x en dispositivos de Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836250"
---
# <span data-ttu-id="14155-103">Habilitar la autenticación por cable 802.1X</span><span class="sxs-lookup"><span data-stu-id="14155-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="14155-104">La [actualización del 14 de noviembre de 2017 de Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (compilación 15063.726) permite a las directivas de MDM de autenticación por cable 802.1X en los dispositivos de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="14155-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="14155-105">La característica permite a las organizaciones aplicar la autenticación de red por cable estandarizada usando el [protocolo de autenticación IEEE 802.1X](http://www.ieee802.org/1/pages/802.1x-2010.html).</span><span class="sxs-lookup"><span data-stu-id="14155-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="14155-106">Ya está disponible para la autenticación inalámbrica mediante perfiles WLAN a través de MDM.</span><span class="sxs-lookup"><span data-stu-id="14155-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="14155-107">En este tema se explica cómo configurar un Surface Hub para usarlo con la autenticación por cable.</span><span class="sxs-lookup"><span data-stu-id="14155-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="14155-108">La aplicación y la habilitación de la autenticación por cable 802.1X en Surface Hub se puede realizar a través de MDM [definición de OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span><span class="sxs-lookup"><span data-stu-id="14155-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="14155-109">La configuración principal que se establecerá es la directiva **LanProfile**.</span><span class="sxs-lookup"><span data-stu-id="14155-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="14155-110">Según el método de autenticación seleccionado, otras directivas pueden ser necesarias, ya sea la directiva **EapUserData** o a través de directivas de MDM para agregar certificados de usuario o equipo (como [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) para certificados de usuario/dispositivo o [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) para certificados de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="14155-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="14155-111">Elemento de directiva LanProfile</span><span class="sxs-lookup"><span data-stu-id="14155-111">LanProfile policy element</span></span>

<span data-ttu-id="14155-112">Para configurar Surface Hub para que use uno de los métodos de autenticación 802.1X admitidos, utilice el siguiente OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="14155-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="14155-113">Este nodo de OMA-URI toma una cadena de texto de XML como parámetro.</span><span class="sxs-lookup"><span data-stu-id="14155-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="14155-114">El XML proporcionado como parámetro debe cumplir el [esquema de perfil de LAN con cable](https://msdn.microsoft.com/library/cc233002.aspx) incluidos los elementos del [esquema 802.1X](https://msdn.microsoft.com/library/cc233003.aspx).</span><span class="sxs-lookup"><span data-stu-id="14155-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="14155-115">En la mayoría de los casos, un usuario o administrador puede exportar el XML LanProfile desde un PC existente que ya esté configurado en la red para 802.1x con este comando NETSH.</span><span class="sxs-lookup"><span data-stu-id="14155-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="14155-116">Al ejecutar este comando se mostrará el siguiente resultado y se colocará un archivo **Ethernet.xml** en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="14155-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="14155-117">Elemento de directiva EapUserData</span><span class="sxs-lookup"><span data-stu-id="14155-117">EapUserData policy element</span></span>

<span data-ttu-id="14155-118">Si tu método de autenticación seleccionado requiere un nombre de usuario y una contraseña en lugar de un certificado, puedes usar el elemento **EapUserData** para especificar las credenciales para el dispositivo que se usará para autenticar en la red.</span><span class="sxs-lookup"><span data-stu-id="14155-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="14155-119">Este nodo de OMA-URI toma una cadena de texto de XML como parámetro.</span><span class="sxs-lookup"><span data-stu-id="14155-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="14155-120">El XML proporcionado como parámetro debe cumplir con el [ejemplo de las propiedades de usuario de PEAP MS-CHAPv2](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span><span class="sxs-lookup"><span data-stu-id="14155-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="14155-121">En el ejemplo, deberás reemplazar todas las instancias de *test* e *ias-domain* por tu información.</span><span class="sxs-lookup"><span data-stu-id="14155-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="14155-122">Agregar certificados</span><span class="sxs-lookup"><span data-stu-id="14155-122">Adding certificates</span></span>

<span data-ttu-id="14155-123">Si el método de autenticación seleccionado es basado en certificados, tendrá que [crear un paquete de aprovisionamiento](provisioning-packages-for-surface-hub.md), [usar MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)o importar un certificado desde configuración (actualización de**configuración**  >  **y**  >  **certificados**de seguridad) para implementar esos certificados en el dispositivo Surface Hub en el almacén de certificados correspondiente.</span><span class="sxs-lookup"><span data-stu-id="14155-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="14155-124">Al agregar certificados, cada PFX debe contener un certificado único (un PFX no puede tener varios certificados).</span><span class="sxs-lookup"><span data-stu-id="14155-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>


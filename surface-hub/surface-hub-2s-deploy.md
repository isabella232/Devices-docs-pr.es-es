---
title: Crear paquetes de aprovisionamiento para Surface Hub 2S
description: Esta página describe cómo implementar Surface Hub 2S con paquetes de aprovisionamiento y otras herramientas.
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836941"
---
# <span data-ttu-id="99590-104">Crear paquetes de aprovisionamiento para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="99590-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="99590-105">Puede usar el diseñador de configuración de Windows (WCD) para crear paquetes de aprovisionamiento para automatizar el proceso de implementación de Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="99590-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="99590-106">Use paquetes de aprovisionamiento para agregar certificados, configurar servidores proxy, configurar cuentas de dispositivos y administradores de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="99590-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="99590-107">También puede usar paquetes de aprovisionamiento junto con un archivo de configuración para implementar varios Surface Hub con una sola unidad USB.</span><span class="sxs-lookup"><span data-stu-id="99590-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="99590-108">Instalar el Diseñador de configuraciones de Windows</span><span class="sxs-lookup"><span data-stu-id="99590-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="99590-109">Instale el diseñador de configuración de Windows desde Windows Assessment and Deployment Kit (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="99590-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="99590-110">Descargue e instale [ADK para Windows 10, versión 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="99590-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="99590-111">Para obtener más información, consulte [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="99590-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="99590-112">Agregar certificados</span><span class="sxs-lookup"><span data-stu-id="99590-112">Add certificates</span></span>

<span data-ttu-id="99590-113">Puede importar certificados de entidad de certificación a Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="99590-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="99590-114">Para agregar certificados a Surface Hub 2S, necesita una copia de cada certificado como X. 509 en formato. cer.</span><span class="sxs-lookup"><span data-stu-id="99590-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="99590-115">No puedes importar. CRT,. pfx ni otros formatos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="99590-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="99590-116">Los certificados deben importarse al diseñador de configuración de Windows y organizarse por jerarquía:</span><span class="sxs-lookup"><span data-stu-id="99590-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![Agregar certificados](images/sh2-wcd.png)

### <span data-ttu-id="99590-118">Configurar el proxy durante OOBE</span><span class="sxs-lookup"><span data-stu-id="99590-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="99590-119">En el diseñador de configuración de Windows, vaya a la pestaña configurar ajustes de proxy y escriba la configuración adecuada como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="99590-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![Definir la configuración de proxy](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="99590-121">Al configurar la configuración de proxy, desactive **detectar automáticamente la configuración** si tiene previsto usar una secuencia de comandos de configuración o un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="99590-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="99590-122">Puede usar un script de configuración *o* un servidor proxy, no ambos.</span><span class="sxs-lookup"><span data-stu-id="99590-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="99590-123">Surface Hub 2 de afiliados con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="99590-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="99590-124">Puede afiliar Surface Hub 2 con Azure Active Directory con un paquete de aprovisionamiento: como administrador global de Azure Active Directory, puede unir un gran número de dispositivos Windows nuevos a Azure Active Directory e Intune con un token en masa.</span><span class="sxs-lookup"><span data-stu-id="99590-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="99590-125">Para crear un token en masa, asígnele un nombre descriptivo, configure la fecha de expiración (máximo de 30 días) y use sus credenciales de administrador para adquirir el token tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="99590-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![Configurar administradores de dispositivos](images/sh2-token.png) <br><br>
 ![Configurar administradores de dispositivos](images/sh2-token2.png) <br><br>
 ![Configurar administradores de dispositivos](images/sh2-token3.png) <br><br>

### <span data-ttu-id="99590-129">Aprovisionamiento de varios dispositivos (archivo. csv)</span><span class="sxs-lookup"><span data-stu-id="99590-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="99590-130">Además del paquete de aprovisionamiento, puede usar un archivo de configuración de Surface hub para que sea aún más fácil configurar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="99590-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="99590-131">Un archivo de configuración de Surface Hub contiene una lista de cuentas de dispositivos y nombres descriptivos para la proyección inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="99590-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="99590-132">Durante la primera ejecución, se obtiene una opción para elegir una cuenta del dispositivo y un nombre descriptivo en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="99590-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="99590-133">Para crear un archivo de configuración de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="99590-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="99590-134">Con Microsoft Excel u otro editor de CSV, cree un archivo CSV denominado: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="99590-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="99590-135">Escriba una lista de cuentas de dispositivos y nombres descriptivos en este formato:</span><span class="sxs-lookup"><span data-stu-id="99590-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="99590-136">Guarde el archivo en la raíz de la unidad USB en la que ha copiado el archivo PPKG.</span><span class="sxs-lookup"><span data-stu-id="99590-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![Ejemplo de archivo de configuración](images/sh2-config-file.png)

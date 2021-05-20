---
title: Crear paquetes de aprovisionamiento para Surface Hub 2S
description: En esta página se describe cómo implementar Surface Hub 2S mediante paquetes de aprovisionamiento y otras herramientas.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576870"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="f21cf-104">Crear paquetes de aprovisionamiento para Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="f21cf-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="f21cf-105">Puede usar Windows Configuration Designer (WCD) para crear paquetes de aprovisionamiento para automatizar la implementación de Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f21cf-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="f21cf-106">Usa paquetes de aprovisionamiento para agregar certificados, configurar servidores proxy, configurar administradores de dispositivos y cuentas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f21cf-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="f21cf-107">También puedes usar paquetes de aprovisionamiento junto con un archivo de configuración para implementar varios Surface Hubs con una única unidad usb.</span><span class="sxs-lookup"><span data-stu-id="f21cf-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="f21cf-108">Instalar el Diseñador de configuraciones de Windows</span><span class="sxs-lookup"><span data-stu-id="f21cf-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="f21cf-109">Instale Windows de configuración desde el kit de evaluación Windows e implementación (ADK) para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f21cf-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="f21cf-110">Descargue e instale [el ADK para Windows 10, versión 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span><span class="sxs-lookup"><span data-stu-id="f21cf-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="f21cf-111">Para obtener más información, consulte [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="f21cf-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="f21cf-112">Agregar certificados</span><span class="sxs-lookup"><span data-stu-id="f21cf-112">Add certificates</span></span>

<span data-ttu-id="f21cf-113">Puede importar certificados de entidad de certificación a Surface Hub 2S.</span><span class="sxs-lookup"><span data-stu-id="f21cf-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="f21cf-114">Para agregar certificados a Surface Hub 2S, necesita una copia de cada certificado como X.509 en formato .cer.</span><span class="sxs-lookup"><span data-stu-id="f21cf-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="f21cf-115">No puede importar .crt, .pfx u otros formatos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="f21cf-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="f21cf-116">Los certificados deben importarse a Windows de configuración y organizarse por jerarquía:</span><span class="sxs-lookup"><span data-stu-id="f21cf-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![Agregar certificados](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="f21cf-118">Configurar proxy durante OOBE</span><span class="sxs-lookup"><span data-stu-id="f21cf-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="f21cf-119">En Windows Configuration Designer, vaya a la pestaña Configurar opciones de proxy y escriba la configuración adecuada como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f21cf-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![Definir la configuración de proxy](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="f21cf-121">Al configurar la configuración de proxy, desactiva **Detectar automáticamente** la configuración si quieres usar un script de instalación o un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f21cf-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="f21cf-122">Puede usar un script de instalación *o un* servidor proxy, no ambos.</span><span class="sxs-lookup"><span data-stu-id="f21cf-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="f21cf-123">Filiale Surface Hub 2S con Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f21cf-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="f21cf-124">Puede asociar Surface Hub 2S con Azure Active Directory mediante un paquete de aprovisionamiento: como administrador global de Azure Active Directory, puede unir un gran número de nuevos dispositivos Windows a Azure Active Directory e Intune mediante un token masivo.</span><span class="sxs-lookup"><span data-stu-id="f21cf-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="f21cf-125">Para crear un token masivo, asigne un nombre descriptivo, configure la fecha de expiración (máximo de 30 días) y use sus credenciales de administrador para adquirir el token como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="f21cf-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![Ejemplo 1 de configuración de administradores de dispositivos](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Ejemplo 2 de configurar administradores de dispositivos](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Ejemplo 3 de configurar administradores de dispositivos](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="f21cf-129">Aprovisionamiento de varios dispositivos (.csv archivo)</span><span class="sxs-lookup"><span data-stu-id="f21cf-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="f21cf-130">Además del paquete de aprovisionamiento, puedes usar un archivo de configuración Surface Hub para que sea aún más fácil configurar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f21cf-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="f21cf-131">Un Surface Hub de configuración contiene una lista de cuentas de dispositivo y nombres descriptivos para la proyección inalámbrica.</span><span class="sxs-lookup"><span data-stu-id="f21cf-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="f21cf-132">Durante la primera ejecución, obtienes una opción para elegir una cuenta de dispositivo y un nombre descriptivo de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f21cf-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="f21cf-133">Para crear un archivo Surface Hub de configuración</span><span class="sxs-lookup"><span data-stu-id="f21cf-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="f21cf-134">Con Microsoft Excel u otro editor CSV, cree un archivo CSV denominado: **SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="f21cf-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="f21cf-135">Escribe una lista de cuentas de dispositivo y nombres descriptivos en este formato:</span><span class="sxs-lookup"><span data-stu-id="f21cf-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="f21cf-136">Guarde el archivo en la raíz de la unidad usb donde copió el archivo PPKG.</span><span class="sxs-lookup"><span data-stu-id="f21cf-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![Ejemplo de archivo de configuración](images/sh2-config-file.png)

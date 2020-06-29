---
title: Usar el nombre de dominio completo con Surface Hub
description: Solucionar problemas comunes, incluidos los problemas de instalación y errores de Exchange ActiveSync.
keywords:
- Solucionar problemas comunes
- problemas de instalación
- Errores de Exchange ActiveSync
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834850"
---
# <span data-ttu-id="b21db-106">Configurar el nombre de dominio de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="b21db-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="b21db-107">Existen algunos escenarios donde es necesario especificar el nombre de dominio del servidor de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="b21db-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="b21db-108">**Varios sufijos DNS**: cuando tu infraestructura de Skype Empresarial tiene espacios de nombres inconexos como ese o más servidores tienen un sufijo DNS que no coincide con el sufijo de la dirección de inicio de sesión (SIP) para Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="b21db-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="b21db-109">**Los sufijos de Skype Empresarial y Exchange son diferentes**: cuando el sufijo de la dirección de inicio de sesión para Skype Empresarial es diferente al sufijo de la dirección de Exchange usada para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b21db-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="b21db-110">**Trabajar con certificados** : organizaciones grandes con servidores locales de Skype empresarial suelen usar certificados con su propia entidad de certificación (CA) raíz.</span><span class="sxs-lookup"><span data-stu-id="b21db-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="b21db-111">El dominio de entidad de certificación raíz suele ser diferente al dominio del servidor de Skype Empresarial, por lo que no se confía en el certificado y se produzca un error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b21db-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="b21db-112">Skype debe conocer el nombre de dominio del certificado para configurar una relación de confianza.</span><span class="sxs-lookup"><span data-stu-id="b21db-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="b21db-113">Las empresas suelen usar directivas de grupo para insertarlo en el escritorio de Skype, pero la directiva de grupo no se admite en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="b21db-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="b21db-114">Para configurar el nombre de dominio de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b21db-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="b21db-115">En Surface Hub, abre **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="b21db-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="b21db-116">Haz clic en **Surface Hub** y, a continuación, haz clic en **Llamadas y audio**.</span><span class="sxs-lookup"><span data-stu-id="b21db-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="b21db-117">En **Configuración de Skype Empresarial**, haz clic en **Configurar nombre de dominio**.</span><span class="sxs-lookup"><span data-stu-id="b21db-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="b21db-118">Escribe el nombre de dominio de tu servidor de Skype Empresarial y, después, haz clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b21db-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="b21db-119">Puedes escribir varios nombres de dominio separados por comas.</span><span class="sxs-lookup"><span data-stu-id="b21db-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="b21db-120">Por ejemplo: lync.com, outlook.com, lync.glbdns.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b21db-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![Agregar FQDN de Skype empresarial a la configuración](images/system-settings-add-fqdn.png)

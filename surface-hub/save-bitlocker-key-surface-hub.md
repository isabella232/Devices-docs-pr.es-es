---
title: Guardar la clave de BitLocker (Surface Hub)
description: Cada Microsoft Surface Hub se configura automáticamente con el software de cifrado de unidad de BitLocker. Microsoft recomienda encarecidamente que te asegures de hacer una copia de seguridad de las claves de recuperación de BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, claves de recuperación de Bitlocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836465"
---
# <span data-ttu-id="49a1e-105">Guardar la clave de BitLocker (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="49a1e-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="49a1e-106">Cada Microsoft Surface Hub se configura automáticamente con el software de cifrado de unidad de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="49a1e-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="49a1e-107">Microsoft recomienda encarecidamente que te asegures de hacer una copia de seguridad de las claves de recuperación de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="49a1e-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="49a1e-108">Hay varias maneras de administrar la clave de BitLocker en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="49a1e-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="49a1e-109">Si uniste Surface Hub a un dominio, el dispositivo realizará una copia de seguridad de la clave del dominio y la almacenará en el objeto del equipo.</span><span class="sxs-lookup"><span data-stu-id="49a1e-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="49a1e-110">Si no encuentras la clave de BitLocker después de unir el dispositivo a un dominio, es probable que tu esquema de Active Directory no admita la copia de seguridad de la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="49a1e-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="49a1e-111">Si no quieres cambiar el esquema, puedes guardar la clave de BitLocker yendo a Configuración y siguiendo el procedimiento para usar una cuenta de administrador local, lo que se detallará más adelante en esta lista.</span><span class="sxs-lookup"><span data-stu-id="49a1e-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="49a1e-112">Si has unido Surface Hub a Azure Active Directory (Azure AD), la clave de BitLocker se almacenará en la cuenta usada para unir el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49a1e-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="49a1e-113">Si está usando una cuenta de administrador local para administrar el dispositivo, puede guardarla en la aplicación **configuración** y navegar para **Actualizar &** la &gt; **recuperación**de seguridad.</span><span class="sxs-lookup"><span data-stu-id="49a1e-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="49a1e-114">Inserta una unidad USB y selecciona la opción para guardar la clave de BitLocker.</span><span class="sxs-lookup"><span data-stu-id="49a1e-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="49a1e-115">La clave se guardará en un archivo de texto en la unidad USB.</span><span class="sxs-lookup"><span data-stu-id="49a1e-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="49a1e-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="49a1e-116">Related topics</span></span>

[<span data-ttu-id="49a1e-117">Administrar Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="49a1e-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="49a1e-118">Guía del administrador de Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="49a1e-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 






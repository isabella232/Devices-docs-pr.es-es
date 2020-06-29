---
title: Administración de contraseñas (Surface Hub)
description: Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: contraseña, administración de contraseñas, rotación de contraseñas, cuenta del dispositivo
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836681"
---
# <span data-ttu-id="b3faa-104">Administración de contraseñas (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b3faa-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="b3faa-105">Cada cuenta del dispositivo de Microsoft Surface Hub requiere una contraseña para autenticarse y habilitar características en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="b3faa-106">Por motivos de seguridad, es posible que quieras cambiar (o "rotar") esta contraseña con regularidad.</span><span class="sxs-lookup"><span data-stu-id="b3faa-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="b3faa-107">Sin embargo, si la contraseña de la cuenta del dispositivo cambia, la contraseña que estaba almacenada en el dispositivo Surface Hub no será válida y se deshabilitarán todas las características que dependan de dicha cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="b3faa-108">Tendrás que actualizar la contraseña de la cuenta del dispositivo en el Surface Hub desde la aplicación Configuración para volver a habilitar estas características.</span><span class="sxs-lookup"><span data-stu-id="b3faa-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="b3faa-109">Para simplificar la administración de contraseñas de las cuentas de dispositivo de Surface Hub, hay dos opciones:</span><span class="sxs-lookup"><span data-stu-id="b3faa-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="b3faa-110">Desactivar la expiración de la contraseña para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="b3faa-111">Permitir que el dispositivo Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="b3faa-112">Desactivar la rotación de contraseñas para la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="b3faa-113">Establece la propiedad **PasswordNeverExpires** de la cuenta del dispositivo en True.</span><span class="sxs-lookup"><span data-stu-id="b3faa-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="b3faa-114">Deberías comprobar si se cumplen los requisitos de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="b3faa-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="b3faa-115">Permitir que el Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b3faa-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="b3faa-116">El Surface Hub puede administrar la contraseña de la cuenta de un dispositivo cambiándola con frecuencia sin necesidad de actualizar manualmente la información de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b3faa-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="b3faa-117">Puedes habilitar esta característica en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="b3faa-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="b3faa-118">Una vez habilitada, la contraseña de la cuenta del dispositivo cambiará semanalmente durante las horas de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b3faa-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="b3faa-119">Ten en cuenta que al cambiar la contraseña de la cuenta del dispositivo, no se mostrará la nueva contraseña.</span><span class="sxs-lookup"><span data-stu-id="b3faa-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="b3faa-120">Si necesitas iniciar sesión en la cuenta o proporcionar la contraseña de nuevo (por ejemplo, si quieres cambiar la configuración de la cuenta del dispositivo en el Surface Hub), necesitarás usar Active Directory o el portal de administración de Office 365 para restablecer la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b3faa-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3faa-121">Si la organización usa una topología híbrida (algunos servicios se hospedan localmente y otros se hospedan en línea mediante Office 365), debes configurar la cuenta del dispositivo con el formato **dominio\usuario**.</span><span class="sxs-lookup"><span data-stu-id="b3faa-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="b3faa-122">De lo contrario, la rotación de contraseñas no funcionará.</span><span class="sxs-lookup"><span data-stu-id="b3faa-122">Otherwise, password rotation will not work.</span></span>

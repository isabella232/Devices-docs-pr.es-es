---
title: Acelerador de implementaciones de Microsoft Surface (Surface)
description: Gracias al Acelerador de implementaciones de Microsoft Surface, las empresas que quieran restablecer la imagen inicial de sus dispositivos Surface podrán usar este mecanismo de implementación de forma rápida y sencilla.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: implementar, instalar, herramienta
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834393"
---
# <span data-ttu-id="75ff2-104">Acelerador de implementaciones de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="75ff2-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="75ff2-105">El acelerador de implementación de Microsoft Surface (SDA) automatiza la creación y la configuración de una experiencia de implementación recomendada de Microsoft mediante las herramientas de implementación gratuitas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75ff2-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="75ff2-106">Rediseñado en abril de 2020 para simplificar y automatizar la implementación de imágenes de Surface en un entorno corporativo, la herramienta SDA le permite crear una imagen de Windows "de fábrica" que puede personalizar según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="75ff2-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="75ff2-107">La herramienta de código empaquetado abierto basado en scripts aprovecha el Windows Assessment and Deployment Kit (ADK) para Windows 10, lo que facilita la creación de imágenes de Windows (WIM) en entornos de prueba o producción.</span><span class="sxs-lookup"><span data-stu-id="75ff2-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="75ff2-108">Si la última versión de ADK aún no está instalada, se descargará e instalará al ejecutar la herramienta SDA.</span><span class="sxs-lookup"><span data-stu-id="75ff2-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="75ff2-109">La imagen resultante se ajusta estrechamente a la configuración de las imágenes de recuperación de equipos integrados (BMR), sin necesidad de aplicaciones preinstaladas, como Microsoft Office o la aplicación Surface para UWP.</span><span class="sxs-lookup"><span data-stu-id="75ff2-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="75ff2-110">Para ejecutar SDA:</span><span class="sxs-lookup"><span data-stu-id="75ff2-110">To run SDA:</span></span>**

1. <span data-ttu-id="75ff2-111">Vaya a [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) en github.</span><span class="sxs-lookup"><span data-stu-id="75ff2-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="75ff2-112">Seleccione **clonar o descargar** y revisar el archivo Léame.</span><span class="sxs-lookup"><span data-stu-id="75ff2-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="75ff2-113">Edite el script con las variables apropiadas para su entorno, tal y como se documenta en el archivo Léame, y revise antes de ejecutarlo en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="75ff2-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![Herramienta ejecutar el acelerador de despliegue de Surface](images/surface-deployment-accelerator.png)

## <span data-ttu-id="75ff2-115">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="75ff2-115">Related links</span></span>

 - [<span data-ttu-id="75ff2-116">Herramienta de implementación de imagen de Open Source Publicada en GitHub</span><span class="sxs-lookup"><span data-stu-id="75ff2-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="75ff2-117">Descargar e instalar Windows ADK</span><span class="sxs-lookup"><span data-stu-id="75ff2-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

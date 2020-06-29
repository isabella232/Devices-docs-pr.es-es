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
# Acelerador de implementaciones de Microsoft Surface

El acelerador de implementación de Microsoft Surface (SDA) automatiza la creación y la configuración de una experiencia de implementación recomendada de Microsoft mediante las herramientas de implementación gratuitas de Microsoft.

Rediseñado en abril de 2020 para simplificar y automatizar la implementación de imágenes de Surface en un entorno corporativo, la herramienta SDA le permite crear una imagen de Windows "de fábrica" que puede personalizar según los requisitos de su organización.

La herramienta de código empaquetado abierto basado en scripts aprovecha el Windows Assessment and Deployment Kit (ADK) para Windows 10, lo que facilita la creación de imágenes de Windows (WIM) en entornos de prueba o producción. Si la última versión de ADK aún no está instalada, se descargará e instalará al ejecutar la herramienta SDA.

La imagen resultante se ajusta estrechamente a la configuración de las imágenes de recuperación de equipos integrados (BMR), sin necesidad de aplicaciones preinstaladas, como Microsoft Office o la aplicación Surface para UWP.

**Para ejecutar SDA:**

1. Vaya a [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) en github. 
2. Seleccione **clonar o descargar** y revisar el archivo Léame.
3. Edite el script con las variables apropiadas para su entorno, tal y como se documenta en el archivo Léame, y revise antes de ejecutarlo en su entorno de prueba. 

   ![Herramienta ejecutar el acelerador de despliegue de Surface](images/surface-deployment-accelerator.png)

## Vínculos relacionados

 - [Herramienta de implementación de imagen de Open Source Publicada en GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

---
title: Problemas conocidos e información adicional sobre Microsoft Surface Hub
description: Describe problemas conocidos de Microsoft Surface Hub.
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: superficie, Hub, problemas
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835433"
---
# Problemas conocidos e información adicional sobre Microsoft Surface Hub

Estamos escuchando. La calidad es una prioridad máxima y queremos mantenerte informado sobre los problemas que afectan a los clientes. A continuación se muestran algunos problemas conocidos de Microsoft Surface Hub:

- **Skype empresarial no está usando el proxy para el tráfico multimedia con RS2**
<br/>Para algunos usuarios de Surface Hub que se encuentran detrás de un proxy, Skype empresarial no utilizará el servidor proxy para los medios. Sin embargo, Surface Hub podrá iniciar sesión en la cuenta. Recibimos sus comentarios y sabemos el problema de tráfico de medios cuando usa un proxy. Estamos investigando de forma activa este problema y publicaremos soluciones tan pronto como se identifique y pruebe una solución. 

- **En el caso de los dispositivos Unidos a AAD, cuando un usuario intenta iniciar sesión en "mis reuniones & archivos", Surface Hub informa que no hay conexión a Internet.**
<br/>Somos conscientes de un conjunto de problemas que afectan al inicio de sesión y a los documentos en Surface Hub. Estamos investigando de forma activa estos problemas. Como solución alternativa hasta que se publique una resolución, los clientes pueden restablecer sus dispositivos y configurar su concentrador para usar una cuenta de administrador local. Después de volver a configurar para usar la cuenta de administrador local, "mis reuniones y archivos" funcionará de la forma esperada.
- **Inicio de sesión único al unir Azure AD**
<br/>Surface Hub se diseñó para Communal espacios, lo que afecta la manera en que se almacenan las credenciales de usuario. Por ello, actualmente existen limitaciones en el modo en que el inicio de sesión único funciona cuando se unen dispositivos de Azure AD. Microsoft tiene constancia de esta limitación y está investigando de forma activa las opciones para una resolución.
- **Se produce un error en Miracast sobre la proyección de la infraestructura en Surface Hub si el Surface Hub tiene un carácter de punto (.) en el nombre descriptivo.**
<br/>Los usuarios de Surface Hub pueden experimentar problemas para proyectar en su dispositivo si el nombre descriptivo incluye un punto o un punto en el nombre (.), por ejemplo, "conf. Room42". Para solucionar el problema, cambie el nombre descriptivo del concentrador de la **configuración**de  >  **Surface Hub**  >  **About**y, a continuación, reinicie el dispositivo. Microsoft está trabajando en una solución para este problema.
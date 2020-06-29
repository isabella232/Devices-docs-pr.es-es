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
# Configurar el nombre de dominio de Skype Empresarial

Existen algunos escenarios donde es necesario especificar el nombre de dominio del servidor de Skype Empresarial:
- **Varios sufijos DNS**: cuando tu infraestructura de Skype Empresarial tiene espacios de nombres inconexos como ese o más servidores tienen un sufijo DNS que no coincide con el sufijo de la dirección de inicio de sesión (SIP) para Skype Empresarial.  
- **Los sufijos de Skype Empresarial y Exchange son diferentes**: cuando el sufijo de la dirección de inicio de sesión para Skype Empresarial es diferente al sufijo de la dirección de Exchange usada para la cuenta del dispositivo.
- **Trabajar con certificados** : organizaciones grandes con servidores locales de Skype empresarial suelen usar certificados con su propia entidad de certificación (CA) raíz. El dominio de entidad de certificación raíz suele ser diferente al dominio del servidor de Skype Empresarial, por lo que no se confía en el certificado y se produzca un error de inicio de sesión.  Skype debe conocer el nombre de dominio del certificado para configurar una relación de confianza. Las empresas suelen usar directivas de grupo para insertarlo en el escritorio de Skype, pero la directiva de grupo no se admite en Surface Hub.

**Para configurar el nombre de dominio de Skype Empresarial Server**</br>
1. En Surface Hub, abre **Configuración**.
2. Haz clic en **Surface Hub** y, a continuación, haz clic en **Llamadas y audio**. 
3. En **Configuración de Skype Empresarial**, haz clic en **Configurar nombre de dominio**. 
4. Escribe el nombre de dominio de tu servidor de Skype Empresarial y, después, haz clic en **Aceptar**. 
   > [!TIP]
   > Puedes escribir varios nombres de dominio separados por comas. <br> Por ejemplo: lync.com, outlook.com, lync.glbdns.microsoft.com

    ![Agregar FQDN de Skype empresarial a la configuración](images/system-settings-add-fqdn.png)

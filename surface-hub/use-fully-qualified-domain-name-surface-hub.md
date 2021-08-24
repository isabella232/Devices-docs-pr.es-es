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
ms.openlocfilehash: c9617ec9c77d0f0c0333a156448ca24c18aec1db
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911765"
---
# <a name="configure-domain-name-for-skype-for-business"></a>Configurar el nombre de dominio de Skype Empresarial

Existen algunos escenarios donde es necesario especificar el nombre de dominio del servidor de Skype Empresarial:
- **Varios sufijos DNS**: cuando tu infraestructura de Skype Empresarial tiene espacios de nombres inconexos como ese o más servidores tienen un sufijo DNS que no coincide con el sufijo de la dirección de inicio de sesión (SIP) para Skype Empresarial.  
- **Los sufijos de Skype Empresarial y Exchange son diferentes**: cuando el sufijo de la dirección de inicio de sesión para Skype Empresarial es diferente al sufijo de la dirección de Exchange usada para la cuenta del dispositivo.
- **Trabajar con certificados:** las organizaciones grandes con servidores de Skype Empresarial locales usan normalmente certificados con su propia entidad de certificación raíz (CA). El dominio de entidad de certificación raíz suele ser diferente al dominio del servidor de Skype Empresarial, por lo que no se confía en el certificado y se produzca un error de inicio de sesión.  Skype debe conocer el nombre de dominio del certificado para configurar una relación de confianza. Las empresas suelen usar directivas de grupo para insertarlo en el escritorio de Skype, pero la directiva de grupo no se admite en Surface Hub.

**Para configurar el nombre de dominio de Skype Empresarial Server**</br>
1. En Surface Hub, abre **Configuración**.
2. Haz clic en **Surface Hub** y, a continuación, haz clic en **Llamadas y audio**. 
3. En **Configuración de Skype Empresarial**, haz clic en **Configurar nombre de dominio**. 
4. Escribe el nombre de dominio de tu servidor de Skype Empresarial y, después, haz clic en **Aceptar**. 
   > [!TIP]
   > Puedes escribir varios nombres de dominio separados por comas. <br> Por ejemplo: lync.com, outlook.com, lync.glbdns.microsoft.com

    ![Agregue Skype Empresarial FQDN a Configuración.](images/system-settings-add-fqdn.png)

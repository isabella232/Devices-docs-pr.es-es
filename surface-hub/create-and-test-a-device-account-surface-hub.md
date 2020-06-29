---
title: Crear y probar una cuenta del dispositivo (Surface Hub)
description: Este tema explica cómo crear y probar una cuenta del dispositivo que use Microsoft Surface Hub para comunicarse con Microsoft Exchange y Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: crear y probar una cuenta del dispositivo, cuenta del dispositivo, Surface Hub y Microsoft Exchange, Surface Hub y Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836338"
---
# Crear y probar una cuenta del dispositivo (Surface Hub)


Este tema explica cómo crear y probar una cuenta del dispositivo que use Microsoft Surface Hub para comunicarse con Microsoft Exchange y Skype.

Una **cuenta del dispositivo** es una cuenta de recursos de Exchange que Surface Hub usa para:

-   Mostrar su calendario de reuniones
-   Unirse a equipos o a llamadas de Skype empresarial
-   Enviar correo electrónico (por ejemplo, enviar el contenido de la pizarra interactiva de una reunión)

Cuando se haya aprovisionado la cuenta del dispositivo en un Surface Hub, las personas podrán agregar esta cuenta a una invitación de reunión del mismo modo que lo harían al invitar a una sala de reuniones. 

## Introducción a la configuración

Esta tabla explica los pasos principales y las decisiones de configuración cuando se crea una cuenta del dispositivo. 
 
| Paso | Descripción                     |  Propósito                             |
|------|---------------------------------|--------------------------------------|
| uno    | Crear un buzón de recursos de Exchange basado en el inicio de sesión (Exchange 2013 o posterior, o Exchange Online) | Este buzón de recursos permite que el dispositivo mantenga un calendario de reuniones, reciba convocatorias de reunión y envíe correos. Debe estar habilitado el inicio de sesión para que se pueda aprovisionar en un Surface Hub. |
| 1    | Configurar las propiedades de buzón de correo | El buzón de correo debe estar configurado con las propiedades correctas para obtener la mejor experiencia de reunión en Surface Hub. Para obtener más información acerca de las propiedades del buzón de correo, consulta [Propiedades del buzón](exchange-properties-for-surface-hub-device-accounts.md). |
| 2    | Aplicar al buzón una directiva de buzón de dispositivo móvil compatible | Surface Hub se administra mediante la administración de dispositivos móviles (MDM) en lugar de a través de directivas de buzón de dispositivo móvil. Para la compatibilidad, la cuenta del dispositivo debe tener una directiva de buzón de dispositivo móvil donde el parámetro **PasswordEnabled** esté establecido en False. De lo contrario, Surface Hub no podrá sincronizar el correo ni la información de calendario. |
| cuatro    | Habilitar el buzón con Skype Empresarial (Lync Server 2013 o posterior, o Skype Empresarial Online) | Skype Empresarial debe estar habilitado para poder usar características de conferencia, como las videollamadas, la mensajería instantánea y la pantalla compartida.  |
| 4    | (Opcional) Incluir el identificador de dispositivo de ActiveSync en una lista blanca | Tu organización puede tener una directiva global que impida que las cuentas del dispositivo sincronicen el correo y la información de calendario. Si es así, debe permitir el identificador de dispositivo ActiveSync de su Surface Hub. |
| 6    | (Opcional) Deshabilitar la caducidad de contraseña | Para simplificar la administración, puedes desactivar la caducidad de contraseña para la cuenta del dispositivo y permitir que Surface Hub rote automáticamente la contraseña de la cuenta del dispositivo. Para obtener más información acerca de la administración de contraseñas, consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md).  |

## Pasos detallados de la configuración 

Te recomendamos configurar tus cuentas del dispositivo mediante PowerShell remoto. Hay disponibles scripts de PowerShell para ayudar a crear y validar cuentas del dispositivo. Para obtener más información acerca de los scripts de PowerShell e instrucciones, consulta el [Apéndice A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md). 

Para pasos detallados sobre el uso de PowerShell para aprovisionar una cuenta del dispositivo, elige una opción de la tabla, en función de la implementación de la organización. 

| Implementación de la organización             |  Descripción                  |
|---------------------------------|--------------------------------------|
| [Implementación en línea (Office 365)](online-deployment-surface-hub-device-accounts.md) | El entorno de tu organización se implementa totalmente en Office 365. |
| [Implementación local (bosque único)](on-premises-deployment-surface-hub-device-accounts.md) | Tu organización tiene servidores que controla y usa para hospedar Active Directory, Exchange y Skype Empresarial (o Lync) en un entorno de bosque único. |
| [Implementación local (varios bosques)](on-premises-deployment-surface-hub-multi-forest.md) | Tu organización tiene servidores que controla y usa para hospedar Active Directory, Exchange y Skype Empresarial (o Lync) en un entorno de varios bosques. |
| [Implementación híbrida](hybrid-deployment-surface-hub-device-accounts.md) | Tu organización tiene una mezcla de servicios, algunos hospedados de forma local y otros hospedados en línea mediante Office 365. |
| [Implementación en línea o híbrida con el entorno de Skype Hybrid Voice](skype-hybrid-voice.md) | Tu organización tiene grupos de servidores principales de Skype Empresarial y servidores de Exchange en la nube, y usa un grupo local de Skype Empresarial 2015 o Cloud Connector Edition conectado a través de la red telefónica conmutada (RTC). |


Si prefieres usar una interfaz gráfica de usuario, se pueden realizar algunos pasos usando la interfaz de usuario en lugar de PowerShell. Para obtener más información, consulta [Crear una cuenta del dispositivo mediante la interfaz de usuario](create-a-device-account-using-office-365.md).

## Verificación y prueba de cuentas

Hay dos métodos disponibles que puedes usar para validar y probar una cuenta del dispositivo Surface Hub: [scripts de verificaciones de cuentas](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) y la [aplicación Diagnóstico de hardware de Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g). El script de verificación de cuenta validará una cuenta del dispositivo creada anteriormente mediante PowerShell desde el escritorio. La aplicación Diagnóstico de hardware de Surface Hub se instala en Surface Hub y proporciona información detallada acerca de los errores de inicio de sesión y comunicación. Ambas son herramientas valiosas para probar las cuentas del dispositivo recién creadas y deben usarse para garantizar una óptima disponibilidad de las cuentas.

 

 

 






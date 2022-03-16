---
title: Restablecer y recuperar para Surface Hub
description: Describe los procesos de restablecimiento y recuperación del Surface Hub y proporciona instrucciones.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: restablecer Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: f0292d4c2ec599ba620ab87930fbecf3bab9e078
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449283"
---
# <a name="reset-and-recovery-for-surface-hub"></a>Restablecer y recuperar para Surface Hub

En este artículo se describe cómo restablecer un Microsoft Surface Hub.  

[Al restablecer el Surface Hub](#reset-a-surface-hub), se devuelve su sistema operativo a la última actualización acumulativa Windows y se quitan todos los archivos de usuario locales y la información de configuración. La información que se quita incluye lo siguiente:

- La cuenta del dispositivo
- Información de cuenta para los administradores locales del dispositivo
- Información de unión a dominio Azure AD unirse a un dominio
- Información de inscripción de Administración de dispositivos móviles (MDM)
- Información de configuración que se estableció mediante MDM o la Configuración aplicación

Puede especificar si el proceso de recuperación conserva otra información almacenada en el Surface Hub. Si no se puede usar la opción de restablecimiento, la [herramienta de recuperación Surface Hub está](surface-hub-recovery-tool.md) disponible para volver a crear una nueva imagen del SSD Surface Hub directamente.

## <a name="reset-a-surface-hub"></a>Restablecer un Surface Hub

Es posible que tenga que restablecer el Surface Hub por motivos como los siguientes:

- Estás reconfigurando el dispositivo para un nuevo espacio de reuniones y quieres volver a configurarlo.
- Quieres cambiar el modo en que se administra el dispositivo de forma local.

Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.

> [!WARNING]
> El proceso de restablecimiento del dispositivo puede tardar hasta seis horas. No apague ni desenchufe el Surface Hub hasta que finalice el proceso. Si interrumpes el proceso, el dispositivo se vuelve inoperable. El dispositivo requiere el servicio de garantía para volver a funcionar.

1. En tu Surface Hub, abre **Configuración**.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra Configuración aplicación para Surface Hub.](images/sh-settings.png)

2. Seleccione **Actualizar & seguridad**.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra Actualizar & seguridad en Configuración aplicación para Surface Hub.](images/sh-settings-update-security.png)

3. Selecciona **Recuperación** y, a continuación, en **Restablecer dispositivo**, selecciona **Introducción**.

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, como se te pedirá más adelante. Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md). Cuando el concentrador se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento.
   
   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra la opción Restablecer dispositivo en Configuración aplicación para Surface Hub.](images/sh-settings-reset-device.png)

   Una vez terminado el proceso de restablecimiento, el Surface Hub inicia de nuevo [el primer programa de ejecución](first-run-program-surface-hub.md). Si el proceso de restablecimiento encuentra un problema, revierte el Surface Hub a la imagen del sistema operativo existente anteriormente y, a continuación, muestra la pantalla de bienvenida.

## <a name="recover-a-locked-surface-hub"></a>Recuperar un Surface Hub bloqueado

Si por algún motivo el Surface Hub se vuelve inutilizable y no puedes iniciar un restablecimiento desde la aplicación Configuración, puedes restablecer el Surface Hub si tienes la clave de recuperación de BitLocker.

1. Busque el conmutador de alimentación en la parte inferior de Surface Hub. El conmutador de alimentación está junto a la conexión del cable de alimentación. Para obtener más información acerca del conmutador de alimentación, [consulte la Surface Hub guía de preparación del sitio (PDF).](surface-hub-site-readiness-guide.md).

2. Mientras el Surface Hub muestra la pantalla de bienvenida, use el conmutador de alimentación para desactivar el Surface Hub.

3. Use el conmutador de alimentación para volver a activar Surface Hub la red. El dispositivo se inicia y muestra la Surface Hub logotipo. Cuando veas puntos giratorios debajo del logotipo de Surface Hub, usa el conmutador de energía para volver a desactivar Surface Hub.  

4. Repita el paso 3 dos veces o hasta que el Surface Hub muestre el mensaje "Preparación de la reparación automática". Después de mostrar este mensaje, el Surface Hub muestra la Windows RE pantalla.
 
5. Seleccione **Restablecer**.

6. Seleccione **Reinstalación local.**

7. Seleccione **Limpiar completamente la unidad.**
 
   ![recuperar y limpiar completamente la unidad.](images/recover-fully-clean-drive.png)

8. Se te **preguntará ¿Estás listo para restablecer este dispositivo?**. Seleccione **Restablecer**. 
   
   ![recuperar y confirmar el restablecimiento.](images/recover-confirm-reset.png)


## <a name="contact-support"></a>Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

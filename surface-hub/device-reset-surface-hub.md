---
title: Restablecer o recuperar un Surface Hub
description: Describe los procesos de restablecimiento y recuperación de Surface Hub y proporciona instrucciones.
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
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406658"
---
# <a name="reset-or-recover-a-surface-hub"></a>Restablecer o recuperar un Surface Hub

En este artículo se describe cómo restablecer o recuperar un Microsoft Surface Hub.  

[Restablecer Surface Hub devuelve](#reset-a-surface-hub) su sistema operativo a la última actualización acumulativa de Windows y quita todos los archivos de usuario locales y la información de configuración. La información que se quita incluye lo siguiente:

- La cuenta del dispositivo
- Información de cuenta para los administradores locales del dispositivo
- Información de unión a dominio o unión a Azure AD
- Información de inscripción de Administración de dispositivos móviles (MDM)
- Información de configuración que se estableció mediante MDM o la aplicación Configuración

[Recuperar un Surface Hub de la nube](#recover-a-surface-hub-from-the-cloud) también quita esta información. Además, Surface Hub descarga una nueva imagen del sistema operativo e la instala. Puedes especificar si el proceso de recuperación conserva otra información almacenada en Surface Hub. La herramienta de recuperación de [Surface Hub](surface-hub-recovery-tool.md) usa la misma imagen del sistema operativo si necesitas recuperar un Surface Hub para el que no se pueda usar ninguna de estas opciones.

## <a name="reset-a-surface-hub"></a>Restablecer un Surface Hub

Es posible que deba restablecer Surface Hub por motivos como los siguientes:

- Estás reconfigurando el dispositivo para un nuevo espacio de reuniones y quieres volver a configurarlo.
- Quieres cambiar el modo en que se administra el dispositivo de forma local.
- Se ha perdido el nombre de usuario o la contraseña de la cuenta del dispositivo o la cuenta de administrador.
- Después de instalar una actualización, el rendimiento del dispositivo disminuye.

Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.

> [!WARNING]
> El proceso de restablecimiento del dispositivo puede tardar hasta seis horas. No desactives ni desenchufes Surface Hub hasta que el proceso haya finalizado. Si interrumpes el proceso, el dispositivo se vuelve inoperable. El dispositivo requiere el servicio de garantía para volver a funcionar.

1. En tu Surface Hub, abre **Configuración**.

   ![Imagen que muestra la aplicación Configuración de Surface Hub.](images/sh-settings.png)

2. Seleccione **Actualizar & seguridad**.

   ![Imagen que muestra Actualizar & seguridad en la aplicación Configuración de Surface Hub.](images/sh-settings-update-security.png)

3. Selecciona **Recuperación**y, a continuación, en **Restablecer dispositivo,** selecciona **Introducción.**

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, como se te pedirá más adelante. Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md). Cuando el concentrador se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento.
   
   ![Imagen que muestra la opción Restablecer dispositivo en la aplicación Configuración de Surface Hub.](images/sh-settings-reset-device.png)

   Una vez terminado el proceso de restablecimiento, Surface Hub vuelve a [iniciar el primer programa de ejecución.](first-run-program-surface-hub.md) Si el proceso de restablecimiento encuentra un problema, revierte Surface Hub a la imagen del sistema operativo existente anteriormente y, a continuación, muestra la pantalla de bienvenida.

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>Recuperar un Surface Hub desde la nube

Si, por algún motivo, Surface Hub se vuelve inutilizable, puedes recuperarlo de la nube sin la ayuda del soporte técnico de Microsoft. Surface Hub puede descargar una imagen del sistema operativo nueva de la nube y usar esa imagen para reinstalar su sistema operativo.

Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:

- [Surface Hub o sus cuentas relacionadas han entrado en un estado inestable](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>El **proceso Recuperar desde la nube** requiere una conexión por cable que proporciona conectividad a Internet abierta (sin proxy u otros mensajes de autenticación).

### <a name="recover-a-surface-hub-in-a-bad-state"></a>Recuperar un Surface Hub de un estado defectuoso

Si la cuenta del dispositivo entra en un estado inestable o si la cuenta de administrador tiene problemas, puedes usar la aplicación Configuración para iniciar el proceso de recuperación en la nube. Solo debes usar el proceso de recuperación en la nube cuando [el](#reset-a-surface-hub) proceso de restablecimiento del dispositivo no solucione el problema.

1. En Surface Hub, selecciona **Configuración** &gt; **Actualizar & recuperación de** &gt; **seguridad.**

2. En **Recuperar desde la nube,** seleccione Reiniciar **ahora**.

   ![recuperar desde la nube](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>Recuperar un Surface Hub bloqueado

En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión. Cuando esto sucede, el dispositivo se reinicia automáticamente e intenta de nuevo la operación. Pero si esta operación falla repetidamente, el dispositivo se bloquea automáticamente para proteger los datos del usuario. Para desbloquearlo, debes [restablecer el](#reset-a-surface-hub) dispositivo o, si no funciona, recuperarlo de la nube.

1. Localiza el conmutador de energía en la parte inferior de Surface Hub. El conmutador de alimentación está junto a la conexión del cable de alimentación. Para obtener más información acerca del conmutador de alimentación, consulta la Guía de preparación del sitio de [Surface Hub (PDF).](surface-hub-site-readiness-guide.md)

2. Mientras surface hub muestra la pantalla de bienvenida, usa el botón de encendido para desactivar Surface Hub.

3. Usa el conmutador de energía para volver a activar Surface Hub. El dispositivo se inicia y muestra la pantalla logotipo de Surface Hub. Cuando veas puntos giratorios debajo del logotipo de Surface Hub, usa el conmutador de energía para desactivar el Surface Hub de nuevo.  

4. Repita el paso 3 tres veces o hasta que Surface Hub muestre el mensaje "Preparar reparación automática". Después de mostrar este mensaje, Surface Hub muestra la pantalla Windows RE.

 
5. Selecciona **Restablecer para volver a instalar Windows**. 
![restablecer para volver a instalar](images/recover-from-cloud.png)

8. Seleccione **Descarga en la nube.** 

   ![Descarga en la nube](images/recover-cloud-download.png)

>[!IMPORTANT]
>Si recibe un mensaje de error que indica **No se puede descargar,** seleccione **Cancelar** e inténtelo de nuevo.

9. Seleccione **Limpiar completamente la unidad.**  
![ recuperar y limpiar completamente la unidad](images/recover-fully-clean-drive.png)

10. Se te **preguntará ¿Estás listo para restablecer este dispositivo?**. Selecciona **Restablecer**. 
![recuperar y confirmar el restablecimiento](images/recover-confirm-reset.png)

11. La descarga comienza y el proceso de recuperación indica **restablecer este dispositivo**. 
![recuperación que se muestra en curso](images/recover-in-progress.png)

## <a name="contact-support"></a>Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

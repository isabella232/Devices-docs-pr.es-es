---
title: Restablecer o recuperar un Surface Hub
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
ms.openlocfilehash: ee8ac1129aab34afeb3be783133681fe80434831
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911025"
---
# <a name="reset-or-recover-a-surface-hub"></a>Restablecer o recuperar un Surface Hub

En este artículo se describe cómo restablecer o recuperar un Microsoft Surface Hub.  

[Al restablecer el Surface Hub,](#reset-a-surface-hub) se devuelve su sistema operativo a la última actualización Windows acumulativa y se quitan todos los archivos de usuario locales y la información de configuración. La información que se quita incluye lo siguiente:

- La cuenta del dispositivo
- Información de cuenta para los administradores locales del dispositivo
- Información de unión a dominio o unión a Azure AD
- Información de inscripción de Administración de dispositivos móviles (MDM)
- Información de configuración que se estableció mediante MDM o la Configuración aplicación

[La recuperación de Surface Hub de la nube](#recover-a-surface-hub-from-the-cloud) también quita esta información. Además, el Surface Hub descarga una nueva imagen del sistema operativo e la instala. Puede especificar si el proceso de recuperación conserva otra información almacenada en el Surface Hub. La herramienta de recuperación [](surface-hub-recovery-tool.md) de Surface Hub usa la misma imagen del sistema operativo si necesita recuperar una Surface Hub para la que no se puede usar ninguna de estas opciones.

## <a name="reset-a-surface-hub"></a>Restablecer un Surface Hub

Es posible que tenga que restablecer el Surface Hub por motivos como los siguientes:

- Estás reconfigurando el dispositivo para un nuevo espacio de reuniones y quieres volver a configurarlo.
- Quieres cambiar el modo en que se administra el dispositivo de forma local.
- Se ha perdido el nombre de usuario o la contraseña de la cuenta del dispositivo o la cuenta de administrador.
- Después de instalar una actualización, el rendimiento del dispositivo disminuye.

Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.

> [!WARNING]
> El proceso de restablecimiento del dispositivo puede tardar hasta seis horas. No desactive ni desenchufe el Surface Hub hasta que el proceso haya finalizado. Si interrumpes el proceso, el dispositivo se vuelve inoperable. El dispositivo requiere el servicio de garantía para volver a funcionar.

1. En tu Surface Hub, abre **Configuración**.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra Configuración aplicación para Surface Hub.](images/sh-settings.png)

2. Seleccione **Actualizar & seguridad**.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra Actualizar & seguridad en Configuración aplicación para Surface Hub.](images/sh-settings-update-security.png)

3. Selecciona **Recuperación**y, a continuación, en **Restablecer dispositivo,** selecciona **Introducción.**

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, como se te pedirá más adelante. Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md). Cuando el concentrador se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento.
   
   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra la opción Restablecer dispositivo en Configuración aplicación para Surface Hub.](images/sh-settings-reset-device.png)

   Una vez terminado el proceso de restablecimiento, el Surface Hub inicia el [primer programa de ejecución de](first-run-program-surface-hub.md) nuevo. Si el proceso de restablecimiento encuentra un problema, revierte el Surface Hub a la imagen del sistema operativo existente anteriormente y, a continuación, muestra la pantalla de bienvenida.

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>Recuperar un Surface Hub desde la nube

Si por algún motivo el Surface Hub se vuelve inutilizable, aún puede recuperarlo de la nube sin la ayuda del soporte técnico de Microsoft. El Surface Hub puede descargar una imagen del sistema operativo nueva de la nube y usar esa imagen para reinstalar su sistema operativo.

Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:

- [El Surface Hub o sus cuentas relacionadas han entrado en un estado inestable](#recover-a-surface-hub-in-a-bad-state)
- [El Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>El **proceso Recuperar desde la nube** requiere una conexión por cable que proporciona conectividad a Internet abierta (sin proxy u otros mensajes de autenticación).

### <a name="recover-a-surface-hub-in-a-bad-state"></a>Recuperar un Surface Hub de un estado defectuoso

Si la cuenta del dispositivo entra en un estado inestable o si la cuenta de administrador tiene problemas, puedes usar la aplicación Configuración para iniciar el proceso de recuperación en la nube. Solo debes usar el proceso de recuperación en la nube cuando [el](#reset-a-surface-hub) proceso de restablecimiento del dispositivo no solucione el problema.

1. En el Surface Hub, seleccione **Configuración** &gt; **Actualizar & de** &gt; **seguridad**.

2. En **Recuperar desde la nube,** seleccione Reiniciar **ahora**.

   > [!div class="mx-imgBorder"]
   > ![recuperarse de la nube.](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>Recuperar un Surface Hub bloqueado

En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión. Cuando esto sucede, el dispositivo se reinicia automáticamente e intenta de nuevo la operación. Pero si esta operación falla repetidamente, el dispositivo se bloquea automáticamente para proteger los datos del usuario. Para desbloquearlo, debes [restablecer el](#reset-a-surface-hub) dispositivo o, si no funciona, recuperarlo de la nube.

1. Busque el conmutador de alimentación en la parte inferior de Surface Hub. El conmutador de alimentación está junto a la conexión del cable de alimentación. Para obtener más información acerca del conmutador de alimentación, consulte la Surface Hub guía de preparación [del sitio (PDF).](surface-hub-site-readiness-guide.md)

2. Mientras el Surface Hub muestra la pantalla de bienvenida, use el conmutador de alimentación para desactivar el Surface Hub.

3. Use el conmutador de alimentación para volver a activar Surface Hub la red. El dispositivo se inicia y muestra la Surface Hub logotipo. Cuando veas puntos giratorios debajo del logotipo de Surface Hub, usa el conmutador de energía para volver a desactivar Surface Hub.  

4. Repita el paso 3 tres veces o hasta que Surface Hub muestra el mensaje "Preparación de reparación automática". Después de mostrar este mensaje, el Surface Hub muestra la Windows RE pantalla.
 
5. Seleccione **Restablecer**. 

6. Si se te pide que escribas la clave de BitLocker, sigue uno de estos procedimientos:
   - Para conservar la información que BitLocker protege en el Surface Hub, escriba la clave de BitLocker.
   - Para descartar la información protegida, seleccione Omitir esta unidad

7. Seleccione **Descarga en la nube.** 

   ![Descarga en la nube.](images/recover-cloud-download.png)

   >[!IMPORTANT]
   >Si recibe un mensaje de error que indica **No se puede descargar**, seleccione **Cancelar** y, a continuación, **Restablecer de** nuevo.

8. Seleccione **Limpiar completamente la unidad.**
 
   ![recuperar y limpiar completamente la unidad.](images/recover-fully-clean-drive.png)

9. Se te **preguntará ¿Estás listo para restablecer este dispositivo?**. Seleccione **Restablecer**. 
   
   ![recuperar y confirmar el restablecimiento.](images/recover-confirm-reset.png)

10. La descarga comienza y el proceso de recuperación indica **restablecer este dispositivo**.

    ![recuperación que se muestra en curso.](images/recover-in-progress.png)

## <a name="contact-support"></a>Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).


## <a name="related-topics"></a>Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

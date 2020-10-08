---
title: Restablecer o recuperar Surface Hub
description: Describe los procesos de restablecimiento y recuperación para Surface Hub, y proporciona instrucciones.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: restablecer Surface Hub, recuperar
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 1c8d8b6d89ec1a20550b7aa13c82c73a239c3965
ms.sourcegitcommit: d0a5c8fb2b37eb11858c7be4549e55c4b36d7471
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104822"
---
# Restablecer o recuperar Surface Hub

En este artículo se describe cómo restablecer o recuperar Microsoft Surface Hub.  

Al [restablecer Surface Hub](#reset-a-surface-hub) , se devuelve su sistema operativo a la última actualización acumulativa de Windows Update y se quitan todos los archivos de usuarios locales y la información de configuración. La información que se elimina incluye lo siguiente:

- La cuenta del dispositivo
- Información de la cuenta para los administradores locales del dispositivo
- Información de unión de dominios o de Azure AD-join
- Información de inscripción de la administración de dispositivos móviles (MDM)
- Información de configuración que se estableció con MDM o la aplicación configuración

[La recuperación de Surface Hub desde la nube](#recover-a-surface-hub-from-the-cloud) también elimina esta información. Además, Surface Hub descarga una nueva imagen de sistema operativo y la instala. Puede especificar si el proceso de recuperación conserva otra información almacenada en Surface Hub.

## Restablecer un Surface Hub

Es posible que tenga que restablecer su Surface Hub por razones como las siguientes:

- Va a cambiar el propósito del dispositivo para un nuevo espacio de reunión y quiere reconfigurarlo.
- Quieres cambiar el modo en que se administra el dispositivo de forma local.
- Se perdió el nombre de usuario o la contraseña de la cuenta del dispositivo o de la cuenta de administrador.
- Después de instalar una actualización, el rendimiento del dispositivo disminuye.

Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.

> [!WARNING]
> El proceso de restablecimiento del dispositivo puede demorar hasta seis horas. No apague ni desconecte Surface Hub hasta que el proceso haya terminado. Si interrumpe el proceso, el dispositivo deja de funcionar. El dispositivo requiere servicio de garantía para volver a funcionar.

1. En tu Surface Hub, abre **Configuración**.

   ![Imagen que muestra la aplicación configuración para Surface Hub.](images/sh-settings.png)

1. Seleccione **actualizar & seguridad**.

   ![Imagen que muestra la actualización & grupo de seguridad en la aplicación configuración de Surface Hub.](images/sh-settings-update-security.png)

1. Seleccione **recuperación**y, a continuación, en **restablecer dispositivo**, seleccione **Introducción.**

   ![Imagen que muestra la opción restablecer dispositivo en la aplicación de configuración de Surface Hub.](images/sh-settings-reset-device.png)

   Una vez finalizado el proceso de restablecimiento, Surface Hub inicia de nuevo el [programa de ejecución inicial](first-run-program-surface-hub.md) . Si el proceso de restablecimiento encuentra un problema, revierte la superficie del sistema operativo existente y, después, muestra la pantalla de bienvenida.

<span id="cloud-recovery" />

## Recuperar un Surface Hub desde la nube

Si, por algún motivo, Surface Hub se vuelve inutilizable, aún puede recuperarlo desde la nube sin la ayuda de soporte técnico de Microsoft. Surface Hub puede descargar una nueva imagen de sistema operativo de la nube y usar esa imagen para reinstalar su sistema operativo.

Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:

- [El Surface Hub o sus cuentas relacionadas han introducido un estado inestable](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>La **recuperación del proceso en la nube** requiere una conexión cableada que proporciona conectividad abierta a Internet (sin solicitudes de proxy u otras solicitudes de autenticación).

### Recuperar un Surface Hub de un estado defectuoso

Si la cuenta del dispositivo se encuentra en un estado inestable o si la cuenta del administrador tiene problemas, puede usar la aplicación configuración para iniciar el proceso de recuperación de la nube. Solo debe usar el proceso de recuperación de la nube cuando el proceso de [restablecimiento del dispositivo](#reset-a-surface-hub) no soluciona el problema.

1. En su Surface Hub, seleccione **configuración** &gt; **& seguridad** &gt; **recuperación**.

1. En **recuperar de la nube**, seleccione **reiniciar ahora**.

   ![recuperar desde la nube](images/recover-from-the-cloud.png)

### Recuperar un Surface Hub bloqueado

En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión. Cuando esto suceda, el dispositivo se reiniciará automáticamente y volverá a intentar la operación. Pero si esta operación falla varias veces, el dispositivo se bloqueará automáticamente para proteger los datos de usuario. Para desbloquearlo, debe [restablecer el dispositivo](#reset-a-surface-hub) o, si no funciona, recuperarlo de la nube.

1. Ubique el interruptor de encendido en la parte inferior de Surface Hub. El interruptor de alimentación está junto a la conexión del cable de alimentación. Para obtener más información sobre el cambio de alimentación, consulte la [Guía de preparación del sitio de Surface Hub (pdf)](surface-hub-site-readiness-guide.md).

1. Mientras el Surface Hub muestra la pantalla de bienvenida, use el interruptor de encendido para desactivar Surface Hub.

1. Use el interruptor de alimentación para activar de nuevo la Surface Hub. El dispositivo se inicia y muestra la pantalla del logotipo de Surface Hub. Cuando veas puntos giratorias debajo del logotipo de Surface Hub, usa el interruptor de alimentación para desactivar de nuevo la Hub de Surface.  

1. Repita el paso 3 3 horas, o hasta que el Surface Hub muestre el mensaje "preparando la reparación automática". Después de mostrar este mensaje, el Surface Hub muestra la pantalla de Windows RE.

1. Seleccione **Opciones avanzadas**.

1. Seleccione **recuperar en la nube**. (Opcionalmente, puede seleccionar **restablecer**. Sin embargo, la opción **de recuperación de la nube** es el método recomendado).

   ![Recuperar desde la nube](images/recover-from-cloud.png)
1. Si se le pide que escriba la clave de BitLocker, realice una de las siguientes acciones:

   - Para conservar la información que BitLocker protege en el Surface Hub, escriba la clave de BitLocker.
   - Para descartar la información protegida, seleccione **omitir esta unidad**  

1. Cuando se le solicite, seleccione **reinstalar**.

    ![Reinstalar](images/reinstall.png)

1. Para volver a particionar el disco, seleccione **sí**.

   ![Volver a particionar](images/repartition.png)

   En primer lugar, el proceso de recuperación descarga la imagen del sistema operativo de la nube.  

   ![descargando 97&](images/recover-progress.png)

   Cuando termine la descarga, el proceso de recuperación restaurará Surface Hub de acuerdo con las opciones que seleccionó.
   

## Contactar con el soporte técnico

Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).


## Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

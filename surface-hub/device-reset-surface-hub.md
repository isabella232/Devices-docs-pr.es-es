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
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304823"
---
# Restablecer o recuperar un Surface Hub

En este artículo se describe cómo restablecer o recuperar un Microsoft Surface Hub.  

[Al restablecer Surface Hub,](#reset-a-surface-hub) se devuelve su sistema operativo a la última actualización acumulativa de Windows y se quitan todos los archivos de usuario local y la información de configuración. La información que se quita incluye lo siguiente:

- La cuenta del dispositivo
- Información de cuenta para los administradores locales del dispositivo
- Información de unión a un dominio o unión a Azure AD
- Información de inscripción de administración de dispositivos móviles (MDM)
- Información de configuración que se estableció mediante MDM o la aplicación Configuración

[La recuperación de un Surface Hub desde la nube](#recover-a-surface-hub-from-the-cloud) también elimina esta información. Además, Surface Hub descarga una nueva imagen del sistema operativo e la instala. Puedes especificar si el proceso de recuperación conserva otra información almacenada en Surface Hub. La herramienta de recuperación de [Surface Hub](surface-hub-recovery-tool.md) usa la misma imagen del sistema operativo si necesitas recuperar un Surface Hub para el que no se pueda usar ninguna de estas opciones.

## Restablecer un Surface Hub

Es posible que tenga que restablecer surface hub por razones como las siguientes:

- Está reconfigurando el dispositivo para un nuevo espacio de reuniones y desea volver a configurarlo.
- Quieres cambiar el modo en que se administra el dispositivo de forma local.
- Se ha perdido el nombre de usuario o la contraseña de la cuenta del dispositivo o la cuenta de administrador.
- Después de instalar una actualización, disminuye el rendimiento del dispositivo.

Durante el proceso de restablecimiento, si ve una pantalla en blanco durante largos períodos de tiempo, espere y no realice ninguna acción.

> [!WARNING]
> El proceso de restablecimiento del dispositivo puede tardar hasta seis horas. No apagues ni desconectes Surface Hub hasta que finalice el proceso. Si interrumpes el proceso, el dispositivo se vuelve inoperable. El dispositivo requiere el servicio de garantía para volver a funcionar.

1. En tu Surface Hub, abre **Configuración**.

   ![Imagen que muestra la aplicación Configuración para Surface Hub.](images/sh-settings.png)

2. Seleccione **Actualizar & seguridad.**

   ![Imagen que muestra el grupo Actualizar & seguridad en la aplicación Configuración para Surface Hub.](images/sh-settings-update-security.png)

3. Seleccione **Recuperación**y, a continuación, en **Restablecer dispositivo,** **seleccione Introducción.**

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, ya que se te pedirá más adelante. Para obtener más información, consulta [Guardar la clave de BitLocker.](save-bitlocker-key-surface-hub.md) Cuando el hub se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento.
   
   ![Imagen que muestra la opción Restablecer dispositivo en la aplicación Configuración para Surface Hub.](images/sh-settings-reset-device.png)

   Una vez que finalice el proceso de restablecimiento, Surface Hub vuelve a [iniciar el programa de primera](first-run-program-surface-hub.md) ejecución. Si el proceso de restablecimiento encuentra un problema, revierte el Surface Hub a la imagen del sistema operativo existente anteriormente y, a continuación, muestra la pantalla de bienvenida.

<span id="cloud-recovery" />

## Recuperar un Surface Hub desde la nube

Si por algún motivo el Surface Hub se vuelve inutilizable, aún puedes recuperarlo de la nube sin la ayuda del soporte técnico de Microsoft. Surface Hub puede descargar una imagen del sistema operativo nueva de la nube y usar esa imagen para reinstalar su sistema operativo.

Es posible que tenga que usar este tipo de proceso de recuperación en las siguientes circunstancias:

- [Surface Hub o sus cuentas relacionadas han entrado en un estado inestable](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub está bloqueado](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>El **proceso de recuperación desde la** nube requiere una conexión cableada que proporciona conectividad abierta a Internet (sin proxy u otros mensajes de autenticación).

### Recuperar un Surface Hub de un estado defectuoso

Si la cuenta del dispositivo entra en un estado inestable o si la cuenta de administrador encuentra problemas, puedes usar la aplicación Configuración para iniciar el proceso de recuperación en la nube. Solo debes usar el proceso de recuperación en la nube cuando el proceso [de restablecimiento](#reset-a-surface-hub) del dispositivo no solucione el problema.

1. En Surface Hub, selecciona Actualización **de** &gt; **configuración &** &gt; **recuperación de seguridad.**

2. En **Recuperar desde la nube,** seleccione Reiniciar **ahora.**

   ![recuperar desde la nube](images/recover-from-the-cloud.png)

### Recuperar un Surface Hub bloqueado

En raras ocasiones, un Surface Hub puede producir un error al limpiar los datos de usuario y de la aplicación al final de una sesión. Cuando esto sucede, el dispositivo se reinicia automáticamente e intenta de nuevo la operación. Pero si esta operación falla repetidamente, el dispositivo se bloquea automáticamente para proteger los datos de usuario. Para desbloquearlo, debes [restablecer el dispositivo](#reset-a-surface-hub) o, si no funciona, recuperarlo de la nube.

1. Busca el interruptor de energía en la parte inferior de Surface Hub. El conmutador de alimentación está junto a la conexión de cable de alimentación. Para obtener más información sobre el conmutador de alimentación, consulta la Guía de preparación del sitio [de Surface Hub (PDF).](surface-hub-site-readiness-guide.md)

2. Mientras surface hub muestra la pantalla de bienvenida, usa el interruptor de alimentación para desactivar Surface Hub.

3. Usa el conmutador de energía para volver a activar Surface Hub. El dispositivo se inicia y muestra la pantalla del logotipo de Surface Hub. Cuando veas puntos giratorios debajo del logotipo de Surface Hub, usa el interruptor de energía para volver a apagar Surface Hub.  

4. Repite el paso 3 tres veces o hasta que Surface Hub muestre el mensaje "Preparar reparación automática". Después de mostrar este mensaje, el Surface Hub muestra la pantalla Windows RE.

5. Seleccione **Opciones avanzadas.**

6. Seleccione **Recuperar desde la nube.** (Opcionalmente, puede seleccionar **Restablecer**. Sin embargo, **la recuperación desde la nube** es el enfoque recomendado).

   ![Recuperar desde la nube](images/recover-from-cloud.png)
7. Si se te pide que escribas la clave de BitLocker, sigue uno de estos procedimientos:

   - Para conservar la información que Bitlocker protege en Surface Hub, escribe la clave de Bitlocker.
   - Para descartar la información protegida, seleccione **Omitir esta unidad**  

8. Cuando se le solicite, seleccione **Reinstalar**.

    ![Reinstalar](images/reinstall.png)

9. Para volver a particionamiento del disco, seleccione **Sí**.

   ![Volver a particionar](images/repartition.png)

   En primer lugar, el proceso de recuperación descarga la imagen del sistema operativo desde la nube.  

   ![descargando 97&](images/recover-progress.png)

   Cuando finaliza la descarga, el proceso de recuperación restaura Surface Hub de acuerdo con las opciones que seleccionaste.
   

## Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede crear [una solicitud de soporte técnico.](https://support.microsoft.com/supportforbusiness/productselection)


## Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

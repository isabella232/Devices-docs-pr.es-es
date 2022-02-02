---
title: Restablecer y recuperar para Surface Hub 2S
description: Obtenga información sobre cómo recuperar y restablecer Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6ba5677fabd3d309875cf339ec1432e99529b23b
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338093"
---
# <a name="reset-and-recovery-for-surface-hub-2s"></a>Restablecer y recuperar para Surface Hub 2S

Si tienes problemas con Surface Hub 2S, puedes restablecer el dispositivo a la configuración de fábrica o restaurarlo con una unidad USB.

Para empezar, inicie sesión en Surface Hub 2S con credenciales de administrador, abra la aplicación Configuración****, seleccione Actualizar & seguridad y, **a** continuación, seleccione **Recuperación**.

## <a name="reset-the-device"></a>Restablecer el dispositivo

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, como se te pedirá más adelante. Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md).

1. Para restablecer el dispositivo, **selecciona Introducción**.

2. Cuando aparezca **la ventana Listo para restablecer** este dispositivo, selecciona **Restablecer**.
  
   > [!TIP]
   > Cuando el concentrador se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento. Una vez que escribes la clave de BitLocker, el concentrador vuelve a instalar el sistema operativo desde la partición de recuperación. Esto puede tardar hasta una hora en completarse.
  
3. Para volver a configurar el dispositivo, ejecute el programa de instalación por primera vez.

4. Si administras el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retira y elimina el registro anterior y, a continuación, vuelve a inscribir el nuevo dispositivo. Para obtener más información, consulta [Quitar dispositivos con borrar, retirar o desenrollar manualmente el dispositivo](/intune/devices-wipe).

   > [!div class="mx-imgBorder"]
   > ![*Restablecer y recuperar para Surface Hub 2S*.](images/sh2-reset.png)
   <br/>*Figura 1. Restablecer y recuperar para Surface Hub 2S*

## <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>Recuperar Surface Hub 2S mediante una unidad de recuperación USB

Como novedad Surface Hub 2S, ahora puedes reinstalar el dispositivo mediante una imagen de recuperación.

### <a name="recovery-from-a-usb-drive"></a>Recuperación desde una unidad USB

Con Surface Hub 2S, puedes reinstalar el dispositivo mediante una imagen de recuperación. Al hacerlo, puedes reinstalar el dispositivo en la configuración de fábrica si has perdido la clave de BitLocker o si ya no tienes credenciales de administrador en la Configuración aplicación.

>[!TIP]
>Usa una unidad USB 3.0 con 8 GB o 16 GB de almacenamiento, con el formato FAT32.

1. Desde un equipo independiente, descarga la .zip de recuperación de archivos desde el sitio web de [Recuperación de Surface](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) y, a continuación, vuelve a estas instrucciones.

2. En el cuadro de búsqueda de la barra de tareas **, escriba unidad** de recuperación y seleccione **Crear una unidad de recuperación** o **Unidad de** recuperación a partir de los resultados. Es posible que deba escribir una contraseña de administrador o confirmar su elección.

3. En el **cuadro Control de cuentas de** usuario, seleccione **Sí**.

4. Asegúrese de borrar la casilla **Copia de seguridad de archivos del sistema en la unidad** de recuperación y, a continuación, seleccione **Siguiente**.

5. Seleccione la unidad USB y, a continuación, seleccione **Siguiente > Crear**.  Algunas utilidades deben copiarse en la unidad de recuperación, por lo que esto puede tardar unos minutos.

6. Cuando la unidad de recuperación esté lista, seleccione **Finalizar**.

7. Haga doble clic en la imagen de .zip archivo que descargó anteriormente para abrirlo.

8. Seleccione todos los archivos de la carpeta de imagen de recuperación, cópielos en la raíz de la unidad USB y, a continuación, seleccione Elegir para **reemplazar los archivos en el destino**.

9. Una vez que los archivos han terminado de copiarse, selecciona el icono **Quitar hardware** y Medios de expulsar de forma segura en la barra de tareas y quita la unidad USB.

10. Conectar la unidad USB a cualquier puerto USB-C o USB-A del Surface Hub 2S. Desactiva el concentrador y, a continuación, arranca desde la unidad USB.

#### <a name="boot-surface-hub-from-usb-drive"></a>Arranque Surface Hub desde una unidad USB

>[!NOTE]
>Si el dispositivo se desenchufó o experimentó un corte brusco de energía o un cable de alimentación, espere al menos 15 segundos antes de intentar arrancar desde USB.

1. Al presionar el botón Bajar volumen, presione el botón De encendido.

2. Sigue presionando ambos botones hasta que veas el Windows logotipo.

3. Suelta el botón De encendido pero mantén presionado el botón Bajar volumen hasta que comience la instalación de la interfaz de usuario.

   ![*Use los botones bajar volumen y encendido para iniciar la recuperación*.](images/sh2-keypad.png)
   <br>*Figura 2. Botones de volumen y encendido*

4. En la pantalla de selección de idioma, seleccione el idioma de presentación para su Surface Hub 2S.

5. Seleccione **Recuperar de una unidad** y **Limpiar completamente la** unidad y, a continuación, **seleccione Recuperar**. Si se te pide una clave de BitLocker, selecciona **Omitir esta unidad**. Surface Hub 2S se reinicia varias veces y puede tardar una hora o más en completar el proceso de recuperación.

6. Cuando aparezca la pantalla de configuración por primera vez, quite la unidad USB.

## <a name="contact-support"></a>Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).

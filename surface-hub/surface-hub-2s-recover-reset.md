---
title: Restablecimiento y recuperación de Surface Hub 2S
description: Aprende a recuperar y restablecer Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342980"
---
# Restablecimiento y recuperación de Surface Hub 2S

Si tienes problemas con Surface Hub 2S, puedes restablecer la configuración de fábrica del dispositivo o restaurarlo mediante una unidad USB.

Para empezar, inicia sesión en Surface Hub 2S con credenciales de administrador, abre la aplicación Configuración, selecciona Actualizar & seguridad y, **a**continuación, selecciona **Recuperación.** ****

## Restablecer el dispositivo

   > [!IMPORTANT]
   > Asegúrate de que tienes la clave de BitLocker disponible antes de restablecer el dispositivo, ya que se te pedirá más adelante. Para obtener más información, consulta [Guardar la clave de BitLocker.](save-bitlocker-key-surface-hub.md)

1. Para restablecer el dispositivo, seleccione **Introducción.**

2. Cuando aparezca **la ventana Listo para restablecer este** dispositivo, seleccione **Restablecer**. 
  
   > [!IMPORTANT]
   > Cuando el hub se reinicia en la partición de recuperación, se te pedirá que escribas la clave de BitLocker. Si se omite ese mensaje, se producirá un error en el restablecimiento. Una vez que escribes la clave de BitLocker, el concentrador vuelve a instalar el sistema operativo desde la partición de recuperación. Esto puede tardar hasta una hora en completarse.
  
3. Para volver a configurar el dispositivo, ejecuta el programa de instalación por primera vez.

4. Si administra el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retire y elimine el registro anterior y vuelva a inscribir el nuevo dispositivo. Para obtener más información, consulta Quitar dispositivos mediante el borrado, la retirada o la [eliminación manual de la inscripción del dispositivo.](https://docs.microsoft.com/intune/devices-wipe)

   > [!div class="mx-imgBorder"]
   > ![*Restablecer y recuperar Surface Hub 2S*](images/sh2-reset.png)
   <br/>*Figura 1. Restablecimiento y recuperación de Surface Hub 2S* 

## Recuperar Surface Hub 2S mediante una unidad de recuperación USB

Nuevo en Surface Hub 2S, ahora puedes reinstalar el dispositivo mediante una imagen de recuperación.

### Recuperación desde una unidad USB

Con Surface Hub 2S, puedes reinstalar el dispositivo mediante una imagen de recuperación. Al hacerlo, puedes reinstalar el dispositivo en la configuración de fábrica si has perdido la clave de BitLocker o si ya no tienes credenciales de administrador en la aplicación Configuración.

>[!NOTE]
>Usa una unidad USB 3.0 con 8 GB o 16 GB de almacenamiento, con el formato FAT32.

1. Desde un equipo independiente, descarga la imagen de recuperación del archivo .zip desde el sitio web de [Recuperación](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) de Surface y, a continuación, vuelve a estas instrucciones. 

1. En el cuadro de búsqueda de la barra de tareas, **escriba**la unidad de recuperación y, a continuación, seleccione Crear una unidad de **recuperación** o unidad **de** recuperación a partir de los resultados. Es posible que tenga que escribir una contraseña de administrador o confirmar su elección.

1. En el **cuadro Control de cuentas** de usuario, seleccione **Sí**.

1. Asegúrese de borrar la casilla De copia de seguridad de **los archivos del sistema en** la unidad de recuperación y, a continuación, seleccione **Siguiente**.

1. Selecciona la unidad USB y, a continuación, selecciona **> Crear**.  Algunas utilidades deben copiarse en la unidad de recuperación, por lo que esto puede tardar unos minutos.

1. Cuando la unidad de recuperación esté lista, seleccione **Finalizar**.

1. Haz doble clic en el archivo .zip de imagen de recuperación que descargaste anteriormente para abrirlo.

1. Seleccione todos los archivos de la carpeta de imagen de recuperación, cópielos en la raíz de la unidad USB y, a continuación, seleccione Elegir para reemplazar los **archivos en el destino.**

1. Una vez que los archivos han terminado de copiarse, selecciona el icono Quitar **hardware** y medios de expulsar de forma segura en la barra de tareas y quita la unidad USB.

1. Conecta la unidad USB a cualquier puerto USB-C o USB-A en Surface Hub 2S.

1. Desactiva el hub y, a continuación, toma estos pasos para arrancar desde la unidad USB:

   1. Al presionar el botón Bajar volumen, presione el botón De encendido.
   1. Mantén presionado ambos botones hasta que veas el logotipo de Windows.
   1. Suelta el botón de inicio/apagado, pero mantén presionado el botón Bajar volumen hasta que comience la interfaz de usuario de instalación.

      ![*Usar los botones bajar volumen y encendido para iniciar la recuperación*](images/sh2-keypad.png)
      <br>*Figura 2. Botones de volumen y energía*

1. En la pantalla de selección de idioma, selecciona el idioma para mostrar de Surface Hub 2S.

1. Seleccione **Recuperar desde una unidad,** limpie completamente **la**unidad y, a continuación, **seleccione Recuperar**. Si se te pide una clave de BitLocker, selecciona **Omitir esta unidad.** Surface Hub 2S se reinicia varias veces y tarda aproximadamente 30 minutos en completar el proceso de recuperación.

Cuando aparezca la pantalla de configuración por primera vez, quita la unidad USB.

## Contactar con el soporte técnico

Si tiene preguntas o necesita ayuda, puede crear [una solicitud de soporte técnico.](https://support.microsoft.com/supportforbusiness/productselection)

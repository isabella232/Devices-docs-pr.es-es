---
title: Restablecer y recuperar para Surface Hub 2S
description: Más información sobre cómo recuperar y restablecer Surface Hub 2S.
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
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835314"
---
# Restablecer y recuperar para Surface Hub 2S

Si tiene problemas con Surface Hub 2S, puede restablecer el dispositivo a la configuración de fábrica o restaurar mediante una unidad USB.

Para comenzar, inicie sesión en Surface Hub 2S con credenciales de administrador, abra la aplicación **configuración** , seleccione **Actualizar & seguridad**y, a continuación, seleccione **recuperación**.

## Restablecer el dispositivo

1. Para restablecer el dispositivo **, seleccione introducción**.
2. Cuando aparezca la ventana **listo para restablecer este dispositivo** , seleccione **restablecer**. 
  
  >[!NOTE]
  >Surface Hub 2S reinstala el sistema operativo desde la partición de recuperación. Esto puede demorar hasta una hora en completarse.
  
3. Para volver a configurar el dispositivo, ejecute el programa de instalación por primera vez.
4. Si administra el dispositivo con Microsoft Intune u otra solución de administración de dispositivos móviles, retire y elimine el registro anterior y, a continuación, vuelva a inscribir el nuevo dispositivo. Para obtener más información, vea [quitar dispositivos mediante barrido, retirada o desafiliación manual del dispositivo](https://docs.microsoft.com/intune/devices-wipe).

![* Restablecer y recuperar para Surface Hub 2S *](images/sh2-reset.png)<br>
*Figura 1. Restablecer y recuperar para Surface Hub 2S* 

## Recuperar Surface Hub 2S con una unidad de recuperación USB

Nuevo en Surface Hub 2S, ahora puede reinstalar el dispositivo con una imagen de recuperación.

### Recuperación desde una unidad USB

Con Surface Hub 2S, puede reinstalar el dispositivo con una imagen de recuperación. Al hacerlo, puede volver a instalar el dispositivo en la configuración de fábrica si ha perdido la clave de BitLocker o si ya no tiene credenciales de administrador en la aplicación configuración.

>[!NOTE]
>Use una unidad USB 3,0 con 8 GB o 16 GB de almacenamiento, con formato FAT32.

1. Desde un PC independiente, descarga la imagen de recuperación de archivos. zip del [sitio web de recuperación superficial](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) y, a continuación, vuelve a estas instrucciones. 
1. Descomprima el archivo descargado en la raíz de la unidad USB.  
1. Conecta la unidad USB a cualquier puerto USB-C o USB: un puerto en Surface Hub 2S.
1. Apague el dispositivo:
   1. Mientras mantiene presionado el botón bajar el volumen, presione el botón de encendido.
   1. Mantenga los dos botones hasta que vea el logotipo de Windows.
   1. Libera el botón de encendido, pero sigue manteniendo el volumen hasta que se inicie la interfaz de usuario de instalación.

    ![* Usar los botones de encendido y de apagado de volumen para iniciar la recuperación *](images/sh2-keypad.png) <br>
   **Figura 2. Botones de volumen y de encendido**

1. En la pantalla de selección de idioma, seleccione el idioma de la pantalla para Surface Hub 2S.
1. Seleccione **recuperar desde una unidad** y **Limpie completamente la unidad**y, a continuación, seleccione **recuperar**. Si se le pide una clave de BitLocker, seleccione **omitir esta unidad**. Surface Hub 2S se reinicia varias veces y tarda aproximadamente 30 minutos en completar el proceso de recuperación.

Cuando aparezca la pantalla de configuración del primer momento, quite la unidad USB.

## Ponerse en contacto con soporte técnico

Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).

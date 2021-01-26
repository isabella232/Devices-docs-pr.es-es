---
title: Administrar la configuración de la UEFI de Surface
description: Usar la configuración de UEFI de Surface para habilitar o deshabilitar dispositivos o componentes, configurar las opciones de seguridad y ajustar la configuración de arranque del dispositivo Surface.
keywords: firmware, seguridad, características, configurar, hardware
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 01/25/2021
ms.openlocfilehash: af9eac171dea5d29ce9776766a2c5842bea9eb8c
ms.sourcegitcommit: 1b12ea363785697ddc705b0a0cc7bb35cad6b327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "11300701"
---
# Administrar la configuración de la UEFI de Surface

 Los dispositivos Surface PC están diseñados para usar una interfaz de firmware extensible unificada (UEFI) única diseñada por Microsoft específicamente para estos dispositivos. La configuración de UEFI de Surface proporciona la capacidad de habilitar o deshabilitar dispositivos y componentes integrados, proteger la configuración de UEFI de cambios y ajustar la configuración de arranque del dispositivo Surface. 

## Productos admitidos

La administración de UEFI es compatible con lo siguiente: 

- Surface Pro 4, Surface Pro (5ª generación), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1.ª generación), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go
- Surface Studio (1ª generación), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## Compatibilidad con la administración basada en la nube

Con los perfiles de La interfaz de configuración de firmware de dispositivo (DFCI) integrados en Microsoft Intune (ahora disponible en la versión preliminar pública), la administración de LA UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware de UEFI. DFCI admite el aprovisionamiento sin intervención táctil, elimina las contraseñas de BIOS, proporciona control de la configuración de seguridad, incluidas las opciones de arranque y periféricos integrados, y establece las bases para escenarios de seguridad avanzados en el futuro. DFCI está disponible actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 y Surface Pro X.  Para obtener más información, consulta la administración [de Intune de la configuración de LA UEFI de Surface.](surface-manage-dfci-guide.md)

## Menú Abrir UEFI de Surface

Para ajustar la configuración de UEFI durante el inicio del sistema:

1. Apaga Surface y espera unos 10 segundos para asegurarte de que está apagada.
2. Mantén presionado el **botón Subir** volumen y, al mismo tiempo, presiona y suelta el botón **De encendido.**
3. A medida que aparezca el logotipo de Microsoft **** o Surface en la pantalla, mantén presionado el botón Subir volumen hasta que aparezca la pantalla UEFI.

## Página de información de UEFI PC

La página de información del equipo incluye información detallada sobre el dispositivo Surface: 

- **Modelo:** el modelo del dispositivo Surface se mostrará aquí, como Surface Book 2 o Surface Pro 7. No se muestra la configuración exacta de tu dispositivo (por ejemplo, el procesador, el tamaño del disco o el tamaño de la memoria). 
- **UUID**: este número de identificación único universal es específico de tu dispositivo y se usa para identificar el dispositivo durante la implementación o la administración. 

- **Número de serie**: este número se usa para identificar este dispositivo de Surface específico para etiquetas de inventario y en escenarios de soporte técnico.
- **Etiqueta de inventario**: la etiqueta de inventario se asigna al dispositivo de Surface con la [Herramienta de etiqueta de inventario](https://docs.microsoft.com/surface/assettag). 

También encontrarás información detallada sobre el firmware del dispositivo Surface. Los dispositivos Surface tienen varios componentes internos y cada uno ejecuta distintas versiones de firmware. La versión de firmware de cada uno de los siguientes dispositivos se muestra en la página **Información del equipo** (como se muestra en la figura 1): 

- UEFI del sistema 

- Controladora SAM 

- Motor de administración de Intel 

- Controlador integrado del sistema 

- Firmware de entrada táctil 

![Información del sistema e información de la versión de firmware](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*Figura 1. Información del sistema e información de la versión de firmware*

Puedes encontrar información actualizada sobre la versión de firmware más reciente para el dispositivo Surface en el [Historial de actualizaciones Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para el dispositivo. 

## Página Seguridad de UEFI 

![Configuración de las opciones de seguridad de la UEFI de Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Figura 2. Configuración de las opciones de seguridad de la UEFI de Surface*

La página Seguridad te permite establecer una contraseña para proteger la configuración de UEFI. Esta contraseña se debe especificar cuando se arranque el dispositivo Surface en la UEFI. La contraseña puede contener los siguientes caracteres (como se muestra en la figura 3): 

- Letras mayúsculas: A-Z 

- Letras minúsculas: a-z 

- Números: 1-0 

- Caracteres especiales: !@#$%^&*()?<>{} []-_=+|.,;:''" 

La contraseña debe tener al menos 6 caracteres y distingue mayúsculas de minúsculas. 

![Agregar una contraseña para proteger la configuración de la UEFI de Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Agregar una contraseña para proteger la configuración de la UEFI de Surface*

En la página Seguridad también puedes cambiar la configuración de arranque seguro en el dispositivo Surface. La tecnología de arranque seguro impide que el código de arranque no autorizado arranque en el dispositivo Surface, lo que protege contra infecciones de malware de tipo bootkit y rootkit. Puedes deshabilitar el arranque seguro para permitir el dispositivo Surface en sistemas operativos de terceros de arranque o medios de arranque. También puedes configurar el arranque seguro para que funcione con certificados de terceros, como se muestra en la figura 4. Lee más sobre el [Arranque seguro](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) en la biblioteca de TechNet.

![Configurar el arranque seguro](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar el arranque seguro*

Según el dispositivo, es posible que también puedas ver si el TPM está habilitado o deshabilitado. Si no ves la opción Habilitar **TPM,**  abre tpm.msc en Windows para comprobar el estado, como se muestra en la figura 5. El TPM se usa para autenticar el cifrado de datos de tu dispositivo con BitLocker. Para obtener más información, consulta Información [general de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) 

![Consola de TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Consola de TPM*


## Menú UEFI: Dispositivos 

La página Dispositivos te permite habilitar o deshabilitar dispositivos y componentes específicos, como:

- Acoplamiento y puertos USB 

- Ranura para tarjeta microSD o SD 

- Cámara trasera 

- Cámara frontal 

- Cámara de infrarrojos (IR) 

- Wi-Fi y Bluetooth 

- Audio integrado (altavoces y micrófono) 

Cada dispositivo aparece con un botón deslizante **** que puedes mover a la posición Activado (habilitado) o Desactivado **(deshabilitado),** como se muestra en la figura 6. 

![Habilitar y deshabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Figura 6. Habilitar y deshabilitar dispositivos específicos*

## Menú UEFI: configuración de arranque 

La página Configuración de arranque te permite cambiar el orden de los dispositivos de arranque, así como habilitar o deshabilitar el arranque de los siguientes dispositivos: 

- Administración de arranque de Windows 

- Almacenamiento USB 

- Red PXE 

- Almacenamiento interno 

Puedes arrancar desde un dispositivo específico inmediatamente o puedes deslizar rápidamente hacia la izquierda en la entrada del dispositivo en la lista con la pantalla táctil. También puedes arrancar inmediatamente en un dispositivo USB o un adaptador Ethernet USB cuando el dispositivo Surface esté apagado, presionando el botón **Bajar el volumen** y el botón **Inicio/apagado** simultáneamente. 

Para que el orden de arranque especificado **** entre en vigor, debes establecer la opción Habilitar secuencia de arranque alternativa en **Activar,** como se muestra en la figura 7. 

![Configurar el orden de arranque para el dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Figura 7. Configurar el orden de arranque para el dispositivo Surface* 

También puedes activar y desactivar la compatibilidad con IPv6 PXE con la opción **Habilitar IPv6 para el arranque de Red PXE**, por ejemplo, al realizar una implementación de Windows con PXE en el que el servidor PXE está configurado solo para IPv4.  

## Menú UEFI: Administración
La página Administración te permite administrar el uso de la administración de UEFI sin entrada táctil y otras características en dispositivos elegibles, como Surface Pro 7, Surface Pro X y Surface Laptop 3.  

![Administrar el acceso a zero Touch UEFI Management y otras características ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *de la figura 8. Administrar el acceso a zero Touch UEFI Management y otras características* 


Zero Touch UEFI Management te permite administrar de forma remota la configuración de UEFI mediante un perfil de dispositivo en Intune denominado Device Firmware Configuration Interface (DFCI). Si no configuras esta opción, la capacidad de administrar dispositivos elegibles con DFCI se establece en **Listo.** Para evitar DFCI, seleccione **Optar por no participar.** 

> [!NOTE]
> La página de configuración de administración de UEFI y el uso de DFCI están disponibles actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 y Surface Pro X. Para obtener más información, consulta [Administración de Intune de la configuración de LA UEFI de Surface.](surface-manage-dfci-guide.md)

## Menú UEFI: Salir 

Use el **botón Reiniciar ahora** de la página **Salir** para salir de la configuración de UEFI, como se muestra en la figura 9. 

![Salir de la UEFI de Surface y reiniciar el dispositivo](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*Figura 9. Haz clic en Reiniciar ahora para salir de la UEFI de Surface y reiniciar el dispositivo*

## Pantallas de arranque de la UEFI de Surface

Cuando actualizas el firmware del dispositivo Surface, ya sea mediante Windows Update o la instalación manual, las actualizaciones no se aplican de inmediato en el dispositivo, sino durante el próximo ciclo de reinicio. Puedes encontrar más información sobre el proceso de actualización de firmware de Surface en [Administrar las actualizaciones de controladores y firmware de Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates). El progreso de la actualización del firmware se muestra en una pantalla con barras de progreso de colores diferentes para indicar el firmware para cada componente. La barra de progreso de cada componente se muestra en las figuras 9 a 18.

![Actualización del firmware de la UEFI de Surface con barra de progreso azul](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figura 10. La actualización del firmware de la UEFI de Surface muestra una barra de progreso azul*

![Firmware de controlador integrado del sistema con la barra de progreso verde](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figura 11. La actualización del firmware de controlador integrado del sistema muestra una barra de progreso verde*

![Actualización del firmware de controladora SAM con barra de progreso naranja](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figura 12. La actualización de firmware de la controladora SAM muestra una barra de progreso naranja*

![Firmware del motor de administración de Intel con barra de progreso roja](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figura 13. La actualización del firmware del motor de administración de Intel muestra una barra de progreso roja*

![Firmware de entrada táctil de Surface con barra de progreso gris](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figura 14. La actualización del firmware de entrada táctil de Surface muestra una barra de progreso gris*

![Firmware surface DESP con barra de progreso verde claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. La actualización de firmware de SURFACE KIP muestra una barra de progreso verde claro*

![Firmware ish de Surface con barra de progreso rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figura 16 La actualización de firmware ish de Surface muestra una barra de progreso rosa claro*

![Firmware de Surface Trackpad con barra de progreso gris](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. La actualización de firmware de Surface Trackpad muestra una barra de progreso rosa*

![Firmware de Surface TCON con barra de progreso gris claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. La actualización de firmware de Surface TCON muestra una barra de progreso gris claro*


![Firmware de TPM de Surface con barra de progreso púrpura claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. La actualización de firmware del TPM de Surface muestra una barra de progreso púrpura*


>[!NOTE]
>Se muestra un mensaje de advertencia adicional que indica que el arranque seguro está deshabilitado, como se muestra en la figura 19.

![Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado en la configuración de la UEFI de Surface*

## Referencias

1. Surface Go y Surface Go 2 usan una UEFI de terceros y no admiten DFCI. 

## Temas relacionados

- [Administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md)

-  [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)

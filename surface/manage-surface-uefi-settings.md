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
ms.date: 10/12/2020
ms.openlocfilehash: 218f98b23adcb7bae2af92655d85144c6e5665e6
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114728"
---
# Administrar la configuración de la UEFI de Surface

Todas las generaciones actuales y futuras de dispositivos de superficie usan una interfaz de firmware extensible (UEFI) única diseñada por Microsoft específicamente para estos dispositivos. La configuración de Surface UEFI ofrece la capacidad de habilitar o deshabilitar dispositivos y componentes integrados, proteger la configuración de UEFI y ajustar la configuración de inicio del dispositivo Surface. 

## Productos admitidos

La administración de UEFI es compatible con los siguientes elementos: 

- Surface Pro 4, Surface Pro (5º gen), Surface Pro 6, Surface Pro 7, Surface Pro X
- Portátil Surface (1. ª gen), portátil Surface 2, portátil Surface 3, Surface portátil Go
- Surface Studio (primer gen), Surface Studio 2
- Libro de superficie, libro de superficie 2, Surface Book 3
- Surface Go, Surface Go 2

## Compatibilidad con la administración basada en la nube

Con los perfiles de la interfaz de configuración de firmware (DFCI) integrado en Microsoft Intune (ahora disponible en la versión preliminar pública), la administración de Surface UEFI amplía la pila de administración moderna al nivel de hardware de UEFI. DFCI es compatible con el aprovisionamiento sin contacto, elimina las contraseñas del BIOS, proporciona el control de la configuración de seguridad, incluidas las opciones de arranque y los periféricos integrados, y establece las bases para escenarios de seguridad avanzada en el futuro. DFCI está disponible actualmente para Surface Pro 7, Surface Pro X y Surface Laptop 3. Para obtener más información, consulte la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md).

## Menú abrir superficie UEFI

Para ajustar la configuración de UEFI durante el inicio del sistema:

1. Apaga tu superficie y espera unos 10 segundos para asegurarse de que está desactivada.
2. Mantén pulsado el botón de **subir el volumen** y, al mismo tiempo, pulsa y suelta el **botón de encendido.**
3. Como el logotipo de Microsoft o de Surface aparece en la pantalla, siga manteniendo el botón **subir de volumen** hasta que aparezca la pantalla UEFI.

## Página de información de UEFI PC

La página información del PC incluye información detallada sobre el dispositivo Surface: 

- **Modelo** : el modelo del dispositivo Surface se mostrará aquí, como Surface Book 2 o Surface Pro 7. No se muestra la configuración exacta de tu dispositivo (por ejemplo, el procesador, el tamaño del disco o el tamaño de la memoria). 
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

## Página de seguridad UEFI 

![Configuración de las opciones de seguridad de la UEFI de Surface](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*Figura 2. Configuración de las opciones de seguridad de la UEFI de Surface*

La página seguridad le permite establecer una contraseña para proteger la configuración de UEFI. Esta contraseña se debe especificar cuando se arranque el dispositivo Surface en la UEFI. La contraseña puede contener los siguientes caracteres (como se muestra en la ilustración 3): 

- Letras mayúsculas: A-Z 

- Letras minúsculas: a-z 

- Números: 1-0 

- Caracteres especiales:! @ # $% ^& * ()? <>{} []-_ = + |.,;: ' ' " 

La contraseña debe tener al menos 6 caracteres y distingue mayúsculas de minúsculas. 

![Agregar una contraseña para proteger la configuración de la UEFI de Surface](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Agregar una contraseña para proteger la configuración de la UEFI de Surface*

En la página Seguridad también puedes cambiar la configuración de arranque seguro en el dispositivo Surface. La tecnología de arranque seguro impide que el código de arranque no autorizado arranque en el dispositivo Surface, lo que protege contra infecciones de malware de tipo bootkit y rootkit. Puedes deshabilitar el arranque seguro para permitir el dispositivo Surface en sistemas operativos de terceros de arranque o medios de arranque. También puede configurar el arranque seguro para que funcione con certificados de terceros, como se muestra en la figura 4. Lee más sobre el [Arranque seguro](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) en la biblioteca de TechNet.

![Configurar el arranque seguro](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar el arranque seguro*

Según el dispositivo que tenga, es posible que también pueda ver si TPM está habilitado o deshabilitado. Si no ve la opción **Habilitar TPM**  , abra TPM. msc en Windows para comprobar el estado, como se muestra en la figura 5. El TPM se usa para autenticar el cifrado de datos de tu dispositivo con BitLocker. Para obtener más información, consulte [información general de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview). 

![Consola de TPM](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Consola de TPM*


## Menú UEFI: dispositivos 

La página dispositivos le permite habilitar o deshabilitar dispositivos y componentes específicos, entre los que se incluyen:

- Acoplamiento y puertos USB 

- Ranura para tarjeta microSD o SD 

- Cámara trasera 

- Cámara frontal 

- Cámara de infrarrojos (IR) 

- Wi-Fi y Bluetooth 

- Audio integrado (altavoces y micrófono) 

Cada dispositivo aparece con un **botón de control** deslizante al que puede desplazarse a la posición (habilitada) o **desactivada** (deshabilitada), tal como se muestra en la figura 6. 

![Habilitar y deshabilitar dispositivos específicos](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*Figura 6. Habilitar y deshabilitar dispositivos específicos*

## Menú UEFI: configuración de arranque 

La página Configuración de arranque le permite cambiar el orden de los dispositivos de inicio, así como habilitar o deshabilitar el inicio de los siguientes dispositivos: 

- Administración de arranque de Windows 

- Almacenamiento USB 

- Red PXE 

- Almacenamiento interno 

Puedes arrancar desde un dispositivo específico inmediatamente o puedes deslizar rápidamente hacia la izquierda en la entrada del dispositivo en la lista con la pantalla táctil. También puedes arrancar inmediatamente en un dispositivo USB o un adaptador Ethernet USB cuando el dispositivo Surface esté apagado, presionando el botón **Bajar el volumen** y el botón **Inicio/apagado** simultáneamente. 

Para que el orden de arranque especificado surta efecto, debe establecer la opción **Habilitar la secuencia de inicio alternativa** en **activado**, como se muestra en la ilustración 7. 

![Configurar el orden de arranque para el dispositivo Surface](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*Figura 7. Configurar el orden de arranque para el dispositivo Surface* 

También puedes activar y desactivar la compatibilidad con IPv6 PXE con la opción **Habilitar IPv6 para el arranque de Red PXE**, por ejemplo, al realizar una implementación de Windows con PXE en el que el servidor PXE está configurado solo para IPv4.  

## Menú UEFI: administración
La página de administración le permite administrar el uso de la administración de UEFI con Zero Touch y otras características en los dispositivos aptos, entre los que se incluyen Surface Pro 7, Surface Pro X y Surface Laptop 3.  

![Administra el acceso a la administración de UEFI sin interacción y otras características, ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *ilustración 8. Administrar el acceso a la administración de UEFI sin interacción y otras características* 


La administración UEFI sin interacción permite administrar de forma remota la configuración de UEFI mediante un perfil de dispositivo en Intune denominado interfaz de configuración de firmware del dispositivo (DFCI). Si no establece esta configuración, la capacidad de administrar los dispositivos aptos con DFCI se establece en **listo**. Para evitar DFCI, seleccione **cancelación de la suscripción**. 

> [!NOTE]
> La página de configuración de administración UEFI y el uso de DFCI solo están disponibles en Surface Pro 7, Surface Pro X y Surface Laptop 3.  

Para obtener más información, consulte la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md).

## Menú UEFI: salir 

Use el botón **reiniciar ahora** de la página de **salida** para salir de la configuración de UEFI, como se muestra en la figura 9. 

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

![Firmware de KIP de superficie con barra de progreso de color claro](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. La actualización del firmware del KIP de superficie muestra una barra de progreso de color verde claro*

![Surface ISH firmware con barra de progreso de color rosa](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Ilustración 16 la actualización del firmware Surface ISH muestra una barra de progreso de color rosa claro*

![Firmware de superficie del panel del panel con barra de progreso gris](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. La actualización del firmware de Surface del panel muestra una barra de progreso de color rosa*

![Surface TCON firmware con barra de progreso de color gris claro](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. La actualización de firmware Surface TCON muestra una barra de progreso de color gris claro*


![Surface firmware TPM con barra de progreso de color claro](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. La actualización de firmware de la superficie de TPM muestra una barra de progreso de color púrpura*


>[!NOTE]
>Aparece un mensaje de ADVERTENCIA adicional que indica que se ha deshabilitado el arranque seguro, como se muestra en la figura 19.

![Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado en la configuración de la UEFI de Surface*

## Temas relacionados

- [Administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md)

-  [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)

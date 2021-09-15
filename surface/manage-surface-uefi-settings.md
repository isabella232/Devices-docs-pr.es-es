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
ms.date: 04/13/2021
ms.openlocfilehash: e21febfcbcbf139aea832c51e354759c0a49f896
ms.sourcegitcommit: a5651e8c8f953fe3130dd476f4e06c16c172aaa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2021
ms.locfileid: "11939541"
---
# <a name="manage-surface-uefi-settings"></a>Administrar la configuración de la UEFI de Surface

 Los dispositivos Surface PC están diseñados para usar una interfaz de firmware extensible unificada (UEFI) única diseñada por Microsoft específicamente para estos dispositivos. La configuración de UEFI de Surface proporciona la capacidad de habilitar o deshabilitar los componentes y dispositivos integrados, proteger la configuración de UEFI para que no se cambie y ajustar la configuración de arranque del dispositivo Surface.

## <a name="supported-products"></a>Productos compatibles

La administración de UEFI se admite en lo siguiente:

- Surface Pro 4, Surface Pro (5ª generación), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X
- Surface Laptop (1ª generación), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4
- Surface Studio (1ª generación), Surface Studio 2
- Surface Book, Surface Book 2, Surface Book 3
- Surface Go, Surface Go 2[ <sup> 1 </sup> ](#references)

## <a name="support-for-cloud-based-management"></a>Compatibilidad con la administración basada en la nube

Con los perfiles de la Interfaz de configuración de firmware de dispositivo (DFCI) integrados en Microsoft Intune (ahora disponibles en la versión preliminar pública), la administración de UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware uefi. DFCI admite el aprovisionamiento sin intervención, elimina las contraseñas del BIOS, proporciona control de la configuración de seguridad, incluidas las opciones de arranque y los periféricos integrados, y establece las bases para escenarios de seguridad avanzados en el futuro. DFCI está disponible actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7 y Surface Pro X.  Para obtener más información, consulte [Administración de Intune de la configuración de UEFI de Surface.](surface-manage-dfci-guide.md)

## <a name="open-surface-uefi-menu"></a>Menú Abrir UEFI de Surface

Para ajustar la configuración de UEFI durante el inicio del sistema:

1. Apaga Surface y espera unos 10 segundos para asegurarte de que está desactivado.
2. Mantenga presionado el botón **Subir** volumen y, al mismo tiempo, presione y suelte el **botón De encendido.**
3. Cuando aparezca el logotipo de Microsoft o Surface **** en la pantalla, mantén presionado el botón Subir volumen hasta que aparezca la pantalla UEFI.

## <a name="uefi-pc-information-page"></a>Página de información de PC UEFI

La página de información del equipo incluye información detallada sobre el dispositivo Surface:

- **Modelo:** el modelo del dispositivo Surface se mostrará aquí, como Surface Book 2 o Surface Pro 7. No se muestra la configuración exacta de tu dispositivo (por ejemplo, el procesador, el tamaño del disco o el tamaño de la memoria).
- **UUID**: este número de identificación único universal es específico de tu dispositivo y se usa para identificar el dispositivo durante la implementación o la administración.

- **Número de serie**: este número se usa para identificar este dispositivo de Surface específico para etiquetas de inventario y en escenarios de soporte técnico.
- **Etiqueta de inventario**: la etiqueta de inventario se asigna al dispositivo de Surface con la [Herramienta de etiqueta de inventario](assettag.md).

También encontrarás información detallada sobre el firmware del dispositivo Surface. Los dispositivos Surface tienen varios componentes internos y cada uno ejecuta distintas versiones de firmware. La versión de firmware de cada uno de los siguientes dispositivos se muestra en la página **Información del equipo** (como se muestra en la figura 1):

- UEFI del sistema

- Controladora SAM

- Motor de administración de Intel

- Controlador integrado del sistema

- Firmware de entrada táctil

:::image type="content" alt-text="Información del sistema e información de versión de firmware." source="images/manage-surface-uefi-figure-1.png":::

*Figura 1. Información del sistema e información de la versión de firmware*

Puedes encontrar información actualizada sobre la versión de firmware más reciente para el dispositivo Surface en el [Historial de actualizaciones Surface](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) para el dispositivo.

## <a name="uefi-security-page"></a>Página Seguridad de UEFI

:::image type="content" alt-text="Configurar la configuración de seguridad de UEFI de Surface." source="images/manage-surface-uefi-fig4.png":::

*Figura 2. Configuración de las opciones de seguridad de la UEFI de Surface*

La página Seguridad permite establecer una contraseña para proteger la configuración de UEFI. Esta contraseña se debe especificar cuando se arranque el dispositivo Surface en la UEFI. La contraseña puede contener los siguientes caracteres (como se muestra en la figura 3):

- Letras mayúsculas: A-Z

- Letras minúsculas: a-z

- Números: 1-0

- Caracteres especiales: !@#$%^&*()?<>{} []-_=+|.,;:''"

La contraseña debe tener al menos 6 caracteres y distingue mayúsculas de minúsculas.

![Agrega una contraseña para proteger la configuración de UEFI de Surface.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figura 3. Agregar una contraseña para proteger la configuración de la UEFI de Surface*

En la página Seguridad también puedes cambiar la configuración de arranque seguro en el dispositivo Surface. La tecnología de arranque seguro impide que el código de arranque no autorizado arranque en el dispositivo Surface, lo que protege contra infecciones de malware de tipo bootkit y rootkit. Puedes deshabilitar el arranque seguro para permitir el dispositivo Surface en sistemas operativos de terceros de arranque o medios de arranque. También puede configurar el arranque seguro para que funcione con certificados de terceros, como se muestra en la figura 4. Para obtener más información, vea [Secure Boot](/windows-hardware/design/device-experiences/oem-secure-boot).

![Configurar arranque seguro.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figura 4. Configurar el arranque seguro*

Según el dispositivo, es posible que también puedas ver si el TPM está habilitado o deshabilitado. Si no ve la configuración Habilitar **TPM,** abra tpm.msc en Windows para comprobar el estado, como se muestra en la figura 5. El TPM se usa para autenticar el cifrado de datos de tu dispositivo con BitLocker. Para obtener más información, consulta [Introducción a BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).

![Consola tpm.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figura 5. Consola tpm*

## <a name="uefi-menu-devices"></a>Menú UEFI: dispositivos

La página Dispositivos le permite habilitar o deshabilitar dispositivos y componentes específicos, incluidos:

- Puerto USB de acoplamiento

- Ranura para tarjeta microSD o SD

- Cámara trasera

- Cámara frontal

- Cámara de infrarrojos (IR)

- Wi-Fi y Bluetooth

- Audio integrado (altavoces y micrófono)

Cada dispositivo aparece con un botón deslizante que puedes mover a **la posición Activado** (habilitado) o **Desactivado** (deshabilitado), como se muestra en la figura 6.

:::image type="content" alt-text="Habilitar y deshabilitar dispositivos específicos." source="images/manage-surface-uefi-fig5a.png":::

*Figura 6. Habilitar y deshabilitar dispositivos específicos*

## <a name="uefi-menu-boot-configuration"></a>Menú UEFI: configuración de arranque

La página Configuración de arranque permite cambiar el orden de los dispositivos de arranque, así como habilitar o deshabilitar el arranque de los siguientes dispositivos:

- Administración de arranque de Windows

- Almacenamiento USB

- Red PXE

- Almacenamiento interno

Puedes arrancar desde un dispositivo específico inmediatamente o puedes deslizar rápidamente hacia la izquierda en la entrada del dispositivo en la lista con la pantalla táctil. También puedes arrancar inmediatamente en un dispositivo USB o un adaptador Ethernet USB cuando el dispositivo Surface esté apagado, presionando el botón **Bajar el volumen** y el botón **Inicio/apagado** simultáneamente.

Para que el orden de arranque especificado **** entre en vigor, debe establecer la opción Habilitar secuencia de arranque alternativa en **On**, tal como se muestra en la figura 7.

:::image type="content" alt-text="Configura el orden de arranque del dispositivo Surface." source="images/manage-surface-uefi-fig6.png":::

*Figura 7. Configurar el orden de arranque para el dispositivo Surface*

También puedes activar y desactivar la compatibilidad con IPv6 PXE con la opción **Habilitar IPv6 para el arranque de Red PXE**, por ejemplo, al realizar una implementación de Windows con PXE en el que el servidor PXE está configurado solo para IPv4.  

## <a name="uefi-menu-management"></a>Menú UEFI: Administración

La página Administración le permite administrar el uso de Zero Touch UEFI Management y otras características en dispositivos elegibles, incluidos Surface Pro 7, Surface Pro X y Surface Laptop 3.  

:::image type="content" alt-text="Administrar el acceso a Zero Touch UEFI Management y otras características." source="images/manage-surface-uefi-fig7a.png":::

*Figura 8. Administrar el acceso a Zero Touch UEFI Management y otras características*

Zero Touch UEFI Management te permite administrar de forma remota la configuración de UEFI mediante un perfil de dispositivo dentro de Intune denominado Device Firmware Configuration Interface (DFCI). Si no configura esta configuración, la capacidad de administrar dispositivos elegibles con DFCI se establece en **Listo**. Para evitar DFCI, seleccione **Optar por no participar.**

> [!NOTE]
> La página de configuración de administración de UEFI y el uso de DFCI están disponibles actualmente para Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7 y Surface Pro X. Para obtener más información, consulta [Administración de Intune de la configuración de UEFI de Surface](surface-manage-dfci-guide.md).

## <a name="uefi-menu-exit"></a>Menú UEFI: Salir

Use el **botón Reiniciar ahora** de la **página** Salir para salir de la configuración de UEFI, como se muestra en la figura 9.

:::image type="content" alt-text="Salga de UEFI de Surface y reinicie el dispositivo." source="images/manage-surface-uefi-fig7.png":::

*Figura 9. Haz clic en Reiniciar ahora para salir de la UEFI de Surface y reiniciar el dispositivo*

## <a name="surface-uefi-boot-screens"></a>Pantallas de arranque de la UEFI de Surface

Cuando actualizas el firmware del dispositivo Surface, ya sea mediante Windows Update o la instalación manual, las actualizaciones no se aplican de inmediato en el dispositivo, sino durante el próximo ciclo de reinicio. Puedes obtener más información sobre el proceso de actualización de firmware de Surface en Administrar e implementar actualizaciones de [controladores y firmware de Surface.](manage-surface-driver-and-firmware-updates.md) El progreso de la actualización del firmware se muestra en una pantalla con barras de progreso de colores diferentes para indicar el firmware para cada componente. La barra de progreso de cada componente se muestra en las figuras 9 a 18.

![Actualización de firmware uefi de Surface con barra de progreso azul.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figura 10. La actualización del firmware de la UEFI de Surface muestra una barra de progreso azul*

![Firmware del controlador incrustado del sistema con barra de progreso verde.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figura 11. La actualización del firmware de controlador integrado del sistema muestra una barra de progreso verde*

![Actualización de firmware del controlador SAM con barra de progreso naranja.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figura 12. La actualización de firmware de la controladora SAM muestra una barra de progreso naranja*

![Firmware del motor de administración intel con barra de progreso roja.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figura 13. La actualización del firmware del motor de administración de Intel muestra una barra de progreso roja*

![Firmware táctil de Surface con barra de progreso gris.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figura 14. La actualización del firmware de entrada táctil de Surface muestra una barra de progreso gris*

![Firmware DE SURFACE KIP con barra de progreso verde claro.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figura 15. La actualización de firmware de Surface KIP muestra una barra de progreso verde claro*

![Firmware ish de Surface con barra de progreso rosa.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figura 16 La actualización de firmware ish de Surface muestra una barra de progreso rosa claro*

![Firmware de Surface Trackpad con barra de progreso gris.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figura 17. La actualización de firmware de Surface Trackpad muestra una barra de progreso rosa*

![Firmware de Surface TCON con barra de progreso gris claro.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figura 18. La actualización de firmware de Surface TCON muestra una barra de progreso gris claro*

![Firmware de TPM de Surface con barra de progreso púrpura claro.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figura 19. La actualización de firmware del TPM de Surface muestra una barra de progreso púrpura*

>[!NOTE]
>Se muestra un mensaje de advertencia adicional que indica que el arranque seguro está deshabilitado, como se muestra en la figura 19.

![Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figura 20. Pantalla de arranque de Surface que indica que el arranque seguro se ha deshabilitado en la configuración de la UEFI de Surface*

## <a name="references"></a>Referencias

1. Surface Go y Surface Go 2 usan una UEFI de terceros y no admiten DFCI.

## <a name="related-topics"></a>Temas relacionados

- [Administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md)

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)

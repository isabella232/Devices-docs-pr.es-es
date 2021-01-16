---
title: Cómo habilitar La activación en la alimentación para Surface
ms.author: v-todmc
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Describe cómo habilitar y deshabilitar La activación en la alimentación para dispositivos Surface.
keywords: update, deploy, implementar, driver, driver, controlador, wake-on-lan, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 01/15/2021
ms.openlocfilehash: 6ad359861f6af29c567bf0fbf26878ec15c7c642
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271564"
---
# Wake on Power para dispositivos Surface

Los dispositivos Surface se pueden apagar mientras estás fuera de tu escritorio o configurarse para hibernar en modo para ahorrar batería. Para mejorar la capacidad de administración de estos dispositivos, La activación en la alimentación permite que los dispositivos Surface compatibles se inicien automáticamente cuando se vuelvan a conectar a la alimentación. Para configurar La activación en la alimentación, puedes usar el Modo de administración de Surface Enterprise (SEMM) a través del Configurador de UEFI de Surface o el Administrador de UEFI.

La característica Activar en energía está disponible en los siguientes dispositivos:

- Surface Pro 7+
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Laptop Go
- Surface Pro X 


## Información general y requisitos previos

El Configurador de UEFI de Surface te permite guardar la configuración de UEFI individual en un paquete .msi de Windows Installer para su distribución en dispositivos de destino. 

> [!NOTE]
> En este artículo se supone que sabe cómo usar SEMM. Para obtener más información, consulta la documentación del Modo [de administración de Surface Enterprise (SEMM).](surface-enterprise-management-mode.md)

## Para habilitar La activación en la alimentación

1.  Descarga la versión más reciente de [Surface UEFI Configurator.](https://www.microsoft.com/download/confirmation.aspx?id=46703)
2.  Inicia sesión en el dispositivo Surface como administrador, abre el **Configurador de UEFI**de Surface, selecciona **Dispositivos Surface**y, a continuación, **selecciona Siguiente.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecciona Dispositivos Surface y selecciona Siguiente.":::
3.  Seleccione **Inicio**y, a continuación, **seleccione Crear en** Paquete de **configuración.**

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione Crear paquete de configuración.":::
4.  Seleccione **Protección de**certificados y agregue el archivo .pfx del certificado. 
5. Escriba su contraseña, seleccione **Siguiente,** agregue **Protección con contraseña,** según corresponda y, a continuación, **seleccione Siguiente**.
6.  En la **página Elegir el tipo de Surface al** que quieres dirigirte, selecciona los dispositivos de destino según corresponda. Por ejemplo, selecciona **Surface Pro 7.**
7.  En la **página Características avanzadas,** seleccione **Activar al**encender , establezca la característica en **Activar**y, a continuación, seleccione **Siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Activar al activar y establecer en Activar."::: 
8.  En la **página Correcto,** seleccione **Finalizar**.

    > [!NOTE]
    > Si es la primera vez que proporcionas la configuración al dispositivo, también se te pedirá que proporciones los dos últimos caracteres de la huella digital del certificado. 
9.  Guarde el paquete .msi. 

## Aplicar el paquete MSI 

Puedes aplicar el paquete MSI a dispositivos de toda la red mediante herramientas de distribución de software como Microsoft Endpoint Configuration Manager. Este procedimiento incluye pasos para instalar el paquete en el equipo local. 

1.  En un símbolo del sistema con privilegios elevados, escriba la ruta de acceso completa del archivo .msi para ejecutar el paquete .msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  En el **cuadro de** diálogo Advertencia, selecciona **Aceptar** o deshabilita BitLocker, según corresponda.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecciona Aceptar o deshabilita BitLocker según corresponda.":::
3.  En la página principal, selecciona **Siguiente** para ejecutar el paquete y aplicar la configuración de UEFI recién configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Una de las páginas de bienvenida, seleccione Siguiente.":::
4.  Reinicia el dispositivo. 

La activación en la alimentación ya está configurada. Para probar la configuración, apaga el dispositivo, desconecta la alimentación y, a continuación, vuelve a conectar la energía. El dispositivo debe iniciarse automáticamente. 

## Referencias

Para obtener más información, vea los artículos siguientes. 

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Activar en LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

¿Aún necesitas ayuda? Vaya a [Microsoft Community.](https://answers.microsoft.com/)
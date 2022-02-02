---
title: Wake on Power para dispositivos Surface
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: Describe cómo habilitar y deshabilitar Wake on Power para dispositivos Surface.
keywords: actualizar, implementar, controlador, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: e8e4ddbd559fc6aea2d04e61208b911ebef3ec22
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338403"
---
# <a name="wake-on-power-for-surface-devices"></a>Wake on Power para dispositivos Surface

Los dispositivos Surface se pueden apagar mientras estás fuera de tu escritorio o configurar el modo de hibernación para ahorrar batería. Para mejorar la capacidad de administración de estos dispositivos, Activar energía permite que los dispositivos Surface compatibles se inicien automáticamente cuando se vuelvan a conectar a la energía. Para configurar Wake on Power, puedes usar surface Enterprise Management Mode (SEMM) a través de Surface UEFI Configurator o el Administrador de UEFI.

La característica Activar energía está disponible en los siguientes dispositivos:

- Surface Pro 8 (solo SKU comerciales)
- Surface Pro 7+ (solo SKU comerciales)
- Surface Pro X (todas las SKU)
- Surface Pro 7 (todas las SKU)
- Surface Go 3 (solo SKU comerciales)
- Surface Laptop Studio (solo SKU comerciales)
- Surface Book 3 (todas las SKU)
- Surface Laptop 4 (solo SKU comerciales)
- Surface Laptop 3 (todas las SKU)
- Surface Laptop Go (todas las SKU)


>[!TIP]
> Las SKU comerciales (también Surface para empresas) ejecutan Windows 10 Pro/Enterprise o Windows 11 Pro/Enterprise; las SKU de consumidor ejecutan Windows 10/Windows 11 Home. Para obtener más información, [consulta Ver la información del sistema](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00). 

## <a name="overview-and-prerequisites"></a>Información general y requisitos previos

Surface UEFI Configurator te permite guardar la configuración de UEFI individual en un Windows Installer .msi paquete para su distribución a dispositivos de destino. 

> [!NOTE]
> En este artículo se supone que sabe cómo usar SEMM. Para obtener más información, [consulta la documentación de Surface Enterprise Management Mode (SEMM](surface-enterprise-management-mode.md)).

## <a name="to-enable-wake-on-power"></a>Para habilitar La activación en la energía

1.  Descarga la versión más reciente de [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Inicia sesión en el dispositivo Surface como administrador, abre **El configurador UEFI de Surface**, selecciona **Dispositivos Surface** y, a continuación, selecciona **Siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Selecciona Dispositivos Surface y selecciona Siguiente.":::
3.  Seleccione **Inicio** y, a continuación, **seleccione Crear en** **Paquete de configuración**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione Crear paquete de configuración.":::
4.  Seleccione **Protección de** certificados y agregue el archivo .pfx del certificado. 
5. Escribe la contraseña, **selecciona Siguiente**, agrega **Protección con contraseña**, según corresponda y, a continuación, selecciona **Siguiente**.
6.  En la **página Elegir el tipo de Surface al que quieres** dirigirte, selecciona los dispositivos de destino según corresponda. Por ejemplo, seleccione **Surface Pro 7**.
7.  En la **página Características avanzadas** , seleccione **Activar al activar**, establecer la característica en **Activar** y, a continuación, **seleccione Siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Activar al activar y establecer en Activar."::: 
8.  En la **página Correcto** , seleccione **Finalizar**.

    > [!NOTE]
    > Si es la primera vez que proporcionas la configuración al dispositivo, se te pedirá que también proporciones los dos últimos caracteres de la huella digital del certificado. 
9.  Guarde el .msi paquete. 

## <a name="apply-the-msi-package"></a>Aplicar el paquete MSI 

Puede aplicar el paquete MSI a dispositivos de toda la red mediante herramientas de distribución de software como Microsoft Endpoint Configuration Manager. Este procedimiento incluye pasos para instalar el paquete en el equipo local. 

1.  En un símbolo del sistema con privilegios elevados, escriba la ruta de acceso completa del archivo .msi para ejecutar el .msi paquete. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  En el **cuadro de diálogo** Advertencia, seleccione **Aceptar** o deshabilitar BitLocker, según corresponda.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Selecciona Aceptar o deshabilita BitLocker según corresponda.":::
3.  En la página de bienvenida, seleccione **Siguiente** para ejecutar el paquete y aplicar la configuración uefi recién configurada.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="Una de la página de bienvenida, seleccione Siguiente.":::
4.  Reinicie el dispositivo 

La activación de la energía ya está configurada. Para probar la configuración, desactiva el dispositivo, desconecta la energía y, a continuación, vuelve a conectar la energía. El dispositivo debe iniciarse automáticamente. 

## <a name="references"></a>Referencias

Para obtener más información, consulte los artículos siguientes. 

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Activar la LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
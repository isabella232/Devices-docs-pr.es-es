---
title: Cómo habilitar la reactivación de energía para Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: Describe cómo habilitar y deshabilitar Wake on Power para dispositivos Surface.
keywords: actualizar, implementar, controlador, WOL, Wake-on-LAN
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903051"
---
# Wake on Power para dispositivos Surface

Los dispositivos Surface pueden apagarse fuera del escritorio o establecerse en el modo de hibernación para ahorrar batería. Para mejorar la capacidad de administración de estos dispositivos, Wake on Power permite que los dispositivos de Surface compatibles se inicien automáticamente cuando vuelvan a conectarse a la energía. Para configurar Wake on Power necesita usar el modo de administración de Surface Enterprise (SEMM), ya sea mediante el configurador Surface UEFI o el administrador UEFI.

Wake on Power es una característica disponible en los siguientes dispositivos:

- Surface Book 3
- Surface Pro 7
- Portátil Surface 3
- Surface Pro X 

## Información general y requisitos previos

Puede usar el configurador de superficie UEFI para configurar las opciones de UEFI individuales que se guardan en un paquete. msi de Windows Installer para su distribución en dispositivos de destino. 

> [!NOTE]
> En este artículo se da por supuesto que ya está familiarizado con el uso de SEMM. Para obtener más información, consulte la documentación del [modo de administración de Surface Enterprise (SEMM)](surface-enterprise-management-mode.md) .

## Para habilitar Wake on Power

1.  Descarga la última versión del [configurador de Surface UEFI](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Inicia sesión en el dispositivo Surface como administrador, abre el **configurador UEFI de Surface**, selecciona **Surface Devices**y, a continuación, haz clic en **siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
3.  Seleccione **Inicio** y, a continuación, en **paquete de configuración** , seleccione **crear**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione crear paquete de configuración.":::
4.  Seleccione **protección de certificado** y agregue el archivo. pfx de certificado. Después de escribir la contraseña, seleccione **siguiente**. Agregar **protección con contraseña**, según corresponda y, a continuación, seleccione **siguiente**.
5.  En la página **elegir el tipo de superficie que desea dirigir** , seleccione los dispositivos de destino según corresponda. Por ejemplo, **Surface Pro 7**.
6.  En la página **características avanzadas** , seleccione **Wake on Power** y establezca en **activado**. Selecciona **Siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Wake on Power y establezca la configuración en activado."::: 
7.  En la página **correcta** , seleccione **fin**. Si es la primera vez que proporciona una configuración a su dispositivo, se le pedirá que proporcione los dos últimos caracteres de la huella digital del certificado. 
8.  Guarde el paquete. msi. 

## Aplicar el paquete MSI 

Puede aplicar el paquete MSI a dispositivos de la red con herramientas de distribución de software como Microsoft Endpoint Configuration Manager. Este procedimiento incluye pasos para instalar el paquete en el equipo local. 

1.  Abra un símbolo del sistema con privilegios elevados y escriba la ruta de acceso completa del archivo. msi para ejecutar el paquete. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  En el cuadro de diálogo de **ADVERTENCIA** , seleccione **Aceptar** o deshabilitar BitLocker según corresponda.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Seleccione Aceptar o deshabilitar BitLocker según corresponda.":::
3.  En la Página principal, seleccione **siguiente** para ejecutar el paquete y aplicar la configuración UEFI recién configurado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="En la Página principal, seleccione siguiente.":::
4.  Reinicie el dispositivo. 

La Wake on Power ya está configurada. Para probar la configuración, apague el dispositivo, desconecte la energía y, a continuación, vuelva a conectar la energía. El dispositivo se iniciará automáticamente. 

## Más información

Para obtener más información, consulte los artículos siguientes. 

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Wake on LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
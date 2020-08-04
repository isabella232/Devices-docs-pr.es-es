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
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903399"
---
# Wake on Power para dispositivos Surface

Los dispositivos de Surface se pueden apagar mientras está lejos de la oficina o en modo de hibernación para ahorrar vida de la batería. Para mejorar la capacidad de administración de estos dispositivos, Wake on Power permite que los dispositivos de Surface compatibles se inicien de forma automática cuando se vuelven a conectar a la alimentación. Para configurar la Wake on Power, puede usar el modo de administración de la empresa de Surface (SEMM), ya sea a través del configurador Surface UEFI o el administrador UEFI.

La característica Wake on Power está disponible en los siguientes dispositivos:

- Surface Book 3
- Surface Pro 7
- Portátil Surface 3
- Surface Pro X 

## Información general y requisitos previos

El configurador de Surface UEFI le permite guardar la configuración de UEFI individual en un paquete. msi de Windows Installer para distribuirlo a los dispositivos de destino. 

> [!NOTE]
> En este artículo se da por supuesto que sabe cómo usar SEMM. Para obtener más información, consulte la documentación del [modo de administración de Surface Enterprise (SEMM)](surface-enterprise-management-mode.md) .

## Para habilitar Wake on Power

1.  Descarga la última versión del [configurador de Surface UEFI](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.  Inicie sesión en el dispositivo Surface como administrador, Abra **Surface configurador UEFI**, seleccione **Surface Devices**y, después, haga clic en **siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Seleccione Surface Devices y haga clic en siguiente.":::
3.  Seleccione **Inicio**y, a continuación, haga clic en **crear** en **paquete de configuración**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Seleccione crear paquete de configuración.":::
4.  Seleccione **protección de certificado**y agregue el archivo. pfx de certificado. 
5. Escriba la contraseña, seleccione **siguiente**, agregar **protección con contraseña**, según corresponda y, a continuación, seleccione **siguiente**.
6.  En la página **elegir el tipo de superficie que desea dirigir** , seleccione los dispositivos de destino según corresponda. Por ejemplo, seleccione **Surface Pro 7**.
7.  En la página **características avanzadas** , seleccione **Wake on Power**, establezca la característica **en activado**y, a continuación, seleccione **siguiente**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Seleccione Wake on Power y establezca la configuración en activado."::: 
8.  En la página **correcta** , seleccione **fin**.

    > [!NOTE]
    > Si esta es la primera vez que proporciona la configuración a su dispositivo, se le pedirá que proporcione también los dos últimos caracteres de la huella digital del certificado. 
9.  Guarde el paquete. msi. 

## Aplicar el paquete MSI 

Puede aplicar el paquete MSI a dispositivos en la red mediante herramientas de distribución de software como Microsoft Endpoint Configuration Manager. Este procedimiento incluye pasos para instalar el paquete en el equipo local. 

1.  En un símbolo del sistema con privilegios elevados, escriba la ruta de acceso completa del archivo. msi para ejecutar el paquete. msi. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  En el cuadro de diálogo de **ADVERTENCIA** , seleccione **Aceptar** o deshabilitar BitLocker, según corresponda.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Seleccione Aceptar o deshabilitar BitLocker según corresponda.":::
3.  En la Página principal, seleccione **siguiente** para ejecutar el paquete y aplicar la configuración UEFI recién configurado.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="En la Página principal, seleccione siguiente.":::
4.  Reinicie el dispositivo. 

La Wake on Power ya está configurada. Para probar la configuración, apague el dispositivo, desconecte la energía y, a continuación, vuelva a conectar la energía. El dispositivo debe iniciarse automáticamente. 

## Referencias

Para obtener más información, consulte los artículos siguientes. 

- [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)
- [Wake on LAN para dispositivos Surface](wake-on-lan-for-surface-devices.md)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
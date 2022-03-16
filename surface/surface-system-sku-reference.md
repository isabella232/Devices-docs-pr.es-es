---
title: Referencia SKU del sistema de Surface
description: Consulta una referencia de nombres de SKU de sistema y modelo de sistema para todos los dispositivos Surface.
keywords: uefi, configure, firmware, secure, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 02/03/2022
ms.reviewer: carlol
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 45fd61ff59273e5ae3fc269058b663f271e641d4
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448693"
---
# <a name="surface-system-sku-reference"></a>Referencia SKU del sistema de Surface

Este documento proporciona una referencia que se puede usar para diversas tareas de TI, como ejecutar comandos o instalar controladores basados en nombres de sku o modelo de dispositivo. Modelo de sistema y SKU del sistema son variables almacenadas en tablas de BIOS de administración del sistema (SMBIOS) en la capa UEFI de dispositivos Surface. Usa el nombre de SKU del sistema siempre que necesites diferenciar entre dispositivos con el mismo nombre del modelo de sistema, como Surface Pro y Surface Pro con LTE Advanced. Las SKU enumeradas en la siguiente tabla hacen referencia a dispositivos comerciales a menos que estén etiquetados como Consumidor. 

| Dispositivo   | Modelo de sistema | SKU del sistema       |
| ---------- | ----------- | -------------- |
| Surface 3 Wi-FI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Norteamérica                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fuera de Norteamérica e Y!mobile en Japón | Surface 3        | Surface_3_ROW                    |
| Surface Book 2 13"                                           | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                           | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                           | SurfaceBook3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                           | SurfaceBook3   | Surface_Book_3_1899
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Consumidor de Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go LTE Commercial                                    | Surface Go       | Surface_Go_1825_Commercial |
| Surface Go 2 Commercial                                      | SurfaceGo2     | Surface_Go_2_1926                |
| Consumidor de Surface Go 2                                        | SurfaceGo2     | Surface_Go_2_1901                |
| Surface Go 2 LTE                                             | SurfaceGo2     | Surface_Go_2_1927                |
| Surface Go 3 Commercial                                      | SurfaceGo3     | Surface_Go_3_1926                |
| Consumidor de Surface Go 3                                        | SurfaceGo3     | Surface_Go_3_1901                |
| Surface Go 3 LTE                                             | SurfaceGo3     | Surface_Go_3_2022                |
| Surface Hub 2S 50"                                           | Surface Hub 2S   | Surface Hub 2S                   |
| Surface Hub 2S 85"                                           | Surface Hub 2S   | Surface Hub 2S 85                |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop Intel de 3 13"                                   | SurfaceLaptop3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop AMD de 3 15"                                     | SurfaceLaptop3 | Surface_Laptop_3_1873      |
| Surface Laptop Intel de 3 15"                                   | SurfaceLaptop3 | Surface_Laptop_3_1872      |
| Surface Laptop AMD de 4 13"                                     | Surface Laptop 4 | Surface_Laptop_4_1958:1959    |
| Surface Laptop Intel de 4 13"                                   | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop AMD de 4 15"                                     | Surface Laptop 4 | Surface_Laptop_4_1952:1953     |
| Surface Laptop Intel de 4 15"                                   | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop Go                                            | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop SE                                            | Surface Laptop SE | Surface Laptop SE            |
| SurfaceLaptopStudio                                        | SurfaceLaptopStudio | Surface_Laptop_Studio_1964 |
| Surface Pro (5ª generación)                                        | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro con LTE Advanced (5ª generación)                      | Surface Pro      | Surface_Pro_1807                 |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 7                                                | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro 7+                                               | Surface Pro 7+   | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+   | Surface_Pro_7+_with_LTE_Advanced_1961|
| SurfacePro8                                                | SurfacePro8    | Surface_Pro_8_for_Business_1983|
| Surface Pro 8 Consumer                                       | SurfacePro8    | Surface_Pro_8_1983|
| Surface Pro 8 LTE                                            | SurfacePro8    | Surface_Pro_8_for_Business_with_LTE_Advanced_1982|
| Surface Pro X con procesador SQ1                             | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X con procesador SQ2                             | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Pro X (Wi-Fi)                                        | Surface Pro X    | Surface_Pro_X_2010        |
| Surface Studio                                               | Surface Studio   | Surface_Studio   |
| Surface Studio 2                                             | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |


## <a name="examples"></a>Ejemplos

**Recuperación de la SKU mediante PowerShell**  
Use el siguiente comando de PowerShell para extraer la información de SKU del sistema:

 ``` powershell  
(Get-CimInstance -Namespace root\wmi -ClassName MS_SystemInformation).SystemSKU
```

**Recuperación de la SKU mediante Información del sistema**  
También puedes encontrar la SKU del sistema y el modelo de sistema para un dispositivo en **Información del sistema**. Para ello, sigua estos pasos:

1. Seleccione **Inicio** y, a continuación, **escriba MSInfo32** en el cuadro de búsqueda.  
1. Seleccione **Información del sistema**.

**Uso de la SKU en una condición WMI de secuencia de tareas**  
Puede usar la información de SKU del sistema en microsoft Deployment Toolkit (MDT) o Microsoft Endpoint Configuration Manager como parte de una condición WMI de secuencia de tareas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## <a name="learn-more"></a>Obtén más información

- [Referencia WMI](/windows/win32/wmisdk/wmi-reference)
- [Soporte del registro de Surface para Windows Autopilot](surface-autopilot-registration-support.md)

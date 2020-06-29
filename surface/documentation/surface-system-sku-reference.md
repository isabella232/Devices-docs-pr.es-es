---
title: Referencia SKU del sistema de Surface
description: En este tema se proporciona una referencia de los nombres de SKU del sistema que puede usar para determinar rápidamente el estado del equipo de un dispositivo específico.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835105"
---
# Referencia de SKU del sistema Surface
Este documento proporciona una referencia de los nombres de SKU del sistema que puede usar para determinar rápidamente el estado del equipo de un dispositivo específico con PowerShell, WMI y otras herramientas relacionadas. 

SKU del sistema es una variable (junto con el modelo del sistema y otras) almacenada en tablas de BIOS de administración del sistema (SMBIOS) en la capa UEFI de dispositivos Surface.  Use el nombre de SKU del sistema siempre que necesite diferenciar entre dispositivos con el mismo nombre de modelo de sistema, como Surface Pro y Surface Pro con LTE avanzado. 

| **Dispositivo**| **Modelo del sistema** | **SKU del sistema**|
| --- | ---| --- |
| Wi-Fi 3                                               | Surface 3        | Surface_3                        |
| Superficie 3 LTE en&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE América del norte                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fuera de Norteamérica y T-Mobile en Japón | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro con LTE avanzada                                | Surface Pro      | Surface_Pro_1807                 |
| Libro de superficie 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Libro de superficie 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Consumidor Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Comercial Surface                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Consumidor Surface Pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Comercial Surface Pro 6                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Consumidor Surface Laptop 2                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Portátil Surface 2                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## Usar las variables de SKU del sistema 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### Información del sistema
También puede encontrar la SKU del sistema y el modelo del sistema para un dispositivo en información del sistema. 
- Haga clic en **iniciar**  >   **MSInfo32**.  

### WMI
Puede usar las variables de SKU del sistema en una condición WMI de secuencia de tareas en Microsoft Deployment Toolkit (MDT) o Microsoft Endpoint Configuration Manager. Por ejemplo: 

    - Espacio de nombres WMI: Root\WMI
    - Consulta WQL: SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"

 
 
 



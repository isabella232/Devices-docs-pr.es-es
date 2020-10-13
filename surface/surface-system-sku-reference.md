---
title: Referencia de SKU del sistema (Surface)
description: Ver una referencia del modelo del sistema y los nombres de SKU del sistema.
keywords: UEFI, configurar, firmware, seguro, SEMM
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ec1d53a4bdbcaaf6606dcb0e52fc81de92a2a53b
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114550"
---
# Referencia de SKU del sistema

Este documento proporciona una referencia del modelo del sistema y los nombres de SKU del sistema que puede usar para determinar rápidamente el estado del equipo de un dispositivo específico mediante PowerShell o WMI.

El modelo del sistema y la SKU del sistema son variables que se almacenan en las tablas del BIOS de administración del sistema (SMBIOS) en la capa UEFI de dispositivos de Surface. Use el nombre de SKU del sistema siempre que necesite diferenciar entre dispositivos con el mismo nombre de modelo de sistema, como Surface Pro y Surface Pro con LTE avanzado.

| Dispositivo   | Modelo del sistema | SKU del sistema       |
| ---------- | ----------- | -------------- |
| Wi-Fi 3                                               | Surface 3        | Surface_3                        |
| Superficie 3 LTE en&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE América del norte                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fuera de Norteamérica e y! teléfono móvil en Japón | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro con LTE avanzada                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13 "                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15 "                                        | Surface Book 3   | Surface_Book_3_1899
| Surface go-Commercial | Sistema Go | Surface_Go_1825_Commercial |
| Consumidor Surface Go                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Comercial Surface                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Consumidor Surface Pro 6                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Comercial Surface Pro 6                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Consumidor Surface Laptop 2                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Portátil Surface 2                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X con procesador SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13 "Intel | Portátil Surface 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15 "Intel | Portátil Surface 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15 "AMD   | Portátil Surface 3 | Surface_Laptop_3_1873      | 
| Portátil Surface Go  | Portátil Surface Go | Surface_Laptop_Go_1943      | 

## Ejemplos 

**Recuperar la SKU con PowerShell**  
Use el siguiente comando de PowerShell para extraer la información de SKU del sistema:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Recuperación de la SKU mediante información del sistema**  
También puede encontrar la SKU del sistema y el modelo del sistema para un dispositivo en **información del sistema**. Para ello, sigue estos pasos:

1. Seleccione **Inicio**y, a continuación, escriba **MSInfo32** en el cuadro de búsqueda.  
1. Seleccione **información del sistema**.

**Usar el SKU en una condición WMI de secuencia de tareas**  
Puede usar la información de SKU del sistema en Microsoft Deployment Toolkit (MDT) o en Microsoft Endpoint Configuration Manager como parte de una condición WMI de secuencia de tareas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

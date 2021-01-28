---
title: Referencia SKU del sistema de Surface
description: Consulta una referencia de los nombres de modelo de sistema y SKU del sistema para todos los dispositivos Surface.
keywords: uefi, configurar, firmware, seguro, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/27/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 0fe13750e7e8c8188b52726c114a6b3668434d39
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304833"
---
# Referencia SKU del sistema de Surface

Este documento proporciona una referencia que se puede usar para diversas tareas de TI, como registrar dispositivos Surface con Windows Autopilot o comprobar el estado de la máquina de un dispositivo específico con PowerShell o WMI.

El modelo del sistema y la SKU del sistema son variables que se almacenan en las tablas de BIOS de administración del sistema (SMBIOS) en la capa UEFI de dispositivos Surface. Usa el nombre de SKU del sistema siempre que necesites diferenciar entre dispositivos con el mismo nombre del modelo de sistema, como Surface Pro y Surface Pro con LTE Advanced.

| Dispositivo   | Modelo de sistema | SKU del sistema       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE Norteamérica                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE fuera de Norteamérica e Y!mobile en Japón | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro con LTE avanzada                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13"                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                        | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                        | Surface Book 3   | Surface_Book_3_1899
| Surface Go LTE Commercial | Ir al sistema | Surface_Go_1825_Commercial |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 2                                                 | Surface Go 2     | Surface_Go_2_1927                |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7+                                               | Surface Pro 7+ | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+ | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X con procesador SQ2                | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Laptop 3 13" Intel | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" Intel | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 3 15" AMD   | Surface Laptop 3 | Surface_Laptop_3_1873      | 
| Surface Laptop Go  | Surface Laptop Go | Surface_Laptop_Go_1943      | 

## Ejemplos 

**Recuperación de la SKU mediante PowerShell**  
Usa el siguiente comando de PowerShell para extraer la información de SKU del sistema:

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**Recuperación de la SKU mediante información del sistema**  
También puedes encontrar la SKU del sistema y el modelo de sistema de un dispositivo en **Información del sistema.** Para ello, sigue estos pasos:

1. Seleccione **Inicio**y, a continuación, **escriba MSInfo32** en el cuadro de búsqueda.  
1. Seleccione **Información del sistema.**

**Usar la SKU en una condición WMI de secuencia de tareas**  
Puedes usar la información de SKU del sistema en Microsoft Deployment Toolkit (MDT) o Microsoft Endpoint Configuration Manager como parte de una condición WMI de secuencia de tareas.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 

## Más información

- [Referencia de WMI](https://docs.microsoft.com/windows/win32/wmisdk/wmi-reference)
- [Soporte del registro de Surface para Windows Autopilot](surface-autopilot-registration-support.md)

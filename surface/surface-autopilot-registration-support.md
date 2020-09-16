---
title: Compatibilidad de Surface registration para Windows AutoPilot
description: En este artículo se describen los requisitos para enviar solicitudes de registro de AutoPilot al soporte técnico de Microsoft.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 9a308edb37cc2cfd99490acad16bd2ae6a4d458a
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016488"
---
# Compatibilidad de Surface registration para Windows AutoPilot

El soporte técnico de Microsoft ahora ofrece un proceso simplificado para registrar dispositivos de superficie para la implementación piloto de Windows. A partir del 2020 de septiembre, los clientes y los proveedores de soluciones en la nube de Microsoft (CSP) pueden registrar dispositivos de Surface enviando solicitudes al soporte técnico de Microsoft. Esta página describe los requisitos para los siguientes escenarios compatibles con el registro de la prueba piloto automático:
 

- **Registro del dispositivo Surface para el piloto automático**. Envía una solicitud para registrar dispositivos de Surface en Windows AutoPilot.
- **Solicitud de hash de hardware del dispositivo Surface.** Envía una solicitud al soporte técnico de Microsoft para proporcionarle los valores de hash de hardware que los clientes o CSP pueden usar para registrar automáticamente los dispositivos a través de Microsoft Intune o el centro de Partners de Microsoft.
- **Anulación del registro de Surface Device Pilot.** Envía una solicitud para eliminar dispositivos de Windows AutoPilot, que normalmente se usa en escenarios de fin de vida del dispositivo.

Consulte la tabla siguiente para obtener detalles de la información que necesitará recopilar antes de enviar solicitudes de registro al soporte técnico de Microsoft.
 
**Tabla 1. Información necesaria para las solicitudes de registro de AutoPilot**
 

| Información necesaria                   | Descripción                                                                                                                                                                                                                                                                                    | Registro de AutoPilot | Solicitud de hash de hardware | AutoPilot<br>Anulación del registro |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **IDENTIFICADOR de inquilino de Azure Active Directory**   | Su identificador de inquilino de Azure Active Directory es un identificador único global (GUID) que es diferente del nombre de su organización o dominio.<br> <br>Para buscar el identificador de inquilino en el portal de Azure [aquí](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Nombre de dominio de Azure Active Directory** | El nombre de dominio de nivel superior; por ejemplo, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Prueba de propiedad**                 | Comprobar la prueba de propiedad cargando la factura o factura original en formato PDF. No se aceptan capturas de pantallas.<br> <br>La factura o factura debe incluir lo siguiente:<br>Números de serie de los dispositivos.<br>Nombre de la empresa.                                                           | Y                      | Y                     | Y                           |
| **Números de serie del dispositivo**              | Cargue el archivo de Excel en formato CSV con cada número de serie del dispositivo en una nueva línea.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Enviar solicitudes de asistencia

  [![Get compatibilidad de registro de AutoPilot para Surface](images/autopilot-reg-support-surface.png)](https://support.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Obtén más información

- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md)
- [Inscribir dispositivos Windows en Intune mediante el uso de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Introducción a WindowsAutopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 


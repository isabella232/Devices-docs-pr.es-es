---
title: Soporte del registro de Surface para Windows Autopilot
description: En este artículo se describen los requisitos para enviar solicitudes de registro de Autopilot al Soporte técnico de Microsoft.
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
ms.openlocfilehash: 4ff3803701ffe71e1c5c0c36200c40e833a7fb25
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271394"
---
# Soporte del registro de Surface para Windows Autopilot

El soporte técnico de Microsoft ya tiene disponible un proceso simplificado de registro de dispositivos Surface para la implementación de Windows Autopilot. A partir de septiembre de 2020, los clientes y los proveedores de soluciones en la nube (SSP) de Microsoft pueden registrar dispositivos Surface enviando solicitudes al Soporte técnico de Microsoft. En esta página se describen los requisitos para los siguientes escenarios de registro de Autopilot admitidos:
 

- **Registro de Surface Device Autopilot**. Envía una solicitud para registrar dispositivos Surface en Windows Autopilot.
- **Solicitud de hash de hardware del dispositivo Surface.** Envía una solicitud al Soporte técnico de Microsoft para proporcionarte hashes de hardware que los clientes o los CSP pueden usar para registrar automáticamente dispositivos a través de Microsoft Intune o el Centro de partners de Microsoft.
- **Desregistration de Surface Device Autopilot.** Envía una solicitud para eliminar dispositivos de Windows Autopilot, que normalmente se usan en escenarios de fin de vida del dispositivo.

Consulte la tabla siguiente para obtener más información sobre la información que necesitará recopilar antes de enviar solicitudes de registro al Soporte técnico de Microsoft.
 
**Tabla 1. Información necesaria para las solicitudes de registro de Autopilot**
 

| Información necesaria                   | Descripción                                                                                                                                                                                                                                                                                    | Registro de Autopilot | Solicitud de hash de hardware | Autopilot<br>Anulación de registro |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Id. de inquilino de Azure Active Directory**   | El identificador de inquilino de Azure Active Directory es un identificador único global (GUID) que es diferente del nombre o dominio de su organización.<br> <br>Para encontrar su id. de inquilino, inicie sesión en Azure Portal [aquí.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) | Y                      | N                     | Y                           |
| **Nombre de dominio de Azure Active Directory** | Su nombre de dominio de nivel superior; por ejemplo, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Prueba de propiedad**                 | Compruebe la prueba de propiedad cargando la factura o la factura original en formato PDF. No se aceptan capturas de pantalla.<br> <br>La factura o la factura debe incluir lo siguiente:<br>Números de serie del dispositivo.<br>Nombre de la compañía.                                                           | Y                      | Y                     | Y                           |
| **Números de serie del dispositivo**              | Cargue el archivo de Excel en formato CSV con cada número de serie de dispositivo en una nueva línea.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Enviar solicitudes de soporte técnico

  [![GEt Autopilot Registration Support for Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## Más información

- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md)
- [Inscribir dispositivos Windows en Intune mediante el uso de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Introducción a WindowsAutopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)

 
 
 


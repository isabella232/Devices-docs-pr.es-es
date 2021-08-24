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
ms.openlocfilehash: 170fdfa9fb85670ec9ed8282f5d264bf2cdbf906
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911985"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>Soporte del registro de Surface para Windows Autopilot

Un proceso simplificado de registro de dispositivos Surface para Windows implementación de Autopilot ya está disponible en el Soporte técnico de Microsoft. A partir de septiembre de 2020, los clientes y los proveedores de soluciones en la nube (SPC) de Microsoft pueden registrar dispositivos Surface enviando solicitudes al Soporte técnico de Microsoft. En esta página se describen los requisitos para los siguientes escenarios de registro de Autopilot admitidos:
 
- **Registro de Surface Device Autopilot**. Envía una solicitud para registrar dispositivos Surface en Windows Autopilot.
- **Solicitud hash de hardware de dispositivo Surface.** Envía una solicitud al Soporte técnico de Microsoft para proporcionarle hashes de hardware que los clientes o LOSP pueden usar para auto registrar dispositivos a través de Microsoft Intune o el Centro de partners de Microsoft.
- **Desregistration de Surface Device Autopilot.** Envía una solicitud para eliminar dispositivos de Windows Autopilot, normalmente usados en escenarios de fin de vida del dispositivo.

Consulta la siguiente tabla para obtener información detallada sobre la información que necesitarás recopilar antes de enviar solicitudes de registro al Soporte técnico de Microsoft. Para obtener los nombres oficiales del modelo de sistema de todos los dispositivos Surface, consulte [Referencia de SKU de Surface System](surface-system-sku-reference.md).
 
**Tabla 1. Información necesaria para solicitudes de registro de Autopilot**
 

| Información necesaria                   | Descripción                                                                                                                                                                                                                                                                                    | Registro de Autopilot | Solicitud de hash de hardware | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory Id. de inquilino**   | El Azure Active Directory de inquilino es un identificador único global (GUID) que es diferente del nombre o dominio de la organización.<br> <br>Para buscar el inicio de sesión del identificador de inquilino en Azure Portal [aquí](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | S                      | N                     | Y                           |
| **Azure Active Directory Nombre de dominio** | Su nombre de dominio de nivel superior; por ejemplo, contoso.com.                                                                                                                                                                                                                                          | S                      | N                     | Y                           |
| **Prueba de propiedad**                 | Compruebe la prueba de propiedad cargando la factura o la factura original en formato PDF. No se aceptan capturas de pantalla.<br> <br>La factura o la factura de venta deben incluir lo siguiente:<br>Números de serie del dispositivo.<br>Nombre de la compañía.                                                           | Y                      | Y                     | Y                           |
| **Números de serie del dispositivo**              | Upload Excel en formato CSV con cada número de serie de dispositivo en una línea nueva.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## <a name="submit-support-requests"></a>Enviar solicitudes de soporte técnico

  [![Get Compatibilidad de registro de Autopilot para Surface.](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>Obtén más información

- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md)
- [Inscribir dispositivos Windows en Intune mediante el uso de Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Introducción a Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Referencia SKU del sistema de Surface](surface-system-sku-reference.md)

 
 
 


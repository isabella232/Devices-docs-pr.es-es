---
title: Administrar Surface Hub 2S con Intune
description: Obtenga información sobre cómo actualizar y administrar Surface Hub 2S con Intune.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/28/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 1d1b836c18a41982497bb28c57f379408c04f8a5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836634"
---
# Administrar Surface Hub 2S con Intune

## Registrar Surface Hub 2S con Intune

Surface Hub 2S permite a los administradores de TI administrar la configuración y las directivas usando un proveedor de administración de dispositivos móviles (MDM). Surface Hub 2S tiene un componente de administración integrado para comunicar con el servidor de administración, por lo que no es necesario instalar clientes adicionales en el dispositivo.

### Registro manual

1. Inicie sesión como administrador local en Surface Hub 2S y abra la aplicación **Configuración**. Seleccione **Surface Hub** > **Administración de dispositivos** y después seleccione **+** para agregar.
2. Después de la autenticación, el dispositivo se registrará automáticamente con Intune.

   ![Registrar Surface Hub 2S con Intune](images/sh2-set-intune1.png)<br>

### Registro automático: afiliado a Azure Active Directory

Durante el proceso de configuración inicial, al afiliar un Surface Hub con un espacio empresarial de Azure AD que tiene habilitada la inscripción automática de Intune, el dispositivo se inscribirá automáticamente con Intune. Para más información, consulte [Métodos de inscripción de Intune para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). La afiliación de Azure AD y la inscripción automática de Intune son necesarias para que Surface Hub sea un "dispositivo compatible" en Intune. 

## Configuración de Windows 10 Team Edition

Seleccione Windows 10 Team para configurar las restricciones de dispositivo preestablecidas para Surface Hub y Surface Hub 2S.

 ![Configurar restricciones de dispositivo para Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Estas configuraciones incluyen la experiencia de usuario y el comportamiento de la aplicación, el registro de Azure Log Analytics, la configuración de las ventanas de mantenimiento, la configuración de la sesión y la configuración de Miracast. Para obtener una lista completa de las configuraciones disponibles de Windows 10 Team, consulte [CSP de SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp).

## Proveedores de servicios de configuración (CSP) compatibles adicionales

Para obtener más CSP compatibles, consulte [CSP de Surface Hub en Windows 10](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

## Configuración de Calidad de servicio (QoS)

Para asegurar la calidad óptima de vídeo y audio en Surface Hub 2S, agregue la siguiente configuración QoS al dispositivo. 

### Configuración de QoS de Microsoft Teams 

|**Nombre**|**Descripción**|**OMA-URI**|**Tipo**|**Valor**|
|:------ |:------------- |:--------- |:------ |:------- |
|**Puertos de audio**| Rango de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Cadena  | 3478-3479 |
|**DSCP de audio**| Marcado de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
|**Puerto de vídeo**| Rango de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Cadena  | 3480 |
|**DSCP de vídeo**| Marcado de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
|**Puertos de audio P2P**| Rango de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Cadena  | 50000-50019 |
|**DSCP de audio P2P**| Marcado de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Integer | 46 |
|**Puertos de vídeo P2P**| Rango de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Cadena  | 50020-50039 |
|**DSCP de vídeo P2P**| Marcado de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Integer | 34 |


### Configuración de QoS de Skype Empresarial

| Nombre               | Descripción         | OMA-URI                                                                  | Tipo    | Valor                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| Puertos de audio        | Rango de puertos de audio    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | Cadena  | 50000-50019                    |
| DSCP de audio         | Marcado de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | Integer | 46                             |
| Fuente multimedia de audio | Nombre de la aplicación de Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | Cadena  | Microsoft.PPISkype.Windows.exe |
| Puertos de vídeo        | Rango de puertos de vídeo    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | Cadena  | 50020-50039                    |
| DSCP de vídeo         | Marcado de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | Integer | 34                             |
| Fuente multimedia de vídeo | Nombre de la aplicación de Skype      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | Cadena  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Ambas tablas muestran los rangos de puertos predeterminados. Los administradores pueden cambiar los intervalos de puertos en Skype Empresarial y en el panel de control de Teams.

## Configuración de modo de Microsoft Teams

Puede establecer el modo de aplicación de Microsoft Teams con Intune. Surface Hub 2S viene instalado con Microsoft Teams en el modo 0, que es compatible tanto con Microsoft Teams como con Skype Empresarial. Puede ajustar los modos tal y como se muestra a continuación.

### Modos:

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: Microsoft Teams con la funcionalidad de Skype Empresarial para reuniones programadas.
- Modo 2: solo Microsoft Teams.

Para establecer modos, agregue la siguiente configuración a un perfil de configuración de dispositivo personalizado.

|**Nombre**|**Descripción**|**OMA-URI**|**Tipo**|**Valor**|
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1 o 2|

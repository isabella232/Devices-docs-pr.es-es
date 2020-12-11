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
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6b5dac9f418207293e3b9b386d59fd26762feb72
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206304"
---
# Administrar Surface Hub 2S con Intune

## Registrar Surface Hub 2S con Intune

Surface Hub 2S permite a los administradores de TI administrar la configuración y las directivas usando un proveedor de administración de dispositivos móviles (MDM). Surface Hub 2S tiene un componente de administración integrado para comunicar con el servidor de administración, por lo que no es necesario instalar clientes adicionales en el dispositivo.

### Registro manual

1. Abre la aplicación **configuración** en Surface Hub 2s e inicia sesión como administrador local. Seleccione **Surface Hub** > **Administración de dispositivos** y después seleccione **+** para agregar.
2. Se le pedirá que inicie sesión con la cuenta que va a usar para Intune. Después de la autenticación, el dispositivo se registrará automáticamente con Intune.

   ![Registrar Surface Hub 2S con Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> La cuenta usada para la autenticación será la cuenta de inscripción de Intune y debe tener una licencia para Intune.

### Registro automático: afiliado a Azure Active Directory

Durante el proceso de configuración inicial, al afiliar un Surface Hub con un espacio empresarial de Azure AD que tiene habilitada la inscripción automática de Intune, el dispositivo se inscribirá automáticamente con Intune. Para más información, consulte [Métodos de inscripción de Intune para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). La afiliación de Azure AD y la inscripción automática de Intune son necesarias para que Surface Hub sea un "dispositivo compatible" en Intune. 

## Administración de la configuración de equipo de Windows 10 con Intune

1. Inicie sesión en **Microsoft Endpoint Manager**y seleccione perfiles de configuración de **dispositivos**  >  ****  >  **crear perfil**. 
2. En **plataforma**, seleccione restricciones de dispositivo con **Windows 10 y versiones posteriores**  >  **(equipo Windows 10)** y, a continuación, seleccione **crear**. 
3. Ahora puedes examinar y seleccionar ajustes preestablecidos de restricción de dispositivo para Surface Hub y Surface Hub 2S.

 ![Configurar restricciones de dispositivo para Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Esta configuración abarca las siguientes categorías: aplicaciones y experiencia, información operativa de Azure, mantenimiento, sesión y proyección inalámbrica.  

## Proveedores de servicios de configuración compatibles (CSP)

Además de las directivas disponibles directamente a través de la consola de Intune, hay numerosos proveedores de servicios de configuración (CSP) que se asignan a claves o archivos del registro. 

Por lo general, Microsoft proporciona nuevos CSP con cada una de las nuevas versiones del sistema operativo Windows 10. La [actualización de Windows 10 Team 2020](surface-hub-2020-update.md) incluye más de 20 directivas nuevas y actualizadas de administración de dispositivos para Surface Hub y Surface Hub 2S. Estas directivas de MDM ofrecen a los administradores de ti el control mejorado de las actualizaciones de la aplicación de Microsoft Store, la configuración de proyección inalámbrica, como Miracast sobre la infraestructura, la configuración de red como la calidad de servicio y la autenticación por cable de 802.1 x, y la nueva configuración relacionada con la privacidad y la RGPD.

Para obtener más información, consulta los siguientes recursos: 

- [Referencia de proveedor de servicios de configuración](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [CSP de directivas admitidas por Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Novedades de la actualización 2020 del equipo de Surface Hub](surface-hub-2020-update-whats-new.md)

## Configuración de Calidad de servicio (QoS)

Para asegurar la calidad óptima de vídeo y audio en Surface Hub 2S, agregue la siguiente configuración QoS al dispositivo. 

### Configuración de QoS de Microsoft Teams 

| Nombre | Descripción | OMA-URI | Tipo | Valor |
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

## Configuración de Microsoft Teams

Puede configurar varias opciones de configuración de Microsoft Teams con Intune.

### Medios

Surface Hub 2S viene instalado con Microsoft Teams en el modo 0, que es compatible tanto con Microsoft Teams como con Skype Empresarial. La función modos, tal como se describe a continuación:

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: Microsoft Teams con la funcionalidad de Skype Empresarial para reuniones programadas.
- Modo 2: solo Microsoft Teams.

Para ajustar el modo, agregue la siguiente configuración a un [Perfil de configuración de dispositivo personalizado](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1 o 2|

### Reuniones coordinadas y Unión de proximidad

Las características de reunión coordinada y de unión de proximidad se pueden [configurar mediante un archivo XML](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) implementado a través de un perfil de Intune.

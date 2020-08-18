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
ms.date: 07/23/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 389db218d06f9f8d3f510e711b03487daf4e06f9
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934870"
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

## Administración de la configuración de equipo de Windows 10 con Intune

1. Inicie sesión en **Microsoft Endpoint Manager**y seleccione perfiles de configuración de **dispositivos**  >  **Configuration profiles**  >  **crear perfil**. 
2. En **plataforma**, seleccione restricciones de dispositivo con **Windows 10 y versiones posteriores**  >  **(equipo Windows 10)** y, a continuación, seleccione **crear**. 
3. Ahora puedes examinar y seleccionar ajustes preestablecidos de restricción de dispositivo para Surface Hub y Surface Hub 2S.

 ![Configurar restricciones de dispositivo para Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Esta configuración abarca las siguientes categorías: aplicaciones y experiencia, información operativa de Azure, mantenimiento, sesión y proyección inalámbrica.  

## Proveedores de servicios de configuración compatibles (CSP)

Además de las directivas disponibles directamente a través de la consola de Intune, hay numerosos proveedores de servicios de configuración (CSP) que se asignan a claves o archivos del registro. 

Por lo general, Microsoft proporciona nuevos CSP con cada una de las nuevas versiones del sistema operativo Windows 10. La [actualización 2020 del equipo de Windows 10](surface-hub-install-2020preview.md), que está disponible en versión preliminar a través del programa Windows Insider, incluye más de 20 directivas de administración de dispositivos nuevas y actualizadas para Surface Hub y Surface Hub 2. Estas directivas de MDM ofrecen a los administradores de ti el control mejorado de las actualizaciones de la aplicación de Microsoft Store, la configuración de proyección inalámbrica, como Miracast sobre la infraestructura, la configuración de red como la calidad de servicio y la autenticación por cable de 802.1 x, y la nueva configuración relacionada con la privacidad y la RGPD.

Para obtener más información, consulta los siguientes recursos: 

- [Referencia de proveedor de servicios de configuración](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [CSP de directivas admitidas por Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

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

## Configuración de modo de Microsoft Teams

Puede establecer el modo de aplicación de Microsoft Teams con Intune. Surface Hub 2S viene instalado con Microsoft Teams en el modo 0, que es compatible tanto con Microsoft Teams como con Skype Empresarial. Puede ajustar los modos tal y como se muestra a continuación.

### Modos:

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: Microsoft Teams con la funcionalidad de Skype Empresarial para reuniones programadas.
- Modo 2: solo Microsoft Teams.

Para establecer modos, agregue la siguiente configuración a un perfil de configuración de dispositivo personalizado.

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1 o 2|

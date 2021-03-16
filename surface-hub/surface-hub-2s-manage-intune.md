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
ms.openlocfilehash: 406fcc58bdb09d7fd47966cd17123d55faec2b65
ms.sourcegitcommit: ea853f2dba67e63e6df33538670fd581e17facab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "11408795"
---
# <a name="manage-surface-hub-2s-with-intune"></a>Administrar Surface Hub 2S con Intune

## <a name="register-surface-hub-2s-with-intune"></a>Registrar Surface Hub 2S con Intune

Surface Hub 2S permite a los administradores de TI administrar la configuración y las directivas usando un proveedor de administración de dispositivos móviles (MDM). Surface Hub 2S tiene un componente de administración integrado para comunicar con el servidor de administración, por lo que no es necesario instalar clientes adicionales en el dispositivo.

### <a name="manual-registration"></a>Registro manual

1. Abre la **aplicación Configuración** en Surface Hub 2S e inicia sesión como administrador local. Seleccione **Surface Hub** > **Administración de dispositivos** y después seleccione **+** para agregar.
2. Se le pedirá que inicie sesión con la cuenta que se va a usar para Intune. Después de la autenticación, el dispositivo se registrará automáticamente con Intune.

   ![Registrar Surface Hub 2S con Intune](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> La cuenta usada para la autenticación será la cuenta de inscripción de Intune y debe tener licencia para Intune.

### <a name="auto-registration--azure-active-directory-affiliated"></a>Registro automático: afiliado a Azure Active Directory

Durante el proceso de configuración inicial, al afiliar un Surface Hub con un espacio empresarial de Azure AD que tiene habilitada la inscripción automática de Intune, el dispositivo se inscribirá automáticamente con Intune. Para más información, consulte [Métodos de inscripción de Intune para dispositivos Windows](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). La afiliación de Azure AD y la inscripción automática de Intune son necesarias para que Surface Hub sea un "dispositivo compatible" en Intune. 

## <a name="managing-windows-10-team-settings-with-intune"></a>Administrar la configuración del equipo de Windows 10 con Intune

1. Inicie sesión en **Microsoft Endpoint Manager**, seleccione ****  >  **Perfiles de configuración de dispositivos**  >  **Crear perfil**. 
2. En **Plataforma,** selecciona **Windows 10 y**versiones posteriores Plantillas Restricciones de dispositivo (Equipo de Windows  >  ****  >  **10)** y, a continuación, selecciona **Crear**. 
3. Ahora puedes examinar y seleccionar la configuración de restricción de dispositivos preestablecida para Surface Hub y Surface Hub 2S.

 ![Configurar restricciones de dispositivo para Surface Hub 2S.](images/sh2-set-intune3.png) <br>

Esta configuración abarca las siguientes categorías: Aplicaciones y experiencia, Información operativa de Azure, Mantenimiento, Sesión y proyección inalámbrica.  

## <a name="supported-configuration-service-providers-csps"></a>Proveedores de servicios de configuración compatibles (SPC)

Además de las directivas disponibles directamente a través de la consola de Intune, hay numerosos proveedores de servicios de configuración (SPC) que se asignan a archivos o claves del Registro. 

Microsoft normalmente proporciona nuevos CSP con cada nueva versión del sistema operativo Windows 10. La [actualización de Windows 10 Team 2020](surface-hub-2020-update.md) incluye más de 20 directivas de administración de dispositivos nuevas y actualizadas para Surface Hub y Surface Hub 2S. Estas directivas MDM dan a los administradores de TI un control mejorado sobre las actualizaciones de aplicaciones de Microsoft Store, la configuración de proyección inalámbrica, como Miracast a través de la infraestructura, la configuración de red, como la calidad del servicio y la autenticación por cable 802.1x, y la nueva configuración relacionada con la privacidad y el RGPD.

Para obtener más información, consulta los siguientes recursos: 

- [Referencia de proveedor de servicios de configuración](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [CSP de directivas admitidas por Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Novedades de la actualización de Surface Hub Team 2020](surface-hub-2020-update-whats-new.md)

## <a name="quality-of-service-qos-settings"></a>Configuración de Calidad de servicio (QoS)

Para asegurar la calidad óptima de vídeo y audio en Surface Hub 2S, agregue la siguiente configuración QoS al dispositivo. 

### <a name="microsoft-teams-qos-settings"></a>Configuración de QoS de Microsoft Teams 

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:------ |:------------- |:--------- |:------ |:------- |
|**Puertos de audio**| Rango de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | Cadena  | 3478-3479 |
|**DSCP de audio**| Marcado de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
|**Puerto de vídeo**| Rango de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | Cadena  | 3480 |
|**DSCP de vídeo**| Marcado de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
|**Puerto compartido**| Intervalo de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | Cadena  | 3481 |
|**Uso compartido de DSCP**| Marcado de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | Integer | 18 |
|**Puertos de audio P2P**| Rango de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | Cadena  | 50000-50019 |
|**DSCP de audio P2P**| Marcado de puertos de audio | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Integer | 46 |
|**Puertos de vídeo P2P**| Rango de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | Cadena  | 50020-50039 |
|**DSCP de vídeo P2P**| Marcado de puertos de vídeo | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Integer | 34 |
|**Puertos de uso compartido P2P**| Intervalo de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | Cadena  | 50040-50059 |
|**P2P Sharing DSCP**| Marcado de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Integer | 18 |


### <a name="skype-for-business-qos-settings"></a>Configuración de QoS de Skype Empresarial

| Nombre                 | Descripción           | OMA-URI                                                                    | Tipo    | Valor                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Puertos de audio          | Rango de puertos de audio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | Cadena  | 50000-50019                    |
| DSCP de audio           | Marcado de puertos de audio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Integer | 46                             |
| Fuente multimedia de audio   | Nombre de la aplicación de Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | Cadena  | Microsoft.PPISkype.Windows.exe |
| Puertos de vídeo          | Rango de puertos de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | Cadena  | 50020-50039                    |
| DSCP de vídeo           | Marcado de puertos de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Integer | 34                             |
| Fuente multimedia de vídeo   | Nombre de la aplicación de Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | Cadena  | Microsoft.PPISkype.Windows.exe |
| Puertos de uso compartido        | Intervalo de puertos compartidos    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | Cadena  | 50040-50059                    |
| Uso compartido de DSCP         | Marcado de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Integer | 18                             |
| Origen multimedia de uso compartido | Nombre de la aplicación de Skype        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | Cadena  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Ambas tablas muestran los rangos de puertos predeterminados. Los administradores pueden cambiar los intervalos de puertos en Skype Empresarial y en el panel de control de Teams.

## <a name="microsoft-teams-settings"></a>Configuración de Microsoft Teams

Puede configurar varias opciones de Configuración de Microsoft Teams con Intune.

### <a name="modes"></a>Modos

Surface Hub 2S viene instalado con Microsoft Teams en el modo 0, que es compatible tanto con Microsoft Teams como con Skype Empresarial. Los modos funcionan como se describe a continuación:

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: Microsoft Teams con la funcionalidad de Skype Empresarial para reuniones programadas.
- Modo 2: solo Microsoft Teams.

Para ajustar el modo, agregue la siguiente configuración a un [perfil de configuración de dispositivo personalizado.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1 o 2|

### <a name="coordinated-meetings-and-proximity-join"></a>Reuniones coordinadas y unión de proximidad

Las características de reunión coordinada y unión de proximidad de Teams se pueden configurar a través de un archivo [XML](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) implementado a través de un perfil de Intune.

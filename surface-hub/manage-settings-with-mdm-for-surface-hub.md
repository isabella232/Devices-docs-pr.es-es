---
title: Administrar la configuración con un proveedor de MDM (Surface Hub)
description: Microsoft Surface Hub proporciona una solución de administración empresarial para ayudar a los administradores de TI a administrar directivas y aplicaciones empresariales en estos dispositivos con una solución de administración de dispositivos móviles (MDM).
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: administración de dispositivos móviles, MDM, administrar directivas
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 384d2d76274121236e76b1b5e45b30505e929c19
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911811"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Administrar Surface Hub con un proveedor MDM

Surface Hub permite a los administradores de TI administrar la configuración y las directivas mediante un proveedor de administración de dispositivos móviles (MDM), como Microsoft Intune. Surface Hub tiene un componente de administración integrado para comunicarse con el servidor de administración. No es necesario instalar clientes adicionales en el dispositivo.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Inscripción de Surface Hub en la administración de MDM 

Puedes inscribir Surface en Microsoft Intune otro proveedor mdm a través de la inscripción manual o automática.

### <a name="manual-enrollment"></a>Inscripción manual

1. Abre la **Configuración** e inicia sesión como administrador local. Seleccione **Surface Hub**  >  **Administración de dispositivos** y, a continuación, seleccione **+Administración de dispositivos**.
2. Se te pedirá que inicies sesión con la cuenta que usarás para tu proveedor mdm. Después de autenticar, el dispositivo se inscribe automáticamente con el proveedor mdm.

> [!TIP]
> Si usa Intune y no se detecta la dirección del servidor, escriba **manage.microsoft.com**.
   
> [!NOTE]
> La inscripción de MDM usa los detalles de la cuenta proporcionados para la autenticación. La cuenta debe tener permisos para inscribir un dispositivo Windows, así como una licencia de Intune (o las licencias de inscripción equivalentes configuradas en el proveedor MDM de terceros).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Inscripción automática: afiliada a Azure AD

Durante el proceso de configuración inicial, al asociar Surface Hub con un inquilino de Azure Active Directory (AD) que tenga habilitada la inscripción automática de Intune, el dispositivo se inscribirá automáticamente en Intune. Para obtener más información, consulte [Intune enrollment methods for Windows devices](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). La afiliación de Azure AD y la inscripción automática de Intune son necesarias para que Surface Hub sea un "dispositivo compatible" en Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Administrar Surface Hub Windows 10 Team configuración con Intune

El bloque de creación fundamental de la administración de la configuración de directivas en Intune y otros proveedores de MDM es el protocolo open mobile Alliance-Device management (OMA-DM) basado en XML. Windows 10 implementa OMA-DM XML a través de uno de los muchos proveedores de servicios de configuración (CSP) disponibles con nombres como AccountManagement CSP, DeviceStatus CSP, WiFi-CSP, entre otros. Para obtener una lista completa, consulte [LOSP compatibles con Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune y otros proveedores de MDM usan CSP para ofrecer una interfaz de usuario que te permita configurar las opciones de directiva en los perfiles de configuración. Intune usa el CSP de Surface Hub para su perfil integrado (restricciones de **dispositivos (Windows 10 Team),** lo que te permite configurar opciones básicas como impedir que Surface Hub "se desenlome" cada vez que alguien se mueva cerca dentro de su intervalo de proximidad. Para administrar la configuración del concentrador y las características fuera del perfil integrado de Intune, deberá usar un perfil personalizado, como se muestra a [continuación.](#create-custom-configuration-profile) 

En resumen, las opciones para configurar y administrar la configuración de directivas en Intune incluyen lo siguiente: 
 
- **Crear un perfil de restricción de dispositivo.** Usa el perfil integrado de Intune y configura la configuración directamente en la interfaz de usuario de Intune. Consulta [Crear perfil de restricción de dispositivos](#create-device-restriction-profile).
- **Crear un perfil de configuración de dispositivo.**  Seleccione una plantilla centrada en una característica o tecnología específica, como Microsoft Defender o certificados de seguridad. Consulta [Crear perfil de configuración de dispositivo](#create-device-configuration-profile).
- **Crear un perfil de configuración personalizado.**  Amplíe el ámbito de administración mediante un identificador uniforme de recursos (URI de OMA) de OMA desde cualquiera de los [CSP admitidos en Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Consulte [Crear perfil de configuración personalizado.](#create-custom-configuration-profile)

> [!NOTE]
> Los perfiles deben asignarse a grupos de dispositivos que contengan los dispositivos Surface Hub inscritos.

## <a name="create-device-restriction-profile"></a>Crear perfil de restricción de dispositivos

1. Inicie sesión en el [**Microsoft Endpoint Manager de administración**](https://endpoint.microsoft.com/), seleccione ****  >  **Perfiles de configuración de dispositivos**  >  **+** **Crear perfil**.
2. En **Plataforma**, **seleccione Windows 10 y versiones posteriores** >
3. En ****Tipo de**perfil,** seleccione **Plantillas** y, a continuación, **seleccione Restricciones de dispositivo (Windows 10 Team)**
4. Seleccione **Crear**, agregar un nombre y, a continuación, **seleccione Siguiente.**
6. Ahora puede examinar y elegir entre la configuración de restricción de dispositivos preestablecida para Surface Hub en las siguientes categorías: Aplicaciones y experiencia, Información operativa de Azure, Mantenimiento, Sesión y proyección inalámbrica. En el ejemplo que se muestra en la figura siguiente se especifica una ventana de mantenimiento de 4 horas y un tiempo de espera de 15 minutos para la pantalla, el suspensión y la reanudación de la sesión.

     ![Configure Surface Hub configuración con el perfil de restricción de dispositivos de Intune.](images/sh-device-restrictions.png)

Para obtener más información acerca de la creación y administración de perfiles, vea Restringir las características [de dispositivos](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)mediante la directiva en Microsoft Intune .
 
Para obtener más información acerca de cómo administrar las Surface Hub y la configuración, consulta [Surface Hub Windows 10 Team restricciones de dispositivos en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Crear perfil de configuración de dispositivo

1. Inicie sesión en el [**Microsoft Endpoint Manager de administración,**](https://endpoint.microsoft.com/)seleccione **Perfiles**  >  **de configuración de dispositivos**  >  **+ Crear perfil**.
2. En **Plataforma**, **seleccione Windows 10 y versiones posteriores** >
3. En **Tipo de perfil,** seleccione **Plantillas** y elija entre las siguientes plantillas admitidas en Surface Hub:

    - Restricciones de dispositivos (Windows 10 Team), como se describe en la [sección anterior](#create-device-restriction-profile).
    - Microsoft Defender para endpoint (Windows 10 Desktop)
    - Certificado PKCS
    - Certificado importado de PKCS
    - Certificado SCEP
    - Certificado de confianza

## <a name="create-custom-configuration-profile"></a>Crear perfil de configuración personalizado

Puede ampliar el ámbito de administración [mediante](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) la creación de un perfil personalizado mediante un URI de OMA desde cualquiera de los [CSP admitidos](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)en Microsoft Surface Hub . Cada configuración de un CSP tiene un OMA-URI correspondiente que puede establecer mediante perfiles de configuración personalizados en Intune. Para obtener información detallada sobre los SURFACE HUB, puede hacer referencia a los siguientes recursos: 

- [Referencia de proveedor de servicios de configuración](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [CSP de directivas admitidas por Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> La administración de la cuenta del dispositivo mediante la configuración del [CSP de SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) no es posible actualmente con Intune y requiere el uso de un proveedor MDM de terceros.

Para implementar la configuración de directiva basada en CSP, empiece generando un URI de OMA y, a continuación, agrégrelo a un perfil de configuración personalizado en Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Generar URI de OMA para la configuración de destino
 
Para generar el URI de OMA para cualquier configuración:

1. En la [documentación de CSP,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)identifique el nodo raíz del CSP. Por lo general, esto tiene el aspecto **./Vendor/MSFT/ <name of CSP> **. 
    - **Ejemplo:** El nodo raíz del [CSP de SurfaceHub](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) es **./Vendor/MSFT/SurfaceHub**.
2. Identificar la ruta de acceso del nodo para la configuración que quieras usar. 
    - **Ejemplo:** La ruta de acceso de nodo para la configuración para habilitar la proyección inalámbrica es **InBoxApps/WirelessProjection/Enabled**.
3. Anexar la ruta de acceso del nodo raíz para generar el URI de OMA. 
    - **Ejemplo:** El URI de OMA para la configuración para habilitar la proyección inalámbrica es **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. El tipo de datos también se indica en la documentación de CSP. Los tipos de datos más comunes son:
    - char (Cadena)
    - int (Entero)
    - bool (Booleano)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Agregar URI de OMA al perfil de configuración personalizado

1. En Endpoint Manager, seleccione **Perfiles**  >  **de configuración de dispositivos Crear**  >  **perfil**.
2. En Plataforma, **seleccione Windows 10 y versiones posteriores.** En Perfil, seleccione **Personalizado**y, a continuación, **seleccione Crear.**
3. Agregue un nombre y una descripción opcional y, a continuación, **seleccione Siguiente.**
4. En **Configuración**  >  **OMA-URI Configuración**, seleccione **Agregar**.

  
## <a name="manage-specific-surface-hub-features"></a>Administrar características Surface Hub específicas

En esta sección se resalta información sobre las características que puedes administrar a través de Intune u otro proveedor mdm. Esto incluye:

- [Calidad del servicio (QoS)](#quality-of-service-settings)
- [Microsoft Teams y Skype Empresarial](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>Configuración de calidad del servicio

Para garantizar una calidad óptima de vídeo y audio en Surface Hub, agrega la siguiente configuración de QoS al dispositivo. 

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


#### <a name="skype-for-business-qos-settings"></a>Configuración de QoS de Skype Empresarial

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

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams y Skype Empresarial configuración

Puede crear un perfil de configuración personalizado para administrar Teams reuniones coordinadas, la unión de proximidad y otras características. Para obtener más información, vea [Manage Microsoft Teams configuration on Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config).

#### <a name="changing-default-business-communications-platform"></a>Cambiar la plataforma de comunicaciones empresariales predeterminada

La plataforma de comunicaciones empresariales predeterminada en Surface Hub varía en función de cómo se instale Windows 10 Team actualización de 2020 (también Windows 10 20H2). Si vuelves a crear Surface Hub a Windows 10 20H2, Microsoft Teams se establecerá como predeterminado, con Skype Empresarial funcionalidad disponible (modo 1). Si actualiza el concentrador desde una versión anterior del sistema operativo, Skype Empresarial permanecerá como predeterminado, con la funcionalidad Teams disponible (modo 0) a menos que ya haya configurado Teams como predeterminado. 

Para cambiar la instalación predeterminada, use un [perfil personalizado](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) estableciendo el modo Teams aplicación de la siguiente manera:  

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: Microsoft Teams con la funcionalidad de Skype Empresarial para reuniones programadas.
- Modo 2: solo Microsoft Teams.

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1 o 2|











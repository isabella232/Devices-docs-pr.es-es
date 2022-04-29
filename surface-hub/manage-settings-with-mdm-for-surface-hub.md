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
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497793"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>Administrar Surface Hub con un proveedor MDM

Surface Hub permite a los administradores de TI administrar la configuración y las directivas mediante un proveedor de administración de dispositivos móviles (MDM), como Microsoft Intune. Surface Hub tiene un componente de administración integrado para comunicarse con el servidor de administración. No es necesario instalar clientes adicionales en el dispositivo.

## <a name="enrolling-surface-hub-into-mdm-management"></a>Inscripción de Surface Hub en la administración de MDM 

Puedes inscribir Surface en Microsoft Intune u otro proveedor de MDM a través de la inscripción manual o automática.

### <a name="manual-enrollment"></a>Inscripción manual

1. Abra la **aplicación Configuración** e inicie sesión como administrador local. Seleccione **Surface Hub** >  **Administración de dispositivos** y, a continuación, seleccione **+Administración de dispositivos**.
2. Se le pedirá que inicie sesión con la cuenta que se usará para su proveedor de MDM. Después de autenticarse, el dispositivo se inscribe automáticamente con el proveedor de MDM.

> [!TIP]
> Si usa Intune y no se detecta la dirección del servidor, escriba **manage.microsoft.com**.
   
> [!NOTE]
> La inscripción de MDM usa los detalles de la cuenta proporcionados para la autenticación. La cuenta debe tener permisos para inscribir un dispositivo Windows, así como una licencia de Intune (o las retiradas de inscripción equivalentes configuradas en el proveedor de MDM de terceros).

### <a name="auto-enrollment--azure-ad-affiliated"></a>Inscripción automática: Azure AD afiliada

Durante el proceso de configuración inicial, al asociar Surface Hub con un inquilino de Azure Active Directory (AD) que tenga habilitada Intune inscripción automática, el dispositivo se inscribirá automáticamente con Intune. Para obtener más información, consulte [métodos de inscripción de Intune para dispositivos Windows](/intune/enrollment/windows-enrollment-methods). La afiliación de Azure AD y la inscripción automática de Intune son necesarias para que Surface Hub sea un "dispositivo compatible" en Intune. 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>Administrar la configuración de Surface Hub Windows 10 Team con Intune

El bloque de creación fundamental de la administración de la configuración de directivas en Intune y otros proveedores de MDM es el protocolo Open Mobile Alliance-Device Management (OMA-DM) basado en XML. Windows implementa OMA-DM XML a través de uno de los muchos proveedores de servicios de configuración (CSP) disponibles con nombres como AccountManagement CSP, DeviceStatus CSP, WiFi-CSP, etc. Para obtener una lista completa, consulte [los CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).

Microsoft Intune y otros proveedores de MDM usan CSP para entregar una interfaz de usuario que le permite configurar las opciones de directiva en los perfiles de configuración. Intune usa el CSP de Surface Hub para su perfil integrado( Restricciones de dispositivos **(Windows 10 Team),** lo que le permite configurar opciones básicas, como impedir que Surface Hub "despertar" siempre que alguien se mueva cerca de su intervalo de proximidad. Para administrar la configuración y las características del centro fuera del perfil integrado de Intune, deberá usar un perfil personalizado, como [se muestra a continuación](#create-custom-configuration-profile). 

Para resumir, las opciones para configurar y administrar las opciones de directiva dentro de Intune incluyen lo siguiente: 
 
- **Cree un perfil de restricción de dispositivos.** Use el perfil integrado de Intune y configure los valores directamente en la interfaz de usuario de Intune. Consulte [Creación de un perfil de restricción de dispositivos](#create-device-restriction-profile).
- **Cree un perfil de configuración de dispositivo.**  Seleccione una plantilla centrada en una característica o tecnología específica, como Microsoft Defender o certificados de seguridad. Consulte [Creación de un perfil de configuración de dispositivo](#create-device-configuration-profile).
- **Cree un perfil de configuración personalizado.**  Amplíe el ámbito de administración mediante un identificador uniforme de recursos de OMA (URI de OMA) de cualquiera de los [CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Consulte [Creación de un perfil de configuración personalizado](#create-custom-configuration-profile).

> [!NOTE]
> Los perfiles deben asignarse a grupos de dispositivos que contengan los dispositivos Surface Hub inscritos.

## <a name="create-device-restriction-profile"></a>Creación de un perfil de restricción de dispositivos

1. Inicie sesión en [**Microsoft Endpoint Manager centro de administración**](https://endpoint.microsoft.com/) y seleccione **DispositivosPerfiles** > **** > **+** de configuración **Crear perfil**.
2. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**. >
3. En Tipo de perfil de ****, seleccione **Plantillas** y, a continuación **,** seleccione Restricciones de dispositivos **(Windows 10 Team)**
4. Seleccione **Crear**, agregue un nombre y, a continuación, seleccione **Siguiente.**
6. Ahora puede examinar y elegir entre la configuración de restricción de dispositivos preestablecida para Surface Hub en las siguientes categorías: Aplicaciones y experiencia, Información operativa de Azure, Mantenimiento, Sesión y Proyección inalámbrica. En el ejemplo que se muestra en la ilustración siguiente se especifica una ventana de mantenimiento de 4 horas y un tiempo de espera de 15 minutos para la pantalla, el modo de suspensión y la reanudación de la sesión.

     ![Configure Surface Hub opciones con Intune perfil de restricción de dispositivo.](images/sh-device-restrictions.png)

Para obtener más información sobre cómo crear y administrar perfiles, consulte [Restricción de características de dispositivos mediante la directiva en Microsoft Intune](/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
Para obtener más información sobre cómo administrar características y configuraciones de Surface Hub, consulte [configuración de Windows 10 Team para permitir o restringir características en Surface Hub mediante Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>Creación de un perfil de configuración de dispositivo

1. Inicie sesión en [**Microsoft Endpoint Manager centro de administración**](https://endpoint.microsoft.com/) y seleccione **DispositivosPerfiles** > **** >  de configuración **+ Crear perfil**.
2. En **Plataforma**, seleccione **Windows 10 y versiones posteriores**. >
3. En **Tipo de perfil**, seleccione **Plantillas** y elija entre las siguientes plantillas admitidas en Surface Hub:

    - Restricciones de dispositivos (Windows 10 Team), como se describe en la [sección anterior](#create-device-restriction-profile).
    - Microsoft Defender para punto de conexión (Windows 10 Desktop)
    - Certificado PKCS
    - Certificado pkcs importado
    - Certificado SCEP
    - Certificado de confianza

## <a name="create-custom-configuration-profile"></a>Creación de un perfil de configuración personalizado

Puede ampliar el ámbito de la administración [mediante la creación de un perfil personalizado](/mem/intune/configuration/custom-settings-configure) mediante un URI de OMA desde cualquiera de los [CSP admitidos en Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). Cada configuración de un CSP tiene un OMA-URI correspondiente que puede establecer mediante perfiles de configuración personalizados en Intune. Para obtener más información sobre los CSP admitidos por Surface Hub, puede hacer referencia a los siguientes recursos: 

- [Referencia de proveedor de servicios de configuración](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [CSP de directivas admitidas por Microsoft Surface Hub](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> La administración de la cuenta de dispositivo mediante la configuración de [CSP de SurfaceHub](/windows/client-management/mdm/surfacehub-csp) no es posible actualmente con Intune y requiere el uso de un proveedor de MDM de terceros.

Para implementar la configuración de directiva basada en CSP, empiece por generar un URI de OMA y, a continuación, agréguelo a un perfil de configuración personalizado en Intune.

### <a name="generate-oma-uri-for-target-setting"></a>Generación del URI de OMA para la configuración de destino
 
Para generar el URI de OMA para cualquier configuración:

1. En la [documentación de CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport), identifique el nodo raíz del CSP. Por lo general, esto se parece **a ./Vendor/MSFT/NameOfCSP**. 
    - **Ejemplo:** El nodo raíz del [CSP de SurfaceHub](/windows/client-management/mdm/surfacehub-csp) es **./Vendor/MSFT/SurfaceHub**.
2. Identificar la ruta de acceso del nodo para la configuración que quieras usar. 
    - **Ejemplo:** La ruta de acceso del nodo para la configuración para habilitar la proyección inalámbrica es **InBoxApps/WirelessProjection/Enabled**.
3. Anexar la ruta de acceso del nodo raíz para generar el URI de OMA. 
    - **Ejemplo:** El URI de OMA de la configuración para habilitar la proyección inalámbrica es **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. El tipo de datos también se indica en la documentación de CSP. Los tipos de datos más comunes son:
    - char (Cadena)
    - int (Entero)
    - bool (Booleano)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>Adición del URI de OMA al perfil de configuración personalizada

1. En Endpoint Manager, seleccione **DispositivosPerfiles** >  >  **de** **configuraciónCrear perfil**.
2. En Plataforma, seleccione **Windows 10 y versiones posteriores.** En Perfil, seleccione **Personalizado** y, a continuación, seleccione **Crear.**
3. Agregue un nombre y una descripción opcional y, a continuación, seleccione **Siguiente.**
4. En **ConfiguraciónConfiguración** >  **CONFIGURACIÓN DE URI** DEOMA, seleccione **Agregar**.

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>configuración de Microsoft Teams y Skype Empresarial

En esta sección se resalta la configuración de Teams y Skype Empresarial que puede administrar a través de Intune u otro proveedor de MDM. Esto incluye:

- [Calidad de servicio (QoS)](#quality-of-service-settings)
- [Administración de características específicas de Teams](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>Configuración de calidad del servicio

Para garantizar una calidad óptima de vídeo y audio en Surface Hub, agregue la siguiente configuración de QoS al dispositivo. 

| Nombre                 | Descripción           | OMA-URI                                                                 | Tipo    | Valor                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| Puertos de audio          | Rango de puertos de audio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | Cadena  | 50000-50019                    |
| DSCP de audio           | Marcado de puertos de audio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | Integer | 46                             |
| Puertos de vídeo          | Rango de puertos de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | Cadena  | 50020-50039                    |
| DSCP de vídeo           | Marcado de puertos de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | Integer | 34                             |
| Uso compartido de puertos        | Intervalo de puertos de uso compartido    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | Cadena  | 50040-50059                    |
| Uso compartido de DSCP         | Marcado de puertos de uso compartido | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | Integer | 18                             |

> [!NOTE]
> En la tabla se muestran los intervalos de puertos predeterminados. Los administradores pueden cambiar los intervalos de puertos en Skype Empresarial y en el panel de control de Teams.

### <a name="manage-teams-specific-features"></a>Administración de características específicas de Teams

Puede crear un perfil de configuración personalizado para administrar Teams reuniones coordinadas, unión a proximidad y otras características. Para más información, consulte [Administración de la configuración de Microsoft Teams en Surface Hub](/microsoftteams/rooms/surface-hub-manage-config).

### <a name="changing-default-app-for-meetings--calls"></a>Cambio de la aplicación predeterminada para las reuniones & llamadas

La aplicación predeterminada para reuniones & llamadas en el Surface Hub varía en función de cómo instale Windows 10 Team actualización de 2020 (también conocida como Windows 10 edición 20H2 Team). Si vuelve a crear una imagen de un Surface Hub en Windows 10 20H2, Microsoft Teams se establecerá como valor predeterminado, con Skype Empresarial no disponible (modo 1). Si actualiza el centro desde una versión anterior del sistema operativo, Skype Empresarial permanecerá como valor predeterminado, con Teams funcionalidad disponible (modo 0) a menos que ya haya configurado Teams como valor predeterminado. 

Para cambiar la instalación predeterminada, use un [perfil personalizado](/mem/intune/configuration/custom-settings-configure) para establecer el modo de reunión Teams como se indica a continuación:  

- Modo 0: Skype Empresarial con la funcionalidad de Microsoft Teams para reuniones programadas.
- Modo 1: solo Microsoft Teams.

| Nombre | Descripción | OMA-URI | Tipo | Valor |
|:--- |:--- |:--- |:--- |:--- |
|**Id. de aplicación de Teams**|Nombre de la aplicación|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|Cadena| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Modo de aplicación de Teams**|Modo Teams|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 o 1|



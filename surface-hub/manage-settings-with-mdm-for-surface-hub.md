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
ms.date: 03/07/2018
ms.localizationpriority: medium
ms.openlocfilehash: d96f5748533a2d83a0ca68cd42a0663506514d36
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10837051"
---
# Administrar la configuración con un proveedor de MDM (Surface Hub)

Surface Hub y otros dispositivos Windows 10 permiten a los administradores de TI administrar la configuración y las directivas usando un proveedor de administración de dispositivos móviles (MDM). Un componente de administración integrado se comunica con el servidor de administración, por lo que no es necesario instalar clientes adicionales en el dispositivo. Para obtener más información, consulta [Administración de dispositivos móviles Windows 10](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx) .

Surface Hub se ha validado con los proveedores de MDM de terceros de Microsoft:
- Microsoft InTune independiente
- MDM local con el administrador de configuración de Microsoft Endpoint

También puedes administrar los dispositivos Surface Hub con cualquier proveedor de MDM de terceros que se pueda comunicar con Windows 10 mediante el protocolo MDM.

## <a href="" id="enroll-into-mdm"></a>Inscribir un Surface Hub en MDM
Puedes inscribir a Surface hubs con inscripción masiva, manual o automática.

### Inscripción masiva
**Configurar la inscripción masiva**
- Surface Hub admite el [aprovisionamiento CSP](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) para la inscripción masiva en MDM. Para obtener más información, consulta [Inscripción masiva de Windows 10](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx).<br>
--O BIEN--
- Si tiene una infraestructura local de Configuration Manager de Microsoft, consulte [cómo inscribir dispositivos en masa con la administración de dispositivos móviles local en Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm).

### Inscripción manual
**Configurar la inscripción manual**
1. En tu Surface Hub, abre **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Selecciona **Este dispositivo** y navega a **Administración de dispositivos**.
4. En **Administración de dispositivos**, selecciona **+ Administración de dispositivos**.
5. Sigue las instrucciones en el cuadro de diálogo para conectarse al proveedor de MDM.

### Inscripción automática a través de Azure Active Directory join

Surface Hub ahora es compatible con la capacidad de inscribirse automáticamente en Intune uniendo el dispositivo a Azure Active Directory. 

El primer paso es configurar la inscripción automática de MDM. Consulte [Habilitar la inscripción automática de Windows 10](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).

Después, cuando los dispositivos se configuren durante la primera ejecución, seleccione la opción para unirse a Azure Active Directory, consulte [configurar administradores para este dispositivo](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## Administrar la configuración de Surface Hub con MDM

Puedes usar MDM para administrar algunas [opciones de configuración del CSP de Surface Hub](#supported-surface-hub-csp-settings) y algunas [opciones de configuración de Windows 10](#supported-windows-10-settings). Según el proveedor de MDM que uses, puedes establecer estas opciones de configuración mediante una interfaz de usuario integrada o implementando SyncML personalizado. Microsoft Intune y Microsoft Endpoint Configuration Manager proporcionan experiencias integradas para ayudar a crear plantillas de directiva para Surface Hub. Consulta la documentación del proveedor de MDM para obtener información sobre cómo crear e implementar SyncML.

### Configuración de CSP de Surface Hub admitida

Puedes configurar la configuración de Surface Hub en la siguiente tabla con MDM. La tabla identifica si la configuración es compatible con Microsoft Intune, Microsoft Endpoint Configuration Manager o SyncML.

Para obtener más información, consulta [Proveedor de servicios de configuración de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323). 


|                                     Opción de configuración                                      |                                                    Nodo en el CSP de SurfaceHub                                                    |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                Horas de mantenimiento                                 |                        MaintenanceHoursSimple/horas/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       Sí                        |                       Sí                       |             Sí             |
|              Activar automáticamente la pantalla con sensores de movimiento               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       Sí                        |                       Sí                       |             Sí             |
|                      Requerir un PIN para la proyección inalámbrica                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       Sí                        |                       Sí                       |             Sí             |
|                            Habilitar la proyección inalámbrica                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       Sí                        | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                 Canal Miracast para usar proyección inalámbrica                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       Sí                        | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|              Conectar con el área de trabajo de Operations Management Suite               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       Sí                        | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                         Imagen de fondo de pantalla de inicio de sesión                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       Sí                        | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Información de la reunión que se muestra en la pantalla de inicio de sesión                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       Sí                        | Sí.<br> [Usa una configuración personalizada.] (#example-administración-Surface-Hub-Settings-with-Microsoft-Endpoint-Configuration-Manager |             Sí             |
|                      Nombre descriptivo para la proyección inalámbrica                       |                                                     Propiedades/FriendlyName                                                      | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                   Cuenta del dispositivo, incluida la rotación de contraseñas                    | DeviceAccount/*`<name_of_policy>`* <br> Consulta [CSP de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). |                        No                        |                       No                        |             Sí             |
|                               Especificar el dominio de Skype                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Iniciar automáticamente la aplicación Conectar cuando se inicie la proyección               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                                Establecer volumen predeterminado                                |                                                     Properties/DefaultVolume                                                     |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                                Establecer el tiempo de espera de la pantalla                                |                                                     Properties/ScreenTimeout                                                     |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                               Establecer el tiempo de espera de la sesión                                |                                                    Properties/SessionTimeout                                                     |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                                Establecer el tiempo de espera para la suspensión del sistema                                 |                                                     Properties/SleepTimeout                                                      |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                   Permitir que la sesión reanude después de que pantalla esté inactiva                   |                                                  Properties/AllowSessionResume                                                   |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|             Permitir que la cuenta del dispositivo se use para la autenticación de proxy             |                                                  Properties/AllowAutoProxyAuth                                                   |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
| Deshabilitar el rellenado automático del cuadro de diálogo de inicio de sesión con los invitados de reuniones programadas |                                               Properties/DisableSignInSuggestions                                                |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|              Deshabilitar la característica "Mi reuniones y archivos" en el menú Inicio               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    Sí </br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                     Establecer LanProfile para autenticación con cable 802.1X                     |                                                         Dot3/LanProfile                                                          | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                    Establecer EapUserData para autenticación con cable 802.1X                     |                                                         Dot3/EapUserData                                                         | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

### Configuración de Windows 10 admitida

Además de la configuración específica del Surface Hub, hay varias opciones de configuración comunes a todos los dispositivos Windows 10. Estas opciones se definen en la [Referencia de proveedores de servicios de configuración](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference). 

Las tablas siguientes incluyen información sobre la configuración de Windows 10 que se ha validado con Surface Hub. Hay una tabla con la configuración para estas áreas: seguridad, explorador, actualizaciones de Windows, Windows Defender, reinicio remoto, certificados y registros. Cada tabla identifica si la configuración es compatible con Microsoft Intune, Microsoft Endpoint Configuration Manager o SyncML.

#### Configuración de seguridad

|      Opción de configuración       |                                            Detalles                                             |                                                                          Referencia de CSP                                                                           |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  Permitir Bluetooth   |                      Mantener habilitado para admitir periféricos Bluetooth.                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    Sí. <br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
| Directivas de Bluetooth | Se usa para establecer el nombre del dispositivo Bluetooth y para bloquear la publicidad, la detección y el emparejamiento automático. |                     Bluetooth/*`<name of policy>`* <br> Consulta [CSP de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    Sí. <br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|    Permitir cámara    |                           Mantenerlo habilitado para Skype Empresarial.                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    Sí. <br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|   Permitir ubicación   |                        Mantenerlo habilitado para admitir aplicaciones como Mapas.                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   Sí. <br> .                    | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|  Permitir telemetría   |                    Mantenerlo habilitado para ayudar a Microsoft a mejorar Surface Hub.                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    Sí. <br>                     | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|  Permitir unidades USB  |                     Mantenerlo habilitado para admitir unidades USB en Surface Hub                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows. 

#### Configuración del explorador

|                          Valor                          |                                                                        Detalles                                                                        |                                                                             Referencia de CSP                                                                              |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         Páginas principales                         |                                               Usar para configurar las páginas principales predeterminadas en Microsoft Edge.                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                       Permitir cookies                       |                    Surface Hub elimina automáticamente las cookies al final de una sesión. Usarlo para bloquear cookies en una sesión.                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                   Permitir herramientas de desarrollo                   |                                                   Usar para impedir que los usuarios usen las herramientas de desarrollo F12.                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                    Permitir Do Not Track                     |                                                          Usar para habilitar el encabezado Do Not Track.                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                       Permitir elementos emergentes                       |                                                         Usar para bloquear las ventanas emergentes del explorador.                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                 Permitir sugerencias de búsqueda                  |                                                  Usar para bloquear las sugerencias de búsqueda en la barra de direcciones.                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|                     Permitir SmartScreen de Windows Defender                     |                                                       Mantén esta opción habilitada para activar SmartScreen de Windows Defender.                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
| Evitar la omisión de advertencias de SmartScreen de Windows Defender para sitios web |     Para mayor seguridad, use este fin para evitar que los usuarios ignoren las advertencias de SmartScreen de Windows Defender y bloquear el acceso a sitios Web maliciosos.     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|  Evitar la omisión de advertencias de SmartScreen de Windows Defender para archivos   | Para mayor seguridad, usa para evitar que los usuarios ignoren las advertencias de SmartScreen de Windows Defender y bloquear la descarga de archivos no comprobados de Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Configuración de Windows Update

|                      Ajuste                      |                                                                                                           Detalles                                                                                                            |                                                                    Referencia de CSP                                                                    |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Usar rama actual frente o rama actual para empresas |                                                       Usar para configurar Windows Update para empresas; consulta [Actualizaciones de Windows](manage-windows-updates-for-surface-hub.md).                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Aplazar actualizaciones de características               |                                                                                                          Ver más arriba.                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Aplazar actualizaciones de calidad               |                                                                                                          Ver más arriba.                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Pausar actualizaciones de características               |                                                                                                          Ver más arriba.                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Pausar actualizaciones de calidad               |                                                                                                          Ver más arriba.                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|           Configurar el dispositivo para usar WSUS            |                                            Usar para conectar el Surface Hub con WSUS en lugar de Windows Update; consulta [Actualizaciones de Windows](manage-windows-updates-for-surface-hub.md).                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|               Optimización de distribución               | Usar el uso compartido de contenido de punto a punto para reducir los problemas de ancho de banda durante las actualizaciones. Consulta [Configurar Optimización de distribución de Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization) para obtener más información. |         DeliveryOptimization/*`<name of policy>`* <br> Consulta [CSP de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Configuración de Windows Defender

|      Valor      |                                              Detalles                                               |                                                     Referencia de CSP                                                      |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Directivas de Defender |            Usar para configurar varios valores de Defender, incluyendo un tiempo de análisis programado.            | Defender/*`<name of policy>`* <br> Consulta [CSP de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
|  Estado de Defender  | Usar para iniciar un examen de defender, forzar una actualización de inteligencia de seguridad, consultar cualquier amenaza detectada. |                   [CSP de Defender](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       Sí                        |                       Sí                       |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Reinicio remoto

|                       Opción de configuración                        |                                                          Detalles                                                          |                                                             Referencia de CSP                                                             |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            Reinicia el dispositivo inmediatamente             | Usar conjuntamente con OMS para reducir los costos de soporte técnico; consulta [Supervisar Microsoft Surface Hub](monitor-surface-hub.md). |        ./Vendor/MSFT/Reboot/RebootNow <br> Consulta [CSP de reinicio](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       Sí                        |                       No                        |             Sí             |
|    Reiniciar el dispositivo en una fecha y hora programadas    |                                                        Ver más arriba.                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> Consulta [CSP de reinicio](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |
| Reiniciar el dispositivo diariamente en una fecha y hora programadas |                                                        Ver más arriba.                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> Consulta [CSP de reinicio](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Instalar certificados

|             Opción de configuración             |                           Detalles                            |                                           Referencia de CSP                                            |                                                         Compatible con<br>¿Intune?                                                          |                                                                  Compatible con<br>¿Configuration Manager?                                                                  | Compatible con<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Instalar certificados de CA de confianza | Usar para implementar certificados raíz de confianza y de CA intermedia. | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | Sí. <br> Consulta [Configurar perfiles de certificado de Intune](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | Sí. <br> Vea [Cómo crear perfiles de certificados en Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles). |             Sí             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Recopilar registros

|     Valor      |                      Detalles                       |                                     Referencia de CSP                                      | Compatible con<br>¿Intune? | Compatible con<br>¿Configuration Manager? | Compatible con<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| Recopilar registros de ETW | Usar para recopilar registros de ETW de forma remota desde Surface Hub. | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            No             |                    No                    |             Sí             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Establecer la directiva de calidad de servicio (QoS) de la red

|        Opción de configuración         |                                                            Detalles                                                             |                                                    Referencia de CSP                                                     |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Establecer la directiva de QoS de red | Se usa para establecer una directiva de QoS para realizar un conjunto de acciones en el tráfico de red. Esto es útil para establecer prioridades de los paquetes de red de Skype. | [CSP de NetworkQoSPolicy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Establecer el proxy de red

|      Opción de configuración      |                               Detalles                               |                                                Referencia de CSP                                                 |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Establecer el proxy de red | Se usa para configurar un servidor proxy para conexiones Wi-Fi y Ethernet. | [CSP de NetworkProxy](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

#### Configurar el menú Inicio

|       Ajuste        |                                                                       Detalles                                                                        |                                                        Referencia de CSP                                                         |            Compatible con<br>¿Intune?             |    Compatible con<br>¿Configuration Manager?     | Compatible con<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Configurar el menú Inicio | Debe usarse para configurar qué aplicaciones se muestran en el menú Inicio. Para obtener más información, consulta [Configurar el menú Inicio de Surface Hub](surface-hub-start-menu.md) | [Directiva de CSP: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | Sí <br> [Usar una directiva personalizada.](#example-manage-surface-hub-settings-with-microsoft-intune) | Sí.<br> [Usar una configuración personalizada.](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             Sí             |

El objeto \*Settings que se admite con SyncML también se puede configurar en un paquete de aprovisionamiento del Diseñador de configuración de Windows.

### Generar URI de OMA para la configuración 
Debe usar un URI OMA de configuración para crear una directiva personalizada en Intune o una configuración personalizada en Microsoft Endpoint Configuration Manager.

**Generar el URI de OMA para cualquier configuración en la documentación de CSP**
1. En la documentación de CSP, identifica el nodo raíz del CSP. Normalmente tiene esta apariencia `./Vendor/MSFT/<name of CSP>` <br>
*Por ejemplo, el nodo raíz del [CSP de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) es `./Vendor/MSFT/SurfaceHub`.*
2. Identificar la ruta de acceso del nodo para la configuración que quieras usar. <br>
*Por ejemplo, la ruta de acceso del nodo para la configuración para habilitar la proyección inalámbrica es `InBoxApps/WirelessProjection/Enabled`.*
3. Anexar la ruta de acceso del nodo raíz para generar el URI de OMA. <br>
*Por ejemplo, el URI de OMA para la configuración para habilitar la proyección inalámbrica es `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`.*

El tipo de datos también se indica en la documentación de CSP. Los tipos de datos más comunes son:
- char (Cadena)
- int (Entero)
- bool (Booleano)


## Ejemplo: Administrar la configuración de Surface Hub con Microsoft Intune

Puedes usar Microsoft Intune para administrar la configuración de Surface Hub. Para la configuración personalizada, sigue las instrucciones de [Cómo configurar opciones de dispositivo personalizado en Microsoft Intune](https://docs.microsoft.com/intune/custom-settings-configure). Para **Plataforma**, selecciona **Windows 10 y versiones posteriores** y en **Tipo de perfil**, selecciona **Restricciones de dispositivo (Windows 10 Team)**.



## Ejemplo: administrar la configuración de Surface Hub con el administrador de configuración de Microsoft Endpoint
Configuration Manager admite la administración de dispositivos modernos que no requieren que el cliente de Configuration Manager los administre, incluidos Surface Hub. Si ya usa Configuration Manager para administrar otros dispositivos de su organización, puede continuar usando la consola de Configuration Manager como su única ubicación para administrar Surface Hub.

> [!NOTE]
> Estas instrucciones se basan en la rama actual del administrador de configuración.

**Crear un elemento de configuración para la configuración de Surface Hub**

1. En el área de trabajo **Activos y compatibilidad** de la consola de Configuration Manager, haz clic en **Introducción** > **Configuración de cumplimiento** > **Elementos de configuración**.
2. En la pestaña **Inicio**, en el grupo **Crear**, haz clic en **Crear elemento de configuración**.
3. En la página **General** del Asistente para crear elemento de configuración, especifica un nombre y una descripción opcional para el elemento de configuración.
4. En **Configuración para los dispositivos administrados sin el cliente Configuration Manager**, selecciona **Windows 8.1 y Windows 10**, y haz clic en **Siguiente**.

    ![ejemplo de interfaz de usuario](images/configmgr-create.png)
5. En la página **Plataformas admitidas**, expande **Windows 10** y selecciona **Todo Windows 10 Team y versiones posteriores**. Anula la selección de las otras plataformas de Windows y haz clic en **Siguiente**.

    ![seleccionar plataforma](images/configmgr-platform.png)
7. En la página **Configuración del dispositivo**, en **Grupos de configuración de dispositivos**, selecciona **Windows 10 Team**.


8. En la página **Windows 10 Team**, configura las opciones de configuración que necesites.

    ![Windows 10 Team](images/configmgr-team.png)
9. Deberás crear una configuración personalizada para administrar las opciones de configuración que no estén disponible en la página de Windows 10 Team. En la página **Configuración del dispositivo**, selecciona la casilla de verificación **Configurar opciones adicionales que no se encuentran en los grupos de configuración predeterminados**.

    ![configuración adicional](images/configmgr-additional.png)
10. En la página **Configuración adicional**, haz clic en **Agregar**.
11. En el cuadro de diálogo **Examinar configuración**, haz clic en **Crear configuración**.
12. En el cuadro de diálogo **Crear configuración**, en la pestaña **General**, especifica un nombre y la descripción opcional de la configuración personalizada.
13. En **Tipo de configuración**, selecciona **OMA URI**.
14. Completa el formulario para crear una nueva configuración y, a continuación, haz clic en **Aceptar**.

    ![configuración OMA URI](images/configmgr-oma-uri.png)
15. En el cuadro de diálogo **Examinar configuración**, en **Opciones de configuración disponibles**, selecciona la nueva configuración que has creado y, a continuación, haz clic en **Seleccionar**.
16. En el cuadro de diálogo **Crear regla**, completa el formulario para especificar una regla para la configuración y, a continuación, haz clic en **Aceptar**.
17. Repite los pasos 9 a 15 para cada configuración personalizada que quieras agregar al elemento de configuración.
18. Cuando hayas terminado, en el cuadro de diálogo **Examinar configuración**, haz clic en **Cerrar**.
19. Completa el asistente. <br> Puedes ver el nuevo elemento de configuración en el nodo **Elementos de configuración** del área de trabajo **Activos y compatibilidad**.

Para obtener más información, vea [crear elementos de configuración para windows 8,1 y dispositivos con Windows 10 administrados sin el cliente de Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client).

## Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)












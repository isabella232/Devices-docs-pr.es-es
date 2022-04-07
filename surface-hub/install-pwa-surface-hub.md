---
title: Instalar Web Apps progresiva en Surface Hub
description: Explica cómo los administradores pueden instalar Web Apps progresivas (PWA) en Surface Hub a través de Intune o un paquete de aprovisionamiento.
keywords: Surface Hub, PPA, aplicación
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: ea30f25451b0be54bd2b6eaa2552036e0d78ff27
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472755"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Instalar Web Apps progresiva en Surface Hub

Los administradores pueden instalar de forma remota [Web Apps progresiva (PWA)](/microsoft-edge/progressive-web-apps-chromium/) en Surface Hubs mediante un proveedor de administración de dispositivos móviles (MDM), como Microsoft Intune o un paquete de aprovisionamiento. Las PWA funcionan como aplicaciones nativas instaladas en plataformas admitidas y funcionan como sitios web normales en otros exploradores. Cuando los administradores instalan PPA en Surface Hub, los usuarios pueden ejecutarlos directamente desde el menú Aplicación. 

> [!IMPORTANT]
> Antes de instalar los PWA, asegúrese de que el Surface Hub tenga [KB5011543](https://support.microsoft.com/help/5011543) (o una actualización de Windows posterior) instalada. Para obtener más información sobre las actualizaciones de Windows 10 Team más recientes, consulte [Surface Hub historial de actualizaciones](surface-hub-update-history.md). 

- [Instalación de PPA en Surface Hub a través de Intune](#install-pwas-via-intune)
- [Instalación de PWA en Surface Hub a través del paquete de aprovisionamiento](#install-pwas-via-provisioning-package)

Los usuarios también pueden instalar PPA para su uso durante la sesión del centro. Cuando finaliza la sesión, se quitan las PPA. Para obtener más información, consulte [Instalación, administración o desinstalación de aplicaciones en Microsoft Edge](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113)

## <a name="install-pwas-via-intune"></a>Instalación de PPA a través de Intune

Usa Intune u otro proveedor de MDM para instalar PPA en Surface Hubs. Para más información, consulte [Administración de la configuración con un proveedor de MDM](manage-settings-with-mdm-for-surface-hub.md).

### <a name="get-started"></a>Comenzar

1. Inicie sesión en el portal de Intune en [**Microsoft Endpoint Manager centro de administración**](https://endpoint.microsoft.com/).
2. Vaya **** a **DispositivosDirectivas** >  **de** **configuraciónCrear** >  perfil. 
3. En Plataforma, seleccione **Windows 10 y versiones posteriores**. En Tipo de perfil, seleccione **Plantillas**. En Nombre de plantilla, seleccione **Plantillas administrativas.**
4. Seleccione **Crear.**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Creación de un perfil de configuración de Intune" :::

5. Asigne un nombre al perfil, escriba una descripción opcional y seleccione **Siguiente**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Perfil de nombre" :::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Configuración de la directiva de Web Apps por fuerza instalada (Intune)

1. Seleccione **Microsoft Edge Configuración** y, en el cuadro Buscar, escriba **force-installed**, seleccione **force-installed Web Apps** y, a continuación, seleccione **Habilitado**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Configuración de Web Apps de instalación forzada" :::

2. En **Direcciones URL para que Web Apps se instalen de forma silenciosa**, cree un fragmento de código XML a partir de la sintaxis siguiente o copie en el [ejemplo](#example-pwas) siguiente. 

    ```
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```
    
#### <a name="example-pwas"></a>PPA de ejemplo

En este ejemplo se instalaN PWA para YoutTube, Webex, Zoom y Uber.

```
    [
{ "url": "https://www.youtube.com/",       "default_launch_container": "window" },
{ "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
{ "url": "https://zoom.us/join",           "default_launch_container": "window" },
{ "url": "https://www.uber.com/",          "default_launch_container": "tab"}
]
```

3. Escriba el fragmento de código que contiene direcciones URL para las aplicaciones que desea instalar.
4. Escriba etiquetas de ámbito opcionales según corresponda y seleccione **Siguiente.**
5. Asigne a los usuarios según corresponda.
6. Asigna a un grupo que contenga los Surface Hubs de destino. Para más información, consulte [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).
7. Revise y seleccione **Crear**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Crear perfil" :::
    

8. Sincronice los dispositivos de destino según corresponda.
9. En Surface Hub, inicie Edge. Las PPA se instalan y aparecen en la lista todas las aplicaciones menú Inicio.

## <a name="install-pwas-via-provisioning-package"></a>Instalación de PWA a través del paquete de aprovisionamiento

Puedes instalar PPA aplicando un paquete de aprovisionamiento a Surface Hubs mediante una unidad USB. Para más información, consulte [Creación de paquetes de aprovisionamiento](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>Comenzar con el aprovisionamiento

1. En un equipo independiente que ejecute Windows 10 o Windows 11, instale [Windows Diseñador de configuración](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) desde el Microsoft Store.
2. En WCD, cree un nuevo Project. Seleccione **Aprovisionar dispositivos de escritorio,** proporcione un nombre para el proyecto y elija **Finalizar.**
3. Seleccione **Cambiar al editor avanzado** y seleccione **Sí** para confirmar.

### <a name="configure-msedgepolicy"></a>Configuración de MSEdgePolicy

1. En el panel Personalizaciones disponibles en WCD, vaya a **\Runtime Configuración\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. En el panel de edición de personalizaciones, escriba el nombre de la aplicación como **MSEdgePolicy** y seleccione **Agregar**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Escriba el nombre de la aplicación como MSEdgePolicy." :::

3. En el panel Personalizaciones disponibles, seleccione **AppName: MSEdgePolicy** y, en el panel de edición, cambie **SettingType** a **Policy** y elija **Agregar**.
4. En el panel Personalizaciones disponibles, seleccione **SettingType: Policy** y, en el panel de edición, establezca **AdmxFileUid** en **MSEdgePolicy** y elija **Agregar**.
5. En el panel Personalizaciones disponibles, seleccione **AdmxFileUid: MSEdgePolicy** y, en el panel de edición, establezca **MSEdgePolicy** escribiendo el código siguiente como una sola línea de texto:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Escriba código para MSEdgePolicy." :::   
   
    ```
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```
 
### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Configuración de la directiva de Web Apps por fuerza instalada (paquete de aprovisionamiento)

1. En el panel Personalizaciones disponibles en WCD, vaya a: **\Runtime Configuración\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. En el panel de edición personalizaciones, escriba areaname como **MSEdgePolicy~Policy~microsoft_edge y** seleccione **Agregar**.
3. En el panel Personalizaciones disponibles, seleccione **AreaName: MSEdgePolicy~Policy~microsoft_edge** y, en el panel de edición, establezca **Nombre de** directiva en **WebAppInstallForceList** y seleccione **Agregar**.
4. En el panel Personalizaciones disponibles, seleccione **PolicyName: WebAppInstallForceList** y, en el panel de edición de **WebAppInstallForceList** , escriba el código siguiente como una sola línea de texto.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Escriba el código para la directiva de Web Apps forzada instalada" :::   

 > [!TIP]
 > En este ejemplo se instala You Tube como PWA. Reemplace la dirección URL según corresponda. 

```
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
```    

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Exportación del paquete de aprovisionamiento y aplicación a Surface Hubs

1. En la barra de menús, seleccione **Exportar**, seleccione **Paquete de aprovisionamiento** y siga las indicaciones para generar el archivo .ppkg.
2. Inserte una unidad flash USB vacía. Seleccione la ubicación de salida para ir a la ubicación del paquete. Copie el archivo .ppkg en la unidad USB.
3. Aplique el paquete de aprovisionamiento a través de la aplicación de Configuración o durante la primera ejecución de la instalación. Para más información, consulte [Creación de paquetes de aprovisionamiento](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub).

## <a name="learn-more"></a>Obtén más información

- [Referencia de WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Introducción a las aplicaciones web progresivas (PWA)](/microsoft-edge/progressive-web-apps-chromium/)

---
title: Instalar aplicaciones web progresivas en Surface Hub
description: Explica cómo los administradores pueden instalar Web Apps progresivas (PWA) en Surface Hub a través de Intune o un paquete de aprovisionamiento.
keywords: Surface Hub, PPA, aplicación
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497582"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>Instalar aplicaciones web progresivas en Surface Hub

La compatibilidad con la aplicación web progresiva (PWA) abre una nueva fuente enriquecida de aplicaciones que amplía significativamente la biblioteca de aplicaciones disponibles que se pueden ejecutar en Suface Hub.  Los usuarios pueden acceder a una gran cantidad de aplicaciones fuera del Microsoft Store y ejecutarlas directamente desde el menú Aplicación.  En comparación con las páginas web, las PPA se comportan más como aplicaciones nativas con funcionalidad sin conexión, la capacidad de actualizar en segundo plano y otras características únicas. La mayoría de los sitios web se pueden instalar como PWA y aprovechar cualquier función adicional habilitada por los desarrolladores web.

Los administradores pueden instalar PPA de forma remota en Surface Hubs a través de proveedores de administración de dispositivos móviles (MDM), como Microsoft Intune. O bien, puede usar un paquete de aprovisionamiento. En este artículo se describen ambos métodos con código de ejemplo para instalar YouTube, WebEx, Zoom y Uber e instrucciones para instalar sus propios PWA. Para más información, consulte [Introducción a la Web Apps progresiva](/microsoft-edge/progressive-web-apps-chromium/).

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

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Creación de un perfil de configuración de Intune" lightbox="images/pwa-hubpwainstall.png":::

5. Asigne un nombre al perfil, escriba una descripción opcional y seleccione **Siguiente**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Perfil de nombre" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>Configuración de la directiva de Web Apps por fuerza instalada (Intune)

1. En All Configuración **Computer Configuration (Configuración** de todos **los Configuración** >  Computer), seleccione **Microsoft Edge** y, en el cuadro Buscar, escriba **force-installed (Forzar instalado**), seleccione **force-installed Web Apps (Forzar instalación de Web Apps**) y, a continuación, seleccione **Enabled (Habilitado).**

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="Habilitación de aplicaciones web instaladas por fuerza" lightbox="images/pwa-enable-force-install.png":::

2. En **Direcciones URL para que Web Apps se instalen silenciosamente**, copie y escriba el siguiente fragmento de código para instalar PWA para YouTube, Webex, Zoom y Uber. O vaya al paso siguiente para instalar otras PPA.

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="Escriba la lista de aplicaciones web instaladas por fuerza." lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. Como alternativa, puede crear un fragmento de código JSON a partir de la siguiente sintaxis para instalar otros PWA.

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. En la página Etiquetas de ámbito, seleccione **Siguiente** para omitir.

5. En la página Asignaciones, en **Grupos incluidos**, seleccione **Agregar grupos**.

    :::image type="content" source="images/pwa-add-groups.png" alt-text="Agregar grupos" lightbox="images/pwa-add-groups.png" :::

6. En **Seleccionar grupos que se van a incluir**, escriba el nombre de un grupo que contenga los Surface Hubs de destino, elija **Seleccionar** y, a continuación, haga clic en **Siguiente**. Para obtener más información sobre cómo asignar un perfil de configuración a un grupo, consulte [Agregar grupos para organizar usuarios y dispositivos](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/pwa-select-groups.png" alt-text="Seleccionar grupos" lightbox="images/pwa-select-groups.png":::

7. Revise y seleccione **Crear**.

    :::image type="content" source="images/pwa-create-profile.png" alt-text="Crear perfil" lightbox="images/pwa-create-profile.png" :::

8. Para aplicar immmediately el perfil de configuración, seleccione **DispositivosTodos** >  **los dispositivos** y busque el dispositivo de destino. Abra su panel Información general y seleccione **Sincronizar**.

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="Sincronizar inquilino" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > Para completar la instalación de PPA, vaya a la Surface Hub e inicie Edge. Las PPA se instalan y aparecen en la lista todas las aplicaciones menú Inicio.

 ### <a name="troubleshooting-intune-managed-pwas"></a>Solución de problemas de PPA administradas por Intune
 
Si no ve los PPA enumerados en **Todas las aplicaciones:**

- Asegúrese de que el Surface Hub tiene las actualizaciones más recientes, específicamente [KB5011543](https://support.microsoft.com/help/5011543) (o una actualización de Windows posterior). Para obtener más información sobre las actualizaciones de Windows 10 Team más recientes, consulte [Surface Hub historial de actualizaciones](surface-hub-update-history.md).
- Compruebe que el perfil de configuración se ha aplicado correctamente y que no tiene ningún conflicto con otras opciones de configuración. 
- Compruebe que el perfil de configuración está destinado a un grupo de seguridad que contiene el Surface Hub. 
- No olvide iniciar Edge una sola vez en el Surface Hub, lo que es necesario para que las PPA administradas por Intune se instalen correctamente.

## <a name="install-pwas-via-provisioning-package"></a>Instalación de PWA a través del paquete de aprovisionamiento

Puedes instalar PPA aplicando un paquete de aprovisionamiento a Surface Hubs mediante una unidad USB. Para más información, consulte [Creación de paquetes de aprovisionamiento](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### <a name="get-started-with-provisioning"></a>Comenzar con el aprovisionamiento

1. En un equipo independiente que ejecute Windows 10 o Windows 11, instale [Windows Diseñador de configuración](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) desde el Microsoft Store.

2. En WCD, cree un nuevo Project. Seleccione **Aprovisionar dispositivos de escritorio,** proporcione un nombre para el proyecto y elija **Finalizar.**

3. Seleccione **Cambiar al editor avanzado** y seleccione **Sí** para confirmar.

### <a name="configure-msedgepolicy"></a>Configuración de MSEdgePolicy

1. En el panel Personalizaciones disponibles en WCD, vaya a **\Runtime Configuración\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**

2. En el panel de edición de personalizaciones, escriba el nombre de la aplicación como **MSEdgePolicy** y seleccione **Agregar**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Escriba el nombre de la aplicación como MSEdgePolicy." lightbox="images/pwa-add-edge-policy.png" :::

3. En el panel Personalizaciones disponibles, seleccione **AppName: MSEdgePolicy** y, en el panel de edición, cambie **SettingType** a **Policy** y elija **Agregar**.

4. En el panel Personalizaciones disponibles, seleccione **SettingType: Policy** y, en el panel de edición, establezca **AdmxFileUid** en **MSEdgePolicy** y elija **Agregar**.

5. En el panel Personalizaciones disponibles, seleccione **AdmxFileUid: MSEdgePolicy** y, en el panel de edición, establezca **MSEdgePolicy** escribiendo el código siguiente como una sola línea de texto:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Escriba código para MSEdgePolicy." lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>Configuración de la directiva de Web Apps por fuerza instalada (paquete de aprovisionamiento)

1. En el panel Personalizaciones disponibles en WCD, vaya a: **\Runtime Configuración\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**

2. En el panel de edición personalizaciones, escriba areaname como **MSEdgePolicy~Policy~microsoft_edge y** seleccione **Agregar**.

3. En el panel Personalizaciones disponibles, seleccione **AreaName: MSEdgePolicy~Policy~microsoft_edge** y, en el panel de edición, establezca **Nombre de** directiva en **WebAppInstallForceList** y seleccione **Agregar**.

4. En el panel Personalizaciones disponibles, seleccione **PolicyName: WebAppInstallForceList** y, en el panel de edición de **WebAppInstallForceList**, escriba [PWA código](#ppkg-code-samples) como una sola línea de texto.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Escriba el código para la directiva de Web Apps forzada instalada" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>Ejemplos de código PPKG

- YouTube PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Varios PWA, incluidos YouTube, Webex, Zoom y Uber:

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- Como alternativa, puede crear un fragmento de código JSON a partir de la sintaxis siguiente para instalar otros PWA:

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>Exportación del paquete de aprovisionamiento y aplicación a Surface Hubs

1. En la barra de menús, seleccione **Exportar**, seleccione **Paquete de aprovisionamiento** y siga las indicaciones para generar el archivo .ppkg.

2. Inserte una unidad flash USB vacía. Seleccione la ubicación de salida para ir a la ubicación del paquete. Copie el archivo .ppkg en la unidad USB.

3. Aplique el paquete de aprovisionamiento a través de la aplicación de Configuración o durante la primera ejecución de la instalación. Para más información, consulte [Creación de paquetes de aprovisionamiento](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub).

 ### <a name="troubleshooting-provisioning-package-pwas"></a>Solución de problemas de APROVISIONAMIENTO de paquetes de aprovisionamiento
 
Si no ve los PPA enumerados en **Todas las aplicaciones**:

- Asegúrese de que el Surface Hub tiene las actualizaciones más recientes, específicamente [KB5011543](https://support.microsoft.com/help/5011543) (o una actualización de Windows posterior). Para obtener más información sobre las actualizaciones de Windows 10 Team más recientes, consulte [Surface Hub historial de actualizaciones](surface-hub-update-history.md).

## <a name="learn-more"></a>Obtén más información

- [Referencia de WCD: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Introducción a las aplicaciones web progresivas (PWA)](/microsoft-edge/progressive-web-apps-chromium/)

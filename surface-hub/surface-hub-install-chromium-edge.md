---
title: Instalar y configurar el nuevo Microsoft Edge en Surface Hub
description: Instala y configura el nuevo Microsoft Edge en Surface Hub.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: cf4d909a8c06bddf2bb0b3e42259f0b69cd97109
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894106"
---
# Instalar y configurar el nuevo Microsoft Edge en Surface Hub

Windows 10 Team 2020 Update es compatible con el nuevo Microsoft Edge basado en cromo (versión 85 o superior) como el explorador recomendado para Surface Hub. Puede instalar Microsoft Edge manualmente usando un paquete de aprovisionamiento, de forma remota con Microsoft Intune o su proveedor de administración de dispositivos móviles (MDM) preferido.

 De forma predeterminada, los dispositivos Surface Hub se preinstalan con Microsoft Edge Legacy (versión 44).

> [!IMPORTANT]
> Surface Hub requiere la versión 85 o posterior del nuevo Microsoft Edge, con disponibilidad limitada para el "[canal de desarrollo](https://docs.microsoft.com/deployedge/microsoft-edge-channels)", diseñado para proporcionar a los administradores una visión temprana de la funcionalidad de vanguardia y prepararse para la próxima versión beta.  La compatibilidad con el canal de desarrollo está temporalmente habilitada para que los participantes de Windows Insider obtengan una vista previa de Microsoft Edge. (Normalmente, Surface Hub es compatible con las versiones publicadas en el "canal estable".) Para obtener más información, vea [información general sobre el canal de Microsoft Edge.](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
### Instalando las compilaciones de canal de desarrollo de Microsoft Edge 

- Por su diseño, Microsoft Edge dev Channel se instala en paralelo con Microsoft Edge Legacy, y los usuarios verán tanto "Microsoft Edge dev" (versión 85) como "Microsoft Edge" (versión 44) en el menú Inicio de Surface Hub. Por el contrario, el canal estable de Microsoft Edge reemplazará Microsoft Edge como el explorador predeterminado.
- Una vez instalado, el canal de desarrollo de Microsoft Edge no se mostrará automáticamente como una aplicación anclada. Para abrir, seleccione **iniciar**  >  **todas las aplicaciones**. Por el contrario, el canal estable de Microsoft Edge reemplaza automáticamente Microsoft Edge Legacy como una aplicación anclada en la lista de todas las aplicaciones.
- Una vez que la versión 85 se promocione a un canal estable, el canal de desarrollo de Microsoft Edge desaparecerá automáticamente del menú Inicio y se le solicitará que instale el canal estable de Microsoft Edge en su Surface Hub.

> [!NOTE]
>  Es necesario restablecer el dispositivo para quitar el nuevo Microsoft Edge. Para obtener más información, consulta [restablecer o recuperar un Surface Hub](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) .

## Instalar Microsoft Edge

### Instalar Microsoft Edge con un paquete de aprovisionamiento

1. Desde un equipo PC, descargue el [paquete de aprovisionamiento de Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeDevInstaller. ppkg) en la carpeta raíz de una unidad USB.
2. Inserte la unidad USB en Surface Hub.
3. En Surface Hub, Abra **configuración** y escriba sus credenciales de administrador cuando se le solicite.
4. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, selecciona **Agregar o quitar un paquete de aprovisionamiento**.
5. Selecciona **Agregar un paquete**.
6. Elija el paquete de aprovisionamiento de Microsoft Edge y seleccione **Agregar**.
7. Verá un resumen de los cambios que aplica el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.
8. Espere a que se complete la instalación de Microsoft Edge. Una vez instalado, ve al menú Inicio de Surface hub para acceder al nuevo Microsoft Edge.              
Vale
> [!IMPORTANT]
>  Una vez instalado, el canal de desarrollo de Microsoft Edge no aparecerá automáticamente como una aplicación anclada en el menú Inicio de Surface Hub. En su lugar, los usuarios lo encontrarán en **iniciar**  >  **todas las aplicaciones**. Si está usando el diseño del menú Inicio predeterminado, puede instalar el menú Inicio con el [paquete de aprovisionamiento de Microsoft Edge](https://aka.ms/HubEdge) para agregar Microsoft Edge como una aplicación anclada. Para obtener más información, consulte la siguiente sección: [Mostrar Microsoft Edge en el menú Inicio de Microsoft Edge](#display-start).

> [!NOTE]
> Si hay una versión más reciente de Microsoft Edge disponible, se actualizará automáticamente.
 
### Instalar Microsoft Edge con Intune
 
> [!NOTE]
> El dispositivo Surface Hub se debe inscribir y administrar con Intune. Para obtener más información, consulte [administrar Surface Hub 2s con Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Descargue el instalador de Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal de desarrollo](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elija **Windows 64-bit**
2. [Agregue el instalador de Microsoft Edge como una aplicación de línea de negocio a Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - Si elige usar la actualización de Microsoft Edge para administrar las actualizaciones automáticas de Microsoft Edge, asegúrese de configurar la opción **omitir la versión** de la aplicación en el panel de información de la **aplicación** . Al cambiar este valor a **sí**, Microsoft Intune no aplicará la versión de la aplicación que está instalada en el dispositivo Surface Hub.

 
### Instalar Microsoft Edge con la administración de dispositivos móviles

1. [Descargue el instalador de Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal de desarrollo](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elija **Windows 64-bit**
2. Almacene el instalador de Microsoft Edge en una ubicación hospedada, como un recurso compartido de archivos local (\\server\share\MicrosoftEdgeEnterpriseX64.msi). El dispositivo Surface Hub debe tener permiso para acceder a la ubicación hospedada.
3. Use el [proveedor de servicio de configuración de EnterpriseDesktopAppManagement (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) a través de su proveedor de MDM para instalar Microsoft Edge.

 

## Configurar Microsoft Edge

### Directivas predeterminadas de Microsoft Edge para Surface Hub
Microsoft Edge está preconfigurado con las siguientes directivas para ofrecer una experiencia optimizada para Surface Hub.
 
> [!NOTE]
>  Le recomendamos mantener el valor predeterminado para estas directivas.
 

| Directiva de Microsoft Edge                                                                                                    | Experiencia recomendada                                                                                                                                                                                                                                               | Valor predeterminado |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | No importe automáticamente los tipos de datos y la configuración de Microsoft Edge Legacy. Esto evita cambiar los perfiles de los usuarios que han iniciado sesión con la configuración compartida de Surface Hub.                                                                                                 | cuatro                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir que los procesos de Microsoft Edge se ejecuten en segundo plano incluso después de cerrar la última ventana del explorador, lo que permite un acceso más rápido a las aplicaciones web durante una sesión.                                                                                                      | uno                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | No permita que los usuarios creen nuevos perfiles en Microsoft Edge. Esto simplifica la experiencia de navegación e iniciada.                                                                                                                                                      | ,0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que solo un usuario inicie sesión en Microsoft Edge. Esto simplifica la experiencia de navegación e iniciar sesión                                                                                                                                                                | ,0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite que los usuarios disfruten de un inicio de sesión único (SSO) en Microsoft Edge. Cuando un usuario inicia sesión en Surface Hub, sus credenciales pueden fluir a sitios Web compatibles sin necesidad de volver a autenticar.  | uno                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impide que los usuarios que no sean administradores instalen nuevas extensiones en Microsoft Edge. Para configurar una lista de extensiones que se instalarán de forma predeterminada, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta la primera experiencia de ejecución y la pantalla de presentación que se muestra normalmente cuando los usuarios ejecutan Microsoft Edge por primera vez. Puesto que Surface Hub es un dispositivo compartido, esto simplifica la experiencia del usuario.                                                                      | uno                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deshabilita el modo InPrivate. Como finalizar sesión ya borra los datos de exploración, esto simplifica la experiencia de navegación e iniciada.                                                                                                                                          | uno                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Muestra la experiencia de fuentes de Office 365 en páginas de pestañas nuevas. Cuando un usuario inicia sesión en Surface Hub, permite un acceso rápido a sus archivos y contenido en Office 365.                                                                                                        | uno                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Cuando un usuario ha iniciado sesión en Surface Hub, se creará un perfil no extraíble con su cuenta de la organización. Esto simplifica la experiencia de inicio de sesión único (SSO).                                                                                                 | uno                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deshabilita la impresión en Microsoft Edge. Surface Hub no admite la impresión.                                                                                                                                                                                              | ,0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite a Microsoft Edge autenticar de forma proactiva a los usuarios que han iniciado sesión con los servicios de Microsoft. Esto simplifica la experiencia de inicio de sesión único (SSO).                                                                                                                         | uno                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Guarda automáticamente los archivos en la carpeta descargas, en lugar de preguntar a los usuarios dónde guardar el archivo. Esto simplifica la navegación.                                                                                                                             | ,0                 |

 
### Configurar las directivas de Microsoft Edge

Use [las directivas del explorador Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) para configurar las opciones del explorador en Microsoft Edge. Estas directivas se pueden aplicar con:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Su proveedor de administración de dispositivos móviles (MDM) que admite la recopilación de ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)o
- [Aprovisionar paquetes mediante la recopilación de ADMX en el diseñador de configuración de Windows](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### Configurar actualizaciones de Microsoft Edge

De forma predeterminada, Microsoft Edge se actualiza automáticamente. Use [las directivas de actualización de Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) para configurar las opciones de actualización de Microsoft Edge.
Tenga en cuenta que Surface Hub no es compatible con las siguientes directivas de actualización de Microsoft Edge:

- **Allowsxs** : en Surface Hub, el canal estable de Microsoft Edge siempre reemplaza a Microsoft Edge heredado.
- **CreateDesktopShortcut** : Surface Hub no usa los métodos abreviados de escritorio.

> [!NOTE]
>  Microsoft Edge requiere conectividad a Internet para posibilitar sus funciones. Asegúrese de que se agregan las [direcciones URL de dominio necesarias](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) a la lista de permitidos para garantizar las comunicaciones a través de firewalls y otros mecanismos de seguridad.
 
### <a name="display-start"></a> Mostrar Microsoft Edge en el menú Inicio de Surface Hub

Una vez instalado, el canal de desarrollo de Microsoft Edge no aparecerá automáticamente como una aplicación anclada en el menú Inicio de Surface Hub. En su lugar, los usuarios lo encontrarán en **iniciar**  >  **todas las aplicaciones**.
Si está usando el diseño del menú Inicio predeterminado, puede instalar el menú Inicio con el paquete de aprovisionamiento de Microsoft Edge para agregar Microsoft Edge como una aplicación anclada.
Si desea aplicar un diseño de menú Inicio personalizado, use el siguiente XML para agregar un mosaico anclado a Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge Dev\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Para obtener más información, consulte [configurar el menú Inicio de Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 
> [!NOTE]
> El nuevo Microsoft Edge no admite sitios web anclados ni vínculos con SecondaryTiles.

## Vínculos relacionados

- [Documentación de Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).


---
title: Instalar y configurar el nuevo MicrosoftEdge en SurfaceHub
description: Instala y configura el nuevo Microsoft Edge en Surface Hub.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/08/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 74ae47e80447f89753110c52a49daf649478dd50
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319174"
---
# Instalar y configurar el nuevo MicrosoftEdge en SurfaceHub

Windows 10 Team 2020 Update admite el nuevo Microsoft Edge basado en Chromium (versión 85 y posteriores) como explorador recomendado para Surface Hub 2S y Surface Hub (v1). En este artículo se explica cómo instalar el explorador mediante uno de estos tres métodos: un paquete de aprovisionamiento, Microsoft Intune o un proveedor de administración de dispositivos móviles (MDM) de terceros.

> [!IMPORTANT]
> De forma predeterminada, los dispositivos Surface Hub están preinstalados con Microsoft Edge (versión 44). Después de instalar [la actualización de 2020,](surface-hub-2020-update.md)se recomienda cambiar al nuevo explorador Microsoft Edge; La compatibilidad [con Microsoft Edge (versión heredada)](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) finalizará el 9 de marzo de 2021.

## Instalar Microsoft Edge con un paquete de aprovisionamiento

1. Desde un equipo, descarga el paquete de aprovisionamiento [de Microsoft Edge](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) en la carpeta raíz de una unidad USB.
2. Inserta la unidad USB en Surface Hub.
3. Desde Surface Hub, abre **Configuración** y escribe tus credenciales de administrador cuando se te pida.
4. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, selecciona **Agregar o quitar un paquete de aprovisionamiento**.
5. Selecciona **Agregar un paquete**.
6. Elija el paquete de aprovisionamiento de Microsoft Edge y seleccione **Agregar**.
7. Verás un resumen de los cambios que se aplican al paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.
8. Espere a que se complete la instalación de Microsoft Edge. Una vez instalado, ve al menú Inicio de Surface Hub para acceder al nuevo Microsoft Edge.              

> [!NOTE]
> Si hay disponible una versión más reciente de Microsoft Edge, se actualizará automáticamente.
 
## Instalar Microsoft Edge con Intune
 
> [!NOTE]
> El dispositivo Surface Hub debe inscribirse y administrarse con Intune. Para obtener más información, consulta [Administrar Surface Hub 2S con Microsoft Intune.](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [Descargue el instalador de Microsoft Edge](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elegir **Windows de 64 bits**
2. [Agregue el instalador de Microsoft Edge como una aplicación](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)de línea de negocio a Microsoft Intune.
    - Si decides usar Microsoft Edge Update para controlar las actualizaciones **** automáticas de Microsoft Edge, asegúrate de configurar la opción Omitir versión de la aplicación en el panel de información **de la** aplicación. Al cambiar esta configuración a **Sí,** Microsoft Intune no aplicará la versión de la aplicación instalada en el dispositivo Surface Hub.

## Instalar Microsoft Edge con un proveedor de MDM de terceros

1. [Descargue el instalador de Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elegir **Windows de 64 bits**
2. Organizar el instalador de Microsoft Edge en una ubicación hospedada, como un recurso compartido de archivos local (\\server\share\MicrosoftEdgeEnterpriseX64.msi). El dispositivo Surface Hub debe tener permiso para acceder a la ubicación hospedada.
3. Usa [enterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) a través de tu proveedor de MDM para instalar Microsoft Edge.

## Configurar Microsoft Edge

### Directivas predeterminadas de Microsoft Edge para Surface Hub

Microsoft Edge está preconfigurado con las siguientes configuraciones de directiva para proporcionar una experiencia optimizada para Surface Hub.
 
> [!TIP]
> Se recomienda conservar el valor predeterminado para esta configuración de directiva.
 

| Configuración de directiva                                                                                                   | Experiencia recomendada                                                                                                                                                                                                                                               | Valor predeterminado |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | No importe automáticamente los tipos de datos y la configuración de Microsoft Edge (versión heredada). Esto evita cambiar los perfiles de los usuarios que han iniciado sesión con la configuración compartida desde Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permite que los procesos de Microsoft Edge sigan ejecutándose en segundo plano incluso después de cerrar la última ventana del explorador, lo que permite un acceso más rápido a las aplicaciones web durante una sesión.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | No permita que los usuarios creen nuevos perfiles en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que solo un usuario inicie sesión en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite a los usuarios disfrutar de Sign-On único (SSO) en Microsoft Edge. Cuando un usuario ha iniciado sesión en Surface Hub, sus credenciales pueden fluir a los sitios web compatibles sin tener que volver a autenticarse.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impide que los usuarios que no son administradores instalen nuevas extensiones en Microsoft Edge. Para configurar una lista de extensiones que se instalarán de forma predeterminada, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta la primera experiencia de ejecución y la pantalla de presentación que normalmente se muestra cuando los usuarios ejecutan Microsoft Edge por primera vez. Dado que Surface Hub es un dispositivo compartido, esto simplifica la experiencia del usuario.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deshabilita el modo InPrivate. Dado que Finalizar sesión ya borra los datos de exploración, esto simplifica la experiencia de exploración y de inicio de sesión.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Muestra la experiencia de fuente de Office 365 en páginas de pestañas nuevas. Cuando un usuario ha iniciado sesión en Surface Hub, esto permite un acceso rápido a sus archivos y contenido en Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Cuando un usuario ha iniciado sesión en Surface Hub, se creará un perfil no extraíble con su cuenta organizativa. Esto simplifica la experiencia de Sign-On de inicio de sesión único (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deshabilita la impresión en Microsoft Edge. Surface Hub no admite la impresión.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite que Microsoft Edge autentique de forma proactiva a los usuarios que han iniciado sesión con los servicios Microsoft. Esto simplifica la experiencia de Sign-On de inicio de sesión único (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Guarda automáticamente los archivos en la carpeta Descargas, en lugar de preguntar a los usuarios dónde guardar el archivo. Esto simplifica la experiencia de exploración.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Actualmente, las aplicaciones web progresivas (PDA) implementables no se admiten en el sistema operativo Windows 10 Team.  Ten en cuenta también que la configuración de directiva de Microsoft Edge [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) no es compatible con Surface Hub. 

### Configurar las opciones de directiva de Microsoft Edge

Use [directivas de explorador de Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policies) para configurar la configuración del explorador en Microsoft Edge. Estas directivas se pueden aplicar mediante:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [El proveedor de administración de dispositivos móviles (MDM) preferido que admite la ingesta de ADMX](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)o
- [Aprovisionar paquetes con ingesta admx en el Diseñador de configuraciones de Windows.](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)

 
### Configurar las actualizaciones de Microsoft Edge

De forma predeterminada, Microsoft Edge se actualiza automáticamente. Usa [las directivas de actualización de Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) para configurar las opciones de Microsoft Edge Update.
Ten en cuenta que Surface Hub no admite las siguientes directivas de actualización de Microsoft Edge:

- **Allowsxs:** en Surface Hub, el canal estable de Microsoft Edge siempre reemplaza a Microsoft Edge (versión heredada).
- **CreateDesktopShortcut:** Surface Hub no usa accesos directos de escritorio.

> [!NOTE]
>  Microsoft Edge requiere conectividad a Internet para posibilitar sus funciones. Asegúrese de que las [direcciones URL de dominio necesarias](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) se agregan a la lista de permitidos para garantizar las comunicaciones a través de firewalls y otros mecanismos de seguridad.
 
### Mostrar Microsoft Edge en el menú Inicio de Surface Hub

Si usas el diseño predeterminado del menú Inicio, puedes instalar el menú Inicio con el paquete de aprovisionamiento de Microsoft Edge para agregar Microsoft Edge como aplicación anclada.
Si quieres aplicar un diseño de menú Inicio personalizado, usa el siguiente XML para agregar un icono anclado para Microsoft Edge.

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

Para obtener más información, consulta [Configurar el menú Inicio de Surface Hub.](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)
 
> [!NOTE]
> El nuevo Microsoft Edge no admite sitios web anclados.

## Vínculos relacionados

- [Documentación de Microsoft Edge](https://docs.microsoft.com/microsoft-edge/).


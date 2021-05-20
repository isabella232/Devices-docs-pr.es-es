---
title: Instalar y configurar el nuevo Microsoft Edge en Surface Hub
description: Instale y configure el nuevo Microsoft Edge en Surface Hub.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576730"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>Instalar y configurar el nuevo Microsoft Edge en Surface Hub

Windows 10 Team 2020 Update admite el nuevo Microsoft Edge basado en Chromium (versión 85 y versiones posteriores) como explorador recomendado para Surface Hub 2S y Surface Hub (v1). En este artículo se explica cómo instalar el explorador mediante uno de tres métodos: un paquete de aprovisionamiento, Microsoft Intune proveedor de administración de dispositivos móviles (MDM) de terceros.

> [!IMPORTANT]
> De forma predeterminada, Surface Hub dispositivos están preinstalados con Microsoft Edge (versión anterior) (versión 44). Después de instalar [la actualización de 2020,](surface-hub-2020-update.md)se recomienda cambiar al nuevo explorador Microsoft Edge actualización; la compatibilidad [Microsoft Edge (versión anterior)](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) finalizará el 9 de marzo de 2021.

> [!NOTE]
> El gesto de deslizar el dedo hacia abajo desde la parte superior de la pantalla para salir del modo de pantalla completa requiere dos dedos con el nuevo Microsoft Edge. La acción salir de pantalla completa también está disponible en el menú contextual que se muestra después de presionar durante mucho tiempo.


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>Instalar Microsoft Edge mediante un paquete de aprovisionamiento

1. Desde un equipo, descargue el Microsoft Edge [de aprovisionamiento](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) en la carpeta raíz de una unidad USB.
2. Inserte la unidad USB en Surface Hub.
3. Desde Surface Hub, abra **Configuración** y escriba sus credenciales de administrador cuando se le pida.
4. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, selecciona **Agregar o quitar un paquete de aprovisionamiento**.
5. Selecciona **Agregar un paquete**.
6. Elija el paquete Microsoft Edge de aprovisionamiento y seleccione **Agregar**.
7. Verá un resumen de los cambios que aplica el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.
8. Espere a que se complete Microsoft Edge instalación. Una vez instalado, vaya al menú Surface Hub inicio para obtener acceso a la nueva Microsoft Edge.              

> [!NOTE]
> Si hay una versión más reciente de Microsoft Edge disponible, se actualizará automáticamente.
 
## <a name="install-microsoft-edge-using-intune"></a>Instalar Microsoft Edge con Intune
 
> [!NOTE]
> Para usar este método de instalación, el Surface Hub debe inscribirse y administrarse con Intune. Para obtener más información, [consulta Administrar Surface Hub 2S con MDM](manage-settings-with-mdm-for-surface-hub.md).
 

1. [Descargue el Microsoft Edge de instalación](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elegir **Windows de 64 bits**
2. [Agregue el Microsoft Edge de instalación como una aplicación de línea de negocio](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)a Microsoft Intune .
    - Si eliges usar Microsoft Edge Update para controlar las actualizaciones automáticas de Microsoft Edge, **** asegúrate de configurar la configuración de la versión de la aplicación Omitir el panel información **de la** aplicación. Al cambiar esta configuración a **Sí**, Microsoft Intune aplicará la versión de la aplicación que está instalada en el Surface Hub dispositivo.

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>Instalar Microsoft Edge con un proveedor MDM de terceros

1. [Descargue el instalador Microsoft Edge de Microsoft](https://www.microsoft.com/edge/business/download).
    - Usar la versión actual del [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(versión 85)**
    - Elegir **Windows de 64 bits**
2. El instalador Microsoft Edge en una ubicación hospedada, como un recurso compartido de archivos local (\\server\share\MicrosoftEdgeEnterpriseX64.msi). El Surface Hub dispositivo debe tener permiso para tener acceso a la ubicación hospedada.
3. Usa [EnterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) a través de tu proveedor MDM para instalar Microsoft Edge.

## <a name="configure-microsoft-edge"></a>Configurar Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>Directivas Microsoft Edge predeterminadas para Surface Hub

Microsoft Edge está preconfigurado con los siguientes conjuntos de directivas para proporcionar una experiencia optimizada para Surface Hub.
 
> [!TIP]
> Se recomienda conservar el valor predeterminado para esta configuración de directiva.
 

| Configuración de directiva                                                                                                   | Experiencia recomendada                                                                                                                                                                                                                                               | Valor predeterminado |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | No importe automáticamente los tipos de datos y la configuración de Microsoft Edge (versión anterior). Esto evita cambiar los perfiles de los usuarios que han iniciado sesión con la configuración compartida de la Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir Microsoft Edge los procesos para seguir ejecutándose en segundo plano incluso después de que se cierre la última ventana del explorador, lo que permite un acceso más rápido a las aplicaciones web durante una sesión.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | No permitir que los usuarios creen nuevos perfiles en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que solo un usuario inicie sesión en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Permite a los usuarios disfrutar de single Sign-On (SSO) en Microsoft Edge. Cuando un usuario ha iniciado sesión Surface Hub, sus credenciales pueden fluir a los sitios web compatibles sin necesidad de que se vuelvan a autenticar.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impide que los usuarios que no son administradores instalen nuevas extensiones en Microsoft Edge. Para configurar una lista de extensiones que se instalarán de forma predeterminada, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta la primera experiencia de ejecución y la pantalla de presentación que normalmente se muestra cuando los usuarios ejecutan Microsoft Edge por primera vez. Dado Surface Hub es un dispositivo compartido, esto simplifica la experiencia del usuario.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deshabilita el modo InPrivate. Dado que End Session ya borra los datos de exploración, esto simplifica la experiencia de exploración y de inicio de sesión.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Muestra la Office 365 de fuentes en páginas de pestañas nuevas. Cuando un usuario ha iniciado sesión Surface Hub, esto permite un acceso rápido a sus archivos y contenido en Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Cuando un usuario ha iniciado sesión Surface Hub, se creará un perfil no extraíble con su cuenta organizativa. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Deshabilita la impresión en Microsoft Edge. Surface Hub no admite la impresión.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite Microsoft Edge autenticación proactiva de usuarios que han iniciado sesión con servicios Microsoft. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Guarda automáticamente los archivos en la carpeta Descargas, en lugar de preguntar a los usuarios dónde guardar el archivo. Esto simplifica la experiencia de exploración.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Actualmente, las aplicaciones web progresivas (PWA) no se admiten en el Windows 10 Team operativo.  Tenga en cuenta también que Microsoft Edge configuración de directiva [webAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) no se admite en Surface Hub. 

### <a name="configure-microsoft-edge-policy-settings"></a>Configurar Microsoft Edge de directiva

Use [Microsoft Edge de explorador para](https://docs.microsoft.com/deployedge/microsoft-edge-policies) configurar la configuración del explorador en Microsoft Edge. Estas directivas se pueden aplicar mediante:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [El proveedor de administración de dispositivos móviles (MDM)](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)preferido que admite la ingesta de ADMX o
- [Aprovisionar paquetes con admx ingestion en Windows de configuración](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### <a name="configure-microsoft-edge-updates"></a>Configurar Microsoft Edge actualizaciones

De forma predeterminada, Microsoft Edge se actualiza automáticamente. Use [Microsoft Edge de actualización para](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) configurar la configuración de Microsoft Edge Update.
Tenga en cuenta que Surface Hub no admite las siguientes directivas Microsoft Edge actualización:

- **Allowsxs:** al Surface Hub, Microsoft Edge de canal estable siempre reemplaza Microsoft Edge (versión anterior).
- **CreateDesktopShortcut:** Surface Hub no usa métodos abreviados de escritorio.

> [!TIP]
>  Microsoft Edge requiere conectividad a Internet para posibilitar sus funciones. Asegúrese de que las [direcciones URL de](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) dominio necesarias se agregan a la lista Permitir para garantizar las comunicaciones a través de firewalls y otros mecanismos de seguridad.

## <a name="related-links"></a>Vínculos relacionados

- [Documentación de Microsoft Edge](https://docs.microsoft.com/microsoft-edge/)


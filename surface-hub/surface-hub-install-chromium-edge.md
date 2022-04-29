---
title: Administrar Microsoft Edge en Surface Hub
description: En este artículo se describen las herramientas y la configuración de directivas de Microsoft Edge predeterminadas para configurar la configuración del explorador.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497733"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Administrar Microsoft Edge en Surface Hub

Use [Microsoft Edge directivas de explorador](/deployedge/microsoft-edge-policies) para configurar la configuración del explorador en Microsoft Edge a través de cualquiera de los métodos siguientes:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Su proveedor de mobile Administración de dispositivos (MDM) preferido que admite la ingesta de ADMX](/deployedge/configure-edge-with-mdm)
- [Aprovisionamiento de paquetes mediante la ingesta de ADMX en Windows Diseñador de configuración](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> El deslizamiento hacia abajo desde la parte superior de la pantalla gesto para salir del modo de pantalla completa requiere dos dedos con el nuevo Microsoft Edge. La acción salir a pantalla completa también está disponible en el menú contextual que se muestra después de pulsar durante mucho tiempo.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Directivas de Microsoft Edge predeterminadas para Surface Hub

Microsoft Edge está preconfigurado con las siguientes configuraciones de directivas para proporcionar una experiencia optimizada para Surface Hub.


> [!TIP]
> Se recomienda conservar el valor predeterminado para esta configuración de directiva.

| Configuración de directiva                                                                                                   | Experiencia recomendada                                                                                                                                                                                                                                               | Valor predeterminado |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | No importe automáticamente los tipos de datos y la configuración de Microsoft Edge (versión anterior). Esto evita cambiar los perfiles de los usuarios que han iniciado sesión con la configuración compartida de la Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir que Microsoft Edge procesos sigan ejecutándose en segundo plano incluso después de cerrar la última ventana del explorador, lo que permite un acceso más rápido a las aplicaciones web durante una sesión.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | No permita que los usuarios creen perfiles nuevos en Microsoft Edge. Esto simplifica la experiencia de exploración e inicio de sesión.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que solo un usuario inicie sesión en Microsoft Edge. Esto simplifica la experiencia de exploración e inicio de sesión                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Permite a los usuarios disfrutar de single Sign-On (SSO) en Microsoft Edge. Cuando un usuario inicia sesión en Surface Hub, sus credenciales pueden fluir a sitios web admitidos sin necesidad de volver a autenticarse.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impide que los usuarios que no son administradores instalen nuevas extensiones en Microsoft Edge. Para configurar una lista de extensiones que se instalarán de forma predeterminada, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta la primera experiencia de ejecución y la pantalla de presentación que se muestra normalmente cuando los usuarios ejecutan Microsoft Edge por primera vez. Dado que Surface Hub es un dispositivo compartido, esto simplifica la experiencia del usuario.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deshabilita el modo InPrivate. Puesto que La sesión final ya borra los datos de exploración, esto simplifica la experiencia de exploración e inicio de sesión.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Muestra la experiencia de fuente de Office 365 en las nuevas páginas de pestaña. Cuando un usuario inicia sesión en Surface Hub, esto permite un acceso rápido a sus archivos y contenido en Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Cuando un usuario inicia sesión en Surface Hub, se creará un perfil no extraíble mediante su cuenta de organización. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Deshabilita la impresión en Microsoft Edge. Surface Hub no admite la impresión.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite que Microsoft Edge autentique de forma proactiva a los usuarios que han iniciado sesión con servicios Microsoft. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Guarda automáticamente los archivos en la carpeta Descargas, en lugar de preguntar a los usuarios dónde guardar el archivo. Esto simplifica la experiencia de exploración.                                                                                                                             | 0                 |

> [!TIP]
> Las aplicaciones web progresivas (PPA) que se pueden implementar ahora se admiten en el sistema operativo Windows 10 Team. Para más información, consulte [Instalación de Web Apps progresiva en Surface Hub](install-pwa-surface-hub.md). 

### <a name="configure-microsoft-edge-updates"></a>Configuración de actualizaciones de Microsoft Edge

De forma predeterminada, Microsoft Edge se actualiza automáticamente. Use [Microsoft Edge directivas de actualización](/deployedge/microsoft-edge-update-policies) para configurar los valores de Microsoft Edge Update. Tenga en cuenta que Surface Hub no admite la configuración de directiva **CreateDesktopShortcut**, ya que Surface Hub no usa accesos directos de escritorio.

> [!TIP]
> Microsoft Edge requiere conectividad a Internet para posibilitar sus funciones. Agregue las [direcciones URL de dominio necesarias](/deployedge/microsoft-edge-security-endpoints) a la lista Permitir para garantizar las comunicaciones a través de firewalls y otros mecanismos de seguridad.

## <a name="related-links"></a>Vínculos relacionados

- [Documentación de Microsoft Edge](/microsoft-edge/)
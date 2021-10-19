---
title: Administrar Microsoft Edge en Surface Hub
description: En este artículo se describen las Microsoft Edge y las herramientas de directiva predeterminadas para configurar la configuración del explorador.
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
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100718"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>Administrar Microsoft Edge en Surface Hub

Use [Microsoft Edge de explorador para](/deployedge/microsoft-edge-policies) configurar la configuración del explorador Microsoft Edge a través de cualquiera de los siguientes métodos:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [El proveedor de administración de dispositivos móviles (MDM) preferido que admite la ingesta de ADMX](/deployedge/configure-edge-with-mdm)
- [Aprovisionar paquetes con admx ingestion en Windows Configuration Designer](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> El gesto de deslizar el dedo hacia abajo desde la parte superior de la pantalla para salir del modo de pantalla completa requiere dos dedos con el nuevo Microsoft Edge. La acción salir de pantalla completa también está disponible en el menú contextual que se muestra después de presionar durante mucho tiempo.

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Directivas Microsoft Edge predeterminadas para Surface Hub

Microsoft Edge está preconfigurado con los siguientes conjuntos de directivas para proporcionar una experiencia optimizada para Surface Hub.


> [!TIP]
> Se recomienda conservar el valor predeterminado para esta configuración de directiva.

| Configuración de directiva                                                                                                   | Experiencia recomendada                                                                                                                                                                                                                                               | Valor predeterminado |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | No importe automáticamente los tipos de datos y la configuración de Microsoft Edge (versión anterior). Esto evita cambiar los perfiles de los usuarios que han iniciado sesión con la configuración compartida de la Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Permitir Microsoft Edge los procesos para seguir ejecutándose en segundo plano incluso después de que se cierre la última ventana del explorador, lo que permite un acceso más rápido a las aplicaciones web durante una sesión.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | No permitir que los usuarios creen nuevos perfiles en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Permite que solo un usuario inicie sesión en Microsoft Edge. Esto simplifica la experiencia de exploración y de sesión                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Permite a los usuarios disfrutar de single Sign-On (SSO) en Microsoft Edge. Cuando un usuario ha iniciado sesión Surface Hub, sus credenciales pueden fluir a los sitios web compatibles sin necesidad de que se vuelvan a autenticar.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Impide que los usuarios que no son administradores instalen nuevas extensiones en Microsoft Edge. Para configurar una lista de extensiones que se instalarán de forma predeterminada, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Oculta la primera experiencia de ejecución y la pantalla de presentación que normalmente se muestra cuando los usuarios ejecutan Microsoft Edge por primera vez. Dado Surface Hub es un dispositivo compartido, esto simplifica la experiencia del usuario.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Deshabilita el modo InPrivate. Dado que End Session ya borra los datos de exploración, esto simplifica la experiencia de exploración y de inicio de sesión.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Muestra la Office 365 de fuentes en páginas de pestañas nuevas. Cuando un usuario ha iniciado sesión Surface Hub, esto permite un acceso rápido a sus archivos y contenido en Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | Cuando un usuario ha iniciado sesión Surface Hub, se creará un perfil no extraíble con su cuenta organizativa. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Deshabilita la impresión en Microsoft Edge. Surface Hub no admite la impresión.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Permite Microsoft Edge autenticación proactiva de usuarios que han iniciado sesión con servicios Microsoft. Esto simplifica la experiencia de single Sign-On (SSO).                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Guarda automáticamente los archivos en la carpeta Descargas, en lugar de preguntar a los usuarios dónde guardar el archivo. Esto simplifica la experiencia de exploración.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Actualmente, las aplicaciones web progresivas (PWA) no se admiten en el Windows 10 Team operativo.  Tenga en cuenta también que Microsoft Edge configuración de directiva [webAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist) no se admite en Surface Hub.

### <a name="configure-microsoft-edge-updates"></a>Configurar Microsoft Edge actualizaciones

De forma predeterminada, Microsoft Edge se actualiza automáticamente. Use [Microsoft Edge de actualización para](/deployedge/microsoft-edge-update-policies) configurar la configuración de Microsoft Edge Update. Tenga en cuenta que Surface Hub no admite la configuración de directiva **CreateDesktopShortcut,** ya que Surface Hub no usa métodos abreviados de escritorio.

> [!TIP]
> Microsoft Edge requiere conectividad a Internet para posibilitar sus funciones. Agregue las [direcciones URL de dominio necesarias](/deployedge/microsoft-edge-security-endpoints) a la lista Permitir para garantizar las comunicaciones a través de firewalls y otros mecanismos de seguridad.

## <a name="related-links"></a>Vínculos relacionados

- [Documentación de Microsoft Edge](/microsoft-edge/)
---
title: Administrar Microsoft Surface Hub
description: Cómo administrar Surface Hub tras finalizar el programa de primera ejecución.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: administrar Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 5e7fca007549d8804a756ef2a042f092f0acb1c3
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387437"
---
# <a name="manage-microsoft-surface-hub"></a>Administrar Microsoft Surface Hub

Después de la configuración inicial de Microsoft Surface Hub, la configuración y la configuración del dispositivo se pueden modificar o cambiar de un par de maneras:

- **Administración local** - Cada Surface Hub se puede configurar localmente con la aplicación **Configuración** en el dispositivo. Para impedir que usuarios no autorizados cambien la configuración, la aplicación Configuración requiere credenciales de administrador para abrir la aplicación. Para obtener más información, consulta [Administración local para la configuración de Surface Hub](local-management-surface-hub-settings.md).
- **Administración remota:** Surface Hub permite a los administradores de TI administrar la configuración y las directivas con un proveedor de administración de dispositivos móviles (MDM), como Microsoft Intune, Microsoft Endpoint Configuration Manager y otros proveedores de terceros. Además, los administradores pueden supervisar Surface Hubs con Azure Monitor.  Para obtener más información, consulta Administrar [la configuración con](manage-settings-with-mdm-for-surface-hub.md)un proveedor MDM y Supervisar Surface [Hubs con Azure Monitor para realizar un seguimiento de su estado.](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs) 

> [!NOTE]
> Estos métodos de administración no son mutuamente excluyentes. Los dispositivos pueden administrarse tanto local como remotamente, si así lo eliges. Sin embargo, las directivas y la configuración de MDM sobrescribirán los cambios locales cuando Surface Hub se sincronice con el servidor de administración. 

## <a name="in-this-section"></a>En esta sección

Obtén información sobre cómo administrar y actualizar Surface Hub.

| Tema | Descripción |
| ----- | ----------- |
| [Administración remota de Surface Hub](remote-surface-hub-management.md) |Temas relacionados con la administración remota del Surface Hub. Incluye instalar aplicaciones, administrar la configuración con MDM y supervisar con Operations Management Suite. |
| [Administrar la configuración de Surface Hub](manage-surface-hub-settings.md) |Temas relacionados con la administración de la configuración de Surface Hub: accesibilidad, cuenta del dispositivo, restablecimiento del dispositivo, nombre de dominio completo, configuración de Windows Update y red inalámbrica |
| [Instalar aplicaciones en Surface Hub]( https://technet.microsoft.com/itpro/surface-hub/install-apps-on-surface-hub) | Los administradores pueden instalar aplicaciones desde Microsoft Store o la Microsoft Store para Empresas.|
[Configurar el menú Inicio de Surface Hub](surface-hub-start-menu.md) | Usar MDM para personalizar el menú Inicio para Surface Hub.
| [Configurar y usar Microsoft Whiteboard](whiteboard-collaboration.md)  | La actualización más reciente de Microsoft Whiteboard incluye la capacidad para que dos dispositivos Surface Hub colaboren en tiempo real en la misma pizarra.   |
| [Finalizar una reunión con Terminar la sesión](https://technet.microsoft.com/itpro/surface-hub/finishing-your-surface-hub-meeting) | Al final de una reunión, los usuarios pueden presionar **Terminar la sesión** para limpiar los datos confidenciales y preparar el dispositivo para la próxima reunión.|
| [Iniciar sesión en Surface Hub con Microsoft Authenticator](surface-hub-authenticator-app.md) | Puedes iniciar sesión en un dispositivo Surface Hub sin una contraseña con la aplicación Microsoft Authenticator, disponible en Android e iOS.   |
| [Guardar la clave de BitLocker](https://technet.microsoft.com/itpro/surface-hub/save-bitlocker-key-surface-hub) | Todos los Surface Hubs se configuran automáticamente con el software de cifrado de unidad de BitLocker. Microsoft recomienda encarecidamente que te asegures de hacer una copia de seguridad de las claves de recuperación de BitLocker.|
| [Conectarse a otros dispositivos y mostrar su contenido con Surface Hub](https://technet.microsoft.com/itpro/surface-hub/connect-and-display-with-surface-hub) | Puedes conectar otro dispositivo a tu Surface Hub para mostrar su contenido.|
| [Miracast en la red inalámbrica o LAN existente](miracast-over-infrastructure.md) | Puedes usar Miracast en tu red inalámbrica o LAN para conectarte a Surface Hub. |
 [Habilitar la autenticación por cable 802.1X](enable-8021x-wired-authentication.md) | Se han habilitado políticas MDM de autenticación por cable 802.1x en dispositivos de Surface Hub. 
| [Uso de un sistema de control de sala](https://technet.microsoft.com/itpro/surface-hub/use-room-control-system-with-surface-hub) | Los sistemas de control de la sala se pueden usar con tu Microsoft Surface Hub.|
[Uso de la herramienta de recuperación de Surface Hub](surface-hub-recovery-tool.md) | Usa la Herramienta de recuperación de Surface Hub para volver a crear una imagen de la SSD de Surface Hub.
[Reemplazo de SSD de Surface Hub](surface-hub-ssd-replacement.md) | Aprende a quitar y reemplazar la unidad de estado sólido en tu Surface Hub.

## <a name="related-topics"></a>Temas relacionados

- [Ver modo de presentación de Power BI en Surface Hub y Windows 10](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)

---
title: Salas de Microsoft Teams en Surface Hub
description: En este artículo se proporciona información general Salas de Microsoft Teams sobre Surface Hub.
keywords: Salas de Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d607a34b532420123941a77d510d19db65531c85
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448733"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Salas de Microsoft Teams en Surface Hub

Salas de Teams para Surface Hub reemplazó automáticamente la aplicación [Surface Hub Teams](hub-teams-app.md) anterior tras la instalación de [KB5004196, KB5004198 y KB5004199](surface-hub-update-history.md).

## <a name="whats-new"></a>Novedades

- Las reuniones unidas desde la Surface Hub de bienvenida o la nueva página Agenda se unen a "Borde a borde" para poner a los usuarios en primer plano.
- Características de reunión conocidas, como burbujas de chat, reacciones, uso compartido de aplicaciones y escritorio, control y audio, soporte PowerPoint en directo, modo conjunto y galería grande.
- Salas de Teams en Surface Hub pueden ejecutarse en paralelo con otras aplicaciones o ejecutarse minimizadas.
- Los administradores pueden configurar características como reunión coordinada y unión de proximidad para Surface Hub. [Los archivos XML](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) son compatibles y se migrarán al nuevo modelo de configuración.
- Nuevas opciones de QoS y requisitos de red. Para obtener más información, vea [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- Si aún no es el valor predeterminado, Teams puede establecerse como la aplicación predeterminada para reuniones y llamadas en **Configuración** >  **Surface Hub** >  **Calling & audio**. Para obtener más información sobre los modos de reunión y configurarlos a través de la directiva MDM, [consulta Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls).

## <a name="in-meeting-experience"></a>En la experiencia de reunión

Salas de Teams en Surface Hub de reuniones está alineada con la experiencia familiar que los usuarios conocen desde sus dispositivos personales con los ajustes realizados para optimizar un dispositivo de pantalla grande. La Teams en Surface Hub permite a los usuarios acceder a características clave, como unirse a una reunión con un solo toque, Reunirse ahora y Panel de marcado para llamadas RTC o punto a punto.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Salas de Teams en Surface Hub Agenda.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Salas de Teams en Surface Hub meeting.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>Administrar Salas de Teams en Surface Hub

 Puede personalizar la experiencia de Teams directamente desde el menú Configuración después de escribir credenciales administrativas, incluidas:

- Configurar [reuniones coordinadas](/microsoftteams/rooms/coordinated-meetings) y unión de proximidad.
- Ajusta la configuración de micrófonos, cámaras y altavoces predeterminados.
- Compruebe la versión del cliente y busque las actualizaciones más recientes.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Salas de Teams Configuración.":::

La nueva Salas de Teams para Surface Hub cliente, aplicará automáticamente la configuración existente configurada a través de archivos XML, paquetes de aprovisionamiento o un proveedor MDM. Estos métodos, explicados en Administrar la configuración de [Microsoft Teams en Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), se reemplazarán por nuevas soluciones basadas en la nube, como se describe a continuación en [Administración](#simplified-management-of-teams-coming-to-surface-hub) simplificada de Teams próximamente Surface Hub.

### <a name="prepare-networking-for-teams-rooms"></a>Preparar las redes para Salas de Teams

Para optimizar Salas de Teams los requisitos y recomendaciones descritos en [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>Administración simplificada de Teams a Surface Hub

Cuando Salas de Teams para Surface Hub se publicó públicamente a finales de este año, los administradores pueden aprovechar las siguientes soluciones:

- **Teams de administración.** Teams Admin Center proporciona una plataforma de autoadministrador completa para supervisar y administrar la experiencia Salas de Teams en Teams dispositivos. Teams centro de administración estará disponible para Salas de Microsoft Teams usuarios sin costo adicional.
- **Salas de Microsoft Teams servicio administrado.** El [servicio administrado](/microsoftteams/rooms/microsoft-teams-rooms-premium) Salas de Microsoft Teams es un servicio de supervisión y administración de TI basado en la nube que mantiene los dispositivos Salas de Microsoft Teams y sus periféricos actualizados y supervisados proactivamente, lo que admite un entorno optimizado para una gran experiencia del usuario.


## <a name="support-for-teams-rooms-in-government-community-cloud-high-gcc-h"></a>Compatibilidad con Salas de Teams en Government Community Cloud High (GCC-H)

Se necesita una actualización manual única del cliente de Salas de Teams a la versión 1.4.00.25354 para que pueda conectarse a un inquilino de GCC-H y, a continuación, mantenerse actualizado automáticamente:

 - Confirme que el concentrador tiene kb5005611 o una actualización acumulativa Windows posterior instalada
 - Usar [Teams_Uninstall_win32.ppkg para](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg) quitar el Salas de Teams actual en Surface Hub versión
 - Reiniciar el dispositivo
 - Instalar [Teams_win32.ppkg para](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg) instalar la versión 1.4.00.25354
 - Reiniciar el dispositivo de nuevo

Pasos detallados:

1. Guarda ambos paquetes de aprovisionamiento en la raíz de la unidad USB.
2.  Inserte la unidad USB en el Surface Hub.
3.  En el Surface Hub, abra el menú Inicio, seleccione Todas las aplicaciones y, a continuación, seleccione Configuración.
4.  Proporcione sus credenciales de administrador del concentrador cuando se le pida.
5.  Vaya a **Surface Hub** >  **DispositivoAgregue** >  **o quite un paquete de aprovisionamiento** y, a continuación, **seleccione Agregar un paquete**.
6.  En **Seleccionar un paquete**, seleccione el paquete de aprovisionamiento Teams_Uninstall_win32.ppkg y, a continuación, reinicie el Surface Hub.
7.  En el Surface Hub, abra el menú Inicio, seleccione Todas las aplicaciones y, a continuación, seleccione Configuración.
8.  Proporcione sus credenciales de administrador del concentrador cuando se le pida.
9.  Vaya a **Surface Hub** >  **DispositivoAgregue** >  **o quite un paquete de aprovisionamiento** y, a continuación, **seleccione Agregar un paquete**.
10. En **Seleccionar un paquete**, seleccione el paquete de aprovisionamiento Teams_win32.ppkg y, a continuación, reinicie el Surface Hub.

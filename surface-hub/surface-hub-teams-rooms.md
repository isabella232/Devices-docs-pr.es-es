---
title: Salas de Microsoft Teams en Surface Hub
description: En este artículo se proporciona información general sobre Salas de Microsoft Teams en Surface Hub.
keywords: Salas de Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 2d8bd08c150c1665365ae21bc87fd3485b8c69a8
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "11910008"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Salas de Microsoft Teams en Surface Hub

Salas de Teams para Surface Hub reemplazará automáticamente la aplicación [](hub-teams-app.md) de Surface Hub Teams actual como parte de un lanzamiento global de 4 semanas a partir del 23 de septiembre. Para obtener una demostración de la nueva experiencia Teams, disponible actualmente como una vista previa a través del programa Windows Insider, vea [Introducing Salas de Teams on Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373).

## <a name="whats-new"></a>Novedades

- Las reuniones unidas desde la Surface Hub de bienvenida o la página Nueva agenda se unen a "Borde a borde" para poner a los usuarios en primer plano.
- Características de reunión conocidas, como burbujas de chat, reacciones, uso compartido de aplicaciones y escritorio, control y audio, soporte PowerPoint en directo, modo conjunto y galería grande.
- Salas de Teams en Surface Hub puede ejecutarse en paralelo con otras aplicaciones o ejecutarse minimizado.
- Los administradores pueden configurar características como reunión coordinada y unión de proximidad para Surface Hub. [Los archivos XML](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) son compatibles y se migrarán al nuevo modelo de configuración.
- Nuevas opciones de QoS y requisitos de red. Para obtener más información, vea [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- Cambia al Teams, reemplazando Skype Empresarial como la aplicación predeterminada de colaboración y reunión. Para obtener más información, vea [Deploy Microsoft Teams for Surface Hub](/MicrosoftTeams/teams-surface-hub).

## <a name="in-meeting-experience"></a>En la experiencia de reunión

Salas de Teams en Surface Hub de reuniones está alineada con la experiencia familiar que los usuarios conocen desde sus dispositivos personales con los ajustes realizados para optimizar un dispositivo de pantalla grande. La Teams en Surface Hub permite a los usuarios acceder a características clave, como unirse a una reunión con un solo toque, Reunirse ahora y Panel de marcado para llamadas RTC o punto a punto.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Salas de Teams en Surface Hub Agenda.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Salas de Teams en Surface Hub reunión.":::

## <a name="manage-teams-rooms-on-surface-hub"></a>Administrar Salas de Teams en Surface Hub

 Puede personalizar la experiencia de Teams directamente desde el menú Configuración después de escribir las credenciales administrativas, incluidas:

- Configurar [reuniones coordinadas](/microsoftteams/rooms/coordinated-meetings) y unión de proximidad.
- Ajusta la configuración de micrófonos, cámaras y altavoces predeterminados.
- Compruebe la versión del cliente y busque las actualizaciones más recientes.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Salas de Teams Configuración.":::

La nueva Salas de Teams para Surface Hub cliente, aplicará automáticamente la configuración existente configurada a través de archivos XML, paquetes de aprovisionamiento o un proveedor mdm. Estos métodos, explicados en Administrar la configuración Microsoft Teams en [Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), se reemplazarán por nuevas soluciones basadas en la nube, como se describe a continuación en Administración simplificada de [Teams](#simplified-management-of-teams-coming-to-surface-hub)próximamente Surface Hub .

### <a name="prepare-networking-for-teams-rooms"></a>Preparar las redes para Salas de Teams

Para optimizar Salas de Teams los requisitos y recomendaciones descritos en [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>Administración simplificada de Teams que llega a Surface Hub

Cuando Salas de Teams para Surface Hub se publicó públicamente a finales de este año, los administradores pueden aprovechar las siguientes soluciones:

- **Teams Centro de administración.** Teams El Centro de administración proporciona una plataforma de autoadministrador completa para supervisar y administrar la experiencia Salas de Teams en Teams dispositivos. Teams El Centro de administración estará disponible para Salas de Microsoft Teams usuarios sin costo adicional.
- **Salas de Microsoft Teams servicio administrado.** El [servicio administrado](/microsoftteams/rooms/microsoft-teams-rooms-premium) Salas de Microsoft Teams es un servicio de supervisión y administración de TI basado en la nube que mantiene los dispositivos Salas de Microsoft Teams y sus periféricos actualizados y supervisados proactivamente, lo que admite un entorno optimizado para una gran experiencia del usuario.

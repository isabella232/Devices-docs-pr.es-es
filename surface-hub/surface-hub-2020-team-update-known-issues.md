---
title: 'Problemas conocidos: Surface Hub'
description: En esta página se proporciona una lista de problemas conocidos para Surface Hubs.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: a9435db1de48b33d062d5e79d0d622f1d17815f0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497490"
---
# <a name="known-issues-surface-hub"></a>Problemas conocidos: Surface Hub

En este artículo se enumeran los problemas conocidos de Surface Hubs que ejecutan el sistema operativo actual, Windows 10 Team actualización de 2020.

Para asegurarse de que Surface Hub recibe las actualizaciones más recientes, inicie sesión con una cuenta de administrador y seleccione **Todas las aplicaciones** >  **Configuración** >  **Actualizar y seguridad** >  **Windows Update** y, a continuación, instale todas las actualizaciones.

| Problema               | Descripción           | Solución                 |
|---------------------|-----------------------|------------------------|
| Cuando se usa la aplicación whiteboard en Surface Hub dispositivos, el contenido no se puede compartir por correo electrónico. | La característica "Easy Share" se ha quitado de la nueva versión de la aplicación Whiteboard. | La manera recomendada de guardar el contenido de Whiteboard es iniciar sesión en la aplicación. Si no es posible iniciar sesión, se puede guardar un archivo de imagen en el almacenamiento local y, a continuación, compartirlo a través de un servicio preferido por el usuario a través del explorador Edge. La característica "Easy Share" devolverá en una versión futura de la Pizarra. [Obtenga más información sobre los escenarios de uso compartido de pizarra.](https://support.microsoft.com/office/enable-microsoft-whiteboard-for-your-organization-1caaa2e2-5c18-4bdf-b878-2d98f1da4b24) |
| Algunos Surface Hubs se reinician cuando un usuario selecciona "Finalizar sesión".  | Cuando Surface Hub usuarios del dispositivo seleccionan la funcionalidad "Finalizar sesión" para borrar los datos de usuario, el dispositivo Surface Hub puede detectar erróneamente un error de limpieza, lo que obliga a reiniciar Windows para asegurarse de que la limpieza se produce correctamente.  | Microsoft es consciente y está investigando activamente este problema.  Microsoft proporcionará información adicional sobre una resolución lo antes posible.|
| Cuando se usa Surface Hubs en GCC entornos altos, la unión a reuniones con un solo clic desde el calendario de la pantalla de bienvenida no funciona. | Al hacer clic en "Unirse" desde el calendario de Surface Hub para una reunión de Teams en un entorno GCC Alto, no se inicia automáticamente la reunión. | Para unirse a la reunión, inicie Teams y, a continuación, únase a ella desde la agenda mostrada del cliente Teams. <br></br>Microsoft también está investigando activamente este problema y proporcionará información adicional sobre una resolución lo antes posible. |
| La configuración de calidad de servicio (QoS) no funciona según lo esperado | Después de configurar la configuración de QoS a través de la directiva MDM o el paquete de aprovisionamiento, las marcas DSCP no se aplican a Teams ni Skype Empresarial tráfico multimedia (SfB). | Microsoft es consciente y está investigando activamente este problema.  Microsoft proporcionará información adicional sobre una resolución lo antes posible. |
| Se produce un error en la sincronización del calendario de cuentas de dispositivo híbrido con buzones locales. | Surface Hub dispositivos usan la autenticación moderna de forma predeterminada para las cuentas que existen en Azure AD, incluso si tienen buzones en entornos locales que no tienen habilitada la [autenticación moderna híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication). En este escenario, Exchange deja de sincronizar reuniones con el dispositivo. Como resultado, el dispositivo no recibe ni muestra nuevas reuniones. | Una vez instalado [KB4598291](https://support.microsoft.com/help/4598291) (o un Windows CU posterior), el [CSP de SurfaceHub](/windows/client-management/mdm/surfacehub-csp) tiene un nuevo parámetro ExchangeModernAuthEnabled disponible para alternar el uso de la autenticación moderna. Esto se puede establecer en false mediante la directiva MDM o el [paquete de aprovisionamiento](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) para evitar que el centro use la autenticación moderna. |
| Un pequeño subconjunto de dispositivos de Surface Hub v1 no puede actualizarse automáticamente a la actualización de Windows 10 Team 2020. | Este pequeño subconjunto de dispositivos Surface Hub v1 se encuentra en un estado que impide la compatibilidad con la actualización directa a través de Windows Update. | Vuelva a crear una imagen manual del dispositivo en la actualización de Windows 10 Team 2020 [mediante la herramienta de recuperación de Surface Hub](surface-hub-recovery-tool.md). |
| Surface Hub muestra el mensaje "Sin dispositivo de arranque" después de intentar instalar la actualización de Windows 10 Team 2020. | Durante el proceso de Windows Update de Windows 10 Team 2020, algunos dispositivos hub v1 pasarán a un estado que no se puede arrancar. | Vuelva a crear una imagen manual del dispositivo en la actualización de Windows 10 Team 2020 [mediante la herramienta de recuperación de Surface Hub](surface-hub-recovery-tool.md). |
| Los dispositivos hub 2S no pueden recibir actualizaciones de controladores mediante WSUS. | Surface Hub 2S admite Windows Update y Windows Update para empresas para distribuir controladores; no se admite la distribución a través de Windows Server Update Services (WSUS). | Si usa WSUS, migre a Windows Update para empresas.<br> <br>**Más información**: [¿Qué es Windows actualización para empresas?](/windows/deployment/update/waas-manage-updates-wufb) |
| El Centro de acciones tiene un vínculo de Configuración que no se puede hacer clic. | Este vínculo no debe aparecer en Windows 10 Team y puede causar confusión. | La funcionalidad es la misma que antes de la actualización de 2020; la sección Aplicaciones del menú Inicio debe usarse para iniciar la aplicación Configuración.  |
| Algunas opciones de configuración de facilidad de acceso persisten después de que finalice una sesión| Cuando los usuarios activan el botón de alternancia Contraste alto desde el menú Acciones rápidas o desde la aplicación Configuración, este botón de alternancia persiste una vez finalizada la sesión del usuario. De forma similar, si los usuarios cambian la visualización de notificaciones para indicar 7 segundos frente a los 5 segundos definidos por el administrador, permanecen 7 segundos, aunque otras configuraciones se restablezcan a los valores definidos por el administrador. | Los usuarios pueden desactivar el botón de alternancia contraste alto del menú acciones rápidas (caret) accesible en la barra de tareas poco después de iniciar una sesión en el centro. El siguiente usuario puede establecer la duración de las notificaciones en un valor diferente a través de la aplicación de Configuración: esta configuración es accesible para todos los usuarios. Microsoft está buscando activamente encontrar una solución a este problema.| 

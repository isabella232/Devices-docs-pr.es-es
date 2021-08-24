---
title: Configuración por primera vez para Surface Hub
description: El término \ 0034;primera ejecución \ 0034;se refiere a la serie de pasos que recorrerás la primera vez que enciendas Surface Hub y significa lo mismo que \ 0034;configuración rápida\ 0034; (OOBE). En esta sección te guiará por el proceso.
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: primera ejecución, Surface Hub, configuración rápida, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: medium
ms.openlocfilehash: 95b3e9dceab3304da627807cf28a9e37a5af10d4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911455"
---
# <a name="first-time-setup-for-surface-hub"></a>Configuración por primera vez para Surface Hub

La primera vez que Surface Hub, el dispositivo entra automáticamente en el modo de configuración por primera vez para guiarte a través de la configuración de la cuenta y la configuración relacionada.

> [!TIP]
> Puedes automatizar todo el proceso de configuración con un paquete [de](#use-provisioning-packages) aprovisionamiento para garantizar una experiencia coherente en varios Surface Hubs.

## <a name="get-started"></a>Comenzar

1. De forma predeterminada, Cortana está habilitado para guiarlo a través del proceso. Para desactivar la Cortana, seleccione el icono del micrófono.

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana está habilitado para guiarlo a través del proceso.":::

2. **Elige tu región.** Confirme la región detectada automáticamente y seleccione **Sí**.

    :::image type="content" source="images/hub-setup-region.png" alt-text="Elige tu región.":::

3. **Confirme el diseño del teclado.** Seleccione **Sí**.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="Confirme el diseño del teclado.":::

4. Para agregar un segundo teclado, seleccione **Agregar diseño**. De lo contrario, **seleccione Omitir**.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="Agregue un segundo teclado.":::

5. **Conectar a una red.** Si ya ha conectado un cable Ethernet, Surface Hub conectará automáticamente a la red. Como alternativa, puede conectarse a una red inalámbrica. **Nota:** No puede conectarse a una red inalámbrica en puntos de acceso (portales cautivos) que redirijan las solicitudes de inicio de sesión al sitio web de un proveedor. Selecciona **Siguiente**.

    :::image type="content" source="images/hub-setup-network.png" alt-text="Conectar a una red.":::

6. **Acepte Windows 10 de licencia.** Seleccione **Aceptar**.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Acepte Windows 10 de licencia.":::

7. **Escribe información de cuenta de** dispositivo con una dirección UPN (user@contoso.com) o una dirección de dominio de nivel inferior (CONTOSO\usuario). Use el formato que coincida con el entorno y escriba la contraseña.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="Escribe Información de la cuenta del dispositivo.":::

| Entorno                                              | Formato requerido para la cuenta del dispositivo |
| -------------------------------------------------------- | ---------------------------------- |
| La cuenta de dispositivo se hospeda solo en línea                     | username@contoso.com               |
| La cuenta de dispositivo solo se hospeda localmente                | CONTOSO\user                       |
| La cuenta de dispositivo se hospeda en línea y local (híbrida) | CONTOSO\user                       |

>[!NOTE]
>Aunque puedes omitir la configuración de una cuenta de dispositivo, el dispositivo no estará totalmente integrado en la infraestructura. Si omites la configuración ahora, puedes agregar una cuenta del dispositivo más adelante mediante la aplicación Configuración.

8. **Escribe la contraseña y** selecciona **Siguiente.**

9. Surface Hub detecta automáticamente la información Exchange servidor y la dirección SIP del dominio especificado en el paso anterior. O, si es necesario, proporcione la dirección Exchange servidor y seleccione **Siguiente**.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange servidor y dirección SIP.":::

10. **Asigne un nombre a este dispositivo.** Escribe un nombre para el dispositivo o usa el sugerido. **Seleccione Siguiente**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="Asigne un nombre a este dispositivo.":::

- El **nombre descriptivo** está visible en la esquina inferior izquierda de Surface Hub 2S y se muestra al proyectar al dispositivo.
- El **nombre del dispositivo** identifica el dispositivo cuando está asociado con Active Directory o Azure Active Directory y al inscribir el dispositivo con Intune.

>[!NOTE]
>Si quieres habilitar [Miracast sobre infraestructura](miracast-over-infrastructure.md), el nombre del dispositivo debe ser reconocible mediante DNS. Puedes lograrlo permitiendo que Surface Hub se registre automáticamente a través de DNS dinámico, o crear manualmente un registro A o AAAA para el nombre de host del dispositivo Surface Hub.

### <a name="configure-device-admin-accounts"></a>Configurar cuentas de administrador de dispositivos

Solo puedes configurar administradores de dispositivos durante la configuración por primera vez. Para más información, consulta:

- [Surface Hub de dispositivos 2S](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [Administración del grupo de administradores](admin-group-management-for-surface-hub.md)

1. **Elija el tipo de cuenta de administrador.** Seleccione una de las siguientes opciones: Servicios de dominio de Active Directory, Azure Active Directory o Administrador local.

    :::image type="content" source="images/hub-setup-join.png" alt-text="Elija el tipo de cuenta de administrador.":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Si tiene la intención de usar Surface Hub en un entorno local, puede asociar El concentrador con **los servicios de dominio de Active Directory**.  Escriba las credenciales de un usuario que tenga permisos para unirse al dispositivo a Active Directory.
2. Selecciona el grupo de seguridad de Active Directory que contiene los miembros que pueden iniciar sesión en la Configuración en Surface Hub 2S.
3. Seleccione **Finalizar**. El dispositivo se reiniciará.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. Si tienes la intención de administrar Surface Hub desde la nube con Microsoft Intune o un proveedor MDM, selecciona **Microsoft Azure Active Directory**.
2. Seleccione Siguiente e inicie sesión con una cuenta laboral o educativa. Si se redirige, autentique con la página de inicio de sesión de su organización y proporcione credenciales adicionales si se solicita. De lo contrario, escriba la contraseña y seleccione **Siguiente.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="Inicie sesión con una cuenta laboral o educativa.":::

>[!NOTE]
>Para configurar quién puede usar la aplicación Configuración para administrar Surface Hubs, asegúrese de que la inscripción automática de Intune está habilitada en el inquilino antes de unir el dispositivo a Azure AD. Las directivas de Intune se pueden usar para [configurar administradores](surface-hub-2s-nonglobal-admin.md) que no son globales en Surface Hubs.

### <a name="local-administrator-account"></a>Cuenta de administrador local

- Escriba un nombre de usuario y una contraseña memorable para el administrador [](surface-hub-2s-recover-reset.md) local. (Si olvida la contraseña de administrador local, tendrá que recuperar el dispositivo y repetir el proceso de configuración).  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="Escriba una contraseña memorable para la cuenta de administrador local.":::

### <a name="choose-privacy-settings-for-your-device"></a>Elegir la configuración de privacidad del dispositivo

- Seleccione entre la configuración de privacidad disponible y seleccione **Aceptar.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="Elija configuración de privacidad.":::

### <a name="use-provisioning-packages"></a>Usar paquetes de aprovisionamiento

Puedes personalizar las opciones de configuración por primera vez, lo que te permite garantizar una experiencia coherente en varios Surface Hubs.

1. Para empezar, revise la documentación de Crear paquetes [de aprovisionamiento](provisioning-packages-for-surface-hub.md) y guarde el paquete de aprovisionamiento en una unidad usb.
2. Inserte la unidad usb en uno de los puertos USB antes de iniciar el proceso de configuración.
3. Cuando se le pida, elija el paquete de aprovisionamiento que desea usar.
4. Si creaste un archivo CSV de varios dispositivos, podrás elegir una configuración de dispositivo.
5. Siga las instrucciones para completar el programa de instalación por primera vez.

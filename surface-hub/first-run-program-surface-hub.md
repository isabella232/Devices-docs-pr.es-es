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
ms.openlocfilehash: 551867ccbb041fe292d9ec60f38bb89acfbc764e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472450"
---
# <a name="first-time-setup-for-surface-hub"></a>Configuración por primera vez para Surface Hub

La primera vez que inicia Surface Hub, el dispositivo entra automáticamente en el modo de configuración por primera vez para guiarle a través de la configuración de la cuenta y la configuración relacionada.

> [!TIP]
> Puedes automatizar todo el proceso de instalación con un [paquete de aprovisionamiento](#use-provisioning-packages) para garantizar una experiencia coherente en varios Surface Hubs.

## <a name="get-started"></a>Comenzar

1. De forma predeterminada, Cortana está habilitado para guiarlo a través del proceso. Para desactivar Cortana asistencia, seleccione el icono de micrófono.

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana está habilitado para guiarlo a través del proceso.":::

2. **Elige tu región.** Confirme la región detectada automáticamente y seleccione **Sí**.

    :::image type="content" source="images/hub-setup-region.png" alt-text="Elige tu región.":::

3. **Confirme el diseño del teclado.** Seleccione **Sí**.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="Confirme el diseño del teclado.":::

4. Para agregar un segundo teclado, seleccione **Agregar diseño**. De lo contrario, seleccione **Omitir**.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="Agregue un segundo teclado.":::

5. **Conectar a una red.** Si ya ha conectado un cable Ethernet, Surface Hub se conecta automáticamente a la red. Como alternativa, puede conectarse a una red inalámbrica. **Nota:** No puede conectarse a una red inalámbrica en zonas activas (portales cautivos) que redirijan solicitudes de inicio de sesión al sitio web de un proveedor. Selecciona **Siguiente**.

    :::image type="content" source="images/hub-setup-network.png" alt-text="Conectar a una red.":::

6. **Acepte Windows 10 contrato de licencia.** Seleccione **Aceptar**.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Acepte Windows 10 contrato de licencia.":::

7. **Escriba la información de la cuenta** de dispositivo mediante una dirección UPN (user@contoso.com) o una dirección de dominio de nivel inferior (CONTOSO\user). Use el formato que coincida con el entorno y escriba la contraseña.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="Escriba Información de la cuenta de dispositivo.":::

| Entorno                                              | Formato requerido para la cuenta del dispositivo |
| -------------------------------------------------------- | ---------------------------------- |
| La cuenta de dispositivo solo se hospeda en línea                     | username@contoso.com               |
| La cuenta de dispositivo solo está hospedada en el entorno local                | CONTOSO\user                       |
| La cuenta de dispositivo se hospeda en línea y en el entorno local (híbrido) | CONTOSO\user                       |

>[!NOTE]
>Aunque puede omitir la configuración de una cuenta de dispositivo, el dispositivo no se integrará completamente en la infraestructura. Si omites la configuración ahora, puedes agregar una cuenta del dispositivo más adelante mediante la aplicación Configuración.

8. **Escriba la contraseña** y seleccione **Siguiente.**

9. Surface Hub detecta automáticamente Exchange información de la dirección SIP y del servidor del dominio especificado en el paso anterior. O bien, si es necesario, proporcione la dirección del servidor Exchange y seleccione **Siguiente**.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange servidor y dirección SIP.":::

10. **Asigne un nombre a este dispositivo.** Escriba un nombre para el dispositivo o use el sugerido. **Seleccione Siguiente**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="Asigne un nombre a este dispositivo.":::

- El **nombre descriptivo** está visible en la esquina inferior izquierda de Surface Hub 2S y se muestra al proyectar en el dispositivo.
- El **nombre del** dispositivo identifica el dispositivo cuando está afiliado a Active Directory o Azure Active Directory, y al inscribir el dispositivo con Intune.

>[!IMPORTANT]
>Si tiene previsto afliar el Surface Hub con Active Directory, el nombre del dispositivo debe cumplir [los requisitos estándar para los nombres de equipo en AD; de](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names) lo contrario, se producirá un error en la instalación.

>[!NOTE]
>Si quieres habilitar [Miracast sobre infraestructura](miracast-over-infrastructure.md), el nombre del dispositivo debe ser reconocible mediante DNS. Puedes lograrlo permitiendo que Surface Hub se registre automáticamente a través de DNS dinámico, o crear manualmente un registro A o AAAA para el nombre de host del dispositivo Surface Hub.

### <a name="configure-device-admin-accounts"></a>Configuración de cuentas de administrador de dispositivos

Solo puede configurar los administradores de dispositivos durante la primera instalación. Para más información, consulta:

- [Surface Hub afiliación de dispositivos 2S](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [Administración del grupo de administradores](admin-group-management-for-surface-hub.md)

1. **Elija el tipo de cuenta de administrador.** Seleccione una de las siguientes opciones: Servicios de dominio de Active Directory, Azure Active Directory o Administrador local.

    :::image type="content" source="images/hub-setup-join.png" alt-text="Elija el tipo de cuenta de administrador.":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Si tiene previsto usar Surface Hub en un entorno local, puede afiliar el Centro con **Servicios de dominio de Active Directory**.  Escriba las credenciales de un usuario que tenga permisos para unir el dispositivo a Active Directory.
2. Seleccione el grupo de seguridad de Active Directory que contiene miembros con permiso para iniciar sesión en la aplicación Configuración en Surface Hub 2S.
3. Seleccione **Finalizar**. El dispositivo se reiniciará.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. Si tiene previsto administrar Surface Hub desde la nube mediante Microsoft Intune o un proveedor de MDM, seleccione **Microsoft Azure Active Directory**.
2. Seleccione Siguiente e inicie sesión con una cuenta profesional o educativa. Si se le redirige, autentíquese mediante la página de inicio de sesión de su organización y proporcione credenciales adicionales si se solicitan. En caso contrario, escriba la contraseña y seleccione **Siguiente.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="Inicie sesión con una cuenta profesional o educativa.":::

>[!NOTE]
>Para configurar quién puede usar la aplicación Configuración para administrar Surface Hubs, asegúrate de que la inscripción automática de Intune esté habilitada en tu inquilino antes de unirte al dispositivo para Azure AD. Intune directivas se pueden usar para [configurar administradores no globales](surface-hub-2s-nonglobal-admin.md) en Surface Hubs.

### <a name="local-administrator-account"></a>Cuenta de administrador local

- Escriba un nombre de usuario y una contraseña memorable para el administrador local. (Si olvida la contraseña de administrador local, tendrá que [recuperar el dispositivo](surface-hub-2s-recover-reset.md) y repetir el proceso de instalación).  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="Escriba una contraseña memorable para la cuenta de administrador local.":::

### <a name="choose-privacy-settings-for-your-device"></a>Elección de la configuración de privacidad del dispositivo

- Seleccione en la configuración de privacidad disponible y seleccione **Aceptar.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="Elija la configuración de privacidad.":::

### <a name="use-provisioning-packages"></a>Usar paquetes de aprovisionamiento

Puedes personalizar las opciones de configuración por primera vez, lo que te permite garantizar una experiencia coherente en varios Surface Hubs.

1. Para empezar, revise la documentación de [Creación de paquetes de aprovisionamiento](provisioning-packages-for-surface-hub.md) y guarde el paquete de aprovisionamiento en una unidad usb.
2. Inserte la unidad usb en uno de los puertos USB cuando vea la página Contrato de licencia (paso 6 en los pasos de configuración anteriores).
3. Cuando se le solicite, elija el paquete de aprovisionamiento que desea usar.
4. Si ha creado un archivo CSV de varios dispositivos, podrá elegir una configuración de dispositivo.
5. Siga las instrucciones para completar el programa de instalación por primera vez.

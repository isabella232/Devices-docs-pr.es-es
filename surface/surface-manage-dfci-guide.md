---
title: Administrar DFCI en dispositivos Surface
description: En este artículo se explica cómo configurar un entorno DFCI en Microsoft Intune y administrar la configuración de firmware para dispositivos Surface de destino.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4
ms.openlocfilehash: 871bead0ae5f73c546b8dbe219d71b819d3a865e
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676454"
---
# <a name="manage-dfci-on-surface-devices"></a>Administrar DFCI en dispositivos Surface

## <a name="introduction"></a>Introducción

La capacidad de administrar dispositivos desde la nube ha simplificado considerablemente la implementación y el aprovisionamiento de TI en todo el ciclo de vida. Con los perfiles de interfaz de configuración de firmware de dispositivo (DFCI) integrados en [Microsoft Intune,](/intune/configuration/device-firmware-configuration-interface-windows)la administración de UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware uefi. DFCI admite el aprovisionamiento sin intervención, elimina las contraseñas del BIOS, proporciona control de la configuración de seguridad, incluidas las opciones de arranque y los periféricos integrados, y establece las bases para escenarios de seguridad avanzados en el futuro. Para obtener respuestas a las preguntas más frecuentes, consulta [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

### <a name="background"></a>Segundo plano

Al igual que cualquier equipo que Windows 10, los dispositivos Surface dependen del código almacenado en el SoC que permite que la CPU se interfaz con unidades de disco duro, dispositivos de pantalla, puertos USB y otros dispositivos. Los programas almacenados en esta memoria de solo lectura (ROM) se conocen como firmware (mientras que los programas almacenados en medios dinámicos se conocen como software).

A diferencia de otros dispositivos Windows 10 disponibles en el mercado actualmente, Surface ofrece a los administradores de TI la capacidad de configurar y administrar el firmware a través de un amplio conjunto de opciones de configuración de UEFI. Esto proporciona una capa de control de hardware sobre la administración de directivas basada en software, tal como se implementa a través de directivas de administración de dispositivos móviles (MDM), Configuration Manager o directiva de grupo. Por ejemplo, las organizaciones que implementan dispositivos en áreas altamente seguras con información confidencial pueden impedir el uso de cámaras quitando la funcionalidad en el nivel de hardware. Desde el punto de vista del dispositivo, desactivar la cámara mediante una configuración de firmware equivale a quitar físicamente la cámara. Compare la seguridad agregada de la administración en el nivel de firmware con la confianza únicamente en la configuración de software del sistema operativo. Por ejemplo, si deshabilita el servicio de audio Windows mediante una configuración de directiva en un entorno de dominio, un administrador local podría volver a habilitar el servicio.

### <a name="dfci-versus-semm"></a>DFCI frente a SEMM

Anteriormente, la administración del firmware requería la inscripción de dispositivos en el Modo de administración de Surface Enterprise (SEMM) con la sobrecarga de tareas manuales intensivas en TI en curso. Por ejemplo, SEMM requiere que el personal de IT acceda físicamente a cada equipo para escribir un pin de dos dígitos como parte del proceso de administración de certificados. Aunque SEMM sigue siendo una buena solución para las organizaciones en un entorno estrictamente local, su complejidad y los requisitos intensivos de TI hacen que su uso sea costoso.

 Con las capacidades de administración de firmware UEFI integradas en Microsoft Intune, la capacidad de bloquear el hardware se simplifica y es más fácil de usar con nuevas características para el aprovisionamiento, la seguridad y la actualización optimizada de todo en una sola consola, ahora unificada [como Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager). En la siguiente figura se muestra la configuración de UEFI que se ve directamente en el dispositivo (izquierda) y se ve en la Endpoint Manager (derecha).

![Configuración de UEFI que se muestra en el dispositivo (izquierda) y en la consola Endpoint Manager (derecha)](images/uefidfci.png)

Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins. DFCI se implementa mediante Windows Autopilot mediante la funcionalidad de perfiles de dispositivo en Intune. Un perfil de dispositivo te permite agregar y configurar opciones que luego se pueden implementar en dispositivos inscritos en la administración dentro de la organización. Una vez que el dispositivo recibe el perfil del dispositivo, las características y la configuración se aplican automáticamente. Algunos ejemplos de perfiles de dispositivo comunes son correo electrónico, restricciones de dispositivo, VPN, Wi-Fi y plantillas administrativas. DFCI es simplemente un perfil de dispositivo adicional que permite administrar las opciones de configuración de UEFI desde la nube sin tener que mantener la infraestructura local.  

## <a name="supported-devices"></a>Dispositivos compatibles

DFCI se admite en los siguientes dispositivos:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Ir
- Surface Laptop 4

> [!NOTE]
> Surface Pro X no admite la administración de la configuración DFCI para cámara integrada, audio y Wi-Fi/Bluetooth.

## <a name="prerequisites"></a>Requisitos previos

- Los dispositivos deben estar registrados Windows Autopilot por un partner [Proveedor de soluciones en la nube de Microsoft (CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) o un distribuidor OEM.

- Antes de configurar DFCI para Surface, debes estar familiarizado con los requisitos de configuración de Autopilot en [Microsoft Intune](/intune/) y [Azure Active Directory](/azure/active-directory/) (Azure AD).

## <a name="before-you-begin"></a>Antes de empezar

Agrega los dispositivos Surface de destino a un grupo de seguridad de Azure AD. Para obtener más información acerca de la creación y administración de grupos de seguridad, consulte [la documentación de Intune](/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## <a name="configure-dfci-management-for-surface-devices"></a>Configurar la administración dfci para dispositivos Surface

Un entorno DFCI requiere configurar un perfil DFCI que contenga la configuración y un perfil de Autopilot para aplicar la configuración a dispositivos registrados. También se recomienda un perfil de estado de inscripción para asegurarse de que la configuración se presiona durante la configuración de OOBE cuando los usuarios inician el dispositivo por primera vez. En esta guía se explica cómo configurar el entorno DFCI y administrar las opciones de configuración de UEFI para dispositivos Surface de destino.

## <a name="create-dfci-profile"></a>Crear perfil DFCI

Antes de configurar las opciones de directiva DFCI, primero cree un perfil DFCI y asígnelo al grupo de seguridad de Azure AD que contiene los dispositivos de destino.

1. Inicie sesión en el espacio empresarial en devicemanagement.microsoft.com.
2. En el Centro Microsoft Endpoint Manager administración, seleccione **Dispositivos > perfiles** de configuración > Crear perfil y escriba un nombre; por ejemplo, **directiva de configuración DFCI.**
3. Seleccione **Windows 10 y posteriores** para el tipo de plataforma.
4. En la lista desplegable Tipo de perfil, seleccione Interfaz de configuración de **firmware** de dispositivo para abrir la hoja DFCI que contiene toda la configuración de directiva disponible. Para obtener información sobre la configuración de DFCI, consulte la tabla 1 de esta página o la [documentación de Intune](/intune/configuration/device-firmware-configuration-interface-windows). Puede configurar dfci durante el proceso de configuración inicial o posterior editando el perfil DFCI.

    ![Crear perfil DFCI](images/df1.png)

5. Haga **clic en Aceptar** y, a **continuación, seleccione Crear**.
6. Seleccione **Asignaciones y,** en **Seleccionar grupos,** seleccione el grupo de seguridad de Azure AD que contiene los dispositivos de destino, como se muestra en la siguiente figura. Haz clic en **Guardar**.

    ![Asignar grupo de seguridad](images/df2a.png)

## <a name="create-autopilot-profile"></a>Crear perfil de Autopilot

1. En Endpoint Manager en devicemanagement.microsoft.com, seleccione dispositivos > Windows **inscripción y** desplácese hacia abajo hasta **Perfiles de implementación.**
2. Seleccione **Crear perfil** y escriba un nombre; por ejemplo, **Mi perfil de Piloto automático**y seleccione **Siguiente**.
3. Seleccione la siguiente configuración:

    - Modo de implementación: **controlado por el usuario**.
    - Tipo de unión: Azure **AD unido**.

4. Deje la configuración predeterminada restante sin cambios y seleccione **Siguiente**, como se muestra en la ilustración siguiente.

    ![Crear perfil de Autopilot](images/df3b.png)

5. En la página Asignaciones, elija **Seleccionar grupos para incluir y** haga clic en el grupo de seguridad de Azure AD. Selecciona **Siguiente**.
6. Acepte el resumen y, a continuación, **seleccione Crear**. El perfil de Autopilot ahora se crea y se asigna al grupo.

## <a name="configure-enrollment-status-page"></a>Configurar la página de estado de inscripción

Para asegurarse de que los dispositivos aplican la configuración DFCI durante OOBE antes de que los usuarios inicien sesión, debe configurar el estado de inscripción.

Para obtener más información, consulte [Configurar una página de estado de inscripción.](/intune/enrollment/windows-enrollment-status)


## <a name="configure-dfci-settings-on-surface-devices"></a>Configuración de DFCI en dispositivos Surface

DFCI incluye un conjunto simplificado de directivas de configuración de UEFI que proporcionan un nivel adicional de seguridad al bloquear dispositivos en el nivel de hardware. DFCI está diseñado para usarse junto con la configuración de administración de dispositivos móviles en el nivel de software. Ten en cuenta que la configuración de DFCI solo afecta a los componentes de hardware integrados en dispositivos Surface y no se extienden a periféricos conectados como cámaras web USB. (Sin embargo, puedes usar directivas de restricción de dispositivos en Intune para desactivar el acceso a periféricos conectados en el nivel de software).

Para configurar la directiva DFCI, edite el perfil DFCI desde Endpoint Manager, como se muestra en la figura siguiente. 

- En Endpoint Manager en devicemanagement.microsoft.com, seleccione **Dispositivos > Windows > perfiles**de configuración > "Nombre de perfil DFCI" > propiedades > Configuración .

    ![Configurar las opciones de DFCI](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a>Bloquear el acceso de usuario a la configuración de UEFI

Para muchos clientes, la capacidad de impedir que los usuarios cambien la configuración de UEFI es fundamental y un motivo principal para usar DFCI. Como se muestra en la tabla 1, esto se administra mediante la configuración Permitir al usuario **local cambiar la configuración de UEFI**. Si no edita ni configura esta configuración, los usuarios locales podrán cambiar cualquier configuración de UEFI no administrada por Intune. Por lo tanto, es muy recomendable deshabilitar Permitir que el usuario **local cambie la configuración de UEFI.**
El resto de la configuración dfci permite desactivar la funcionalidad que, de lo contrario, estaría disponible para los usuarios. Por ejemplo, si necesitas proteger la información confidencial en áreas altamente seguras, puedes deshabilitar la cámara y, si no quieres que los usuarios arranquen desde unidades USB, también puedes deshabilitarla.

### <a name="table-1-dfci-scenarios"></a>Tabla 1. Escenarios DFCI

| Objetivo de administración de dispositivos                        | Pasos de configuración                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que los usuarios locales cambien la configuración de UEFI | En Características de seguridad > Permitir que el usuario local cambie la configuración **de UEFI**, seleccione **Ninguno**.              |
| Deshabilitar cámaras                               | En **Cámaras integradas > hardware,** seleccione **Deshabilitado**.                                       |
| Deshabilitar micrófonos y altavoces              | En **Hardware integrado > micrófonos y altavoces,** seleccione **Deshabilitado**.                      |
| Deshabilitar radios (Bluetooth, Wi-Fi)             | En **Hardware integrado > radios (Bluetooth, Wi-Fi, etc.),** seleccione **Deshabilitado**.                   |
| Deshabilitar el arranque desde medios externos (USB, SD)    | En **Built in Hardware > Boot Options > Boot from external media (USB, SD),** seleccione **Disabled**. |

> [!CAUTION]
> La **configuración Deshabilitar radios (Bluetooth, Wi-Fi)** solo debe usarse en dispositivos que tengan una conexión Ethernet cableada.
 
> [!NOTE]
>  DFCI en Intune incluye dos configuraciones que actualmente no se aplican a dispositivos Surface: (1) virtualización de E/S y CPU y (2) Deshabilitar el arranque desde adaptadores de red.
 
Intune proporciona etiquetas de ámbito para delegar derechos administrativos y reglas de aplicabilidad para administrar los tipos de dispositivo. Para obtener más información sobre el soporte técnico de administración de directivas y detalles completos sobre todas las configuraciones de DFCI, consulte [Microsoft Intune documentación](/intune/configuration/device-firmware-configuration-interface-windows).

## <a name="register-devices-in-autopilot"></a>Registrar dispositivos en Autopilot

Como se mencionó anteriormente, DFCI solo se puede aplicar en dispositivos registrados en Windows Autopilot por el revendedor o distribuidor y solo se admite en Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X y Surface Laptop 3. Por motivos de seguridad, no es posible "aprovisionar automáticamente" los dispositivos en Autopilot. Para obtener más información, consulta Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md). 

## <a name="manually-sync-autopilot-devices"></a>Sincronizar manualmente dispositivos Autopilot

Aunque la configuración de directiva de Intune normalmente se aplica casi inmediatamente, puede haber un retraso de 10 minutos antes de que la configuración suba a los dispositivos de destino. En raras circunstancias, son posibles retrasos de hasta 8 horas. Para garantizar que la configuración se aplique lo antes posible (como en escenarios de prueba), puedes sincronizar manualmente los dispositivos de destino.

- En Endpoint Manager en devicemanagement.microsoft.com, ve a Dispositivos > Inscripción de dispositivos > Windows inscripción > Windows **Autopilot Devices** y selecciona **Sincronizar**.

 Para obtener más información, consulte [Sincronizar el dispositivo Windows manualmente.](/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> Al ajustar la configuración directamente en UEFI, debes asegurarte de que el dispositivo se reinicie completamente al inicio de sesión Windows estándar.

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a>Comprobar la configuración de UEFI en dispositivos administrados por DFCI

En un entorno de prueba, puedes comprobar la configuración en la interfaz UEFI de Surface.

1. Abra La UEFI de Surface, que implica presionar los botones **Volumen +** y **Energía** al mismo tiempo.
2. Seleccione **Dispositivos**. El menú UEFI reflejará la configuración, como se muestra en la siguiente figura.

    ![Surface UEFI](images/df3.png)

    Tenga en cuenta cómo:

      - La configuración está en gris porque Permitir que el usuario local cambie la configuración **de UEFI** está establecida en Ninguno.
      - El audio está desactivado porque **los micrófonos y los altavoces** están establecidos en **Deshabilitado**.

## <a name="removing-dfci-policy-settings"></a>Quitar la configuración de directiva DFCI

Al crear un perfil DFCI, todas las opciones configuradas permanecerán en vigor en todos los dispositivos dentro del ámbito de administración del perfil. Solo puede quitar la configuración de directiva DFCI editando el perfil DFCI directamente.

Si se ha eliminado el perfil DFCI original, puede quitar la configuración de directiva creando un perfil nuevo y editando la configuración, según corresponda.

## <a name="removing-dfci-management"></a>Eliminación de la administración dfci

**Para quitar la administración de DFCI y devolver el dispositivo al nuevo estado de fábrica:**

1. Retire el dispositivo de Intune:
    1. En Endpoint Manager en devicemanagement.microsoft.com, elija **Grupos > Todos los dispositivos**. Selecciona los dispositivos que quieres retirar y, a continuación, elige **Retirar/Borrar.** Para obtener más información, consulte Quitar dispositivos con borrar, retirar o [desenrollar manualmente el dispositivo](/intune/remote-actions/devices-wipe). 
2. Eliminar el registro de Autopilot de Intune:
    1.  Elija **Inscripción de dispositivos > Windows inscripción > Dispositivos**.
    2. En Windows autopilot, elija los dispositivos que desea eliminar y, a continuación, **elija Eliminar**.
3. Conectar dispositivo a Internet por cable con adaptador Ethernet de marca Surface. Reinicie el dispositivo y abra el menú UEFI (mantenga presionado el botón de volumen hacia arriba mientras también presiona y suelta el botón de encendido).
4. Seleccione **Administración > Configurar > actualizar desde red** y, a continuación, elija No **participar.**

Para seguir administrando el dispositivo con Intune, pero sin la administración de DFCI, registre automáticamente el dispositivo en Autopilot e inscríbalo en Intune. DFCI no se aplicará a dispositivos auto registrados.

## <a name="learn-more"></a>Obtén más información
- [Ignite 2019: Anuncio de](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) la administración remota de la configuración de UEFI de Surface desde Intune 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md) 
- [Usar perfiles DFCI en Windows dispositivos en Microsoft Intune](/intune/configuration/device-firmware-configuration-interface-windows)

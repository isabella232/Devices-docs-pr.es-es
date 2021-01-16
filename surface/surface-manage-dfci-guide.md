---
title: Administración de Intune de la configuración de la UEFI de Surface
description: En este artículo se explica cómo configurar un entorno DFCI en Microsoft Intune y administrar la configuración de firmware para dispositivos Surface de destino.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
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
ms.openlocfilehash: dde34126c726ec0ac8093a665804c4fb0f639e3e
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271574"
---
# Administración de Intune de la configuración de la UEFI de Surface

## Introducción

La capacidad de administrar dispositivos desde la nube ha simplificado considerablemente la implementación y el aprovisionamiento de TI a lo largo del ciclo de vida. Con los perfiles de interfaz de configuración de firmware de dispositivo (DFCI) integrados en [Microsoft Intune,](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)la administración de UEFI de Surface amplía la pila de administración moderna hasta el nivel de hardware de UEFI. DFCI admite el aprovisionamiento sin intervención táctil, elimina las contraseñas de BIOS, proporciona control de la configuración de seguridad, incluidas las opciones de arranque y periféricos integrados, y establece las bases para escenarios de seguridad avanzados en el futuro. Para obtener respuestas a las preguntas más frecuentes, consulta [Ignite 2019: Anuncio](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)de la administración remota de la configuración de LA UEFI de Surface desde Intune.

### Segundo plano

Al igual que cualquier equipo que ejecute Windows 10, los dispositivos Surface dependen del código almacenado en el SoC que permite que la CPU se interfaz con unidades de disco duro, dispositivos de pantalla, puertos USB y otros dispositivos. Los programas almacenados en esta memoria de solo lectura (ROM) se conocen como firmware (mientras que los programas almacenados en medios dinámicos se conocen como software).

A diferencia de otros dispositivos Windows 10 disponibles en el mercado actualmente, Surface proporciona a los administradores de TI la capacidad de configurar y administrar el firmware a través de un amplio conjunto de opciones de configuración de UEFI. Esto proporciona una capa de control de hardware sobre la administración de directivas basadas en software tal como se implementa a través de directivas de administración de dispositivos móviles (MDM), Configuration Manager o Directiva de grupo. Por ejemplo, las organizaciones que implementan dispositivos en áreas de alta seguridad con información confidencial pueden impedir el uso de cámaras quitando la funcionalidad en el nivel de hardware. Desde el punto de vista del dispositivo, desactivar la cámara mediante una configuración de firmware equivale a quitar físicamente la cámara. Compare la seguridad agregada de la administración en el nivel de firmware con la confianza únicamente en la configuración de software del sistema operativo. Por ejemplo, si deshabilita el servicio de audio de Windows a través de una configuración de directiva en un entorno de dominio, un administrador local podría volver a habilitar el servicio.

### DFCI frente a SEMM

Anteriormente, la administración del firmware requería inscribir dispositivos en el Modo de administración de Surface Enterprise (SEMM) con la sobrecarga de tareas manuales intensivas de TI en curso. Por ejemplo, SEMM requiere que el personal de IT acceda físicamente a cada equipo para escribir un pin de dos dígitos como parte del proceso de administración de certificados. Aunque SEMM sigue siendo una buena solución para las organizaciones en un entorno estrictamente local, su complejidad y los requisitos intensivos de TI hacen que su uso sea costoso.

 Con las funcionalidades integradas de administración de firmware UEFI en Microsoft Intune, la capacidad de bloquear el hardware se simplifica y es más fácil de usar con nuevas características de aprovisionamiento, seguridad y actualización optimizada en una sola consola, ahora unificada como [Microsoft Endpoint Manager.](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) La siguiente figura muestra la configuración de UEFI que se ve directamente en el dispositivo (izquierda) y se ve en la consola de Endpoint Manager (derecha).

![Configuración de UEFI que se muestra en el dispositivo (izquierda) y en la consola de Endpoint Manager (derecha)](images/uefidfci.png)

Fundamentalmente, DFCI permite la administración sin interacción táctil, lo que elimina la necesidad de interacción manual por parte de los administradores de TI. DFCI se implementa a través de Windows Autopilot con la funcionalidad de perfiles de dispositivo en Intune. Un perfil de dispositivo te permite agregar y configurar opciones que se pueden implementar en dispositivos inscritos en la administración de la organización. Una vez que el dispositivo recibe el perfil del dispositivo, las características y la configuración se aplican automáticamente. Algunos ejemplos de perfiles de dispositivo comunes son correo electrónico, restricciones de dispositivo, VPN, Wi-Fi y plantillas administrativas. DFCI es simplemente un perfil de dispositivo adicional que te permite administrar las opciones de configuración de UEFI desde la nube sin tener que mantener la infraestructura local.  

## Dispositivos compatibles

DFCI se admite en los siguientes dispositivos:

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go

> [!NOTE]
> Surface Pro X no admite la administración de la configuración DFCI para cámaras integradas, audio y Wi-Fi/Bluetooth.

## Requisitos previos

- Los dispositivos deben estar registrados en Windows Autopilot por un partner de Proveedor de soluciones en la nube [(CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) de Microsoft o un distribuidor oem.

- Antes de configurar DFCI para Surface, debes estar familiarizado con los requisitos de configuración de Autopilot en  [Microsoft Intune](https://docs.microsoft.com/intune/) y Azure [Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).

## Antes de comenzar

Agrega los dispositivos Surface de destino a un grupo de seguridad de Azure AD. Para obtener más información acerca de la creación y administración de grupos de seguridad, consulte la [documentación de Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)

## Configurar la administración de DFCI para dispositivos Surface

Un entorno DFCI requiere configurar un perfil DFCI que contenga la configuración y un perfil de Autopilot para aplicar la configuración a los dispositivos registrados. También se recomienda un perfil de estado de inscripción para asegurarse de que la configuración se inserta durante la configuración OOBE cuando los usuarios inician el dispositivo por primera vez. En esta guía se explica cómo configurar el entorno DFCI y administrar las opciones de configuración de UEFI para dispositivos Surface de destino.

## Crear perfil DFCI

Antes de configurar las opciones de directiva DFCI, primero crea un perfil DFCI y asígnelo al grupo de seguridad de Azure AD que contiene los dispositivos de destino.

1. Inicie sesión en su espacio empresarial en devicemanagement.microsoft.com.
2. En el Centro de administración de Microsoft Endpoint Manager, selecciona **> perfiles** de configuración > Crear perfil y escribe un nombre; por ejemplo, directiva **de configuración DFCI.**
3. Selecciona **Windows 10 y versiones posteriores para** el tipo de plataforma.
4. En la lista desplegable Tipo de perfil, seleccione Interfaz de configuración de **firmware** de dispositivo para abrir la hoja DFCI que contiene todas las configuraciones de directiva disponibles. Para obtener información sobre la configuración de DFCI, consulte la tabla 1 de esta página o la documentación [de Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) Puedes configurar las opciones de DFCI durante el proceso de configuración inicial o posterior mediante la edición del perfil DFCI.

    ![Crear perfil DFCI](images/df1.png)

5. Haga **clic en Aceptar** y, a continuación, seleccione **Crear**.
6. Selecciona **Asignaciones y,** en **Seleccionar grupos,** para incluir selecciona el grupo de seguridad de Azure AD que contiene los dispositivos de destino, como se muestra en la ilustración siguiente. Haz clic en **Guardar**.

    ![Asignar grupo de seguridad](images/df2a.png)

## Crear perfil de Autopilot

1. En Endpoint Manager en devicemanagement.microsoft.com, selecciona los dispositivos **> inscripción de Windows** y desplázate hacia abajo hasta los **perfiles de implementación.**
2. Seleccione **Crear perfil** y escriba un nombre; por ejemplo, **Mi perfil de Autopilot**y seleccione **Siguiente.**
3. Seleccione la siguiente configuración:

    - Modo de implementación: **controlado por el usuario.**
    - Tipo de unión: Unido a Azure **AD.**

4. Deje la configuración predeterminada restante sin cambios y seleccione **Siguiente,** como se muestra en la ilustración siguiente.

    ![Crear perfil de Autopilot](images/df3b.png)

5. En la página Asignaciones, elija **Seleccionar grupos para incluir y** haga clic en el grupo de seguridad de Azure AD. Selecciona **Siguiente**.
6. Acepte el resumen y, a continuación, **seleccione Crear**. El perfil de Autopilot ya se ha creado y asignado al grupo.

## Configurar la página de estado de inscripción

Para asegurarse de que los dispositivos aplican la configuración DFCI durante la OOBE antes de que los usuarios inicien sesión, debes configurar el estado de inscripción.

Para obtener más información, consulta [Configurar una página de estado de inscripción.](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)


## Configurar las opciones de DFCI en dispositivos Surface

DFCI incluye un conjunto simplificado de directivas de configuración de UEFI que proporcionan un nivel adicional de seguridad mediante el bloqueo de dispositivos en el nivel de hardware. DFCI está diseñado para usarse junto con la configuración de administración de dispositivos móviles en el nivel de software. Ten en cuenta que la configuración de DFCI solo afecta a los componentes de hardware integrados en dispositivos Surface y no se extienden a periféricos conectados, como cámaras web USB. (Sin embargo, puedes usar directivas de restricción de dispositivos en Intune para desactivar el acceso a periféricos conectados en el nivel de software).

Para configurar las opciones de directiva DFCI, edita el perfil DFCI desde Endpoint Manager, como se muestra en la ilustración siguiente. 

- En Endpoint Manager en devicemanagement.microsoft.com, selecciona Dispositivos > Perfiles de configuración de Windows > > "Nombre de perfil **DFCI"**> Propiedades > Configuración.

    ![Configurar las opciones de DFCI](images/dfciconfig.png)

### Bloquear el acceso del usuario a la configuración de UEFI

Para muchos clientes, la capacidad de impedir que los usuarios cambien la configuración de UEFI es fundamental y un motivo principal para usar DFCI. Como se muestra en la tabla 1, esto se administra a través de la configuración Permitir al usuario **local cambiar la configuración de UEFI.** Si no edita ni configura esta opción, los usuarios locales podrán cambiar cualquier configuración de UEFI no administrada por Intune. Por lo tanto, es muy recomendable deshabilitar Permitir que el **usuario local cambie la configuración de UEFI.**
El resto de la configuración de DFCI te permite desactivar la funcionalidad que, de lo contrario, estaría disponible para los usuarios. Por ejemplo, si necesitas proteger la información confidencial en áreas altamente seguras, puedes deshabilitar la cámara y, si no quieres que los usuarios arranquen desde unidades USB, también puedes deshabilitarla.

### Tabla 1. Escenarios dfci

| Objetivo de administración de dispositivos                        | Pasos de configuración                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que los usuarios locales cambien la configuración de UEFI | En Características de seguridad > Permitir que el usuario local cambie la configuración **de UEFI,** seleccione **Ninguno**.              |
| Deshabilitar cámaras                               | En **Cámaras integradas de hardware >,** seleccione **Deshabilitado.**                                       |
| Deshabilitar micrófonos y altavoces              | En **Hardware integrado > micrófonos y altavoces,** seleccione **Deshabilitado.**                      |
| Deshabilitar radios (Bluetooth, Wi-Fi)             | En **Hardware integrado > radios (Bluetooth, Wi-Fi, etc.),** seleccione **Deshabilitado.**                   |
| Deshabilitar el arranque desde medios externos (USB, SD)    | En Opciones de arranque integradas > hardware > arranque desde medios **externos (USB, SD),** selecciona **Deshabilitado.** |

> [!CAUTION]
> La **opción Deshabilitar radios (Bluetooth, Wi-Fi)** solo debe usarse en dispositivos que tengan una conexión Ethernet cableada.
 
> [!NOTE]
>  DFCI en Intune incluye dos configuraciones que actualmente no se aplican a dispositivos Surface: (1) virtualización de CPU e E/S y (2) Deshabilitar el arranque desde adaptadores de red.
 
Intune proporciona etiquetas de ámbito para delegar derechos administrativos y reglas de aplicabilidad para administrar tipos de dispositivos. Para obtener más información sobre la compatibilidad con la administración de directivas y detalles completos sobre todas las configuraciones de DFCI, consulte la [documentación de Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

## Registrar dispositivos en Autopilot

Como se indicó anteriormente, el revendedor o distribuidor solo puede aplicar DFCI en dispositivos registrados en Windows Autopilot y solo se admite en Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X y Surface Laptop 3. Por motivos de seguridad, no es posible "aprovisionar automáticamente" los dispositivos en Autopilot. Para obtener más información, consulta Soporte de registro de Surface [para Windows Autopilot.](surface-autopilot-registration-support.md) 

## Sincronizar manualmente dispositivos de Autopilot

Aunque la configuración de directiva de Intune suele aplicarse casi inmediatamente, puede haber un retraso de 10 minutos antes de que la configuración entre en vigor en los dispositivos de destino. En raras circunstancias, son posibles retrasos de hasta 8 horas. Para garantizar que la configuración se aplique lo antes posible (como en escenarios de prueba), puedes sincronizar manualmente los dispositivos de destino.

- En Endpoint Manager en devicemanagement.microsoft.com, ve a Dispositivos > Inscripción de dispositivos > inscripción de **Windows > Dispositivos Windows Autopilot y** selecciona **Sincronizar.**

 Para obtener más información, consulta [Sincronizar el dispositivo Windows manualmente.](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)

> [!NOTE]
> Al ajustar la configuración directamente en UEFI, debes asegurarte de que el dispositivo se reinicie completamente al inicio de sesión estándar de Windows.

## Comprobar la configuración de UEFI en dispositivos administrados por DFCI

En un entorno de prueba, puedes comprobar la configuración en la interfaz de LA UEFI de Surface.

1. Abre la UEFI de Surface, **** que implica presionar los botones **Volumen +** y Energía al mismo tiempo.
2. Seleccione **Dispositivos**. El menú UEFI reflejará las opciones configuradas, como se muestra en la ilustración siguiente.

    ![Surface UEFI](images/df3.png)

    Ten en cuenta cómo:

      - La configuración está en gris porque Permitir que el usuario local cambie la configuración **de UEFI** está establecida en Ninguno.
      - El audio está desactivado porque **los micrófonos y los altavoces** están **deshabilitados.**

## Quitar la configuración de directiva DFCI

Al crear un perfil DFCI, todas las opciones configuradas permanecerán en vigor en todos los dispositivos dentro del ámbito de administración del perfil. Solo puedes quitar la configuración de directiva DFCI editando el perfil DFCI directamente.

Si se ha eliminado el perfil DFCI original, puede quitar la configuración de directiva creando un nuevo perfil y editando la configuración, según corresponda.

## Quitar la administración de DFCI

**Para quitar la administración de DFCI y devolver el dispositivo a un nuevo estado de fábrica:**

1. Retire el dispositivo de Intune:
    1. En Endpoint Manager en devicemanagement.microsoft.com, elija **Grupos > Todos los dispositivos.** Selecciona los dispositivos que quieres retirar y, a continuación, elige **Retirar o borrar.** Para obtener más información, consulta Quitar dispositivos mediante el borrado, la retirada o la [eliminación manual de la inscripción del dispositivo.](https://docs.microsoft.com/intune/remote-actions/devices-wipe) 
2. Elimina el registro de Autopilot de Intune:
    1.  Elija **Inscripción de dispositivos > inscripción de Windows > dispositivos.**
    2. En Dispositivos Windows Autopilot, elija los dispositivos que desea eliminar y, a continuación, **elija Eliminar**.
3. Conecta el dispositivo a Internet por cable con un adaptador Ethernet de marca Surface. Reinicia el dispositivo y abre el menú UEFI (mantén presionado el botón de subir volumen mientras también presionas y suelta el botón de encendido).
4. Seleccione **Administración > Configurar > actualizar** desde la red y, a continuación, elija No **participar.**

Para seguir administrando el dispositivo con Intune, pero sin la administración de DFCI, registra automáticamente el dispositivo en Autopilot e inscríbalo en Intune. DFCI no se aplicará a los dispositivos auto registrados.

## Más información
- [Ignite 2019: Anuncio de la administración](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) remota de la configuración de la UEFI de Surface desde Intune 
 [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md) 
- [Usar perfiles DFCI en dispositivos Windows en Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

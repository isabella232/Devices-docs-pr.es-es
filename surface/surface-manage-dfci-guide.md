---
title: Administración de Intune de la configuración de la UEFI de Surface
description: En este artículo se explica cómo configurar un entorno de DFCI en Microsoft Intune y cómo administrar la configuración del firmware para dispositivos Surface de destino.
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
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: e984741a8367935eab18351815c5f00d9f8a72b7
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228551"
---
# Administración de Intune de la configuración de la UEFI de Surface

## Introducción

La capacidad de administrar dispositivos desde la nube ha simplificado considerablemente la implementación y el aprovisionamiento de TI en todo el ciclo de vida. Con los perfiles de la interfaz de configuración de firmware (DFCI) de dispositivos integrados en [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows), la administración de Surface UEFI extiende la pila de administración moderna al nivel de hardware UEFI. DFCI es compatible con el aprovisionamiento sin contacto, elimina las contraseñas del BIOS, proporciona el control de la configuración de seguridad, incluidas las opciones de arranque y los periféricos integrados, y establece las bases para escenarios de seguridad avanzada en el futuro. Para obtener respuestas a las preguntas más frecuentes, consulte [encendido de la 2019: anuncio de la administración remota de la configuración de Surface UEFI desde Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

### Segundo plano

Al igual que con los equipos que ejecutan Windows 10, los dispositivos Surface se basan en el código almacenado en el SoC, que permite que la CPU pueda funcionar con unidades de disco duro, dispositivos de pantalla, puertos USB y otros dispositivos. Los programas almacenados en esta memoria de solo lectura (ROM) se conocen como firmware (mientras que los programas almacenados en medios dinámicos se conocen como software).

A diferencia de otros dispositivos Windows 10 disponibles actualmente en el mercado, Surface proporciona a los administradores de ti la capacidad de configurar y administrar el firmware a través de un conjunto completo de parámetros de configuración de UEFI. Esto proporciona una capa de control de hardware en la parte superior de la administración de directivas basada en software, como se implementa mediante las directivas de administración de dispositivos móviles (MDM), el administrador de configuración o la Directiva de grupo. Por ejemplo, las organizaciones que implementan dispositivos en áreas muy seguras con información confidencial pueden impedir el uso de la cámara al quitar la funcionalidad en el nivel de hardware. Desde el punto de vista del dispositivo, la desactivación de la cámara a través de una configuración de firmware es equivalente a quitar físicamente la cámara. Compare la seguridad añadida de administrar en el nivel del firmware para confiar únicamente en la configuración del software del sistema operativo. Por ejemplo, si deshabilita el servicio audio de Windows a través de una configuración de directiva en un entorno de dominio, un administrador local aún podría volver a habilitar el servicio.

### DFCI frente a SEMM

Anteriormente, la administración del firmware requirió la inactividad de los dispositivos en el modo de administración de empresa de Surface (SEMM) con el overhead de las tareas manuales intensivas en curso. A modo de ejemplo, SEMM requiere que el personal de ti acceda físicamente a cada PC para introducir un PIN de dos dígitos como parte del proceso de administración de certificados. Aunque SEMM sigue siendo una buena solución para las organizaciones en un entorno estrictamente local, la complejidad y los requisitos de ti hacen que sea costoso utilizarlos.

 Gracias a las capacidades integradas de administración de firmware UEFI en Microsoft Intune, la capacidad de bloquear el hardware se simplifica y es más fácil de usar con nuevas características para el aprovisionamiento, la seguridad y la actualización simplificada en una única consola, ahora unificada como [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager). La siguiente ilustración muestra la configuración de UEFI visualizada directamente en el dispositivo (a la izquierda) y visualizada en la consola de Endpoint Manager (derecha).

![Configuración de UEFI mostrada en el dispositivo (izquierda) y en la consola de Endpoint Manager (derecha)](images/uefidfci.png)

De manera importante, DFCI habilita la administración sin toque, lo que elimina la necesidad de que los administradores de ti la interacciones sean manuales. DFCI se implementa a través de Windows AutoPilot con la funcionalidad de perfiles de dispositivos en Intune. Un perfil de dispositivo le permite agregar y configurar parámetros que se pueden implementar en dispositivos inscritos en la administración de su organización. Una vez que el dispositivo recibe el perfil del dispositivo, se aplican automáticamente las características y la configuración. Algunos ejemplos de perfiles de dispositivo comunes son el correo electrónico, las restricciones de dispositivo, VPN, Wi-Fi y las plantillas administrativas. DFCI es simplemente un perfil de dispositivo adicional que le permite administrar las opciones de configuración de UEFI desde la nube sin tener que mantener la infraestructura local.  

## Dispositivos compatibles

DFCI es compatible con los siguientes dispositivos:

- Surface Pro 7
- Surface Pro X
- Portátil Surface 3
- Surface Book 3
- Portátil Surface Go

> [!NOTE]
> Surface Pro X no admite la administración de la configuración de DFCI para cámaras, audio y Wi-Fi/Bluetooth incorporados.

## Requisitos previos

- Los dispositivos deben estar registrados con el piloto automático de Windows por un [asociado de proveedor de soluciones en la nube de Microsoft (CSP)](https://partner.microsoft.com/membership/cloud-solution-provider) o distribuidor OEM.

- Antes de configurar DFCI para Surface, debe estar familiarizado con los requisitos de configuración de AutoPilot en  [Microsoft Intune](https://docs.microsoft.com/intune/) y [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure ad).

## Antes de comenzar

Agregue los dispositivos Surface de destino a un grupo de seguridad de Azure AD. Para obtener más información sobre cómo crear y administrar grupos de seguridad, consulte la [documentación de Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

## Configurar la administración de DFCI para dispositivos Surface

Un entorno de DFCI requiere configurar un perfil de DFCI que contenga la configuración y un perfil de AutoPilot para aplicar la configuración a los dispositivos registrados. También se recomienda un perfil de estado de inscripción para asegurarse de que la configuración se inserta durante la instalación de OOBE cuando el usuario inicia el dispositivo por primera vez. Esta guía explica cómo configurar el entorno DFCI y administrar la configuración de UEFI para dispositivos Surface objetivo.

## Crear Perfil de DFCI

Antes de configurar las opciones de directiva de DFCI, cree un perfil de DFCI y asígnelo al grupo de seguridad de Azure AD que contiene los dispositivos de destino.

1. Inicie sesión en su inquilino en devicemanagement.microsoft.com.
2. En el centro de administración de Microsoft Endpoint Manager, seleccione **dispositivos > perfiles de configuración > crear perfil** y escriba un nombre. por ejemplo, la **Directiva de configuración DFCI.**
3. Seleccione **Windows 10 y versiones posteriores** para el tipo de plataforma.
4. En la lista desplegable tipo de perfil, seleccione **interfaz de configuración de firmware de dispositivo** para abrir el blade de DFCI con todas las configuraciones de directiva disponibles. Para obtener información sobre la configuración de DFCI, consulte la tabla 1 de esta página o la [documentación de Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows). Puede establecer la configuración de DFCI durante el proceso de configuración inicial o más adelante editando el perfil de DFCI.

    ![Crear Perfil de DFCI](images/df1.png)

5. Haga clic en **Aceptar** y, después, seleccione **crear**.
6. Seleccione **tareas** y, en **seleccionar grupos para incluir** , seleccione el grupo de seguridad de Azure ad que contiene los dispositivos de destino, como se muestra en la siguiente ilustración. Haga clic en **Guardar**.

    ![Asignar grupo de seguridad](images/df2a.png)

## Crear Perfil de AutoPilot

1. En Endpoint Manager en devicemanagement.microsoft.com, seleccione **dispositivos > el registro de Windows** y desplácese hacia abajo hasta **perfiles de implementación**.
2. Seleccione **crear perfil** y escriba un nombre. por ejemplo, **mi perfil de AutoPilot**y seleccione **siguiente**.
3. Seleccione la configuración siguiente:

    - Modo de implementación: **controlado por el usuario**.
    - Tipo de combinación: Unión de Azure **ad**.

4. No cambie la configuración predeterminada restante y seleccione **siguiente**, tal y como se muestra en la siguiente ilustración.

    ![Crear Perfil de AutoPilot](images/df3b.png)

5. En la página tareas, elija **seleccionar grupos para incluir** y haga clic en el grupo de seguridad de Azure ad. Selecciona **Siguiente**.
6. Acepte el Resumen y, a continuación, seleccione **crear**. El perfil de AutoPilot se ha creado y se ha asignado al grupo.

## Página configurar estado de inscripción

Para asegurarse de que los dispositivos aplican la configuración de DFCI durante la OOBE antes de que los usuarios inicien sesión, debe configurar el estado de inscripción.

Para obtener más información, consulte [configurar una página de estado de inscripción](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).


## Establecer la configuración de DFCI en dispositivos Surface

DFCI incluye un conjunto simplificado de directivas de configuración de UEFI que proporcionan un nivel adicional de seguridad al bloquear dispositivos en el nivel de hardware. DFCI está diseñado para usarse conjuntamente con la configuración de administración de dispositivos móviles en el nivel de software. Ten en cuenta que la configuración de DFCI solo afecta a los componentes de hardware creados en dispositivos Surface y no se extiende a periféricos conectados, como cámaras web USB. (Sin embargo, puede usar las directivas de restricción de dispositivos en Intune para desactivar el acceso a los periféricos conectados a nivel de software).

Para configurar las opciones de directiva de DFCI, edite el perfil de DFCI desde Endpoint Manager, como se muestra en la siguiente ilustración. 

- En Endpoint Manager en devicemanagement.microsoft.com, seleccione **dispositivos > perfiles de configuración de Windows > > "DFCI Profile name" > Properties > Settings**.

    ![Establecer la configuración de DFCI](images/dfciconfig.png)

### Bloquear el acceso de usuarios a la configuración de UEFI

Para muchos clientes, la capacidad de bloquear a los usuarios de cambiar la configuración de UEFI es crítica y una razón principal para usar DFCI. Como se muestra en la tabla 1, esto se administra mediante la configuración **permitir que el usuario local cambie la configuración de UEFI**. Si no modifica ni establece esta configuración, los usuarios locales podrán cambiar cualquier configuración de UEFI no administrada por Intune. Por lo tanto, se recomienda encarecidamente deshabilitar permitir que un **usuario local cambie la configuración de UEFI.**
El resto de la configuración de DFCI le permite desactivar la funcionalidad que, de otro modo, estaría disponible para los usuarios. Por ejemplo, si necesita proteger la información confidencial en áreas de alta seguridad, puede deshabilitar la cámara y, si no quiere que los usuarios inicien desde unidades USB, también puede deshabilitarla.

### Tabla 1. Escenarios de DFCI

| Objetivo de la administración de dispositivos                        | Pasos de configuración                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Impedir que los usuarios locales cambien la configuración de UEFI | En **características de seguridad > permitir que el usuario local cambie la configuración de UEFI**, seleccione **ninguno**.              |
| Deshabilitar cámaras                               | En **cámaras > integradas en hardware**, seleccione **deshabilitado**.                                       |
| Deshabilitar micrófonos y altavoces              | En **hardware integrado > micrófonos y altavoces**, seleccione **deshabilitado**.                      |
| Deshabilitar radios (Bluetooth, Wi-Fi)             | En **Hardware > integrada (Bluetooth, WiFi, etc.)**, seleccione **deshabilitado**.                   |
| Deshabilitar el arranque a partir de medios externos (USB, SD)    | En **hardware integrado > opciones de inicio > arranque desde medios externos (USB, SD)**, seleccione **deshabilitado**. |

> [!CAUTION]
> La opción **deshabilitar radios (Bluetooth, Wi-Fi)** solo debe usarse en dispositivos que tengan una conexión Ethernet cableada.
 
> [!NOTE]
>  DFCI en Intune incluye dos opciones de configuración que actualmente no se aplican a los dispositivos de Surface: (1) virtualización de e/s y (2) deshabilite el inicio desde los adaptadores de red.
 
Intune proporciona etiquetas de ámbito para delegar derechos de administración y reglas de aplicabilidad para administrar tipos de dispositivos. Para obtener más información sobre la compatibilidad de administración de directivas y todos los detalles sobre la configuración de DFCI, consulte la [documentación de Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).

## Registrar dispositivos en AutoPilot

Como se indicó anteriormente, DFCI solo se puede aplicar en dispositivos registrados en Windows AutoPilot por su distribuidor o distribuidor y solo se admite, en este momento, en Surface Pro 7, Surface Pro X y Surface Laptop 3. Por razones de seguridad, no es posible "autoaprovisionar" sus dispositivos en AutoPilot.

## Sincronizar manualmente dispositivos AutoPilot

Aunque la configuración de la Directiva de Intune generalmente se aplica casi inmediatamente, puede haber un retraso de 10 minutos antes de que la configuración surta efecto en los dispositivos de destino. En raras ocasiones, es posible que se produzcan demoras de hasta 8 horas. Para asegurarse de que la configuración se aplique lo antes posible (como en los escenarios de prueba), puede sincronizar manualmente los dispositivos de destino.

- En Endpoint Manager en devicemanagement.microsoft.com, vaya a **dispositivos > inscripción de dispositivos > la inscripción de windows > dispositivos de AutoPilot de Windows** y seleccione **sincronizar**.

 Para obtener más información, consulte [sincronizar el dispositivo de Windows de forma manual](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

> [!NOTE]
> Al ajustar la configuración directamente en UEFI, debe asegurarse de que el dispositivo se reinicie por completo en el inicio de sesión estándar de Windows.

## Comprobar la configuración de UEFI en dispositivos administrados por DFCI

En un entorno de prueba, puede verificar la configuración en la interfaz UEFI de la superficie.

1. Superficie abierta UEFI, que implica presionar los botones de **encendido** y de **volumen** al mismo tiempo.
2. Seleccione **dispositivos**. El menú UEFI reflejará la configuración configurada, tal como se muestra en la siguiente ilustración.

    ![Superficie UEFI](images/df3.png)

    Observe cómo:

      - La configuración está atenuada porque permitir que el **usuario local cambie la configuración de UEFI** está establecida en ninguno.
      - El audio se establece en desactivado porque los **micrófonos y los altavoces** están **deshabilitados**.

## Quitar la configuración de directiva de DFCI

Al crear un perfil de DFCI, todos los valores configurados seguirán vigentes en todos los dispositivos dentro del ámbito de administración del perfil. Solo puedes quitar la configuración de la Directiva de DFCI editando el perfil de DFCI directamente.

Si se ha eliminado el perfil de DFCI original, puede quitar la configuración de la Directiva creando un nuevo perfil y, a continuación, editando la configuración, según corresponda.

## Quitar la administración de DFCI

**Para quitar la administración de DFCI y devolver el dispositivo al nuevo estado de fábrica:**

1. Retirar el dispositivo de Intune:
    1. En Endpoint Manager en devicemanagement.microsoft.com, elija **groups > todos los dispositivos**. Seleccione los dispositivos que desea retirar y, a continuación, elija **retirada/borrado.** Para obtener más información [, consulte quitar dispositivos mediante el borrado, la retirada o la desafiliación manual del dispositivo](https://docs.microsoft.com/intune/remote-actions/devices-wipe). 
2. Eliminar el registro de AutoPilot de Intune:
    1.  Elija **inscripción de dispositivos > dispositivos de inscripción de Windows >**.
    2. En dispositivos de Windows AutoPilot, elija los dispositivos que desea eliminar y, a continuación, elija **eliminar**.
3. Conecta el dispositivo a Internet por cable con un adaptador Ethernet de marca superficial. Reinicie el dispositivo y abra el menú de UEFI (mantenga presionado el botón de subir el volumen mientras pulsa y suelta el botón de encendido).
4. Seleccione **administración > configurar > actualizar desde la red** y, a continuación, elija **la opción de cancelación.**

Para mantener la administración del dispositivo con Intune, pero sin la administración DFCI, registre automáticamente el dispositivo en autopiloto y regístrelo a Intune. DFCI no se aplicará a los dispositivos autofirmados.

## Obtén más información
- [Encendido 2019: anuncio de la administración remota de la configuración de Surface UEFI de Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
 [Windows AutoPilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md) 
- [Usar perfiles de DFCI en dispositivos Windows en Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)

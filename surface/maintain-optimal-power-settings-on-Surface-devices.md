---
title: Procedimiento recomendado de configuración de energía para dispositivos Surface
description: En este tema se describen los procedimientos recomendados para mantener la configuración de energía óptima y se explica cómo la superficie racionaliza la experiencia de administración de energía. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7, Surface Pro X y Surface Laptop 3.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834658"
---
# Procedimiento recomendado de configuración de energía para dispositivos Surface

Los dispositivos Surface están diseñados para aprovechar los últimos adelantos en el consumo de energía de los dispositivos móviles para ofrecer una experiencia optimizada optimizada en todas las cargas de trabajo. En función de lo que haga, Surface ajustará de manera dinámica cómo fluye el suministro de energía a componentes de hardware individuales, con lo que se activarán momentáneamente los componentes del sistema para controlar las tareas en segundo plano, como un correo electrónico entrante o un tráfico de red, antes de volver a un estado inactivo de bajo consumo (S0ix).

## Resumen de recomendaciones para administradores de ti

Para garantizar que los dispositivos Surface de toda la organización se beneficien totalmente de las características de optimización de energía:

-  Instale los drivers y el firmware más recientes desde Windows Update, el controlador de superficie y el MSI de firmware. Esto crea el plan de energía equilibrado (conocido como perfil de alimentación) de forma predeterminada y configura las opciones de energía óptimas.  Para obtener más información, consulte [administrar e implementar actualizaciones de controlador y firmware de superficie](manage-surface-driver-and-firmware-updates.md).
- Evite crear perfiles de energía personalizados o ajustar la configuración de energía avanzada no visible en la interfaz de usuario predeterminada (alimentación**del sistema**  >  **& suspensión**).
- Si debe administrar el perfil de energía de los dispositivos de toda la red (por ejemplo, en organizaciones muy administradas), use la herramienta powercfg para exportar el plan de energía de la imagen de fábrica del dispositivo Surface y, a continuación, impórtelo en el paquete de aprovisionamiento para sus dispositivos Surface. 

    >[!NOTE]
    >Solo puede exportar un plan de energía en el mismo tipo de dispositivo Surface.  Por ejemplo, no puede exportar un plan de energía desde un portátil Surface y importarlo en Surface Pro.  Para obtener más información, consulte [configurar opciones de energía](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).

- Excluya los dispositivos de la superficie de la configuración de la Directiva de administración de energía existente. 

## Segundo plano

La manera en que la superficie implementa la administración de energía difiere significativamente del estándar anterior del sistema operativo que reduce y apaga gradualmente la energía a través de una serie de Estados de espera. por ejemplo, pasando por S1, S2, S3, etc.

En su lugar, la superficie se ha representando con un perfil de energía personalizado que reemplaza la funcionalidad de suspensión y consumo de energía heredada por características modernas de espera y ajuste dinámico. Este perfil de energía personalizado se implementa mediante el controlador del concentrador serie de Surface y el módulo de agregador del sistema (SAM). El chip SAM funciona como el propietario de la política de energía del dispositivo Surface, que usa algoritmos para calcular los requisitos de energía óptimos. Funciona junto con el administrador de energía de Windows para asignar o limitar solo la cantidad de energía exacta necesaria para que los componentes de hardware funcionen. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7, Surface Pro X y Surface Laptop 3.

## Uso del perfil de energía personalizado en Surface

Si pasas a las opciones de energía en un dispositivo Surface, verás que hay un solo plan de energía disponible. Este es el perfil de energía personalizado. Y si va a la configuración avanzada de energía, verá un subconjunto mucho más pequeño de opciones de energía en comparación con un PC genérico con Windows 10. A diferencia de los dispositivos genéricos, Surface tiene firmware y componentes personalizados para administrar estas opciones de energía.


## Standby moderno

El perfil de energía personalizado incrustado por algoritmos permite la conectividad de reserva moderna para Surface manteniendo un estado de bajo consumo para la funcionalidad de encendido/apagado instantáneo típica de smartphones. S0ix, también conocido como el estado de plataforma inactiva en tiempo de ejecución más profundo, es el modo de energía predeterminado para dispositivos Surface. El modo de espera moderno tiene dos modos:

- **Modo de espera conectado.** El modo predeterminado para la entrega de mensajes de correo electrónico, mensajes y datos sincronizados en la nube al momento del minuto, el modo de espera conectado mantiene Wi-Fi activado y mantiene la conectividad de red.

- **Modo de espera desconectado.** Un modo opcional de prolongación de la duración de la batería, el modo de espera desconectado ofrece la misma experiencia instantánea y ahorra energía desactivando Wi-Fi, Bluetooth y conectividad de red relacionada.

Para obtener más información sobre la espera moderna, consulte el [centro de desarrollo de hardware de Microsoft](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## Cómo la superficie simplifica la experiencia de administración de energía 

Surface integra las siguientes características diseñadas para ayudar a los usuarios a optimizar la experiencia de administración de energía:

- [Plan de energía singular](#singular-power-plan)

- [Interfaz de usuario de configuración de energía simplificada](#simplified-power-settings-user-interface)

- [Control deslizante de rendimiento de Windows](#windows-performance-power-slider)

### Plan de energía singular

Surface está diseñado para una experiencia de administración de energía simplificada que elimina la necesidad de crear planes de energía personalizados o configurar manualmente las opciones de energía. Microsoft optimiza la experiencia del usuario al ofrecer un plan de energía único (equilibrado) que reemplaza los diversos planes de energía de las compilaciones estándar de Windows.

### Interfaz de usuario de configuración de energía simplificada

Surface proporciona una interfaz de usuario simplificada de acuerdo con las recomendaciones de configuración de energía de procedimientos recomendados. En general, se recomienda ajustar la configuración visible en la interfaz de usuario predeterminada y evitar la configuración avanzada de la configuración de energía o de la Directiva de grupo. Usar la pantalla predeterminada y los tiempos de espera de suspensión, evitando los niveles de brillo máximos son las formas más eficaces para que los usuarios mantengan una mayor duración de la batería.

![Figura 1. Configuración simplificada de energía & suspensión](images/powerintrofig1.png)

Figura 1. Configuración de energía y suspensión simplificada

### Control deslizante de rendimiento de Windows

Los dispositivos Surface que ejecutan Windows 10 compilación 1709 y versiones posteriores incluyen un control deslizante de encendido que le permite priorizar la duración de la batería cuando sea necesario o favorecer el rendimiento si lo desea. Para acceder al control deslizante de la barra de tareas, haga clic en el icono de la batería. Deslizar a la izquierda para una mayor duración de la batería (modo de ahorro de batería) o hacia la derecha para obtener un rendimiento más rápido.

![Figura 2. Control deslizante de encendido](images/powerintrofig2a.png)

Figura 2. Control deslizante de encendido

El control deslizante de encendido permite cuatro Estados, tal y como se describe en la tabla siguiente:

| Modo de control deslizante| Descripción |
|---|---|
| Ahorro de batería| Ayuda a ahorrar energía y prolongar la duración de la batería cuando el sistema se desconecta de una fuente de alimentación. Cuando el ahorro de batería está activado, algunas características de Windows se deshabilitan, se limitan o se comportan de manera diferente. También se reduce el brillo de la pantalla. El ahorro de batería solo está disponible cuando se usa la energía de la batería (DC). Para obtener más información, consulte [ahorro de batería](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).|
| Recomendaciones | Ofrece una mayor duración de la batería que la configuración predeterminada de versiones anteriores de Windows. |
| Mejor rendimiento | Favorece ligeramente el rendimiento de la duración de la batería, funcionando como el modo de control deslizante predeterminado. |
| Mejor rendimiento | Favorece el rendimiento por la energía de las cargas de trabajo que requieren el máximo rendimiento y la capacidad de respuesta, independientemente del consumo de energía de la batería.|

Los modos de control deslizante de energía controlan directamente los componentes de hardware específicos que se muestran en la tabla siguiente.

| Componente | Funcionalidad Slider |
|---|---|
| Sugerencia de preferencia de cambio de velocidad de Intel (registro de energía de CPU) y rendimiento de energía. | Selecciona la mejor frecuencia de funcionamiento y el voltaje para obtener un rendimiento y una potencia óptimos. La preferencia de rendimiento energético (PERFEPP) es una indicación global de eficiencia energética para la CPU. |
| Velocidad de ventilador (RPM)| Donde corresponda, se ajusta para las condiciones cambiantes como mantener el ventilador en modo deslizante de ahorro de batería.|
| Límites de potencia del paquete del procesador (PL1/PL2).| Requiere que la CPU administre las opciones de frecuencia para dar cabida a un límite de potencia promedio móvil para las cargas de trabajo de estado fijo (PL1) y Turbo (PL2).|
| Límites de frecuencia del procesador Turbo (limitaciones del IA Turbo). | Ajusta el rendimiento de los procesadores y gráficos para que los núcleos de procesador se ejecuten más rápido o más lento que la frecuencia de funcionamiento calificada.                                                |

>[!NOTE]
>El control deslizante de energía es totalmente independiente de la configuración de energía del sistema operativo, ya sea que esté configurado desde el panel de control o las opciones de energía, la Directiva de grupo o métodos relacionados.

Para obtener más información, consulte:

-   [Personalizar el control deslizante de rendimiento de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Ahorro de batería.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Procedimientos recomendados para prolongar la duración de la batería


| Procedimiento recomendado | Ve a | Pasos siguientes |
|---|---|---|                                                                                                                                    
| Asegúrate de que tu dispositivo Surface esté actualizado| Windows Update | En el cuadro búsqueda de la barra de tareas, escriba **Windows Update** y seleccione **Buscar actualizaciones**. |
| Elegir la mejor configuración de energía para lo que está haciendo | Control deslizante de encendido | En la barra de tareas, seleccione el icono de la batería y, a continuación, elija **mejor rendimiento**, **mejor duración**de la batería o en cualquier parte de.|
| Ahorrar batería cuando está baja | Ahorro de batería | En la barra de tareas, seleccione el icono de la batería y haga clic en **configuración de batería**. Seleccione **activar automáticamente el ahorro de batería si la batería cae por debajo** y, después, mueva el control deslizante hacia la derecha para obtener una mayor duración de la batería. |
| Configurar el brillo óptimo de la pantalla | Ahorro de batería | En la barra de tareas, seleccione el icono de batería y haga clic en **configuración de batería**, seleccione **brillo de pantalla bajo en ahorro de batería**. |
| Ahorrar energía cuando no estés conectado | Ahorro de batería| Seleccione **activar el estado del ahorro de batería hasta el próximo cobro**.|
| Investigue los problemas con la configuración de energía. | Solucionador de problemas de energía | En la barra de tareas, busque solucionar problemas, seleccione **solucionar problemas**y, a continuación, seleccione **energía** y siga las instrucciones.|
| Comprobar el uso de la aplicación | Tus aplicaciones | Cierre aplicaciones.|
| Comprueba si hay daños en el cable de alimentación.| El cable de alimentación | Sustituya el cable de alimentación si está desgastado o dañado.|

## Obtén más información 

- [Standby moderno](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar el control deslizante de rendimiento de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Ahorro de batería](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Administrar e implementar actualizaciones de drivers y firmware de Surface](manage-surface-driver-and-firmware-updates.md)

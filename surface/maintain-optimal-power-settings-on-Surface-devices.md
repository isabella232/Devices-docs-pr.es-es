---
title: Procedimiento recomendado de configuración de energía para dispositivos Surface
description: En este tema se proporcionan recomendaciones de procedimientos recomendados para mantener una configuración de energía óptima y se explica cómo Surface simplifica la experiencia de administración de energía. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7+, Surface Pro 7, Surface Pro X y Surface Laptop 3.
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
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: b4a9a1756abc4d7a45c5b4eb5081e8f5a72565eb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448313"
---
# <a name="best-practice-power-settings-for-surface-devices"></a>Procedimiento recomendado de configuración de energía para dispositivos Surface

Los dispositivos Surface están diseñados para aprovechar los últimos avances en el consumo de energía de dispositivos móviles para ofrecer una experiencia optimizada en todas las cargas de trabajo. En función de lo que estés haciendo, Surface ajusta dinámicamente cómo fluye la energía a componentes de hardware individuales, lo que activa momentáneamente los componentes del sistema para controlar las tareas en segundo plano ,como un correo electrónico entrante o el tráfico de red, antes de volver a un estado de inactividad de baja potencia (S0ix).

## <a name="summary-of-recommendations-for-it-administrators"></a>Resumen de recomendaciones para administradores de TI

Para garantizar que los dispositivos Surface de toda la organización se beneficien completamente de las características de optimización de energía de Surface:

-  Instala los controladores y firmware más recientes de Windows Update o el MSI de controlador y firmware de Surface. Esto crea el plan de energía equilibrado (también conocido como perfil de energía) de forma predeterminada y configura una configuración de energía óptima.  Para obtener más información, consulta [Administrar e implementar actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md).
- Evite crear perfiles de energía personalizados o ajustar la configuración avanzada de energía no visible en la interfaz de usuario predeterminada (**SystemPower** >  **& suspensión**).
- Si debes administrar el perfil de energía de los dispositivos en toda la red (por ejemplo, en organizaciones altamente administradas), usa la herramienta de comandos powercfg para exportar el plan de energía desde la imagen de fábrica del dispositivo Surface y luego importarlo al paquete de aprovisionamiento para tus dispositivos Surface. 

    >[!NOTE]
    >Solo puedes exportar un plan de energía en el mismo tipo de dispositivo Surface.  Por ejemplo, no puede exportar un plan de energía desde Surface Laptop e importarlo en Surface Pro.  Para obtener más información, consulte [Configure power settings](/windows-hardware/customize/power-settings/configure-power-settings).

- Excluir dispositivos Surface de cualquier configuración de directiva de administración de energía existente. 

## <a name="background"></a>Segundo plano

La forma en que Surface implementa la administración de energía difiere significativamente del estándar anterior del sistema operativo que reduce y desactiva gradualmente la energía a través de una serie de estados de suspensión; por ejemplo, el ciclo a través de S1, S2, S3, y así sucesivamente.

En su lugar, Surface se muestra con un perfil de energía personalizado que reemplaza la funcionalidad heredada de suspensión y consumo de energía por características modernas de espera y ajuste dinámico. Este perfil de energía personalizado se implementa a través del controlador de Surface Serial Hub y el módulo de agregador de sistema (SAM). El chip SAM funciona como el propietario de la directiva de energía del dispositivo Surface, usando algoritmos para calcular los requisitos de energía óptimos. Funciona junto con Windows de energía para asignar o limitar solo la cantidad exacta de energía necesaria para que funcionen los componentes de hardware. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X y Surface Laptop 3.

## <a name="utilizing-the-custom-power-profile-in-surface"></a>Uso del perfil de energía personalizado en Surface

Si vas a las opciones de energía de un dispositivo surface, verás que hay un solo plan de energía disponible. Este es el perfil de energía personalizado. Y si vas a la configuración avanzada de energía, verás un subconjunto mucho más pequeño de opciones de energía en comparación con un equipo genérico que ejecuta Windows 10 o Windows 11. A diferencia de los dispositivos genéricos, Surface tiene firmware y componentes personalizados para administrar estas opciones de energía.


## <a name="modern-standby"></a>Espera moderna

El perfil de energía personalizado incrustado algorítmicamente permite la conectividad de espera moderna para Surface manteniendo un estado de energía bajo para la funcionalidad de encendido y apagado instantáneo típica de los smartphones. S0ix, también conocido como Deepest Runtime Idle Platform State (DRIPS), es el modo de alimentación predeterminado para dispositivos Surface. El modo de espera moderno tiene dos modos:

- **Modo de espera conectado.** El modo predeterminado para la entrega al minuto de mensajes de correo electrónico, mensajería y datos sincronizados en la nube, el modo de espera conectado mantiene Wi-Fi y mantiene la conectividad de red.

- **Modo de espera desconectado.** Un modo opcional para una duración prolongada de la batería, el modo de espera desconectado ofrece la misma experiencia instantánea y ahorra energía desactivando la conectividad de red wi-fi, Bluetooth y la conectividad de red relacionada.

Para obtener más información sobre el modo de espera moderno, consulte microsoft [Centro de desarrollo de hardware](/windows-hardware/design/device-experiences/modern-standby-wake-sources).

## <a name="how-surface-streamlines-the-power-management-experience"></a>Cómo Surface simplifica la experiencia de administración de energía 

Surface integra las siguientes características diseñadas para ayudar a los usuarios a optimizar la experiencia de administración de energía:

- [Plan de energía singular](#singular-power-plan)

- [Interfaz de usuario de configuración de energía simplificada](#simplified-power-settings-user-interface)

- [Windows control deslizante de potencia de rendimiento](#windows-performance-power-slider)

### <a name="singular-power-plan"></a>Plan de energía singular

Surface está diseñado para una experiencia de administración de energía optimizada que elimina la necesidad de crear planes de energía personalizados o configurar manualmente la configuración de energía. Microsoft simplifica la experiencia del usuario al ofrecer un solo plan de energía (equilibrado) que reemplaza los múltiples planes de energía de las compilaciones Windows estándar.

### <a name="simplified-power-settings-user-interface"></a>Interfaz de usuario de configuración de energía simplificada

Surface proporciona una interfaz de usuario simplificada de acuerdo con las recomendaciones de configuración de potencia de procedimiento recomendado. En general, se recomienda ajustar solo la configuración visible en la interfaz de usuario predeterminada y evitar la configuración avanzada de energía o la configuración de directiva de grupo. El uso de la pantalla predeterminada y los tiempos de espera de suspensión mientras se evitan los niveles máximos de brillo son las formas más eficaces para que los usuarios mantengan una duración prolongada de la batería.

![Figura 1. Configuración simplificada de & de suspensión.](images/powerintrofig1.png)

Figura 1. Configuración simplificada de energía y suspensión

### <a name="windows-performance-power-slider"></a>Windows control deslizante de potencia de rendimiento

Los dispositivos Surface Windows 10 compilación 1709 y posteriores incluyen un control deslizante de energía que te permite priorizar la duración de la batería cuando sea necesario o favorecer el rendimiento si lo deseas. Puedes acceder al control deslizante de energía desde la barra de tareas haciendo clic en el icono de batería. Deslizar a la izquierda para una mayor duración de la batería (modo de ahorro de batería) o deslizar hacia la derecha para un rendimiento más rápido.

![Figura 2. Control deslizante de energía.](images/powerintrofig2a.png)

Figura 2. Control deslizante de energía

El control deslizante de energía habilita cuatro estados como se describe en la tabla siguiente:

| Modo deslizante| Descripción |
|---|---|
| Ahorro de batería| Ayuda a conservar la energía y prolongar la duración de la batería cuando el sistema está desconectado de una fuente de alimentación. Cuando el ahorro de batería está activado, algunas Windows se deshabilitan, limitan o se comportan de forma diferente. El brillo de la pantalla también se reduce. El ahorro de batería solo está disponible cuando se usa energía de batería (DC). Para obtener más información, consulta [Ahorro de batería](/windows-hardware/design/component-guidelines/battery-saver).|
| Recomendaciones | Ofrece una duración de batería más larga que la configuración predeterminada en versiones anteriores de Windows. |
| Mejor rendimiento | Favorece ligeramente el rendimiento sobre la duración de la batería, funcionando como el modo de control deslizante predeterminado. |
| Mejor rendimiento | Favorece el rendimiento sobre la potencia de las cargas de trabajo que requieren el máximo rendimiento y capacidad de respuesta, independientemente del consumo de energía de la batería.|

Los modos de control deslizante de energía controlan directamente componentes de hardware específicos que se muestran en la tabla siguiente.

| Componente | Funcionalidad de control deslizante |
|---|---|
| Cambio de velocidad intel (registros de energía de CPU) y sugerencia de preferencia de rendimiento de energía. | Selecciona la mejor frecuencia de funcionamiento y tensión para un rendimiento y una potencia óptimos. La preferencia de rendimiento energético (PERFEPP) es una sugerencia global de eficiencia energética para la CPU. |
| Velocidad del ventilador (RPM)| Cuando corresponda, se ajusta para cambiar las condiciones, como mantener el ventilador silencioso en modo deslizante de ahorro de batería.|
| Límites de potencia del paquete de procesador (PL1/PL2).| Requiere que la CPU administre sus opciones de frecuencia para adaptarse a un límite de energía promedio en ejecución para cargas de trabajo de estado estable (PL1) y de turbo (PL2).|
| Límites de frecuencia de turbo del procesador (limitaciones de IA). | Ajusta el rendimiento del procesador y los gráficos, lo que permite que los núcleos del procesador se ejecuten más rápido o más lento que la frecuencia de funcionamiento nominal.                                                |

>[!NOTE]
>El control deslizante de energía es totalmente independiente de la configuración de energía del sistema operativo, ya sea configurada desde el Panel de control/ Opciones de energía, directiva de grupo o métodos relacionados.

Para obtener más información, vea:

-   [Personalizar el control Windows de potencia de rendimiento](/windows-hardware/customize/desktop/customize-power-slider)

-   [Ahorro de batería.](/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a>Procedimientos recomendados para una duración prolongada de la batería


| Procedimiento recomendado | Ve a | Pasos siguientes |
|---|---|---|                                                                                                                                    
| Asegúrate de que el dispositivo Surface esté actualizado| Windows Update | En el cuadro de búsqueda de la barra de tareas, **escriba Windows Actualizar** y **seleccione Buscar actualizaciones**. |
| Elija la mejor configuración de energía para lo que está haciendo | Control deslizante de energía | En la barra de tareas, selecciona el icono de batería y, a continuación **, elige** Mejor rendimiento, **Mejor duración de** la batería o en algún lugar entre.|
| Conservar la batería cuando está baja | Ahorro de batería | En la barra de tareas, selecciona el icono de batería y haz clic en **Configuración de la batería**. Selecciona **Activar automáticamente el ahorro** de batería si la batería está por debajo y, a continuación, mueve el control deslizante hacia la derecha para una mayor duración de la batería. |
| Configurar el brillo óptimo de la pantalla | Ahorro de batería | En la barra de tareas, selecciona el icono de batería y **haz clic en** Configuración de la batería, selecciona Brillo inferior de la pantalla **mientras ahorras batería**. |
| Conservar energía siempre que no esté conectado | Ahorro de batería| Selecciona **Activar el estado del ahorro de batería hasta la próxima carga**.|
| Investigar problemas con la configuración de energía. | Solucionador de problemas de energía | En la barra de tareas buscar solución de problemas, seleccione **Solucionar** problemas y, a continuación, **seleccione Energía** y siga las instrucciones.|
| Comprobar el uso de la aplicación | Tus aplicaciones | Cerrar aplicaciones.|
| Compruebe si el cable de alimentación está dañado.| El cable de alimentación | Reemplace el cable de alimentación si está gastado o dañado.|

## <a name="learn-more"></a>Obtén más información 

- [Espera moderna](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar el control Windows de potencia de rendimiento](/windows-hardware/customize/desktop/customize-power-slider)

- [Ahorro de batería](/windows-hardware/design/component-guidelines/battery-saver)
- [Administrar e implementar actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md)

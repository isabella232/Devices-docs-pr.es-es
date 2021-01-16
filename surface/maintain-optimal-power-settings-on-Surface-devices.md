---
title: Procedimiento recomendado de configuración de energía para dispositivos Surface
description: En este tema se proporcionan recomendaciones para mantener una configuración de energía óptima y se explica cómo Surface simplifica la experiencia de administración de energía. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7+, Surface Pro 7, Surface Pro X y Surface Laptop 3.
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
ms.openlocfilehash: 54aff228e8a72d413fc53bd14fe15d8ad7b15ab0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271404"
---
# Procedimiento recomendado de configuración de energía para dispositivos Surface

Los dispositivos Surface están diseñados para aprovechar los últimos avances en el consumo de energía de dispositivos móviles para ofrecer una experiencia optimizada en todas las cargas de trabajo. En función de lo que estés haciendo, Surface ajusta dinámicamente la forma en que fluye la energía a componentes de hardware individuales, activando momentáneamente los componentes del sistema para controlar las tareas en segundo plano , como un correo electrónico entrante o el tráfico de red, antes de volver a un estado inactivo de bajo consumo (S0ix).

## Resumen de recomendaciones para administradores de TI

Para garantizar que los dispositivos Surface de toda la organización se beneficien completamente de las características de optimización de energía de Surface:

-  Instala los controladores y el firmware más recientes de Windows Update o el MSI de controladores y firmware de Surface. Esto crea el plan de energía equilibrado (también conocido como perfil de energía) de forma predeterminada y configura opciones de energía óptimas.  Para obtener más información, consulta [Administrar e implementar actualizaciones de controladores y firmware de Surface.](manage-surface-driver-and-firmware-updates.md)
- Evita crear perfiles de energía personalizados o ajustar la configuración avanzada de energía no visible en la interfaz de usuario predeterminada (**Sistema**  >  **de energía & suspensión**).
- Si debes administrar el perfil de energía de los dispositivos en toda la red (por ejemplo, en organizaciones altamente administradas), usa la herramienta de comandos powercfg para exportar el plan de energía desde la imagen de fábrica del dispositivo Surface y luego importarlo en el paquete de aprovisionamiento de los dispositivos Surface. 

    >[!NOTE]
    >Solo puedes exportar un plan de energía en el mismo tipo de dispositivo Surface.  Por ejemplo, no puedes exportar un plan de energía desde Surface Laptop e importarlo en Surface Pro.  Para obtener más información, consulte [Configuración de la energía.](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)

- Excluye los dispositivos Surface de cualquier configuración de directiva de administración de energía existente. 

## Segundo plano

La forma en que Surface implementa la administración de energía difiere significativamente del estándar anterior del sistema operativo que reduce y desactiva gradualmente la energía a través de una serie de estados de suspensión; por ejemplo, el ciclo por S1, S2, S3, y así sucesivamente.

En su lugar, Surface se muestra con un perfil de energía personalizado que reemplaza la funcionalidad heredada de suspensión y consumo de energía por características modernas de espera y ajuste dinámico. Este perfil de energía personalizado se implementa a través del controlador de Surface Serial Hub y el módulo de agregador del sistema (SAM). El chip SAM funciona como el propietario de la directiva de energía del dispositivo Surface, usando algoritmos para calcular los requisitos de energía óptimos. Funciona junto con el Administrador de energía de Windows para asignar o limitar solo la cantidad exacta de energía necesaria para que funcionen los componentes de hardware. Este artículo se aplica a todos los dispositivos Surface compatibles actualmente, incluidos Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X y Surface Laptop 3.

## Uso del perfil de energía personalizado en Surface

Si entras en las opciones de energía en un dispositivo surface, verás que hay un único plan de energía disponible. Este es el perfil de energía personalizado. Y si vas a la configuración avanzada de energía, verás un subconjunto mucho más pequeño de opciones de energía en comparación con un equipo genérico que ejecuta Windows 10. A diferencia de los dispositivos genéricos, Surface tiene firmware y componentes personalizados para administrar estas opciones de energía.


## Espera moderna

El perfil de energía personalizado incrustado de forma algorítmica permite la conectividad de espera moderna para Surface al mantener un estado de bajo consumo para la funcionalidad de encendido y apagado instantáneo típica de los smartphones. S0ix, también conocido como Estado de la plataforma inactiva de Tiempo de ejecución de desenlazado (DESENLAZ), es el modo de energía predeterminado para dispositivos Surface. El modo de espera moderno tiene dos modos:

- **Espera conectada.** El modo predeterminado para la entrega al minuto de mensajes de correo electrónico, mensajería y datos sincronizados en la nube, el modo de espera conectado mantiene Wi-Fi y mantiene la conectividad de red.

- **Espera desconectada.** Un modo opcional para una mayor duración de la batería, el modo de espera desconectado ofrece la misma experiencia de activación instantánea y ahorra energía al desactivar la conexión Wi-Fi, Bluetooth y la conectividad de red relacionada.

Para obtener más información sobre el modo de espera moderno, consulta el Centro de desarrollo [de hardware de Microsoft.](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## Cómo Surface simplifica la experiencia de administración de energía 

Surface integra las siguientes características diseñadas para ayudar a los usuarios a optimizar la experiencia de administración de energía:

- [Plan de energía singular](#singular-power-plan)

- [Interfaz de usuario de configuración de energía simplificada](#simplified-power-settings-user-interface)

- [Control deslizante de energía de rendimiento de Windows](#windows-performance-power-slider)

### Plan de energía singular

Surface está diseñado para una experiencia de administración de energía optimizada que elimina la necesidad de crear planes de energía personalizados o configurar manualmente las opciones de energía. Microsoft simplifica la experiencia del usuario al ofrecer un único plan de energía (equilibrado) que reemplaza los planes de energía múltiples de las compilaciones estándar de Windows.

### Interfaz de usuario de configuración de energía simplificada

Surface proporciona una interfaz de usuario simplificada de acuerdo con las recomendaciones de configuración de energía de prácticas recomendadas. En general, se recomienda ajustar solo la configuración visible en la interfaz de usuario predeterminada y evitar la configuración avanzada de energía o la configuración de directiva de grupo. Usar los tiempos de espera predeterminados de pantalla y de suspensión a la vez que se evitan los niveles máximos de brillo son las formas más eficaces para que los usuarios mantengan una mayor duración de la batería.

![Figura 1. Configuración de suspensión & energía simplificada](images/powerintrofig1.png)

Figura 1. Configuración de energía y suspensión simplificada

### Control deslizante de energía de rendimiento de Windows

Los dispositivos Surface que ejecutan Windows 10 compilación 1709 y versiones posteriores incluyen un control deslizante de energía que te permite priorizar la duración de la batería cuando sea necesario o mejorar el rendimiento si lo deseas. Puedes acceder al control deslizante de energía desde la barra de tareas haciendo clic en el icono de batería. Desliza hacia la izquierda para una mayor duración de la batería (modo de ahorro de batería) o desliza hacia la derecha para un rendimiento más rápido.

![Figura 2. Control deslizante de energía](images/powerintrofig2a.png)

Figura 2. Control deslizante de energía

El control deslizante de energía habilita cuatro estados como se describe en la tabla siguiente:

| Modo deslizante| Descripción |
|---|---|
| Ahorro de batería| Ayuda a ahorrar energía y a prolongar la duración de la batería cuando el sistema se desconecta de una fuente de alimentación. Cuando el ahorro de batería está activado, algunas características de Windows se deshabilitan, se limitan o se comportan de forma diferente. El brillo de la pantalla también se reduce. El ahorro de batería solo está disponible cuando se usa energía (DC). Para obtener más información, consulta [Ahorro de batería.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)|
| Recomendaciones | Proporciona una duración de la batería más larga que la configuración predeterminada en versiones anteriores de Windows. |
| Mejor rendimiento | Favorece ligeramente el rendimiento sobre la duración de la batería, funcionando como el modo de control deslizante predeterminado. |
| Mejor rendimiento | Favorece el rendimiento sobre la energía para cargas de trabajo que requieren el máximo rendimiento y capacidad de respuesta, independientemente del consumo de energía de la batería.|

Los modos de control deslizante de energía controlan directamente componentes de hardware específicos que se muestran en la tabla siguiente.

| Componente | Funcionalidad de control deslizante |
|---|---|
| Cambio de velocidad intel (registros de energía de CPU) y sugerencia de preferencia de rendimiento de energía. | Selecciona la mejor frecuencia de funcionamiento y la mejor frecuencia de respuesta para obtener un rendimiento y una potencia óptimos. La preferencia de rendimiento de energía (PERFEPP) es una sugerencia de eficiencia energética global para la CPU. |
| Velocidad del abanico (RPM)| Cuando corresponda, se ajusta para cambiar condiciones, como mantener el abanico en silencio en el modo deslizante de ahorro de batería.|
| Límites de energía del paquete de procesador (PL1/PL2).| Requiere que la CPU administre sus opciones de frecuencia para dar cabida a un límite de energía promedio en ejecución para cargas de trabajo de estado estable (PL1) y de rebosor (PL2).|
| Límites de frecuencia del procesador (limitaciones de IA turbo). | Ajusta el rendimiento del procesador y los gráficos, lo que permite que los núcleos del procesador se ejecuten más rápido o más lento que la frecuencia de funcionamiento clasificada.                                                |

>[!NOTE]
>El control deslizante de energía es totalmente independiente de la configuración de energía del sistema operativo, ya sea configurada desde el Panel de control/ Opciones de energía, directiva de grupo o métodos relacionados.

Para obtener más información, consulte:

-   [Personalizar el control deslizante de energía de rendimiento de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [Ahorro de batería.](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## Procedimientos recomendados para ampliar la duración de la batería


| Procedimiento recomendado | Ve a | Pasos siguientes |
|---|---|---|                                                                                                                                    
| Asegurarse de que el dispositivo Surface esté actualizado| Windows Update | En el cuadro de búsqueda de la barra de tareas, escriba **Windows Update** y seleccione **Buscar actualizaciones.** |
| Elegir la mejor configuración de energía para lo que está haciendo | Control deslizante de energía | En la barra de tareas, seleccione el icono de la batería y, a continuación, elija Mejor **rendimiento,** **Mejor duración**de la batería o en algún lugar entre ellos.|
| Conservar la batería cuando esté baja | Ahorro de batería | En la barra de tareas, selecciona el icono de la batería y haz clic en **Configuración de la batería.** Selecciona **Activar el ahorro de batería automáticamente** si la batería se encuentra por debajo y, a continuación, mueve el control deslizante más a la derecha para una mayor duración de la batería. |
| Configurar el brillo óptimo de la pantalla | Ahorro de batería | En la barra de tareas, selecciona el icono de la batería y haz clic en Configuración de la **batería,** selecciona Brillo inferior de la pantalla **mientras se ahorra batería.** |
| Conservar energía siempre que no esté conectado | Ahorro de batería| Selecciona **Activar el estado del ahorro de batería hasta la siguiente carga.**|
| Investiga problemas con la configuración de energía. | Solucionador de problemas de energía | En la barra de tareas, busque solución de problemas, seleccione Solucionar problemas y, a continuación, **seleccione Encendido** y siga las instrucciones. ****|
| Comprobar el uso de la aplicación | Tus aplicaciones | Cierra aplicaciones.|
| Compruebe si hay daños en el cable de alimentación.| Cable de alimentación | Reemplace el cable de alimentación si se daña o se daña.|

## Más información 

- [Espera moderna](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [Personalizar el control deslizante de energía de rendimiento de Windows](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [Ahorro de batería](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [Administrar e implementar actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md)

---
title: Solucionar problemas de Miracast en Surface Hub
description: Aprende a resolver problemas con Miracast en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836951"
---
# Soluciona problemas de Miracast en Surface Hub

Surface Hub admite la proyección inalámbrica a través del protocolo Miracast. La mayoría de los monitores y adaptadores inalámbricos disponibles hoy en día usan la implementación original de Miracast. Surface Hub usa una versión de Miracast ligeramente diferente conocida como **Miracast Autonomous Group Owner (AGO)**. Un paso común de solución de problemas cuando se produce un error en la proyección inalámbrica a Surface Hub es probar a proyectar a otro monitor o adaptador inalámbrico. Sin embargo, en la mayoría de los casos, estos dispositivos no usan Miracast AGO y no gestiona la proyección inalámbrica del mismo modo que lo hace Surface Hub.

En el Miracast tradicional, el dispositivo de proyección conectará el punto de acceso configurado por el monitor habilitado para Miracast y luego el monitor enviará el tráfico al dispositivo de proyección mediante el canal de red del este último. Miracast AGO es un proceso de conexión de dos pasos:

- El primer paso es una conexión inicial a 2,4GHz. 
- Después de ese protocolo de enlace inicial, el dispositivo de proyección envía el tráfico al monitor con la configuración de canal inalámbrico de este. Si Surface Hub está conectado a una red Wi-Fi, el punto de acceso, usará el mismo canal que la red conectada, de lo contrario usará el canal de Miracast que se indica en la configuración.

Por lo general, hay dos tipos de problemas con Miracast a Surface Hub: [conexión](#connect-issues) y [rendimiento](#performance-issues). En cualquier caso, es una buena idea obtener una imagen general de la actividad de la red inalámbrica en la ubicación del Surface Hub. Si ejecutas una herramienta de análisis de red, verás las redes disponibles y el uso de canal del entorno.

## Problemas de conexión

Asegúrate de que Wi-Fi y Miracast están habilitados en la configuración de Surface Hub. 

Si ejecutaste un análisis de red, deberías ver Surface Hub Miracast en la lista de puntos de acceso. Si la red Miracast de Surface Hub se muestra en el análisis, pero no puede verla como un dispositivo disponible, puede intentar ajustar el canal Miracast usado por Surface Hub. 

Cuando Surface Hub está conectado a una red Wi-Fi, usará la misma configuración de canal que el punto de acceso Wi-Fi para su punto de acceso de Miracast. Para solucionar problemas, desconecta Surface Hub desde las redes Wi-Fi (pero mantén Wi-Fi habilitado), para que puedas controlar el canal que se usa para Miracast. Puedes seleccionar manualmente el canal de Miracast en Configuración. Tendrás que reiniciar el Surface Hub después de cada cambio. Por lo general, es recomendable usar los canales que no muestran un uso intensivo tras el análisis de la red.

También es posible que el problema de conexión sea el resultado de un problema en el dispositivo de conexión. Si el dispositivo de proyección ejecuta Windows, debería ser Windows 8.1 o una versión posterior para asegurar compatibilidad completa con Miracast. Nuevamente, para la solución de problemas, desconecta el dispositivo de proyección de las redes Wi-Fi. De este modo, se eliminará cualquier cambio de canal entre el canal de punto de acceso y el canal de Miracast establecido en Surface Hub. Asimismo, es posible que algunas opciones de configuración de directiva de grupo y del firewall estén asociadas a una red Wi-Fi.

### Comprobar controladores

También es recomendable asegurarte de que los controladores y las actualizaciones más recientes estén instalados en el dispositivo de proyección. En el Administrador de dispositivos, abre el adaptador Wi-Fi y adaptador de vídeo, y comprueba si hay una versión de controlador actualizada. Es recomendable instalar la [revisión 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3) para Surface Pro 3 y Surface Pro 4 si estos dispositivos usan un controlador Wi-Fi más antiguo. 

### Comprobar la compatibilidad de Miracast

A continuación, asegúrate de que Miracast se admite en el dispositivo. 

1. Presiona la tecla Windows + R y escribe `dxdiag`. 
2. Haga clic en "guardar toda la información". 
3. Abre el archivo dxdiag.txt guardado y busca **Miracast**. Debe aparecer **Available, with HDCP**. 
    
### Comprobar el firewall
    
El firewall de Windows puede bloquear el tráfico de Miracast. La prueba más sencilla consiste en deshabilitar el firewall y probar la proyección. Si Miracast funciona con el firewall deshabilitado, agrega una excepción.

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### Comprobar la configuración de directiva de grupo

En los dispositivos unidos a un dominio, la directiva de grupo también puede bloquear Miracast. 

1. Usa la tecla Windows + R y escribe `rsop.msc` para ejecutar el complemento **Conjunto resultante de directivas**. De este modo, se mostrarán las directivas actuales que se aplican al equipo. 
2. Consulta la información de **Configuración del equipo** > **Configuración de Windows** > **Configuración de seguridad** > **Directivas de red inalámbrica (IEEE 802.11)**. Debería haber una opción de configuración para las directivas de conexiones inalámbricas. 
3. Haz doble clic en la configuración de las directivas conexiones inalámbricas. Aparecerá un cuadro de diálogo. 
4. Abre la pestaña **Permisos de red** y selecciona **Permitir a todos crear perfiles de todos los usuarios**.

### Comprobar los registros de eventos

El último lugar donde comprobar es en los registros de eventos. Los eventos de Miracast se registrarán en **Wlanautoconfig**. Esto sucede en Surface Hub y en el dispositivo de proyección. Si exporta los registros de Surface Hub, puede ver los Wlanautoconfig de Surface Hub en la carpeta **WindowsEventLog** . Los errores en el registro de eventos pueden proporcionar algunos detalles adicionales sobre dónde se produce el error de conexión.

## Problemas de rendimiento

Cuando se haya conectado una proyección inalámbrica, es posible se produzcan problemas de rendimiento que provocan latencia. Esto suele ser el resultado de una saturación general del canal o de una situación que provoca cambios de canal. 

En el caso de saturación del canal, consulta el análisis de red y prueba a usar canales con menos tráfico.

Los cambios de canal se producen cuando el adaptador Wi-Fi necesita enviar tráfico a varios canales. Algunos canales admiten la selección de frecuencia dinámica (DFS). DFS se usa en los canales 49 a 148. Algunos controladores Wi-Fi tendrán un rendimiento deficiente cuando se conectan a un canal DFS. Si experimentas un rendimiento deficiente de Miracast mientras estés conectado a un canal DFS, prueba a realizar la proyección en un canal que no sea DFS. Tanto Surface Hub y como el dispositivo proyección deben usar canales no DFS.

Si Surface Hub y el dispositivo de proyección están conectados a Wi-Fi, pero con distintos puntos de acceso con diferentes canales, Surface Hub y el dispositivo de proyección estará obligado a cambiar de canal mientras está conectado Miracast. Esto resultará en una proyección inalámbrica deficiente y un rendimiento de red deficiente a través de Wi-Fi. Los cambios de canal afectarán al rendimiento de todo el tráfico inalámbrico, no solo la proyección inalámbrica. 

Los cambios de canal también se producirán si el dispositivo de proyección está conectado a una red Wi-Fi con un canal diferente que el canal que Surface Hub usa para Miracast. Por lo tanto, un procedimiento recomendado es establecer el canal Miracast del Surface Hub en el mismo canal que el punto de acceso que se usa con más frecuencia. 

Si hay varios puntos de acceso o redes Wi-Fi en el entorno, es inevitable que se produzcan algunos cambios de canal. Para resolver esto, es recomendable que todos los controladores Wi-Fi estén actualizados.

## Ponerse en contacto con soporte técnico

Si tiene alguna pregunta o necesita ayuda, puede [crear una solicitud de soporte técnico](https://support.microsoft.com/supportforbusiness/productselection).

---
title: Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio
description: Cómo usar SDT para ayudar a los usuarios de tu organización a ejecutar la herramienta para identificar y diagnosticar problemas con el dispositivo Surface, así como enviar solicitudes de soporte técnico directamente desde la herramienta.
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 7/31/2020
ms.openlocfilehash: 7d09bc70a2e0c882bde9106ee2c241568c1fc991
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154135"
---
# <a name="use-surface-diagnostic-toolkit-for-business-in-desktop-mode"></a>Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio

En este tema se explica cómo usar surface diagnostic Toolkit (SDT) para ayudar a los usuarios de la organización a ejecutar la herramienta para identificar y diagnosticar problemas con su dispositivo Surface, así como enviar solicitudes de soporte técnico directamente desde la herramienta. 

La ejecución correcta de SDT puede determinar rápidamente si un problema notificado se debe a un error de hardware o de usuario. Para obtener una lista de dispositivos Surface compatibles en SDT, consulte [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).


1. Dirija al usuario a instalar [el paquete SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)) desde un punto de distribución de software o recurso compartido de red. Después de instalarlo, estará listo para guiar al usuario a través de una serie de pruebas. 

2. Comience en la página principal, que permite a los usuarios escribir una descripción del problema y haga clic en Continuar **,** como se muestra en la figura 1.

    ![Inicie SDT en modo de escritorio.](images/sdt-desk-1.png)<br/>
    *Figura 1. SDT en modo de escritorio*

3. Cuando SDT indica que el dispositivo **** tiene las actualizaciones más recientes, haz clic en Continuar para avanzar al catálogo de pruebas disponibles, como se muestra en la figura 2.

    ![Seleccione entre las opciones de SDT.](images/sdt1.png)<br/>
    *Figura 2. Seleccionar entre opciones de SDT*

4. Puede elegir ejecutar todas las pruebas de diagnóstico. O bien, si ya sospecha que hay un problema concreto, **** como una pantalla defectuosa o un problema de fuente de alimentación, haga clic en Seleccionar para elegir entre las pruebas disponibles y haga clic en Ejecutar seleccionado **,** tal como se muestra en la figura 3. Consulte la tabla siguiente para obtener más información sobre cada prueba. 

    ![Seleccione pruebas de hardware.](images/sdt2.png)<br/>
    *Figura 3. Seleccionar pruebas de hardware*

    Prueba de hardware | Descripción
    --- | ---
    Fuente de alimentación y batería |  Comprueba que la fuente de alimentación funciona de forma óptima
    Pantalla y sonido   | Comprueba el brillo, los píxeles atascados o muertos, el altavoz y el funcionamiento del micrófono
    Puertos y accesorios   | Comprueba accesorios, conexión de pantalla y funcionamiento USB
    Conectividad |  Comprueba Bluetooth, conectividad inalámbrica y LTE
    Seguridad    | Comprueba problemas relacionados con la seguridad
    Función táctil   | Comprueba los problemas relacionados con las comprobaciones
    Teclado y toque |    Comprueba la conexión de teclado integrada y la cubierta de tipos
    Sensores | Comprueba el funcionamiento de diferentes sensores en el dispositivo
    Hardware |  Comprueba problemas con diferentes componentes de hardware, como la tarjeta gráfica y la cámara

5. Una vez finalizadas todas las pruebas, la herramienta te pide que confirmes si el problema está corregido. 

    ![¿Se ha resuelto el problema?](images/sdt3.png)<br/>
    *Figura 3a. ¿Se ha resuelto el problema?*

6. Si el problema no se ha resuelto o no lo sabe, puede enviar un vale de soporte técnico seleccionando Póngase **en** contacto con nosotros para **obtener ayuda ahora.**
 
    ![Enviar un vale de soporte técnico.](images/sdt4.png)<br/>
    *Figura 3b. Enviar un vale de soporte técnico*

<span id="multiple" />

## <a name="running-multiple-hardware-tests-to-troubleshoot-issues"></a>Ejecutar varias pruebas de hardware para solucionar problemas

SDT está diseñado como una herramienta interactiva que ejecuta una serie de pruebas. Para cada prueba, SDT proporciona instrucciones que resumen la naturaleza de la prueba y lo que los usuarios deben esperar o buscar para que la prueba se haga correctamente. Por ejemplo, para diagnosticar si el brillo de la pantalla funciona correctamente, SDT comienza en cero y **** aumenta el brillo al 100 por ciento, lo que pide a los usuarios que confirmen (respondiendo Sí o **No)** que el brillo funciona como se esperaba, como se muestra en la figura 4. 

Para cada prueba, si la funcionalidad no funciona como se esperaba y el usuario hace clic en **No**, SDT genera un informe de las posibles causas y formas de solucionarlo. 

![Ejecución de diagnósticos de hardware. ](images/sdt-desk-4.png)
 *Figura 4. Ejecución de diagnósticos de hardware*

1. Si el brillo se ajusta correctamente del 0 al 100 por ciento como se esperaba, dirija al usuario a hacer clic en **Sí** y, a continuación, haga clic en **Continuar**. 
2. Si el brillo no se ajusta del 0 al 100 por ciento como se esperaba, dirija al usuario a hacer clic en **No** y, a continuación, haga clic en **Continuar**. 
3. Guía a los usuarios a través de las pruebas restantes según corresponda. Una vez terminado, SDT proporciona automáticamente un resumen de alto nivel del informe, incluidas las posibles causas de cualquier problema de hardware, junto con instrucciones para la resolución.


### <a name="repairing-applications"></a>Reparar aplicaciones

SDT permite diagnosticar y reparar aplicaciones que pueden estar causando problemas, como se muestra en la figura 5.

![Ejecución de reparaciones. ](images/sdt-desk-5.png)
 *Figura 5. Ejecución de reparaciones*
<span id="logs" />

### <a name="generating-logs-for-analyzing-issues"></a>Generación de registros para analizar problemas 

SDT proporciona una amplia compatibilidad de diagnóstico habilitada para registros en aplicaciones, controladores, hardware y problemas del sistema operativo, como se muestra en la figura 6.

![Generación de registros. ](images/sdt-desk-6.png)
 *Figura 6. Generación de registros*

<span id="detailed-report" />

### <a name="generating-detailed-report-comparing-device-vs-optimal-configuration"></a>Generación de informes detallados que comparan el dispositivo con la configuración óptima

En función de los registros, SDT genera un informe para problemas basados en software y firmware que puede guardar en una ubicación preferida.

## <a name="related-topics"></a>Temas relacionados

- [Ejecutar la consola de aplicaciones de línea de comandos con Surface Diagnostic Toolkit para empresas](surface-diagnostic-toolkit-command-line.md)

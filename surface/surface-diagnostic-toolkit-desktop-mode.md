---
title: Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio
description: Cómo usar SDT para ayudar a los usuarios de su organización a ejecutar la herramienta para identificar y diagnosticar problemas con el dispositivo Surface, así como enviar solicitudes de asistencia directamente desde la herramienta.
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
ms.openlocfilehash: 8b113d16f2053fe0904518b2643f1bafeaebdf64
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145945"
---
# Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio

En este tema se explica cómo usar el kit de herramientas de diagnóstico de Surface (SDT) para ayudar a los usuarios de su organización a ejecutar la herramienta para identificar y diagnosticar problemas con su dispositivo Surface, así como enviar solicitudes de asistencia directamente desde la herramienta. 

La ejecución correcta de SDT puede determinar rápidamente si un problema notificado se debe a un error de hardware o de usuario. Para obtener una lista de los dispositivos Surface admitidos en SDT, consulte [deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).


1. Indique al usuario que instale [el paquete SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution)desde un punto de distribución de software o un recurso compartido de red. Una vez instalado, estará listo para guiar al usuario a través de una serie de pruebas. 

2. Comience en la Página principal, lo que permite a los usuarios introducir una descripción del problema y haga clic en **continuar**, como se muestra en la ilustración 1.

    ![Inicie SDT en la figura 1 del modo de escritorio ](images/sdt-desk-1.png)
 *. SDT en modo de escritorio*

3. Cuando SDT indica que el dispositivo tiene las actualizaciones más recientes, haga clic en **continuar** para avanzar hasta el catálogo de pruebas disponibles, como se muestra en la ilustración 2.

    ![Seleccione la figura 2 de opciones de SDT ](images/sdt1.png)
 *. Seleccionar de las opciones de SDT*

4. Puede elegir ejecutar todas las pruebas de diagnóstico. O bien, si ya sospecha un problema determinado, como una pantalla defectuosa o un problema de fuente de alimentación, haga clic en **seleccionar** para elegir entre las pruebas disponibles y haga clic en **Ejecutar seleccionado**, como se muestra en la ilustración 3. Para obtener detalles de cada prueba, consulte la tabla siguiente. 

    ![Seleccione pruebas de hardware, ](images/sdt2.png)
 *ilustración 3. Seleccionar pruebas de hardware*

    Prueba de hardware | Descripción
    --- | ---
    Fuente de alimentación y batería |  Comprueba que la fuente de alimentación funcione de manera óptima
    Pantalla y sonido   | Comprueba el brillo, el brillo o los píxeles muertos, el altavoz y el micrófono.
    Puertos y accesorios   | Comprueba los accesorios, la conexión en pantalla y el funcionamiento con USB
    Conectividad |  Verifica la conectividad de Bluetooth, inalámbrico y LTE
    Seguridad    | Comprueba los problemas relacionados con la seguridad
    Función táctil   | Comprueba los problemas relacionados con el tacto
    Teclado y toque |    Comprueba la conexión de teclado y la cubierta de tipo integrada
    Sensores | Comprueba el funcionamiento de los distintos sensores en el dispositivo
    Hardware |  Comprueba los problemas con diferentes componentes de hardware, como la tarjeta gráfica y la cámara.

5. Cuando haya finalizado todas las pruebas, la herramienta le pedirá que confirme si el problema se ha corregido. 

 ![¿Se ha solucionado el problema? ](images/sdt3.png)
 *Ilustración 3A. ¿se ha resuelto el problema?*

6. Si el problema no se resuelve o no sabe, puede enviar un vale de soporte técnico seleccionando **ponerse en contacto con nosotros** para **obtener ayuda ahora.**
 
 ![Enviar una incidencia de soporte técnico ](images/sdt4.png)
 *3B.*

<span id="multiple" />

## Ejecución de varias pruebas de hardware para solucionar problemas

SDT está diseñado como una herramienta interactiva que ejecuta una serie de pruebas. Para cada prueba, SDT proporciona instrucciones que resumen la naturaleza de la prueba y qué usuarios deberían esperar o buscar para que la prueba se realice correctamente. Por ejemplo, para diagnosticar si el brillo de la pantalla funciona correctamente, SDT comienza por cero y aumenta el brillo al 100 por ciento, lo que pide a los usuarios que lo confirmen, respondiendo **sí** o **no** , que el brillo funciona como se muestra en la ilustración 4. 

Para cada prueba, si la funcionalidad no funciona como se espera y el usuario hace clic en **no**, SDT genera un informe de las posibles causas y las formas de solucionarlo. 

![Ejecución de los diagnósticos de hardware, ](images/sdt-desk-4.png)
 *ilustración 4. Ejecución de diagnósticos de hardware*

1. Si el brillo se ajusta correctamente de 0-100 por ciento como se espera, indique al usuario que haga clic en **sí** y, a continuación, haga clic en **continuar**. 
2. Si el brillo no se ajusta al 0-100 por ciento según lo esperado, indique al usuario que haga clic en **no** y, a continuación, haga clic en **continuar**. 
3. Guiar a los usuarios por las pruebas restantes según corresponda. Cuando haya terminado, SDT proporcionará automáticamente un resumen de alto nivel del informe, incluidas las posibles causas de los problemas de hardware junto con las instrucciones de resolución.


### Reparar aplicaciones

SDT le permite diagnosticar y reparar aplicaciones que pueden estar causando problemas, como se muestra en la figura 5.

![Ejecutando reparación, ](images/sdt-desk-5.png)
 *ilustración 5. Ejecución de reparaciones*
<span id="logs" />

### Generando registros para analizar problemas 

SDT proporciona una amplia compatibilidad de diagnósticos compatibles con el registro en todas las aplicaciones, drivers, hardware y problemas del sistema operativo, como se muestra en la figura 6.

![Generando registros, ](images/sdt-desk-6.png)
 *Ilustración 6. Generando registros*

<span id="detailed-report" />

### Generando informe detallado comparando el dispositivo y la configuración óptima

Según los registros, SDT genera un informe de problemas basados en el software y el firmware que puede guardar en una ubicación preferida.

##  <a name="related-topics"></a>Temas relacionados

- [Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos](surface-diagnostic-toolkit-command-line.md)


---
title: Implementar el Kit de herramientas de diagnóstico de Surface para empresas
description: En este tema se explica cómo usar Surface Diagnostic Toolkit para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271584"
---
# Implementar el Kit de herramientas de diagnóstico de Surface para empresas

Microsoft Surface Diagnostic Toolkit para empresas (SDT) permite a los administradores de TI investigar, solucionar problemas y resolver problemas de hardware, software y firmware rápidamente con dispositivos Surface. Puedes ejecutar una serie de pruebas de diagnóstico y reparaciones de software, además de obtener información sobre el estado del dispositivo y instrucciones para resolver problemas. 

En concreto, SDT para empresas te permite:

- [Personaliza el paquete.](#preparing-the-sdt-package-for-distribution)
- [Ejecuta la aplicación mediante comandos.](surface-diagnostic-toolkit-command-line.md)
- [Ejecute varias pruebas de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Generar registros para analizar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenga un informe detallado que compare el dispositivo con la configuración óptima.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Escenarios principales y recursos de descarga 

Para ejecutar SDT para empresas, descarga los componentes enumerados en la tabla siguiente.


Modo |  Escenarios principales | Descargar | Más información
--- | --- | --- | ---
Modo de escritorio |  Ayudar a los usuarios a ejecutar SDT en sus dispositivos Surface para solucionar problemas.<br>Crea un paquete personalizado para implementarlo en uno o varios dispositivos Surface, lo que permite a los usuarios seleccionar registros específicos para recopilar y analizar. | Paquete MSI distribuible de SDT:<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar Surface Diagnostic Toolkit en modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
Línea de comandos |  Solucionar directamente problemas de dispositivos Surface de forma remota sin la interacción del usuario, con herramientas estándar como Configuration Manager. Incluye los siguientes comandos:<br>`-DataCollector` recopila todos los archivos de registro<br>`-bpa` ejecuta diagnósticos de estado mediante el Analizador de procedimientos recomendados.<br>`-windowsupdate` comprueba windows Update si faltan actualizaciones de controladores o firmware.<br>`-warranty` comprueba la información de garantía. <br><br>| Aplicación de consola de SDT:<br>Microsoft Surface Diagnostics App Console<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Ejecutar Surface Diagnostic Toolkit con comandos](surface-diagnostic-toolkit-command-line.md)

## Dispositivos compatibles 

SDT para empresas es compatible con Dispositivos Surface 3 y posteriores, incluidos:

- Surface Book: todas las generaciones
- Surface Go: todas las generaciones
- Surface Laptop: todas las generaciones
- Surface Pro 3 y versiones posteriores
- Surface Pro X: todas las generaciones
- Surface Studio: todas las generaciones
- Surface 3 LTE
- Surface 3


## Instalación de Surface Diagnostic Toolkit para empresas

Para crear un paquete de SDT que puedes distribuir a los usuarios de tu organización:

1. Inicia sesión en el dispositivo Surface con la cuenta de administrador.
2. Descarga el paquete de Windows Installer de SDT (.msi) desde la página de descarga de Herramientas de [Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI y cópielo en una ubicación preferida del dispositivo Surface, como Escritorio.
3. Aparece el asistente para la configuración de SDT, como se muestra en la figura 1. Haz clic en **Siguiente**. 

    >[!NOTE]
    >Si no aparece el asistente para la instalación, asegúrese de que ha iniciado sesión en la cuenta de administrador en el equipo. 

    ![Asistente para la configuración del Kit de herramientas de diagnóstico de Surface](images/sdt-1.png)

    *Figura 1. Asistente para la configuración del Kit de herramientas de diagnóstico de Surface*

4. Cuando aparezca el Asistente para la instalación de SDT, haz clic en **Siguiente,** acepta el Contrato de licencia para el usuario final (CLUF)

5. En la pantalla Opciones de instalación, cambie la ubicación de instalación predeterminada si lo desea. 
6. En Tipo de instalación, seleccione **Opciones avanzadas.** 

    >[!NOTE]
    >La opción estándar permite a los usuarios ejecutar la herramienta de diagnóstico directamente en su dispositivo Surface siempre que se haya iniciado sesión en el dispositivo con una cuenta de administrador. 
    
     ![Opciones de instalación: Opciones avanzadas](images/sdt-install.png)

7. Haga **clic en Siguiente** y, a continuación, haga clic en **Instalar**. 

## Instalación mediante la línea de comandos
Si lo deseas, puedes instalar SDT en un símbolo del sistema y establecer una marca personalizada para instalar la herramienta en modo de administrador. SDT contiene las siguientes marcas de opción de instalación:

- `SENDTELEMETRY` envía datos de telemetría a Microsoft. La marca acepta `0` para deshabilitado o para `1` habilitado. El valor predeterminado es `1` enviar telemetría.
- `ADMINMODE` configura la herramienta para que se instale en modo de administrador. La marca acepta para `0` el modo de cliente o para el modo de administrador de `1` TI. El valor predeterminado es `0`.

### Para instalar SDT desde la línea de comandos:

1. Abra un símbolo del sistema y escriba:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Por ejemplo:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Buscar SDT en el dispositivo Surface

Tanto SDT como la consola de la aplicación de SDT se instalan en `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Además del archivo .exe, SDT instala un archivo JSON y un archivo admin.dll (modules\admin.dll), como se muestra en la figura 2.

![lista de archivos instalados de SDT en el Explorador de archivos](images/sdt-2.png)

*Figura 2. Archivos instalados por SDT*

## Preparar el paquete de SDT para su distribución

La creación de un paquete personalizado te permite dirigir la herramienta a problemas conocidos específicos.

1. Haz **clic en > ejecutar,** escribe **Surface** y, a continuación, haz clic en Surface Diagnostic Toolkit **para empresas.** 
2. Cuando se abra la herramienta, haga **clic en Crear paquete personalizado,** como se muestra en la figura 3.

    ![Opción crear paquete personalizado](images/sdt-3.png)

    *Figura 3. Crear paquete personalizado*

### Configuración de idioma y telemetría

  Al crear un paquete, puedes seleccionar la configuración de idioma o no enviar información de telemetría a Microsoft. De forma predeterminada, SDT envía telemetría a Microsoft que se usa para mejorar la aplicación de acuerdo con la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Si desea rechazar, desactive la casilla al crear un paquete personalizado, como se muestra a continuación. O bien, desactive **la casilla Enviar telemetría a Microsoft** en la página Opciones de **instalación** durante la instalación de SDT. 

>[!NOTE]
>Esta configuración no afecta a la telemetría mínima almacenada automáticamente en los servidores De Microsoft cuando se ejecutan pruebas y reparaciones que requieren una conexión a Internet, como la reparación de Windows Update y software, o al proporcionar comentarios con los botones Sonriente o Desaprobado en la barra de herramientas de la aplicación. 


![Seleccionar la configuración de idioma y telemetría](images/sdt-4.png)

*Figura 4. Seleccionar la configuración de idioma y telemetría*


### Página de Windows Update

Seleccione la opción adecuada para su organización. La mayoría de las organizaciones con varios usuarios normalmente seleccionarán recibir actualizaciones a través de Windows Server Update Services (WSUS), como se muestra en la figura 5. Si usas paquetes locales de Windows Update o WSUS, escribe la ruta de acceso según corresponda. 

![Opción Seleccionar Windows Update](images/sdt-5.png)

*Figura 5. Opción de Windows Update*

### Página de reparación de software

Esto le permite seleccionar o quitar la opción para ejecutar actualizaciones de reparación de software. 

![Seleccionar la opción de reparación de software](images/sdt-6.png)

*Figura 6. Opción de reparación de software*

### Recopilar registros y guardar la página del paquete

Puedes seleccionar ejecutar una amplia variedad de registros en aplicaciones, controladores, hardware y el sistema operativo. Haga clic en el área adecuada y seleccione en el menú de registros disponibles. A continuación, puedes guardar el paquete en un punto de distribución de software o una ubicación equivalente a la que los usuarios puedan tener acceso. 

![Seleccionar opciones de registro](images/sdt-7.png)

*Figura 7. Opción de registro y guardar paquete*

## Pasos siguientes

- [Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
- [Usar Surface Diagnostic Toolkit para empresas mediante comandos](surface-diagnostic-toolkit-command-line.md)

## Cambios y actualizaciones

### Versión 2.131.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Compatibilidad con Surface Pro 7+
- Experiencia de compatibilidad sin problemas en Surface Pro X
- Mejoras de seguridad
- Mejoras en la experiencia del usuario inclusiva

### Versión 2.124.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Compatibilidad integrada sin problemas
- Guardar todos los resultados de las pruebas
- Comprobar si la imagen está creada de forma personalizada
- Incluir advertencias del administrador de dispositivos
- Versión de firmware de dock
- Marcar las unidades como posibles errores en la prueba de almacenamiento
- Quitar vínculo de almacén 

### Versión 2.121.139
*Fecha de lanzamiento: 31 de julio de 2020*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Experiencia de soporte sin problemas
- Correcciones de errores

### Versión 2.94.139.0
*Fecha de lanzamiento: 11 de mayo de 2020*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Capacidad de omitir Windows Update para realizar la comprobación de hardware.
- Capacidad de recibir notificaciones sobre la actualización de la versión más reciente
- Surface Go 2
- Surface Book 3
- Mostrar indicador de progreso


### Versión 2.43.139.0
*Fecha de lanzamiento: 21 de octubre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Surface Pro 7
- Surface Laptop 3

### Versión 2.42.139.0
*Fecha de lanzamiento: 24 de septiembre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente: 
- Capacidad de descargar informes de hardware.
- Capacidad de ponerse en contacto con el soporte técnico de Microsoft directamente desde la herramienta. <br>

### Versión 2.41.139.0
*Fecha de lanzamiento: 24 de junio de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente: 
- Información de la versión del controlador incluida en los registros y el informe.
- Capacidad de proporcionar comentarios sobre la aplicación.<br>


### Versión 2.36.139.0
*Fecha de lanzamiento: 26 de abril de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente: 
- Opción de configuración avanzada para desbloquear las capacidades de administración a través de la interfaz de usuario del instalador, sin necesidad de configurar la línea de comandos.
- Mejoras de accesibilidad.
- Configuración de control de brillo de surface incluida en los registros.
- Vínculo de compatibilidad de monitor externo en el generador de informes.

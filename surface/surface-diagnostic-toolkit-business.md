---
title: Implementar el Kit de herramientas de diagnóstico de Surface para empresas
description: En este tema se explica cómo usar el kit de herramientas de diagnóstico de Surface para empresas.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 97d0a3d76cf9286ca946e08be9f605084084b2ba
ms.sourcegitcommit: 5448f775d3fe177806fce6cbaf0b2b091ed8b7d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2020
ms.locfileid: "11145965"
---
# Implementar el Kit de herramientas de diagnóstico de Surface para empresas

El kit de herramientas de diagnóstico de Microsoft Surface para empresas (SDT) permite a los administradores de ti investigar, solucionar y resolver problemas de hardware, software y firmware rápidamente con dispositivos Surface. Puede ejecutar una variedad de pruebas de diagnóstico y reparaciones de software además de obtener información y consejos sobre el estado del dispositivo para resolver los problemas. 

En concreto, SDT para empresas le permite:

- [Personalizar el paquete.](#preparing-the-sdt-package-for-distribution)
- [Ejecute la aplicación con comandos.](surface-diagnostic-toolkit-command-line.md)
- [Ejecute varias pruebas de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Generar registros para analizar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtener información detallada sobre la comparación de dispositivos y la configuración óptima.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## Escenarios principales y recursos de descarga 

Para ejecutar SDT para empresas, descargue los componentes enumerados en la tabla siguiente.


Modo |  Escenarios principales | Descargar | Obtén más información
--- | --- | --- | ---
Modo de escritorio |  Ayudar a los usuarios a ejecutar SDT en sus dispositivos Surface para solucionar problemas.<br>Cree un paquete personalizado para implementarlo en uno o más dispositivos de superficie que permitan a los usuarios seleccionar registros específicos para recopilar y analizar. | Paquete MSI distribuible distribuible:<br>Kit de herramientas de diagnóstico de Microsoft Surface para Business Installer<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar el kit de herramientas de diagnóstico de Surface en el modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
Línea de comandos |  Solucione directamente los dispositivos de superficie sin interacción del usuario con herramientas estándar, como Configuration Manager. Incluye los siguientes comandos:<br>`-DataCollector` Recopila todos los archivos de registro<br>`-bpa` ejecuta los diagnósticos de estado mediante el analizador de procedimientos recomendados.<br>`-windowsupdate` comprueba si faltan actualizaciones del firmware o el controlador en Windows Update.<br>`-warranty` verifica la información de garantía. <br><br>| Aplicación de consola SDT:<br>Consola de la aplicación Microsoft Surface Diagnostics<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Ejecutar el kit de herramientas de diagnóstico de superficie con comandos](surface-diagnostic-toolkit-command-line.md)

## Dispositivos compatibles 

SDT para empresas es compatible con los dispositivos Surface 3 y versiones posteriores, entre los que se incluyen:

- Portátil Surface Go
- Surface Book 3
- Surface Go 2
- Surface Pro X
- Surface Pro 7
- Portátil Surface 3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- Ir a la superficie con LTE
- Surface Book 2
- Surface Pro con LTE avanzada (modelo 1807)
- Surface Pro (modelo 1796)
- Surface Laptop
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3

## Instalación de Surface Diagnostic Toolkit for Business

Para crear un paquete SDT que puede distribuir a los usuarios de su organización:

1. Inicia sesión en tu dispositivo Surface con la cuenta de administrador.
2. Descargue el paquete de Windows Installer (. msi) SDT desde la [Página de descarga herramientas para ti](https://www.microsoft.com/download/details.aspx?id=46703) y cópielo en una ubicación preferida del dispositivo Surface, como el escritorio.
3. Aparece el Asistente de configuración SDT, como se muestra en la figura 1. Haz clic en **Siguiente**. 

    >[!NOTE]
    >Si el Asistente de configuración no aparece, asegúrese de que ha iniciado sesión en la cuenta de administrador del equipo. 

    ![Bienvenido al asistente de configuración del kit de herramientas de diagnóstico de Surface](images/sdt-1.png)

    *Figura 1. Asistente de configuración del kit de herramientas de diagnóstico de Surface*

4. Cuando aparezca el Asistente de configuración SDT, haga clic en **siguiente**y acepte el contrato de licencia para el usuario final (CLUF).

5. En la pantalla de opciones de instalación, cambie la ubicación de instalación predeterminada, si lo desea. 
6. En tipo de configuración, seleccione **avanzadas**. 

    >[!NOTE]
    >La opción estándar permite a los usuarios ejecutar la herramienta de diagnóstico directamente en su dispositivo Surface, siempre y cuando hayan iniciado sesión en su dispositivo con una cuenta de administrador. 
    
     ![Opciones de instalación: avanzadas](images/sdt-install.png)

7. Haga clic en **siguiente** y, después, en **instalar**. 

## Instalar con la línea de comandos
Si lo desea, puede instalar SDT en un símbolo del sistema y establecer una marca personalizada para instalar la herramienta en el modo de administrador. SDT contiene las siguientes marcas de opción de instalación:

- `SENDTELEMETRY` envía datos de telemetría a Microsoft. La marca acepta `0` deshabilitado o `1` habilitado. El valor predeterminado es `1` Enviar telemetría.
- `ADMINMODE` configura la herramienta para que se instale en el modo de administrador. La marca acepta el `0` modo de cliente o el `1` modo de administrador de ti. El valor predeterminado es `0`.

### Para instalar SDT desde la línea de comandos:

1. Abra un símbolo del sistema y escriba:

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **Por ejemplo:**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Ubicación de SDT en el dispositivo Surface

Tanto SDT como la consola de la aplicación SDT están instaladas en `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Además del archivo. exe, SDT instala un archivo JSON y un archivo admin.dll (modules\admin.dll), como se muestra en la figura 2.

![lista de archivos instalados de SDT en el explorador de archivos](images/sdt-2.png)

*Figura 2. Archivos instalados por SDT*

## Preparar el paquete SDT para la distribución

Crear un paquete personalizado le permite dirigir la herramienta a problemas conocidos específicos.

1. Haga clic en **inicio > ejecutar**, escriba **Surface** y luego haga clic en **Surface Diagnostic Toolkit para empresas**. 
2. Cuando se abra la herramienta, haga clic en **crear paquete personalizado**, como se muestra en la ilustración 3.

    ![Crear una opción de paquete personalizado](images/sdt-3.png)

    *Figura 3. Crear paquete personalizado*

### Configuración de idioma y telemetría

  Al crear un paquete, puede seleccionar la configuración de idioma o dejar de enviar la información de telemetría a Microsoft. De forma predeterminada, SDT envía telemetría a Microsoft que se usa para mejorar la aplicación de acuerdo con la [declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Si desea rechazar, desactive la casilla al crear un paquete personalizado, como se muestra a continuación. O desactive la casilla de verificación **Enviar telemetría a Microsoft** en la página de **Opciones de instalación** durante SDT Setup. 

>[!NOTE]
>Esta configuración no afecta a la telemetría mínima almacenada automáticamente en los servidores de Microsoft cuando se ejecutan pruebas y reparaciones que requieren una conexión a Internet, como Windows Update y la reparación de software, o proporcionan comentarios con los botones de sonrisa o enfadado de la barra de herramientas de la aplicación. 


![Seleccionar configuración de idioma y telemetría](images/sdt-4.png)

*Figura 4. Seleccionar configuración de idioma y telemetría*


### Página de Windows Update

Seleccione la opción adecuada para su organización. Normalmente, la mayoría de las organizaciones con varios usuarios seleccionarán recibir actualizaciones a través de Windows Server Update Services (WSUS), como se muestra en la figura 5. Si usa paquetes de Windows Update locales o WSUS, escriba la ruta de acceso según corresponda. 

![Seleccione la opción Windows Update](images/sdt-5.png)

*Figura 5. Opción Windows Update*

### Página de reparación de software

Esto le permite seleccionar o quitar la opción de ejecutar actualizaciones de reparación de software. 

![Seleccione la opción de reparación de software](images/sdt-6.png)

*Figura 6. Opción de reparación de software*

### Recopilar registros y guardar la página del paquete

Puede seleccionar ejecutar una amplia variedad de registros entre las aplicaciones, los drivers, el hardware y el sistema operativo. Haga clic en el área correspondiente y seleccione en el menú de registros disponibles. Después, puede guardar el paquete en un punto de distribución de software o en una ubicación equivalente a la que los usuarios puedan tener acceso. 

![Seleccionar opciones de registro](images/sdt-7.png)

*Figura 7. Opción log y guardar paquete*

## Pasos siguientes

- [Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
- [Usar el kit de herramientas de diagnóstico de Surface para empresas con comandos](surface-diagnostic-toolkit-command-line.md)

## Cambios y actualizaciones

### Versión 2.124.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:

- Soporte integrado y transparente
- Guardar todos los resultados de pruebas
- Comprobar si la imagen se ha creado de forma personalizada
- Incluir advertencias desde el administrador de dispositivos
- Versión del firmware del Dock
- Marcar unidades como posibles errores en la prueba de almacenamiento
- Quitar vínculo de tienda 

### Versión 2.121.139
*Fecha de lanzamiento: 31 2020 de julio*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:

- Experiencia de soporte técnico perfecta
- Correcciones de errores

### Versión 2.94.139.0
*Fecha de lanzamiento: 11 de mayo de 2020*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:

- Posibilidad de omitir Windows Update para realizar la comprobación de hardware.
- Posibilidad de recibir notificaciones sobre la actualización de la versión más reciente
- Surface Go 2
- Surface Book 3
- Mostrar indicador de progreso


### Versión 2.43.139.0
*Fecha de lanzamiento: 21 de octubre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos:

- Surface Pro 7
- Portátil Surface 3

### Versión 2.42.139.0
*Fecha de lanzamiento: 24 de septiembre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos: 
- Posibilidad de descargar informes de hardware.
- Posibilidad de ponerse en contacto con el soporte técnico de Microsoft directamente desde la herramienta. <br>

### Versión 2.41.139.0
*Fecha de lanzamiento: 24 de junio de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos: 
- Información de versión del controlador incluida en los registros y en el informe.
- Capacidad para proporcionar comentarios sobre la aplicación.<br>


### Versión 2.36.139.0
*Fecha de lanzamiento: 26 de abril de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con los siguientes elementos: 
- Opción de configuración avanzada para desbloquear las capacidades de administrador a través de la interfaz de usuario del instalador, sin necesidad de configuración de línea de comandos.
- Mejoras de accesibilidad.
- Configuración de control de brillo de la superficie incluida en los registros.
- Vínculo de compatibilidad con monitor externo en el generador de informes.

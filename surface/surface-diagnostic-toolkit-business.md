---
title: Kit de herramientas de diagnóstico de Surface para empresas
description: En este tema se explica cómo implementar y usar el Toolkit de diagnóstico de Surface para empresas, que permite a los administradores de TI investigar, solucionar y solucionar rápidamente problemas de hardware, software y firmware con dispositivos Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/25/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 71a909a00187cf8727ada4e1adabd998b26eb3c0
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "12153985"
---
# <a name="surface-diagnostic-toolkit-for-business"></a>Kit de herramientas de diagnóstico de Surface para empresas

Si Surface no funciona correctamente, el servicio de diagnóstico de Microsoft Surface Toolkit (SDT) para empresas puede ayudarte a ti o al administrador a encontrar y resolver problemas.  SDT para empresas te permite investigar, solucionar y solucionar rápidamente problemas de hardware, software y firmware con dispositivos Surface en toda la red.

> [!NOTE]
> Surface Diagnostic Toolkit para empresas está diseñada para dispositivos comerciales. Si el dispositivo es un dispositivo personal y no está administrado por el trabajo o la escuela, ejecute la página de diagnóstico [de Surface Toolkit](https://support.microsoft.com/help/4037239/surface-fix-common-surface-problems-using-surface-diagnostic-toolkit) en su lugar.

En concreto, SDT para empresas le permite:

- [Personalizar el paquete.](#preparing-the-sdt-package-for-distribution)
- [Ejecuta la aplicación con comandos.](surface-diagnostic-toolkit-command-line.md)
- [Ejecute varias pruebas de hardware para solucionar problemas.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Generar registros para analizar problemas.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtenga un informe detallado que compara el dispositivo con la configuración óptima.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)

## <a name="primary-scenarios-and-download-resources"></a>Escenarios principales y recursos de descarga

Para ejecutar Surface Diagnostic Toolkit para empresas, descarga los componentes enumerados en la tabla siguiente.

Modo | Escenarios principales | Descargar | Obtén más información
--- | --- | --- | ---
Modo de escritorio | Ayudar a los usuarios a ejecutar SDT en sus dispositivos Surface para solucionar problemas.<br>Crea un paquete personalizado para implementarlo en uno o varios dispositivos Surface, lo que permite a los usuarios seleccionar registros específicos para recopilar y analizar. | Paquete MSI distribuible de SDT:<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Usar surface diagnostic Toolkit en modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
Línea de comandos | Solucione directamente problemas de dispositivos Surface de forma remota sin la interacción del usuario, con herramientas estándar como Configuration Manager. Incluye los siguientes comandos:<br>`-DataCollector` recopila todos los archivos de registro<br>`-bpa` ejecuta diagnósticos de estado con el Analizador de procedimientos recomendados.<br>`-windowsupdate` comprueba Windows actualizar si faltan actualizaciones de firmware o controladores.<br>`-warranty` comprueba la información de garantía. <br><br>| Aplicación de consola SDT:<br>Microsoft Surface Diagnostics App Console<br>[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) | [Ejecutar la consola de aplicaciones de línea de comandos con Surface Diagnostic Toolkit para empresas](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices"></a>Dispositivos compatibles

SDT para empresas es compatible con dispositivos Surface 3 y posteriores (excepto para dispositivos configurados en modo S):

- Surface Book: todas las generaciones
- Surface Laptop Studio
- Surface Go: todas las generaciones
- Surface Laptop: todas las generaciones
- Surface Laptop Ir
- Surface Pro 3 y posteriores
- Surface Pro X: todas las generaciones
- Surface Studio: todas las generaciones
- Surface 3 LTE
- Surface 3

## <a name="installing-surface-diagnostic-toolkit-for-business"></a>Instalación de surface diagnostic Toolkit para empresas

Para crear un paquete de SDT que pueda distribuir a los usuarios de su organización:

1. Inicia sesión en tu dispositivo Surface con la cuenta de administrador.

2. Descarga SDT Windows Installer Package (.msi) desde la página de descarga [de Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703).

    - Para dispositivos Intel/AMD, descargue: **Surface_Diagnostic_Toolkit_for_Business_v2.168.139.0.msi**.
    - Para ARM dispositivos, descarga: **Surface_Diagnostic_Toolkit_for_Business_v2.168.139.0_x86.msi**.

3. Copie el .msi en una ubicación preferida en el dispositivo Surface, como Desktop.Aparece el asistente de configuración de SDT, como se muestra en la figura 1. Haz clic en **Siguiente**.

    >[!NOTE]
    >Si no aparece el asistente para la instalación, asegúrese de que ha iniciado sesión en la cuenta de administrador en el equipo.

    ![bienvenido al Asistente para la Toolkit de configuración de Surface Diagnostic.](images/sdt-1.png)<br/>
    *Figura 1. Asistente para configuración Toolkit diagnóstico de Surface*

4. Cuando aparezca el asistente para la instalación de SDT, haga clic en **Siguiente**, acepte el Contrato de licencia de usuario final (CLUF).

5. En la pantalla Opciones de instalación, cambie la ubicación de instalación predeterminada si lo desea.

6. En Tipo de instalación, seleccione **Avanzadas**.

    >[!NOTE]
    >La opción estándar permite a los usuarios ejecutar la herramienta de diagnóstico directamente en su dispositivo Surface siempre que se haya iniciado sesión en su dispositivo con una cuenta de administrador.

    ![Opciones de instalación: Avanzadas.](images/sdt-install.png)

7. Haga **clic en Siguiente** y, a continuación, en **Instalar**.

## <a name="installing-using-the-command-line"></a>Instalación con la línea de comandos

Si lo desea, puede instalar SDT en un símbolo del sistema y establecer una marca personalizada para instalar la herramienta en modo de administración. SDT contiene las siguientes marcas de opción de instalación:

- `SENDTELEMETRY` envía datos de telemetría a Microsoft. La marca acepta `0` para deshabilitado o `1` habilitado. El valor predeterminado es `1` enviar telemetría.
- `ADMINMODE` configura la herramienta para que se instale en modo de administración. La marca acepta para `0` el modo de cliente o para el modo de administrador de `1` TI. El valor predeterminado es `0`.

### <a name="to-install-sdt-from-the-command-line"></a>Para instalar SDT desde la línea de comandos

1. Abra un símbolo del sistema y escriba:

    ```console
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```

    **Por ejemplo:**

    ```console
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a>Localizar SDT en el dispositivo Surface

Tanto SDT como la consola de la aplicación SDT se instalan en `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` .

Además del archivo .exe, SDT instala un archivo JSON y un archivo admin.dll (modules\admin.dll), como se muestra en la figura 2.

:::image type="content" alt-text="lista de archivos instalados de SDT en el Explorador de archivos." source="images/sdt-2.png":::<br/>
*Figura 2. Archivos instalados por SDT*

## <a name="preparing-the-sdt-package-for-distribution"></a>Preparación del paquete de SDT para la distribución

La creación de un paquete personalizado le permite dirigir la herramienta a problemas conocidos específicos.

1. Haz **clic en > Ejecutar**, escribe **Surface** y, a continuación, haz clic en Surface Diagnostic Toolkit **para empresas**.

2. Cuando se abra la herramienta, haga clic **en Crear paquete personalizado**, como se muestra en la figura 3.

    ![Crear una opción de paquete personalizado.](images/sdt-3.png)<br/>
    *Figura 3. Crear paquete personalizado*

### <a name="language-and-telemetry-settings"></a>Configuración de idioma y telemetría

  Al crear un paquete, puede seleccionar la configuración de idioma o no enviar información de telemetría a Microsoft. De forma predeterminada, SDT envía telemetría a Microsoft que se usa para mejorar la aplicación de acuerdo con la Declaración [de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement). Si desea rechazar, desactive la casilla al crear un paquete personalizado, como se muestra a continuación. O desactive la casilla **Enviar telemetría a Microsoft** en la página Opciones de **instalación** durante la instalación de SDT.

>[!NOTE]
>Esta configuración no afecta a la telemetría mínima almacenada automáticamente en los servidores De Microsoft al ejecutar pruebas y reparaciones que requieren una conexión a Internet, como una reparación de actualización y software de Windows, o proporcionar comentarios con los botones Smile o Frown de la barra de herramientas de la aplicación.

![Seleccione la configuración de idioma y telemetría.](images/sdt-4.png)<br/>
*Figura 4. Seleccionar idioma y configuración de telemetría*

### <a name="windows-update-page"></a>Windows Página de actualización

Seleccione la opción adecuada para su organización. La mayoría de las organizaciones con varios usuarios suelen seleccionar recibir actualizaciones a través de Windows Server Update Services (WSUS), como se muestra en la figura 5. Si usas paquetes Windows Update o WSUS, escribe la ruta de acceso según corresponda.

![Seleccione Windows opción Actualizar.](images/sdt-5.png)<br/>
*Figura 5. Windows Opción Actualizar*

### <a name="software-repair-page"></a>Página de reparación de software

Esto le permite seleccionar o quitar la opción para ejecutar actualizaciones de reparación de software.

![Seleccione la opción de reparación de software.](images/sdt-6.png)<br/>
*Figura 6. Opción de reparación de software*

### <a name="collecting-logs-and-saving-package-page"></a>Recopilar registros y guardar la página del paquete

Puede seleccionar ejecutar una amplia variedad de registros en aplicaciones, controladores, hardware y el sistema operativo. Haga clic en el área adecuada y seleccione en el menú de registros disponibles. A continuación, puede guardar el paquete en un punto de distribución de software o una ubicación equivalente a la que los usuarios puedan tener acceso.

![Seleccione opciones de registro.](images/sdt-7.png)<br/>
*Figura 7. Opción Registrar y guardar paquete*

## <a name="next-steps"></a>Pasos siguientes

- [Usar Kit de herramientas de diagnóstico de Surface para empresas en modo de escritorio](surface-diagnostic-toolkit-desktop-mode.md)
- [Ejecutar la consola de aplicaciones de línea de comandos con Surface Diagnostic Toolkit para empresas](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a>Cambios y actualizaciones

### <a name="version-21681390"></a>Versión 2.168.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Surface Pro 8
- Surface Laptop Studio
- Surface Go 3

### <a name="version-21311390"></a>Versión 2.131.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Surface Pro 7+
- Experiencia de soporte sin problemas en Surface Pro X
- Mejoras de seguridad
- Mejoras en la experiencia de usuario inclusiva

### <a name="version-21241390"></a>Versión 2.124.139.0

Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Compatibilidad integrada sin problemas
- Guardar todos los resultados de la prueba
- Comprobar si la imagen está creada de forma personalizada
- Incluir advertencias del administrador de dispositivos
- Versión de firmware de acoplamiento
- Marcar las unidades como posibles errores en la prueba de almacenamiento
- Quitar vínculo de almacén

### <a name="version-2121139"></a>Versión 2.121.139

*Fecha de lanzamiento: 31 de julio de 2020*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Experiencia de soporte sin problemas
- Correcciones de errores

### <a name="version-2941390"></a>Versión 2.94.139.0

*Fecha de lanzamiento: 11 de mayo de 2020*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Posibilidad de omitir Windows update para realizar la comprobación de hardware.
- Capacidad para recibir notificaciones sobre la actualización de versión más reciente
- Surface Go 2
- Surface Book 3
- Mostrar indicador de progreso

### <a name="version-2431390"></a>Versión 2.43.139.0

*Fecha de lanzamiento: 21 de octubre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Surface Pro 7
- Surface Laptop 3

### <a name="version-2421390"></a>Versión 2.42.139.0

*Fecha de lanzamiento: 24 de septiembre de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Capacidad para descargar informes de hardware.
- Capacidad de ponerse en contacto con el Soporte técnico de Microsoft directamente desde la herramienta.

### <a name="version-2411390"></a>Versión 2.41.139.0

*Fecha de lanzamiento: 24 de junio de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Información de la versión del controlador incluida en los registros y el informe.
- Capacidad de proporcionar comentarios sobre la aplicación.

### <a name="version-2361390"></a>Versión 2.36.139.0

*Fecha de lanzamiento: 26 de abril de 2019*<br>
Esta versión de Surface Diagnostic Toolkit para empresas agrega compatibilidad con lo siguiente:

- Opción de configuración avanzada para desbloquear las capacidades de administración a través de la interfaz de usuario del instalador, sin necesidad de configuración de línea de comandos.
- Mejoras de accesibilidad.
- Configuración del control de brillo de Surface incluida en los registros.
- Vínculo de compatibilidad de monitor externo en el generador de informes.

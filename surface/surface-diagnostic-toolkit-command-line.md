---
title: Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos
description: Cómo ejecutar Surface Diagnostic Toolkit en una consola de comandos
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327334"
---
# Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos

La ejecución de Surface Diagnostic Toolkit (SDT) en un símbolo del sistema requiere descargar la consola de la aplicación de SDT. Después de instalarla, puedes ejecutar SDT en un símbolo del sistema a través de la consola de comandos de Windows (cmd.exe) o mediante Windows PowerShell, incluido el Entorno de scripting integrado (ISE) de PowerShell, que proporciona compatibilidad para la autocompletar comandos, copiar y pegar, y otras características.  Para obtener una lista de dispositivos Surface compatibles en SDT, consulta [Implementar Surface Diagnostic Toolkit para empresas.](surface-diagnostic-toolkit-business.md)

>[!NOTE]
>Para ejecutar SDT mediante comandos, debes haber iniciado sesión en la cuenta de administrador o haber iniciado sesión en una cuenta que sea miembro del grupo Administrador en el dispositivo Surface.

##  <a name="running-sdt-app-console"></a>Ejecución de la consola de la aplicación de SDT

Descarga e instala la consola de la aplicación SDT desde la página de descarga de [Herramientas de Surface para TI.](https://www.microsoft.com/download/details.aspx?id=46703) Puedes usar el símbolo del sistema de Windows (cmd.exe) o Windows PowerShell para: 

- Recopilar todos los archivos de registro.
- Ejecute diagnósticos de estado con el Analizador de procedimientos recomendados.
- Comprueba la actualización de las actualizaciones de controladores o firmware que faltan.

>[!NOTE]
>En esta versión, la consola de la aplicación SDT solo admite comandos únicos. La ejecución de varias opciones de línea de comandos requiere ejecutar el exe de consola por separado para cada comando. 

De forma predeterminada, los archivos de salida se guardan en la misma ubicación que la aplicación de consola. Consulte la tabla siguiente para obtener una lista completa de comandos.

Comando | Notas
--- | ---
-DataCollector "output file" | Recopila los detalles del sistema en un archivo zip. "archivo de salida" es la ruta de acceso del archivo para crear el archivo zip de detalles del sistema.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Comprueba varias opciones de configuración e indicadores de estado en el dispositivo. "archivo de salida" es la ruta de acceso del archivo para crear el informe HTML.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Comprueba si faltan actualizaciones de controladores o firmware en los servidores en línea de Windows Update.<br><br>**Ejemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Comprueba la información de garantía del dispositivo (válida o no válida). El "archivo de salida" opcional es la ruta de acceso del archivo para crear el archivo XML. <br><br>**Ejemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"


>[!NOTE]
>Para ejecutar la consola de la aplicación SDT de forma remota en dispositivos de destino, puedes usar una herramienta de administración de configuración como Microsoft Endpoint Configuration Manager. Como alternativa, puedes crear un archivo .zip que contenga la aplicación de consola y los comandos de consola adecuados e implementar según los procesos de distribución de software de la organización. 

##  <a name="running-best-practice-analyzer"></a>Ejecución del Analizador de procedimientos recomendados 

Puedes ejecutar pruebas BPA en componentes clave como BitLocker, Arranque seguro y Módulo de plataforma segura (TPM) y, a continuación, generar los resultados en un archivo que se pueda compartir. La herramienta genera una serie de tablas con encabezados codificados por colores y descriptores de condición, junto con instrucciones sobre cómo abordar la resolución del problema. 

- El color verde indica que el componente se está ejecutando en una condición óptima (óptima).
- Naranja indica que el componente no se está ejecutando en una condición óptima (no es óptima).
- El color rojo indica que el componente está en un estado anómalo. 

###  <a name="sample-bpa-results-output"></a>Resultados de BPA de ejemplo

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si BitLocker está habilitado en la unidad del sistema.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Protección en</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Se recomienda encarecidamente habilitar BitLocker para proteger los datos.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Arranque seguro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el arranque seguro está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Se recomienda encarecidamente habilitar el arranque seguro para proteger el equipo.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Módulo de plataforma segura</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Garantiza que el TPM es funcional.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Sin un TPM funcional, es posible que las funciones basadas en seguridad como BitLocker no funcionen correctamente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espera conectada</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si está habilitado el modo de espera conectado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>El modo de espera conectado permite que un dispositivo Surface reciba actualizaciones y notificaciones mientras no se usa. Para obtener la mejor experiencia, debe habilitarse el modo de espera conectado.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si Bluetooth está habilitada.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Habilitado</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de depuración</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el sistema operativo está en modo depuración.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La opción de arranque de depuración habilita o deshabilita la depuración de kernel del sistema operativo Windows. Habilitar esta opción puede causar inestabilidad en el sistema y puede impedir la reproducción de medios protegidos con DRM (administración de derechos digitales).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Firma de prueba</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si la firma de prueba está habilitada.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La firma de prueba es una configuración de inicio de Windows que solo debe usarse para probar controladores de versión previa.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plan de energía activo</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba que el plan de energía correcto está activo.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Equilibrado</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Se recomienda usar el plan de energía "equilibrado" para maximizar la productividad y la duración de la batería.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el dispositivo está actualizado con las actualizaciones de Windows.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Microsoft Silverlight (KB4023307), actualización de definiciones para antivirus de Windows Defender : KB2267602 (definición 1.279.1433.0)</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="ff9500">No óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La actualización a las ventanas más recientes te asegura que tienes el firmware y los controladores más recientes. Se recomienda mantener siempre actualizado el dispositivo</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espacio libre en disco duro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si hay poco espacio libre en el disco duro.</td></tr>
<tr><td><strong>Valor:</strong></td><td>66%</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Para obtener el mejor rendimiento, el disco duro debe tener al menos el 10 % de su capacidad como espacio libre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Dispositivos que no funcionan</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Lista de dispositivos que no funcionan en el Administrador de dispositivos.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Los dispositivos que no funcionan en el Administrador de dispositivos pueden causar problemas impredecibles con dispositivos Surface, como, entre otros, ningún ahorro de energía para el componente de hardware respectivo.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Monitor externo</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si hay un monitor externo que pueda tener problemas de compatibilidad.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Comprueba con el fabricante del equipo original la compatibilidad con el dispositivo Surface.</td></tr>
</table>

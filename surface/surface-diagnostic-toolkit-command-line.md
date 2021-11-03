---
title: Ejecutar la consola de aplicaciones de línea de comandos con Surface Diagnostic Toolkit para empresas
description: Cómo ejecutar surface diagnostic Toolkit en una consola de comandos
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
ms.openlocfilehash: 1410760fc89d4654322f2bc9b738e87e839251c3
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154125"
---
# <a name="run-command-line-app-console-with-surface-diagnostic-toolkit-for-business"></a>Ejecutar la consola de aplicaciones de línea de comandos con Surface Diagnostic Toolkit para empresas

La ejecución del Toolkit de diagnóstico de Surface (SDT) en un símbolo del sistema requiere descargar la consola de la aplicación de SDT. Después de instalarlo, puede ejecutar SDT en un símbolo del sistema a través de la consola de comandos de Windows (cmd.exe) o mediante Windows PowerShell, incluido el entorno de scripting integrado (ISE) de PowerShell, que proporciona compatibilidad con la autocompletar de comandos, copiar y pegar y otras características.  Para obtener una lista de dispositivos Surface compatibles en SDT, consulte [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Para ejecutar SDT con comandos, debes haber iniciado sesión en la cuenta de administrador o haber iniciado sesión en una cuenta que sea miembro del grupo Administrador en el dispositivo Surface.

## <a name="running-sdt-app-console"></a>Ejecución de la consola de aplicaciones de SDT

1. Descargue e instale la consola de la aplicación SDT desde la [página de descarga de Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703).

- Para dispositivos Intel/AMD, descargue: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- Para ARM dispositivos, descarga: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. Use el Windows de comandos (cmd.exe) o Windows PowerShell para:

- Recopilar todos los archivos de registro
- Ejecutar diagnósticos de estado con el analizador de procedimientos recomendados
- Comprobar la actualización si faltan actualizaciones de firmware o controladores

>[!NOTE]
>En esta versión, la consola de la aplicación SDT solo admite comandos únicos. La ejecución de varias opciones de línea de comandos requiere ejecutar el exe de consola por separado para cada comando.

De forma predeterminada, los archivos de salida se guardan en la misma ubicación que la aplicación de consola. Consulte la tabla siguiente para obtener una lista completa de comandos.

Comando | Notas
--- | ---
-DataCollector "output file" | Recopila los detalles del sistema en un archivo zip. "archivo de salida" es la ruta de acceso del archivo para crear el archivo zip de detalles del sistema.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Comprueba varias configuraciones e indicadores de estado en el dispositivo. "archivo de salida" es la ruta de acceso del archivo para crear el informe HTML.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Comprueba Windows actualizar servidores en línea en busca de actualizaciones de controladores o firmware que falte.<br><br>**Ejemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Comprueba la información de garantía en el dispositivo (válida o no válida). El "archivo de salida" opcional es la ruta de acceso del archivo para crear el archivo xml. <br><br>**Ejemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"

>[!NOTE]
>Para ejecutar la consola de la aplicación SDT de forma remota en dispositivos de destino, puedes usar una herramienta de administración de configuración como Microsoft Endpoint Configuration Manager. Como alternativa, puedes crear un archivo .zip que contenga la aplicación de consola y los comandos de consola adecuados e implementar según los procesos de distribución de software de la organización.

## <a name="running-best-practice-analyzer"></a>Ejecución del analizador de procedimientos recomendados

Puedes ejecutar pruebas de BPA en componentes clave como BitLocker, Arranque seguro y Módulo de plataforma de confianza (TPM) y, a continuación, generar los resultados en un archivo que se pueda compartir. La herramienta genera una serie de tablas con encabezados codificados por colores y descriptores de condición, junto con instrucciones sobre cómo abordar la solución del problema.

- El color verde indica que el componente se ejecuta en una condición óptima (óptima).
- Naranja indica que el componente no se está ejecutando en una condición óptima (no óptima).
- El color rojo indica que el componente está en un estado anómalo.

### <a name="sample-bpa-results-output"></a>Resultados de BPA de ejemplo

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si BitLocker está habilitado en la unidad del sistema.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Protección en</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Es muy recomendable habilitar BitLocker para proteger los datos.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Arranque seguro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el arranque seguro está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Se recomienda habilitar el arranque seguro para proteger el equipo.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Módulo de plataforma segura</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Garantiza que el TPM es funcional.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Sin un TPM funcional, es posible que las funciones basadas en seguridad como BitLocker no funcionen correctamente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de espera conectado</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el modo de espera conectado está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>El modo de espera conectado permite que un dispositivo Surface reciba actualizaciones y notificaciones mientras no se usa. Para obtener la mejor experiencia, debe habilitarse el modo de espera conectado.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si Bluetooth está habilitado.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Habilitado</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de depuración</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el sistema operativo está en modo de depuración.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La opción de arranque de depuración habilita o deshabilita la depuración del kernel del Windows sistema operativo. Habilitar esta opción puede provocar inestabilidad en el sistema y evitar que se reen reproducción de medios protegidos con DRM (administración de derechos digitales).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Firma de prueba</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si la firma de prueba está habilitada.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La firma de prueba es Windows configuración de inicio que solo se debe usar para probar controladores de versión previa.</td></tr>
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
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el dispositivo está actualizado con Windows actualizaciones.</td></tr>
<tr><td><strong>Valor:</strong></td><td>Microsoft Silverlight (KB4023307), actualización de definiciones para Antivirus de Windows Defender - KB2267602 (definición 1.279.1433.0)</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="ff9500">No óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>La actualización a las ventanas más recientes te asegura de que estás en el firmware y controladores más recientes. Se recomienda mantener siempre actualizado el dispositivo</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espacio libre en disco duro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si hay poco espacio libre en la unidad de disco duro.</td></tr>
<tr><td><strong>Valor:</strong></td><td>66%</td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Para obtener el mejor rendimiento, el disco duro debe tener al menos el 10 % de su capacidad como espacio libre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Dispositivos que no funcionan</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Lista de dispositivos que no funcionan en el Administrador de dispositivos.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Los dispositivos que no funcionan en el Administrador de dispositivos pueden causar problemas impredecibles con dispositivos Surface, como, entre otros, ningún ahorro de energía para el componente de hardware correspondiente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Monitor externo</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si hay un monitor externo que pueda tener problemas de compatibilidad.</td></tr>
<tr><td><strong>Valor:</strong></td><td></td></tr>
<tr><td><strong>Condición:</strong></td><td><font color="00ff00">Óptimo</font></td></tr>
<tr><td><strong>Instrucciones:</strong></td><td>Comprueba con el fabricante de equipamiento original la compatibilidad con el dispositivo Surface.</td></tr>
</table>

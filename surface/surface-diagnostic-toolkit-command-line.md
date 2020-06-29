---
title: Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos
description: Cómo ejecutar el kit de herramientas de diagnóstico de Surface en una consola de comandos
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
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834297"
---
# Ejecutar el Kit de herramientas de diagnóstico de Surface para empresas con comandos

Ejecutar el kit de herramientas de diagnóstico de Surface (SDT) en un símbolo del sistema requiere descargar la consola de la aplicación estándar. Una vez instalado, puede ejecutar SDT en un símbolo del sistema con la consola de comandos de Windows (cmd.exe) o con Windows PowerShell, incluido el entorno de scripting integrado (ISE) de PowerShell, que proporciona soporte técnico para la finalización automática de comandos, copiado y pegado, entre otras características.  Para obtener una lista de los dispositivos Surface admitidos en SDT, consulte [deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>Para ejecutar SDT con los comandos, debe haber iniciado sesión en la cuenta de administrador o haber iniciado sesión en una cuenta que sea miembro del grupo de administradores de su dispositivo Surface.

## Consola de la aplicación SDT en ejecución

Descargue e instale la consola de la aplicación SDT desde la [Página de descarga herramientas para ti de Surface](https://www.microsoft.com/download/details.aspx?id=46703). Puede usar el símbolo del sistema de Windows (cmd.exe) o Windows PowerShell para: 

- Recopilar todos los archivos de registro.
- Ejecute los diagnósticos de estado con el analizador de procedimientos recomendados.
- Compruebe si faltan actualizaciones del firmware o el controlador.

>[!NOTE]
>En esta versión, la consola de la aplicación SDT solo admite comandos individuales. La ejecución de varias opciones de la línea de comandos requiere ejecutar la consola exe por separado para cada comando. 

De forma predeterminada, los archivos de salida se guardan en la misma ubicación que la aplicación de consola. Para obtener una lista completa de los comandos, consulte la tabla siguiente.

Comando | Notas
--- | ---
-"Archivo de salida" | Recopila detalles del sistema en un archivo zip. "archivo de salida" es la ruta de acceso del archivo para crear el archivo zip de detalles del sistema.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-"archivo de salida" BPA | Comprueba varias configuraciones y indicadores de estado en el dispositivo. "archivo de salida" es la ruta de acceso del archivo para crear el informe HTML.<br><br>**Ejemplo**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Comprueba si faltan actualizaciones de firmware o de controlador en los servidores de Internet Update.<br><br>**Ejemplo**:<br>Microsoft.Surface.Diagnostics.App.Console.exe-windowsupdate
-"archivo de salida" de la garantía | Verifica la información de garantía en el dispositivo (válido o no). El "archivo de salida" opcional es la ruta de acceso del archivo para crear el archivo XML. <br><br>**Ejemplo**: <br>Microsoft.Surface.Diagnostics.App.Console.exe: garantía "warranty.xml"


>[!NOTE]
>Para ejecutar la consola de la aplicación SDT de forma remota en los dispositivos de destino, puede usar una herramienta de administración de configuración como Microsoft Endpoint Configuration Manager. Como alternativa, puede crear un archivo. zip que contenga la aplicación de consola y los comandos de consola adecuados para implementar los procesos de distribución de software de su organización. 

## Ejecución del analizador de procedimientos recomendados 

Puede ejecutar pruebas de BPA en componentes clave como BitLocker, arranque seguro y módulo de plataforma segura (TPM) y, a continuación, generar los resultados en un archivo que se puede compartir. La herramienta genera una serie de tablas con encabezados y descriptores de condiciones codificados por colores, además de instrucciones sobre cómo resolver el problema. 

- El color verde indica que el componente se está ejecutando en una condición óptima (óptima).
- El color naranja indica que el componente no se está ejecutando en una condición óptima (no óptima).
- Rojo indica que el componente se encuentra en un estado anormal. 

### Salida de resultados de BPA de ejemplo

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si BitLocker está habilitado en la unidad del sistema.</td></tr>
<tr><td><strong>Eje</strong></td><td>Protección en</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Se recomienda encarecidamente habilitar BitLocker para proteger los datos.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Arranque seguro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el arranque seguro está habilitado.</td></tr>
<tr><td><strong>Eje</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Es muy recomendable que habilites el arranque seguro para proteger tu equipo informático.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Módulo de plataforma segura</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Garantiza que el TPM es funcional.</td></tr>
<tr><td><strong>Eje</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Sin un TPM funcional, las funciones basadas en la seguridad como BitLocker pueden no funcionar correctamente.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de espera conectado</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el modo de espera conectado está habilitado.</td></tr>
<tr><td><strong>Eje</strong></td><td>Verdadero</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>El modo de espera conectado permite que un dispositivo Surface Reciba actualizaciones y notificaciones mientras no se está usando. Para obtener la mejor experiencia, se debe habilitar el modo de espera conectado.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Bluetooth</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si Bluetooth está habilitado.</td></tr>
<tr><td><strong>Eje</strong></td><td>Habilitado</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Modo de depuración</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el sistema operativo está en modo de depuración.</td></tr>
<tr><td><strong>Eje</strong></td><td>Normal</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>La opción de inicio de depuración habilita o deshabilita la depuración de kernel del sistema operativo Windows. Habilitar esta opción puede provocar la inestabilidad del sistema y puede impedir que se reproduzcan los medios protegidos de DRM (managemend).</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Firma de prueba</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si la firma de prueba está habilitada.</td></tr>
<tr><td><strong>Eje</strong></td><td>Normal</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>La firma de prueba es una configuración de inicio de Windows que solo se debe usar para probar los drivers preliminares.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Plan de energía activo</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba que el plan de energía correcto está activo.</td></tr>
<tr><td><strong>Eje</strong></td><td>Cuadrada</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Es muy recomendable usar el plan de energía "equilibrado" para maximizar la productividad y la duración de la batería.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si el dispositivo está actualizado con las actualizaciones de Windows.</td></tr>
<tr><td><strong>Eje</strong></td><td>Microsoft Silverlight (KB4023307), actualización de definiciones para antivirus de Windows Defender-KB2267602 (definición 1.279.1433.0)</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="ff9500">No es óptimo</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Si actualizas a la versión más reciente de Windows, estás seguro de que estás en el firmware y los drivers más recientes. Se recomienda mantener el dispositivo siempre actualizado</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Espacio libre en el disco duro</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Comprueba si hay espacio libre en el disco duro.</td></tr>
<tr><td><strong>Eje</strong></td><td>66%</td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Para obtener el mejor rendimiento, el disco duro debe tener al menos el 10% de su capacidad en espacio libre.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Dispositivos que no funcionen</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Lista de dispositivos que no funcionan en el administrador de dispositivos.</td></tr>
<tr><td><strong>Eje</strong></td><td></td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Los dispositivos que no funcionen en el administrador de dispositivos pueden causar problemas imprevisibles con dispositivos Surface, como, entre otros, no ahorro de energía para el componente de hardware respectivo.</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Monitor externo</font></th></tr>
<tr><td><strong>Descripción:</strong></td><td>Busca un monitor externo que pueda tener problemas de compatibilidad.</td></tr>
<tr><td><strong>Eje</strong></td><td></td></tr>
<tr><td><strong>Requisito</strong></td><td><font color="00ff00">Ideal</font></td></tr>
<tr><td><strong>Indicaciones</strong></td><td>Consulta con el fabricante de equipos originales para la compatibilidad con tu dispositivo Surface.</td></tr>
</table>

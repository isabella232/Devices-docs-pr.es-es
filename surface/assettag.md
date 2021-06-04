---
title: Herramienta de etiqueta de activos de Surface
description: En este tema se explica cómo usar la herramienta de etiqueta de activos de Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834746"
---
# Herramienta de etiqueta de activos de Surface

La etiqueta de activo de Surface es una utilidad de interfaz de línea de comandos (CLI) que permite ver, asignar y modificar un valor de etiqueta de activo asignado para dispositivos de Surface. Funciona en Surface Pro 3 y en todos los dispositivos de superficie más recientes.

##  <a name="system-requirements"></a>Requisitos del sistema

- Surface Pro 3 o posterior

- Versión de firmware UEFI 3.9.150.0 o posterior

##  <a name="using-surface-asset-tag-"></a>Uso de etiquetas de activos de Surface 

Para ejecutar la etiqueta de inventario de Surface:

1.  En el dispositivo Surface, descargue **surface Tag.zip** en el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extraiga el archivo zip y guarde AssetTag.exe en la carpeta deseada (en este ejemplo, C:\\assets).

    > [!NOTE]
    > Para Surface Pro X, use la aplicación denominada **AssetTag_x86** en el archivo zip. 

2.  Abra una consola de comandos como administrador y ejecute AssetTag.exe, para ello, escriba la ruta completa de la herramienta.

3.  Superficie de reinicio.

###  <a name="asset-tag-tool-commands"></a>Comandos de la herramienta etiqueta de activos   
En los siguientes ejemplos, AssetTag.exe se guarda en un directorio en un equipo local (C:\assets). 

Para obtener la etiqueta de activo propuesta, ejecute AssetTag-g.

**Ejemplo**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 Para borrar la etiqueta de activo propuesta, ejecute AssetTag-s.
 
 **Ejemplo**
 
   ```
C:\assets\AssetTag.exe -s
  ```
Para establecer la etiqueta de activo propuesta, ejecute AssetTag-s testassettag12.

**Ejemplo**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>El valor de la etiqueta de activo debe contener entre 1 y 36 caracteres. Los caracteres válidos son A-Z, a-z, 0-9, punto (.) y guión (-).


##  <a name="managing-asset-tags"></a>Administración de etiquetas de activos

Puede ver la etiqueta de activo existente en la configuración de UEFI en información del dispositivo (**Panel de Control > recuperación > inicio avanzado > reiniciar ahora**).

La siguiente ilustración muestra los resultados de la ejecución de la herramienta de etiqueta de activos en Surface go.

![Resultados de la herramienta de etiqueta de activos de Surface en Surface go.
](images/assettag-fig1.png)

> **Figura 1.** Resultados de la herramienta de etiqueta de activos de Surface en la superficie Go

Como alternativa, puede usar WMI para consultar la etiqueta de activo existente en un dispositivo:

(Get-WmiObject-Query "Select * from Win32_SystemEnclosure")

**Ejemplo**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
###  <a name="using-powershell"></a>Uso de PowerShell

Puede usar la siguiente secuencia de comandos como forma de obtener el valor propuesto e interpretar los errores.

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```

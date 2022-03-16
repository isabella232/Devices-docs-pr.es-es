---
title: Herramienta de etiqueta de activos de Surface
description: En este tema se explica cómo usar la Herramienta de etiqueta de activos de Surface.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 3b6525c979160d6f732e330086565c3de6f73cbd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449153"
---
# <a name="surface-asset-tag-tool"></a>Herramienta de etiqueta de activos de Surface

Surface Asset Tag es una utilidad de interfaz de línea de comandos (CLI) que te permite ver, asignar y modificar un valor de etiqueta de activo asignado para dispositivos Surface. Funciona en Surface Pro 3 y todos los dispositivos Surface más recientes.

## <a name="system-requirements"></a>Requisitos del sistema

- Surface Pro 3 o posterior

- Versión de firmware uefi 3.9.150.0 o posterior

## <a name="using-surface-asset-tag"></a>Usar etiqueta de activos de Surface

Para ejecutar la etiqueta de activos de Surface:

1. En el dispositivo Surface, descarga **Surface Asset Tag.zip** desde el Centro de descarga de [Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extrae el archivo zip y guarda AssetTag.exe en la carpeta deseada (en este ejemplo, C:\\assets).

    > [!NOTE]
    > Para Surface Pro X, use la aplicación denominada **AssetTag_x86** en el archivo ZIP.

2. Abra una consola de comandos como administrador y ejecute AssetTag.exe, especificando la ruta de acceso completa a la herramienta.

3. Reinicie Surface.

    > [!NOTE]
    > Después de establecer la etiqueta de activo, se requiere un segundo reinicio antes de que aparezca en WMI.

### <a name="asset-tag-tool-commands"></a>Comandos de la herramienta Etiqueta de activos

En los ejemplos siguientes, AssetTag.exe se guarda en un directorio de una máquina local (C:\assets).

Para obtener la etiqueta de activo propuesta, ejecute **AssetTag -g**:

```console
C:\assets\AssetTag.exe -g
```

Para borrar la etiqueta de activo propuesta, ejecute **AssetTag -s**:

```console
C:\assets\AssetTag.exe -s
```

Para establecer la etiqueta de activo propuesta, ejecute **AssetTag -s testassettag12**:

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>El valor de la etiqueta de activo debe contener entre 1 y 36 caracteres. Los caracteres válidos incluyen A-Z, a-z, 0-9, punto (.) y guión (-).

## <a name="managing-asset-tags"></a>Administración de etiquetas de activos

Puedes ver la etiqueta de activo existente en la configuración de UEFI en Información del dispositivo (**Panel de control > recuperación > inicio > reiniciar ahora**).

En la figura siguiente se muestran los resultados de la ejecución de la Herramienta de etiqueta de activos en Surface Go.

![Resultados de la ejecución de la herramienta Etiqueta de activos de Surface en Surface Go.](images/assettag-fig1.png)

> **Figura 1.** Resultados de la ejecución de la herramienta Etiqueta de activos de Surface en Surface Go

Como alternativa, puedes usar WMI para consultar la etiqueta de activo existente en un dispositivo:

(Get-WmiObject -query "Select * from Win32_SystemEnclosure")

### <a name="example"></a>Por ejemplo:

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>Uso de PowerShell

Puede usar el script siguiente como una forma de obtener el valor propuesto e interpretar cualquier error.

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```

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
# <span data-ttu-id="96a51-103">Herramienta de etiqueta de activos de Surface</span><span class="sxs-lookup"><span data-stu-id="96a51-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="96a51-104">La etiqueta de activo de Surface es una utilidad de interfaz de línea de comandos (CLI) que permite ver, asignar y modificar un valor de etiqueta de activo asignado para dispositivos de Surface.</span><span class="sxs-lookup"><span data-stu-id="96a51-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="96a51-105">Funciona en Surface Pro 3 y en todos los dispositivos de superficie más recientes.</span><span class="sxs-lookup"><span data-stu-id="96a51-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="96a51-106">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="96a51-106">System requirements</span></span>

- <span data-ttu-id="96a51-107">Surface Pro 3 o posterior</span><span class="sxs-lookup"><span data-stu-id="96a51-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="96a51-108">Versión de firmware UEFI 3.9.150.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="96a51-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="96a51-109">Uso de etiquetas de activos de Surface</span><span class="sxs-lookup"><span data-stu-id="96a51-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="96a51-110">Para ejecutar la etiqueta de inventario de Surface:</span><span class="sxs-lookup"><span data-stu-id="96a51-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="96a51-111">En el dispositivo Surface, descargue **surface Tag.zip** en el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=46703), extraiga el archivo zip y guarde AssetTag.exe en la carpeta deseada (en este ejemplo, C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="96a51-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="96a51-112">Para Surface Pro X, use la aplicación denominada **AssetTag_x86** en el archivo zip.</span><span class="sxs-lookup"><span data-stu-id="96a51-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="96a51-113">Abra una consola de comandos como administrador y ejecute AssetTag.exe, para ello, escriba la ruta completa de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="96a51-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="96a51-114">Superficie de reinicio.</span><span class="sxs-lookup"><span data-stu-id="96a51-114">Restart Surface.</span></span>

### <span data-ttu-id="96a51-115">Comandos de la herramienta etiqueta de activos</span><span class="sxs-lookup"><span data-stu-id="96a51-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="96a51-116">En los siguientes ejemplos, AssetTag.exe se guarda en un directorio en un equipo local (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="96a51-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="96a51-117">Para obtener la etiqueta de activo propuesta, ejecute AssetTag-g.</span><span class="sxs-lookup"><span data-stu-id="96a51-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="96a51-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96a51-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="96a51-119">Para borrar la etiqueta de activo propuesta, ejecute AssetTag-s.</span><span class="sxs-lookup"><span data-stu-id="96a51-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="96a51-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96a51-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="96a51-121">Para establecer la etiqueta de activo propuesta, ejecute AssetTag-s testassettag12.</span><span class="sxs-lookup"><span data-stu-id="96a51-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="96a51-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96a51-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="96a51-123">El valor de la etiqueta de activo debe contener entre 1 y 36 caracteres.</span><span class="sxs-lookup"><span data-stu-id="96a51-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="96a51-124">Los caracteres válidos son A-Z, a-z, 0-9, punto (.) y guión (-).</span><span class="sxs-lookup"><span data-stu-id="96a51-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="96a51-125">Administración de etiquetas de activos</span><span class="sxs-lookup"><span data-stu-id="96a51-125">Managing asset tags</span></span>

<span data-ttu-id="96a51-126">Puede ver la etiqueta de activo existente en la configuración de UEFI en información del dispositivo (**Panel de Control > recuperación > inicio avanzado > reiniciar ahora**).</span><span class="sxs-lookup"><span data-stu-id="96a51-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="96a51-127">La siguiente ilustración muestra los resultados de la ejecución de la herramienta de etiqueta de activos en Surface go.</span><span class="sxs-lookup"><span data-stu-id="96a51-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="96a51-128">Resultados de la herramienta de etiqueta de activos de Surface en Surface go.</span><span class="sxs-lookup"><span data-stu-id="96a51-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="96a51-129">Figura 1.</span><span class="sxs-lookup"><span data-stu-id="96a51-129">Figure 1.</span></span>** <span data-ttu-id="96a51-130">Resultados de la herramienta de etiqueta de activos de Surface en la superficie Go</span><span class="sxs-lookup"><span data-stu-id="96a51-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="96a51-131">Como alternativa, puede usar WMI para consultar la etiqueta de activo existente en un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="96a51-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="96a51-132">(Get-WmiObject-Query "Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="96a51-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="96a51-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96a51-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="96a51-134">Uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="96a51-134">Using PowerShell</span></span>

<span data-ttu-id="96a51-135">Puede usar la siguiente secuencia de comandos como forma de obtener el valor propuesto e interpretar los errores.</span><span class="sxs-lookup"><span data-stu-id="96a51-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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

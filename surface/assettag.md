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
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643836"
---
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="040fb-103">Herramienta de etiqueta de activos de Surface</span><span class="sxs-lookup"><span data-stu-id="040fb-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="040fb-104">Surface Asset Tag es una utilidad de interfaz de línea de comandos (CLI) que te permite ver, asignar y modificar un valor de etiqueta de activo asignado para dispositivos Surface.</span><span class="sxs-lookup"><span data-stu-id="040fb-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="040fb-105">Funciona en Surface Pro 3 y todos los dispositivos Surface más recientes.</span><span class="sxs-lookup"><span data-stu-id="040fb-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="040fb-106">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="040fb-106">System requirements</span></span>

- <span data-ttu-id="040fb-107">Surface Pro 3 o posterior</span><span class="sxs-lookup"><span data-stu-id="040fb-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="040fb-108">Versión de firmware uefi 3.9.150.0 o posterior</span><span class="sxs-lookup"><span data-stu-id="040fb-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="040fb-109">Usar etiqueta de activos de Surface</span><span class="sxs-lookup"><span data-stu-id="040fb-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="040fb-110">Para ejecutar la etiqueta de activos de Surface:</span><span class="sxs-lookup"><span data-stu-id="040fb-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="040fb-111">En el dispositivo Surface, descarga **Surface Asset Tag.zip** desde el Centro de descarga de [Microsoft,](https://www.microsoft.com/download/details.aspx?id=46703)extrae el archivo zip y guarda AssetTag.exe en la carpeta deseada (en este ejemplo, C:\\assets).</span><span class="sxs-lookup"><span data-stu-id="040fb-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="040fb-112">Para Surface Pro X, use la aplicación denominada **AssetTag_x86** en el archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="040fb-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="040fb-113">Abra una consola de comandos como administrador y ejecute AssetTag.exe, especificando la ruta de acceso completa a la herramienta.</span><span class="sxs-lookup"><span data-stu-id="040fb-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="040fb-114">Reinicie Surface.</span><span class="sxs-lookup"><span data-stu-id="040fb-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="040fb-115">Después de establecer la etiqueta de activo, se requiere un segundo reinicio antes de que aparezca en WMI.</span><span class="sxs-lookup"><span data-stu-id="040fb-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="040fb-116">Comandos de la herramienta Etiqueta de activos</span><span class="sxs-lookup"><span data-stu-id="040fb-116">Asset Tag tool commands</span></span>

<span data-ttu-id="040fb-117">En los ejemplos siguientes, AssetTag.exe se guarda en un directorio de una máquina local (C:\assets).</span><span class="sxs-lookup"><span data-stu-id="040fb-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="040fb-118">Para obtener la etiqueta de activo propuesta, ejecute **AssetTag -g**:</span><span class="sxs-lookup"><span data-stu-id="040fb-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="040fb-119">Para borrar la etiqueta de activo propuesta, ejecute **AssetTag -s**:</span><span class="sxs-lookup"><span data-stu-id="040fb-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="040fb-120">Para establecer la etiqueta de activo propuesta, ejecute **AssetTag -s testassettag12**:</span><span class="sxs-lookup"><span data-stu-id="040fb-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="040fb-121">El valor de la etiqueta de activo debe contener entre 1 y 36 caracteres.</span><span class="sxs-lookup"><span data-stu-id="040fb-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="040fb-122">Los caracteres válidos incluyen A-Z, a-z, 0-9, punto (.) y guión (-).</span><span class="sxs-lookup"><span data-stu-id="040fb-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="040fb-123">Administración de etiquetas de activos</span><span class="sxs-lookup"><span data-stu-id="040fb-123">Managing asset tags</span></span>

<span data-ttu-id="040fb-124">Puedes ver la etiqueta de activo existente en la configuración de UEFI en Información del dispositivo ( Panel de**control > Recuperación**> inicio > reiniciar ahora ).)</span><span class="sxs-lookup"><span data-stu-id="040fb-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="040fb-125">En la figura siguiente se muestran los resultados de la ejecución de la Herramienta de etiqueta de activos en Surface Go.</span><span class="sxs-lookup"><span data-stu-id="040fb-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![Resultados de la ejecución de la herramienta Etiqueta de activos de Surface en Surface Go.](images/assettag-fig1.png)

> **<span data-ttu-id="040fb-127&quot;>Figura 1.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;040fb-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;040fb-128&quot;>Resultados de la ejecución de la herramienta Etiqueta de activos de Surface en Surface Go</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;040fb-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;040fb-129&quot;>Como alternativa, puedes usar WMI para consultar la etiqueta de activo existente en un dispositivo:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;040fb-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;040fb-130&quot;>(Get-WmiObject -query &quot;Select \* from Win32_SystemEnclosure")</span><span class="sxs-lookup"><span data-stu-id="040fb-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="040fb-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="040fb-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="040fb-132">Uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="040fb-132">Using PowerShell</span></span>

<span data-ttu-id="040fb-133">Puede usar el script siguiente como una forma de obtener el valor propuesto e interpretar cualquier error.</span><span class="sxs-lookup"><span data-stu-id="040fb-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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

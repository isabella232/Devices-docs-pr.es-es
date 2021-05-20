---
title: Configurar el menú Inicio de Surface Hub
description: Usar MDM para personalizar el menú Inicio en Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: cf9649b8d1f747722064793fbbde70116bc7f424
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576850"
---
# <a name="configure-surface-hub-start-menu"></a><span data-ttu-id="bcd90-103">Configurar el menú Inicio de Surface Hub</span><span class="sxs-lookup"><span data-stu-id="bcd90-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="bcd90-104">La [actualización de 17 de enero de 2018 a Windows 10](https://support.microsoft.com/help/4057144) (compilación 15063.877) permite menús Inicio personalizados en dispositivos Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="bcd90-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="bcd90-105">Aplica el diseño del menú Inicio personalizado usando administración de dispositivos móviles (MDM).</span><span class="sxs-lookup"><span data-stu-id="bcd90-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="bcd90-106">Al aplicar un diseño de menú Inicio personalizado a Surface Hub, los usuarios no pueden anclar, desanclar ni desinstalar aplicaciones desde Inicio.</span><span class="sxs-lookup"><span data-stu-id="bcd90-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a><span data-ttu-id="bcd90-107">Cómo aplicar un menú Inicio personalizado a Surface Hub</span><span class="sxs-lookup"><span data-stu-id="bcd90-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="bcd90-108">El menú Inicio personalizado se define en un archivo XML de diseño de Inicio.</span><span class="sxs-lookup"><span data-stu-id="bcd90-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="bcd90-109">Tienes dos opciones para crear el archivo XML de diseño de Inicio:</span><span class="sxs-lookup"><span data-stu-id="bcd90-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="bcd90-110">Editar el [XML de Inicio de Surface Hub predeterminado](#default)</span><span class="sxs-lookup"><span data-stu-id="bcd90-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="bcd90-111">O bien</span><span class="sxs-lookup"><span data-stu-id="bcd90-111">-or-</span></span>

- <span data-ttu-id="bcd90-112">Configurar el menú Inicio deseado en un equipo de escritorio (anclando solo aplicaciones que estén disponibles en Surface Hub) y luego [exportar el diseño](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span><span class="sxs-lookup"><span data-stu-id="bcd90-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="bcd90-113">Para agregar una ventana con un vínculo web al menú Inicio de escritorio, ve al vínculo en Microsoft Edge, selecciona `...` en la esquina superior derecha y selecciona **Anclar esta página a Inicio**.</span><span class="sxs-lookup"><span data-stu-id="bcd90-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="bcd90-114">Consulta [un diseño de Inicio que incluya un vínculo de Microsoft Edge](#edge) para ver un ejemplo de cómo aparecerán los vínculos en el XML.</span><span class="sxs-lookup"><span data-stu-id="bcd90-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="bcd90-115">Para editar el XML predeterminado o el diseño exportado, familiarízate con el [XML de diseño de Inicio](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span><span class="sxs-lookup"><span data-stu-id="bcd90-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="bcd90-116">Hay unas pocas [diferencias entre el diseño de Inicio en un escritorio y en Surface Hub.](#differences)</span><span class="sxs-lookup"><span data-stu-id="bcd90-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="bcd90-117">Cuando tengas el menú Inicio definido en un XML de diseño de Inicio, [crea una directiva MDM para aplicar el diseño.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="bcd90-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a><span data-ttu-id="bcd90-118">Diferencias entre los menús Inicio de Surface Hub y de escritorio</span><span class="sxs-lookup"><span data-stu-id="bcd90-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="bcd90-119">Existen unas pocas diferencias clave entre la personalización del menú Inicio para Surface Hub y para un escritorio de Windows 10:</span><span class="sxs-lookup"><span data-stu-id="bcd90-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="bcd90-120">No puede usar **DesktopApplicationTile** ( en el XML de diseño de inicio porque Windows aplicaciones de escritorio https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) (Win32) no se admiten en Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="bcd90-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="bcd90-121">No puedes usar el XML de diseño de Inicio para configurar la barra de tareas o la pantalla de inicio de sesión de Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="bcd90-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="bcd90-122">La directiva de diseño de inicio solo debe asignarse a dispositivos, no a usuarios.</span><span class="sxs-lookup"><span data-stu-id="bcd90-122">The Start layout policy should be assigned only to devices, not users.</span></span>
- <span data-ttu-id="bcd90-123">La configuración de OMA-URI que se va a usar en la directiva es</span><span class="sxs-lookup"><span data-stu-id="bcd90-123">The OMA-URI setting to use in the policy is</span></span> `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- <span data-ttu-id="bcd90-124">Surface Hub admite un máximo de 6 columnas (6 ventanas 1 x 1); sin embargo, **debes** definir `GroupCellWidth=8` incluso aunque Surface Hub muestre solo ventanas de pantalla en las columnas 0 - 5, y no en las columnas 6 y 7.</span><span class="sxs-lookup"><span data-stu-id="bcd90-124">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="bcd90-125">Surface Hub admite un número máximo de 6 filas (6 iconos de 1 x 1)</span><span class="sxs-lookup"><span data-stu-id="bcd90-125">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="bcd90-126">, que se usa para vínculos, que abrirán el vínculo en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="bcd90-126">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a><span data-ttu-id="bcd90-127">Ejemplo: Diseño de Inicio de Surface Hub predeterminado</span><span class="sxs-lookup"><span data-stu-id="bcd90-127">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a><span data-ttu-id="bcd90-128">Ejemplo: Diseño de Inicio que incluye un vínculo de Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bcd90-128">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="bcd90-129">Este ejemplo muestra un vínculo a un sitio web y un vínculo a un archivo .pdf.</span><span class="sxs-lookup"><span data-stu-id="bcd90-129">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="bcd90-130">El icono secundario de Microsoft Edge usa un icono de 150 x 150 píxeles.</span><span class="sxs-lookup"><span data-stu-id="bcd90-130">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="bcd90-131">El valor predeterminado de es light; no es necesario incluirlo en el XML a menos que cambie el `ForegroundText` `ForegroundText` valor a oscuro.</span><span class="sxs-lookup"><span data-stu-id="bcd90-131">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>

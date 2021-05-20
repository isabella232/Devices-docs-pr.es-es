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
# <a name="configure-surface-hub-start-menu"></a>Configurar el menú Inicio de Surface Hub

La [actualización de 17 de enero de 2018 a Windows 10](https://support.microsoft.com/help/4057144) (compilación 15063.877) permite menús Inicio personalizados en dispositivos Surface Hub. Aplica el diseño del menú Inicio personalizado usando administración de dispositivos móviles (MDM).

Al aplicar un diseño de menú Inicio personalizado a Surface Hub, los usuarios no pueden anclar, desanclar ni desinstalar aplicaciones desde Inicio. 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>Cómo aplicar un menú Inicio personalizado a Surface Hub

El menú Inicio personalizado se define en un archivo XML de diseño de Inicio. Tienes dos opciones para crear el archivo XML de diseño de Inicio:

- Editar el [XML de Inicio de Surface Hub predeterminado](#default)

    O bien

- Configurar el menú Inicio deseado en un equipo de escritorio (anclando solo aplicaciones que estén disponibles en Surface Hub) y luego [exportar el diseño](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).

>[!TIP]
>Para agregar una ventana con un vínculo web al menú Inicio de escritorio, ve al vínculo en Microsoft Edge, selecciona `...` en la esquina superior derecha y selecciona **Anclar esta página a Inicio**. Consulta [un diseño de Inicio que incluya un vínculo de Microsoft Edge](#edge) para ver un ejemplo de cómo aparecerán los vínculos en el XML.

Para editar el XML predeterminado o el diseño exportado, familiarízate con el [XML de diseño de Inicio](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop). Hay unas pocas [diferencias entre el diseño de Inicio en un escritorio y en Surface Hub.](#differences)

Cuando tengas el menú Inicio definido en un XML de diseño de Inicio, [crea una directiva MDM para aplicar el diseño.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Diferencias entre los menús Inicio de Surface Hub y de escritorio

Existen unas pocas diferencias clave entre la personalización del menú Inicio para Surface Hub y para un escritorio de Windows 10:

- No puede usar **DesktopApplicationTile** ( en el XML de diseño de inicio porque Windows aplicaciones de escritorio https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) (Win32) no se admiten en Surface Hub.
- No puedes usar el XML de diseño de Inicio para configurar la barra de tareas o la pantalla de inicio de sesión de Surface Hub.  
- La directiva de diseño de inicio solo debe asignarse a dispositivos, no a usuarios.
- La configuración de OMA-URI que se va a usar en la directiva es `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- Surface Hub admite un máximo de 6 columnas (6 ventanas 1 x 1); sin embargo, **debes** definir `GroupCellWidth=8` incluso aunque Surface Hub muestre solo ventanas de pantalla en las columnas 0 - 5, y no en las columnas 6 y 7.
- Surface Hub admite un número máximo de 6 filas (6 iconos de 1 x 1)
- `SecondaryTile`, que se usa para vínculos, que abrirán el vínculo en Microsoft Edge.


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>Ejemplo: Diseño de Inicio de Surface Hub predeterminado

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

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>Ejemplo: Diseño de Inicio que incluye un vínculo de Microsoft Edge

Este ejemplo muestra un vínculo a un sitio web y un vínculo a un archivo .pdf. El icono secundario de Microsoft Edge usa un icono de 150 x 150 píxeles.

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
>El valor predeterminado de es light; no es necesario incluirlo en el XML a menos que cambie el `ForegroundText` `ForegroundText` valor a oscuro.

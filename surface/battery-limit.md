---
title: Configuración del límite de la batería (Surface)
description: El límite de la batería es una configuración de UEFI que cambia el modo en que se cobra la batería del dispositivo Surface y puede prolongar su longevidad.
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 5/06/2020
ms.openlocfilehash: 927f00681bd5756f380025adf00a08a34a3f411f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835986"
---
# Configuración del límite de batería

La opción de límite de batería es una configuración de UEFI que cambia el modo en que se cobra la batería del dispositivo Surface y puede prolongar su longevidad. Esta configuración se recomienda en aquellos casos en los que el dispositivo está continuamente conectado a la alimentación eléctrica, por ejemplo cuando los dispositivos se integran en soluciones de quiosco.  

## Cómo funciona el límite de batería

Si estableces el dispositivo en el límite de la batería, se cambiará el protocolo para cargar la batería del dispositivo. Cuando el límite de la batería está habilitado, la carga de la batería se limitará al 50% de su capacidad máxima. El nivel de cargo registrado en Windows reflejará este límite. Por lo tanto, mostrará que la batería se carga hasta el 50% y no se cobrará más allá de este límite. Si habilita el límite de la batería mientras el dispositivo está por encima del 50% de cargo, el icono de la batería mostrará que el dispositivo está conectado, pero se descargará hasta que el dispositivo alcance el 50% de la capacidad máxima de carga.  

## Dispositivos compatibles
El ajuste de límite de batería de UEFI está integrado en los últimos dispositivos de Surface, incluidos Surface Pro 7 y Surface Laptop 3. Los dispositivos anteriores requieren una [actualización de firmware de Surface UEFI](manage-surface-driver-and-firmware-updates.md), disponible a través de Windows Update o a través del controlador MSI y paquetes de firmware en el [sitio de asistencia de superficie](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface). Seleccione [Activar "límite de batería" para los dispositivos de Surface que deben conectarse durante largos períodos de tiempo](https://support.microsoft.com/help/4464941) para la versión UEFI de la superficie específica requerida para cada dispositivo admitido. 

## Habilitar límite de batería en Surface UEFI (Surface Pro 4 y posterior)

La configuración del límite de la batería de Surface UEFI se puede configurar arrancando en Surface UEFI (**Power + Vol up** al encender el dispositivo). Elija **configuración de arranque**y, a continuación, en **Opciones avanzadas**, Active activar el **modo de límite de batería** **en activado**.  

![Captura de pantalla de opciones avanzadas](images/enable-bl.png) 

## Habilitar el límite de batería en Surface Go y Surface Go 2
La configuración del límite de batería de superficie se puede configurar al arrancar en Surface UEFI (**Power + Vol** al encender el dispositivo). Elija **configuración de arranque**y, a continuación, en **modo de pantalla completa**, mueva el control deslizante hacia la derecha para establecer límite de batería en **habilitado**.  

![Captura de pantalla del límite de batería de modo quiosco en Surface Go](images/go-batterylimit.png) 

## Habilitar límite de batería en Surface UEFI (Surface Pro 3)

La configuración del límite de la batería de Surface UEFI se puede configurar arrancando en Surface UEFI (**Power + Vol up** al encender el dispositivo). Elija **modo de pantalla completa**, seleccione **límite de batería**y, a continuación, seleccione **habilitado**.

![Captura de pantalla de opciones avanzadas](images/enable-bl-sp3.png) 

![Captura de pantalla de opciones avanzadas](images/enable-bl-sp3-2.png) 

## Habilitar el límite de batería con el modo de administración de Surface Enterprise (SEMM) o los scripts de PowerShell de firmware Surface Pro 3

El límite de batería de Surface UEFI también está disponible para la configuración a través de los métodos siguientes:

- Surface Pro 4 y posterior 
    - [Configurador UEFI de Surface de Microsoft](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Scripts de PowerShell de Surface UEFI Manager (SEMM_Powershell.zip) en las [herramientas de Surface para descargas de ti](https://www.microsoft.com/download/details.aspx?id=46703)
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### Uso del configurador Microsoft Surface UEFI

Para configurar el modo de límite de batería, establezca la configuración de **invalidaciones de quiosco** en la página de configuración de **Configuración avanzada** en SEMM (Surface Pro 4 y posterior).

![Captura de pantalla de configuración avanzada](images/semm-bl.png)

### Uso de scripts de PowerShell de Surface UEFI Manager

La característica de límite de batería se controla mediante la siguiente configuración:  

`407 = Battery Profile`

**Descripción**: Plan de administración activo para el patrón de uso de la batería

**Valor predeterminado**:  `0` 

Establezca esta opción para `1` Habilitar el límite de batería.

### Uso de las herramientas de firmware Surface Pro 3

La característica de límite de batería se controla mediante la siguiente configuración:  

**Nombre**: BatteryLimitEnable

**Descripción**: BatteryLimit

**Valor actual**:  `0` 

**Valor predeterminado**: `0`

**Valor propuesto**: `0` 

Establezca esta opción para `1` Habilitar el límite de batería.

>[!NOTE]
>Para configurar esta opción, debe usar [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703). 


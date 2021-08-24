---
title: Configuración de límite de batería (Surface)
description: Límite de batería es una configuración UEFI que cambia la forma en que se carga la batería del dispositivo Surface y puede prolongar su longevidad.
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
ms.date: 1/15/2021
ms.openlocfilehash: 52e43a1ac14f89f5671b6fad8fc2e1ef49480470
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911845"
---
# <a name="battery-limit-setting"></a>Configuración del límite de batería

La opción Límite de batería es una configuración UEFI que cambia la forma en que se carga la batería del dispositivo Surface y puede prolongar su longevidad. Esta configuración se recomienda en casos en los que el dispositivo está conectado continuamente a la energía, por ejemplo, cuando los dispositivos están integrados en soluciones de quiosco.  

## <a name="how-battery-limit-works"></a>Cómo funciona el límite de batería

Al establecer el dispositivo en Límite de batería, se cambia el protocolo para cargar la batería del dispositivo. Cuando el límite de batería está habilitado, la carga de la batería se limitará al 50 % de su capacidad máxima. El nivel de carga notificado en Windows reflejará este límite. Por lo tanto, se mostrará que la batería se carga hasta un 50 % y no se cargará más allá de este límite. Si habilitas el límite de batería mientras el dispositivo está por encima del 50 % de carga, el icono De batería mostrará que el dispositivo está conectado pero que se descarga hasta que el dispositivo alcanza el 50 % de su capacidad de carga máxima.  

## <a name="supported-devices"></a>Dispositivos compatibles

La configuración UEFI límite de batería está integrada en los dispositivos Surface más recientes, incluidos Surface Pro 7+, Surface Pro 7 y Surface Laptop 3. Los dispositivos anteriores requieren una actualización de firmware de [UEFI](manage-surface-driver-and-firmware-updates.md)de Surface, disponible a través de Windows Update o a través del controlador MSI y los paquetes de firmware en el [sitio de soporte técnico de Surface.](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface) Activa [Habilitar "Límite](https://support.microsoft.com/help/4464941) de batería" para dispositivos Surface que tengan que conectarse durante períodos prolongados de tiempo para la versión específica de UEFI de Surface necesaria para cada dispositivo compatible.

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>Habilitar el límite de batería en Surface UEFI (Surface Pro 4 y versiones posteriores)

La configuración de límite de batería de UEFI de Surface se puede configurar arrancando en Surface UEFI (**Power + Vol Up** al activar el dispositivo). Elija **configuración de**arranque y, a continuación, en Opciones **avanzadas,** cambie Habilitar el modo límite **de batería** a **On**.  

![Límite de batería Opciones avanzadas.](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-and-surface-go-2"></a>Habilitar el límite de batería en Surface Go y Surface Go 2

La configuración límite de batería de Surface se puede configurar arrancando en Surface UEFI (**Power + Vol Up** al activar el dispositivo). Elija **configuración de**arranque y, a continuación, en Modo de pantalla **completa,** mueva el control deslizante a la derecha para establecer el límite de batería en **Habilitado**.  

![Límite de batería del modo quiosco en Surface Go.](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>Habilitar el límite de batería en Surface UEFI (Surface Pro 3)

La configuración de límite de batería de UEFI de Surface se puede configurar arrancando en Surface UEFI (**Power + Vol Up** al activar el dispositivo). Elija **Modo quiosco,** seleccione **Límite de**batería y, a continuación, elija **Habilitado**.

![Captura de pantalla de opciones avanzadas.](images/enable-bl-sp3.png)

![Opciones avanzadas.](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>Habilitar el límite de batería mediante el modo de administración de Surface Enterprise (SEMM) o Surface Pro scripts de PowerShell de 3 firmware

El límite de batería uefi de Surface también está disponible para la configuración mediante los siguientes métodos:

- Surface Pro 4 y posteriores
  - [Microsoft Surface UEFI Configurator](surface-enterprise-management-mode.md)  
    - Scripts de Powershell de Surface UEFI Manager (SEMM_Powershell.zip) en las descargas [de Surface Tools para TI](https://www.microsoft.com/download/details.aspx?id=46703)

### <a name="using-microsoft-surface-uefi-configurator"></a>Uso de Microsoft Surface UEFI Configurator

Para configurar el modo límite de batería, **** establece la configuración **Invalidaciones** de quiosco en la página Configuración Configuración configuración avanzada en SEMM (Surface Pro 4 y versiones posteriores).

![Captura de pantalla de la configuración avanzada.](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>Uso de scripts de PowerShell de Surface UEFI Manager

La característica de límite de batería se controla mediante la siguiente configuración:  

`407 = Battery Profile`

**Descripción:** esquema de administración activa para el patrón de uso de batería

**Valor**predeterminado :  `0`

Esta opción se `1` establece para habilitar el límite de batería.

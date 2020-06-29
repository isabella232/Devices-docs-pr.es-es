---
title: Crear paquetes de aprovisionamiento para Surface Hub 2S
description: Esta página describe cómo implementar Surface Hub 2S con paquetes de aprovisionamiento y otras herramientas.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836941"
---
# Crear paquetes de aprovisionamiento para Surface Hub 2S

Puede usar el diseñador de configuración de Windows (WCD) para crear paquetes de aprovisionamiento para automatizar el proceso de implementación de Surface Hub 2S. Use paquetes de aprovisionamiento para agregar certificados, configurar servidores proxy, configurar cuentas de dispositivos y administradores de dispositivos. También puede usar paquetes de aprovisionamiento junto con un archivo de configuración para implementar varios Surface Hub con una sola unidad USB.

### Instalar el Diseñador de configuraciones de Windows

Instale el diseñador de configuración de Windows desde Windows Assessment and Deployment Kit (ADK) para Windows 10. Descargue e instale [ADK para Windows 10, versión 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Para obtener más información, consulte [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### Agregar certificados

Puede importar certificados de entidad de certificación a Surface Hub 2S.
Para agregar certificados a Surface Hub 2S, necesita una copia de cada certificado como X. 509 en formato. cer. No puedes importar. CRT,. pfx ni otros formatos de contenedor. Los certificados deben importarse al diseñador de configuración de Windows y organizarse por jerarquía:

 ![Agregar certificados](images/sh2-wcd.png)

### Configurar el proxy durante OOBE

En el diseñador de configuración de Windows, vaya a la pestaña configurar ajustes de proxy y escriba la configuración adecuada como se muestra a continuación.

 ![Definir la configuración de proxy](images/sh2-proxy.png) 

> [!NOTE]
> Al configurar la configuración de proxy, desactive **detectar automáticamente la configuración** si tiene previsto usar una secuencia de comandos de configuración o un servidor proxy. Puede usar un script de configuración *o* un servidor proxy, no ambos.

### Surface Hub 2 de afiliados con Azure Active Directory

Puede afiliar Surface Hub 2 con Azure Active Directory con un paquete de aprovisionamiento: como administrador global de Azure Active Directory, puede unir un gran número de dispositivos Windows nuevos a Azure Active Directory e Intune con un token en masa.

Para crear un token en masa, asígnele un nombre descriptivo, configure la fecha de expiración (máximo de 30 días) y use sus credenciales de administrador para adquirir el token tal y como se muestra a continuación:

 ![Configurar administradores de dispositivos](images/sh2-token.png) <br><br>
 ![Configurar administradores de dispositivos](images/sh2-token2.png) <br><br>
 ![Configurar administradores de dispositivos](images/sh2-token3.png) <br><br>

### Aprovisionamiento de varios dispositivos (archivo. csv)

Además del paquete de aprovisionamiento, puede usar un archivo de configuración de Surface hub para que sea aún más fácil configurar los dispositivos. Un archivo de configuración de Surface Hub contiene una lista de cuentas de dispositivos y nombres descriptivos para la proyección inalámbrica. Durante la primera ejecución, se obtiene una opción para elegir una cuenta del dispositivo y un nombre descriptivo en un archivo de configuración.

### Para crear un archivo de configuración de Surface Hub

1. Con Microsoft Excel u otro editor de CSV, cree un archivo CSV denominado: **SurfaceHubConfiguration.csv**
2. Escriba una lista de cuentas de dispositivos y nombres descriptivos en este formato:

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. Guarde el archivo en la raíz de la unidad USB en la que ha copiado el archivo PPKG.

    ![Ejemplo de archivo de configuración](images/sh2-config-file.png)

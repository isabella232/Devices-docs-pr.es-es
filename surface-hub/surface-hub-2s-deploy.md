---
title: Crear paquetes de aprovisionamiento para Surface Hub 2S
description: En esta página se describe cómo implementar Surface Hub 2S mediante paquetes de aprovisionamiento y otras herramientas.
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
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576870"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>Crear paquetes de aprovisionamiento para Surface Hub 2S

Puede usar Windows Configuration Designer (WCD) para crear paquetes de aprovisionamiento para automatizar la implementación de Surface Hub 2S. Usa paquetes de aprovisionamiento para agregar certificados, configurar servidores proxy, configurar administradores de dispositivos y cuentas de dispositivo. También puedes usar paquetes de aprovisionamiento junto con un archivo de configuración para implementar varios Surface Hubs con una única unidad usb.

### <a name="install-windows-configuration-designer"></a>Instalar el Diseñador de configuraciones de Windows

Instale Windows de configuración desde el kit de evaluación Windows e implementación (ADK) para Windows 10. Descargue e instale [el ADK para Windows 10, versión 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542). Para obtener más información, consulte [Descargar e instalar Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).

### <a name="add-certificates"></a>Agregar certificados

Puede importar certificados de entidad de certificación a Surface Hub 2S.
Para agregar certificados a Surface Hub 2S, necesita una copia de cada certificado como X.509 en formato .cer. No puede importar .crt, .pfx u otros formatos de contenedor. Los certificados deben importarse a Windows de configuración y organizarse por jerarquía:

> [!div class="mx-imgBorder"]
> ![Agregar certificados](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>Configurar proxy durante OOBE

En Windows Configuration Designer, vaya a la pestaña Configurar opciones de proxy y escriba la configuración adecuada como se muestra a continuación.

> [!div class="mx-imgBorder"]
> ![Definir la configuración de proxy](images/sh2-proxy.png) 

> [!NOTE]
> Al configurar la configuración de proxy, desactiva **Detectar automáticamente** la configuración si quieres usar un script de instalación o un servidor proxy. Puede usar un script de instalación *o un* servidor proxy, no ambos.

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>Filiale Surface Hub 2S con Azure Active Directory

Puede asociar Surface Hub 2S con Azure Active Directory mediante un paquete de aprovisionamiento: como administrador global de Azure Active Directory, puede unir un gran número de nuevos dispositivos Windows a Azure Active Directory e Intune mediante un token masivo.

Para crear un token masivo, asigne un nombre descriptivo, configure la fecha de expiración (máximo de 30 días) y use sus credenciales de administrador para adquirir el token como se muestra a continuación:

> [!div class="mx-imgBorder"]
> ![Ejemplo 1 de configuración de administradores de dispositivos](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![Ejemplo 2 de configurar administradores de dispositivos](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![Ejemplo 3 de configurar administradores de dispositivos](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>Aprovisionamiento de varios dispositivos (.csv archivo)

Además del paquete de aprovisionamiento, puedes usar un archivo de configuración Surface Hub para que sea aún más fácil configurar los dispositivos. Un Surface Hub de configuración contiene una lista de cuentas de dispositivo y nombres descriptivos para la proyección inalámbrica. Durante la primera ejecución, obtienes una opción para elegir una cuenta de dispositivo y un nombre descriptivo de un archivo de configuración.

### <a name="to-create-a-surface-hub-configuration-file"></a>Para crear un archivo Surface Hub de configuración

1. Con Microsoft Excel u otro editor CSV, cree un archivo CSV denominado: **SurfaceHubConfiguration.csv**

2. Escribe una lista de cuentas de dispositivo y nombres descriptivos en este formato:

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. Guarde el archivo en la raíz de la unidad usb donde copió el archivo PPKG.

    > [!div class="mx-imgBorder"]
    > ![Ejemplo de archivo de configuración](images/sh2-config-file.png)

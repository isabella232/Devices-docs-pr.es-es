---
title: Proteger y administrar Surface Hub 2S con SEMM
description: Obtenga más información sobre cómo proteger Surface Hub 2S con SEMM.
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
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911045"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>Proteger y administrar Surface Hub 2S con SEMM y UEFI

Como novedad Surface Hub 2S, puedes usar SEMM para administrar la configuración UEFI del dispositivo.
Usa el Configurador UEFI de Microsoft Surface para controlar los siguientes componentes:

- LAN de cable
- Cámaras
- Bluetooth
- Wi-Fi
- Sensor de ocupación

Usa el Configurador UEFI de Microsoft Surface para activar o desactivar la siguiente configuración de UEFI:

- Arranque

    - IPv6 para el arranque PXE
    - Arranque alternativo
    - Bloqueo de orden de arranque
    - Arranque desde USB
- Página principal uefi

    - Dispositivos
    - Arranque
    - Fecha y hora

## <a name="create-uefi-configuration-image"></a>Crear imagen de configuración de UEFI

A diferencia de otros dispositivos Surface, no puedes usar un archivo MSI o una imagen win PE para aplicar esta configuración en Surface Hub 2S. En su lugar, debes crear una imagen USB para cargarla en el dispositivo. Para crear una Surface Hub de configuración de UEFI de 2S, descarga e instala la versión más reciente del Configurador UEFI de Microsoft Surface desde la página Herramientas de [Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft. Para obtener más información acerca del uso de UEFI y SEMM, consulta [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).

## <a name="to-configure-uefi-on-surface-hub-2s"></a>Para configurar UEFI en Surface Hub 2S

1. Inicie el configurador UEFI y, en la primera pantalla, elija **Paquete de configuración**.<br><br>
![* Inicie el configurador UEFI y elija Paquete de configuración*.](images/sh2-uefi1.png) <br> <br>
2. Para agregar el certificado al paquete, debe tener un certificado válido con la clave privada en un formato de archivo .pfx para firmar y proteger el paquete. Seleccione **+ Protección de certificados.** <br>
![* Seleccione + Protección de certificados *.](images/sh2-uefi2.png) <br><br>
3. Escriba la contraseña de la clave privada del certificado.<br>
![* Escriba la contraseña de la clave privada del certificado *.](images/sh2-uefi3.png) <br><br>
4. Después de importar la clave privada, continúe creando el paquete.<br>
![* Continuar creando el paquete *.](images/sh2-uefi4.png) <br><br>
5. Elija **Concentrador** y **Surface Hub 2S** como destino para el paquete de configuración de UEFI.<br>
![* Elija Concentrador y Surface Hub 2S como destino para el paquete de configuración de UEFI *.](images/sh2-uefi5.png) <br><br>
6. Elija los componentes y la configuración que desea activar o desactivar en Surface Hub 2S.<br>
![* Elija los componentes y la configuración que desea activar o desactivar *.](images/sh2-uefi6.png) <br><br>
7. Usa la opción USB para exportar el archivo.<br>
![* Use la opción USB para exportar el archivo *.](images/sh2-uefi8.png) <br><br>
8. Inserte y elija la unidad USB que desea usar para este paquete. La unidad USB tendrá formato y perderás cualquier información que tenga en ella.<br>
![* Inserte y elija la unidad USB del paquete *.](images/sh2-uefi9.png) <br><br>
9. Una vez creado correctamente el paquete, el Configurador mostrará los dos últimos caracteres de la huella digital del certificado. Necesita estos caracteres al importar a la configuración a Surface Hub 2S.<br>
![* Configuración correcta del paquete *.](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>Para arrancar en UEFI

Desactivar Surface Hub 2S. Mantenga presionado el botón **Subir** volumen y presione el **botón de** encendido. Mantenga presionado el botón Subir volumen hasta que aparezca el menú UEFI.

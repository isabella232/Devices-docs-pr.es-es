---
title: Proteger y administrar Surface Hub 2S con SEMM
description: Más información sobre cómo proteger Surface Hub 2S con SEMM.
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835273"
---
# Proteger y administrar Surface Hub 2S con SEMM y UEFI

Nuevo en Surface Hub 2S, puede usar SEMM para administrar la configuración de UEFI del dispositivo.
Use el configurador de Microsoft Surface UEFI para controlar los siguientes componentes:

- LAN de cable
- Cámaras
- Bluetooth
- Wi-Fi
- Sensor de ocupación

Use el configurador UEFI de Microsoft Surface para activar o desactivar los siguientes ajustes de UEFI:

- Arranque

    - IPv6 para el arranque PXE
    - Arranque alternativo
    - Bloqueo de orden de arranque
    - Arranque desde USB
- Página frontal de UEFI

    - Dispositivos
    - Arranque
    - Fecha y hora

##  <a name="create-uefi-configuration-image"></a>Crear imagen de configuración UEFI

A diferencia de otros dispositivos de Surface, no puede usar un archivo MSI o una imagen Win PE para aplicar esta configuración en Surface Hub 2S. En su lugar, debe crear una imagen USB para cargarla en el dispositivo. Para crear una imagen de configuración UEFI de Surface Hub 2S, descargue e instale la última versión del configurador Microsoft Surface UEFI desde la página [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft. Para obtener más información sobre el uso de UEFI y SEMM, consulte [modo de administración de Microsoft Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).

##  <a name="to-configure-uefi-on-surface-hub-2s"></a>Para configurar UEFI en Surface Hub 2S

1. Inicie el configurador UEFI y, en la primera pantalla, elija **paquete de configuración**.<br><br>
![* Inicie el configurador UEFI y seleccione paquete de configuración *](images/sh2-uefi1.png) <br> <br>
2. Para agregar el certificado a su paquete, debe tener un certificado válido con la clave privada en un formato de archivo. pfx para firmar y proteger el paquete. Seleccione **protección de certificado +.** <br>
![* Protección de certificados de selección *](images/sh2-uefi2.png) <br><br>
3. Escriba la contraseña de la clave privada del certificado.<br>
![* Escriba la contraseña de la clave privada del certificado *](images/sh2-uefi3.png) <br><br>
4. Después de importar la clave privada, siga creando el paquete.<br>
![* Continuar con la creación del paquete *](images/sh2-uefi4.png) <br><br>
5. Elija **concentrador** y **Surface Hub 2** como destino para el paquete de configuración UEFI.<br>
![* Elige Hub y Surface Hub 2 como destino para el paquete de configuración UEFI *](images/sh2-uefi5.png) <br><br>
6. Elija los componentes y la configuración que desee activar o desactivar en Surface Hub 2S.<br>
![* Elija los componentes y la configuración que desea activar o desactivar *.](images/sh2-uefi6.png) <br><br>
7. Use la opción USB para exportar el archivo.<br>
![* Use la opción USB para exportar el archivo *](images/sh2-uefi8.png) <br><br>
8. Inserta y elige la unidad USB que deseas usar para este paquete. La unidad USB tendrá formato y perderá la información que tenga.<br>
![* Inserta y elige la unidad USB para tu paquete *](images/sh2-uefi9.png) <br><br>
9. Una vez que se haya creado el paquete correctamente, el configurador mostrará los dos últimos caracteres de la huella digital de su certificado. Estos caracteres se necesitan al importar a la configuración a Surface Hub 2S.<br>
![* Configuración correcta del paquete *](images/sh2-uefi10.png) <br>

##  <a name="to-boot-into-uefi"></a>Para arrancar en UEFI

Desactiva Surface Hub 2S. Mantén pulsado el botón **subir el volumen** y pulsa el botón de **encendido** . Mantenga pulsado el botón subir el volumen hasta que aparezca el menú UEFI.

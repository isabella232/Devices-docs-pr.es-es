---
title: Habilitar la autenticación por cable 802.1X
description: Se han habilitado políticas MDM de autenticación por cable 802.1x en dispositivos de Surface Hub.
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: dcb2799accfcbccb41e44e09f0df3fd1ac6eb57e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154045"
---
# <a name="enable-8021x-wired-authentication"></a>Habilitar la autenticación por cable 802.1X

La actualización del 14 de noviembre de [2017 a Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (compilación 15063.726) habilitó directivas MDM de autenticación por cable 802.1x en Surface Hub dispositivos. La característica permite a las organizaciones aplicar la autenticación de red por cable estandarizada usando el [protocolo de autenticación IEEE 802.1X](http://www.ieee802.org/1/pages/802.1x-2010.html). Esto ya estaba disponible para la autenticación inalámbrica mediante [perfiles WLAN a](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) través de MDM. En este tema se explica cómo configurar un Surface Hub para usarlo con la autenticación por cable. 

La aplicación y la habilitación de la autenticación por cable 802.1X en Surface Hub se puede realizar a través de MDM [definición de OMA-URI](/mem/intune/configuration/custom-settings-windows-10). 

La configuración principal que se establecerá es la directiva **LanProfile**. Según el método de autenticación seleccionado, otras directivas pueden ser necesarias, ya sea la directiva **EapUserData** o a través de directivas de MDM para agregar certificados de usuario o equipo (como [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) para certificados de usuario/dispositivo o [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) para certificados de dispositivo). 

## <a name="lanprofile-policy-element"></a>Elemento de directiva LanProfile

Para configurar Surface Hub para que use uno de los métodos de autenticación 802.1X admitidos, utilice el siguiente OMA-URI. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Este nodo de OMA-URI toma una cadena de texto de XML como parámetro. El XML proporcionado como parámetro debe cumplir el [esquema de perfil de LAN con cable](/openspecs/windows_protocols/ms-gpwl/c88a926a-087b-405f-9a76-effaf7277bf3) incluidos los elementos del [esquema 802.1X](/openspecs/windows_protocols/ms-gpwl/71f2eda6-d018-4ba3-ad37-32c98b926ebb). 

En la mayoría de los casos, un usuario o administrador puede exportar el XML LanProfile desde un PC existente que ya esté configurado en la red para 802.1x con este comando NETSH. 

```
netsh lan export profile folder=.
```

Al ejecutar este comando se mostrará el siguiente resultado y se colocará un archivo **Ethernet.xml** en el directorio actual. 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <a name="eapuserdata-policy-element"></a>Elemento de directiva EapUserData

Si tu método de autenticación seleccionado requiere un nombre de usuario y una contraseña en lugar de un certificado, puedes usar el elemento **EapUserData** para especificar las credenciales para el dispositivo que se usará para autenticar en la red. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Este nodo de OMA-URI toma una cadena de texto de XML como parámetro. El XML proporcionado como parámetro debe cumplir con el [ejemplo de las propiedades de usuario de PEAP MS-CHAPv2](/windows/win32/eaphost/peap-ms-chapv2-user-properties). En el ejemplo, deberás reemplazar todas las instancias de *test* e *ias-domain* por tu información.



## <a name="adding-certificates"></a>Agregar certificados

Si el método de autenticación seleccionado está [](provisioning-packages-for-surface-hub.md)basado en certificados, deberás crear un paquete de aprovisionamiento, usar [MDM](/windows/client-management/mdm/clientcertificateinstall-csp)o importar un certificado de la configuración (**Configuración**  >  **Update and Security**  >  **Certificates**) para implementar dichos certificados en el dispositivo Surface Hub en el almacén de certificados adecuado. Al agregar certificados, cada PFX debe contener un certificado único (un PFX no puede tener varios certificados).


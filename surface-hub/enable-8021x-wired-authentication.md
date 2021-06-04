---
title: Habilitar la autenticación por cable 802.1x
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
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836250"
---
# Habilitar la autenticación por cable 802.1X

La [actualización del 14 de noviembre de 2017 de Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (compilación 15063.726) permite a las directivas de MDM de autenticación por cable 802.1X en los dispositivos de Surface Hub. La característica permite a las organizaciones aplicar la autenticación de red por cable estandarizada usando el [protocolo de autenticación IEEE 802.1X](http://www.ieee802.org/1/pages/802.1x-2010.html). Ya está disponible para la autenticación inalámbrica mediante perfiles WLAN a través de MDM. En este tema se explica cómo configurar un Surface Hub para usarlo con la autenticación por cable. 

La aplicación y la habilitación de la autenticación por cable 802.1X en Surface Hub se puede realizar a través de MDM [definición de OMA-URI](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings). 

La configuración principal que se establecerá es la directiva **LanProfile**. Según el método de autenticación seleccionado, otras directivas pueden ser necesarias, ya sea la directiva **EapUserData** o a través de directivas de MDM para agregar certificados de usuario o equipo (como [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) para certificados de usuario/dispositivo o [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) para certificados de dispositivo). 

##  <a name="lanprofile-policy-element"></a>Elemento de directiva LanProfile

Para configurar Surface Hub para que use uno de los métodos de autenticación 802.1X admitidos, utilice el siguiente OMA-URI. 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

Este nodo de OMA-URI toma una cadena de texto de XML como parámetro. El XML proporcionado como parámetro debe cumplir el [esquema de perfil de LAN con cable](https://msdn.microsoft.com/library/cc233002.aspx) incluidos los elementos del [esquema 802.1X](https://msdn.microsoft.com/library/cc233003.aspx). 

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

##  <a name="eapuserdata-policy-element"></a>Elemento de directiva EapUserData

Si tu método de autenticación seleccionado requiere un nombre de usuario y una contraseña en lugar de un certificado, puedes usar el elemento **EapUserData** para especificar las credenciales para el dispositivo que se usará para autenticar en la red. 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

Este nodo de OMA-URI toma una cadena de texto de XML como parámetro. El XML proporcionado como parámetro debe cumplir con el [ejemplo de las propiedades de usuario de PEAP MS-CHAPv2](https://msdn.microsoft.com/library/windows/desktop/bb891979). En el ejemplo, deberás reemplazar todas las instancias de *test* e *ias-domain* por tu información.



##  <a name="adding-certificates"></a>Agregar certificados

Si el método de autenticación seleccionado es basado en certificados, tendrá que [crear un paquete de aprovisionamiento](provisioning-packages-for-surface-hub.md), [usar MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)o importar un certificado desde configuración (actualización de**configuración**  >  **y**  >  **certificados**de seguridad) para implementar esos certificados en el dispositivo Surface Hub en el almacén de certificados correspondiente. Al agregar certificados, cada PFX debe contener un certificado único (un PFX no puede tener varios certificados).


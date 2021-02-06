---
title: Preparar el entorno para Microsoft Surface Hub (v1)
description: Esta sección contiene una introducción sobre los pasos necesarios para preparar el entorno para que puedas usar todas las características de Microsoft Surface Hub.
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: preparar el entorno, características de Surface Hub, crear y probar la cuenta del dispositivo, comprobar la disponibilidad de red
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/04/2017
ms.localizationpriority: medium
appliesto:
- Surface Hub
ms.openlocfilehash: 95b575e5213e3e11685b342cb2a7b77eb3e868a0
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314403"
---
# Preparar el entorno para Microsoft Surface Hub (v1)


Esta sección contiene una descripción general de las dependencias del programa de instalación y del proceso de instalación. Revisa la información de esta sección para que te resulte más fácil preparar el entorno y recopilar la información necesaria para configurar Surface Hub.


## Revisar las dependencias de la infraestructura
Revisa estas dependencias para asegurarte de que las características de Surface Hub funcionarán en tu infraestructura de TI.

| Dependencia        | Propósito           |
|-------------|------------------|
| Active Directory o Azure Active Directory (Azure AD) | <p>Surface Hub usa una cuenta de Active Directory o Azure AD (llamada una **cuenta del dispositivo**) para acceder a los servicios de Exchange y Skype Empresarial. Surface Hub debe ser capaz de conectarse al controlador de dominio de Active Directory o al inquilino de Azure AD para validar las credenciales de la cuenta del dispositivo, así como para acceder a información como el nombre para mostrar de la cuenta del dispositivo, el alias, el servidor Exchange y la dirección de Protocolo de inicio de sesión (SIP).</p>También puedes unir tu Surface Hub a un dominio o a Azure AD para permitir que un grupo de usuarios autorizados configure los parámetros en Surface Hub. |
| Exchange (Exchange 2013 o posterior, o Exchange Online) y Exchange ActiveSync | <p>Exchange se usa para habilitar las características de correo y calendario, y también permite que los usuarios que usen el dispositivo envíen convocatorias de reunión a Surface Hub, lo que permite sumarse a la reunión con un solo toque.</p>ActiveSync se usa para sincronizar el calendario y el correo electrónico de la cuenta del dispositivo con Surface Hub. Si el dispositivo no puede usar ActiveSync, no mostrará reuniones en la pantalla de bienvenida y no se habilitarán la opción de unirse a reuniones ni el envío de pizarras por correo electrónico. |
| Skype Empresarial (Lync Server 2013 o posterior, o Skype Empresarial Online)  | Skype Empresarial se usa para varias características de conferencia, como videollamadas, mensajería instantánea y uso compartido de la pantalla.|
| Solución de administración de dispositivos móviles (MDM) (Microsoft Intune, Microsoft Endpoint Configuration Manager o proveedor de MDM de terceros compatible) | Si quieres aplicar la configuración e instalar las aplicaciones de forma remota, y hacerlo en varios dispositivos a la vez, debes configurar una solución MDM e inscribir el dispositivo en dicha solución. Consulta [Administrar la configuración con un proveedor de MDM](manage-settings-with-mdm-for-surface-hub.md) para obtener más información. |
| Microsoft Operations Management Suite (OMS)   | OMS se usa para supervisar el estado de los dispositivos Surface Hub. Consulta [Supervisar Surface Hub](monitor-surface-hub.md) para obtener más información. |
| Acceso a redes e Internet   | Para que funcione correctamente, Surface Hub debe tener acceso a una red cableada o inalámbrica. En general, es preferible una conexión por cable. Se admite la autenticación 802.1X para conexiones inalámbricas y cableadas.</br></br></br>**Autenticación 802.1X:** En Windows 10, versión 1703, la autenticación 802.1X para conexiones con cable e inalámbricas está habilitada de manera predeterminada en Surface Hub. Si la organización no usa la autenticación 802.1X, no es necesario realizar ninguna configuración y Surface Hub seguirá funcionando normalmente. Si usas la autenticación 802.1X, debes asegurarte de que la certificación de autenticación esté instalada en Surface Hub. Puedes entregar el certificado a Surface Hub mediante el [CSP de ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) en MDM, o bien puedes [crear un paquete de aprovisionamiento](provisioning-packages-for-surface-hub.md) e instalarlo durante la primera ejecución o a través de la aplicación Configuración. Después de que el certificado se aplique a Surface Hub, la autenticación 802.1X comenzará a funcionar automáticamente.</br>**Nota:** Para obtener más información acerca de cómo habilitar la autenticación con cable 802.1X en Surface Hub, consulta [Habilitar autenticación con cable 802.1X](enable-8021x-wired-authentication.md).</br></br>**IP dinámica:** Surface Hub no se puede configurar para usar una dirección IP estática. Debe usar DHCP para asignar una dirección IP.</br></br>**Servidores proxy:** si la topología requiere una conexión a un servidor proxy para alcanzar servicios de Internet, puedes configurarla durante la primera ejecución o en Configuración. Las credenciales de proxy se almacenan entre sesiones de Surface Hub y solo deben establecerse una vez. |

Además, ten en cuenta que Surface Hub requiere los siguientes puertos abiertos:
- HTTPS: 443
- HTTP: 80
- NTP: 123

Si usas Surface Hub con Skype Empresarial, deberás abrir puertos adicionales. Siga las instrucciones siguientes:
- Si usa Skype Empresarial Online, consulte direcciones IP de [Office 365 e intervalos de direcciones IP.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)
- Si usa Skype Empresarial Server, consulte Skype Empresarial [Server: Puertos y protocolos para servidores internos.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols) 
- Si usa un entorno híbrido de Skype Empresarial Online y Skype Empresarial Server, debe abrir todos los puertos documentados de direcciones IP e intervalos de direcciones IP de [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) y Skype Empresarial [Server: puertos](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)y protocolos para servidores internos.

Microsoft recopila datos de diagnóstico para ayudar a mejorar la experiencia de Surface Hub. Agrega estos sitios a la lista de permitidos:
- Punto de conexión de cliente de datos de diagnóstico: `https://vortex.data.microsoft.com/`
- Punto de conexión de configuración de datos de diagnóstico: `https://settings.data.microsoft.com/`

### Configuración de proxy

Si tu organización restringe la conexión a Internet de los equipos de la red, hay un conjunto de direcciones URL que deben estar disponibles para los dispositivos de modo que puedan usar la Microsoft Store para Empresas. Algunas de las funciones de la Microsoft Store para Empresas usan la aplicación y los servicios de Microsoft Store. Los dispositivos que usen la Microsoft Store para Empresas, ya sea para adquirir, instalar o actualizar aplicaciones, necesitarán acceso a estas direcciones URL. Si usas un servidor proxy para bloquear el tráfico, la configuración debe permitir estas direcciones URL:

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com (anterior a Windows 10, versión 1607)
- www.msftconnecttest.com/connecttest.txt (reemplaza a www.msftncsi.com a partir de Windows 10, versión 1607)


## Trabajar con otros administradores

Surface Hub interactúa con unos cuantos productos y servicios diferentes. En función del tamaño de la organización, puede haber varias personas que ofrezcan soporte para distintos productos en tu entorno. Querrás incluir personas que administren Exchange, Active Directory (o Azure Active Directory), la administración de dispositivos móviles (MDM) y los recursos de red en tu planeamiento y preparación para las implementaciones de Surface Hub. 


## Crear y comprobar una cuenta del dispositivo

Una cuenta del dispositivo es una cuenta de recursos de Exchange que Surface Hub usa para mostrar su calendario de reuniones, unirse a llamadas de Skype Empresarial, enviar correo electrónico y (opcionalmente) autenticarse en Exchange. Consulta [Crear y probar una cuenta del dispositivo](create-and-test-a-device-account-surface-hub.md) para más información.

Cuando hayas creado tu cuenta de dispositivo, para comprobar que está configurada correctamente, ejecuta los scripts de PowerShell de validación de la cuenta del dispositivo Surface Hub. Para obtener más información, consulta [Scripts de PowerShell para Surface Hub](appendix-a-powershell-scripts-for-surface-hub.md) más adelante en esta guía. 

 

## Prepararse para un programa de primera ejecución 
Hay unos cuantos elementos más a tener en cuenta antes de iniciar el [programa de primera ejecución](first-run-program-surface-hub.md).  

### Crear paquetes de aprovisionamiento (opcional)
Puedes usar paquetes de aprovisionamiento para agregar certificados, personalizar la configuración e instalar aplicaciones. Consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md) para obtener más información. Puedes [instalar paquetes de aprovisionamiento en la primera ejecución](first-run-program-surface-hub.md#first-page).

### Configurar grupos de administradores
Cada Surface Hub se puede configurar localmente mediante la aplicación Configuración en el dispositivo. Para impedir que usuarios no autorizados cambien la configuración, la aplicación Configuración requiere credenciales de administrador para abrir la aplicación. Consulta [Administración del grupo de administradores](admin-group-management-for-surface-hub.md) para obtener detalles sobre cómo se configuran y se administran los grupos de administradores. Deberás [configurar administradores para el dispositivo en la primera ejecución](first-run-program-surface-hub.md#setup-admins).

### Revisar y completar la hoja de cálculo del programa de instalación de Surface Hub (opcional)
Cuando sigas los pasos del programa de primera ejecución de Surface Hub, tendrás que proporcionar determinada información. La hoja de cálculo del programa de instalación resume esa información y proporciona listas de información específica del entorno que necesitarás cuando sigas los pasos del programa de primera ejecución. Para obtener más información, consulta [Hoja de cálculo del programa de instalación](setup-worksheet-surface-hub.md).


## En esta sección

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Tema</th>
<th align="left">Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">Crear y probar una cuenta del dispositivo</a></p></td>
<td align="left"><p>Este tema explica cómo crear y probar la cuenta del dispositivo que Surface Hub usa para comunicarse con Skype.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">Crear paquetes de aprovisionamiento</a></p></td>
<td align="left"><p>En Windows10, la configuración que usa el Registro o una plataforma de servicios de contenido (CSP) se puede configurar mediante paquetes de aprovisionamiento. También puedes agregar certificados durante la primera ejecución mediante el aprovisionamiento.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">Administración del grupo de administradores</a></p></td>
<td align="left"><p>Cada Surface Hub se puede configurar individualmente abriendo la aplicación Configuración en el dispositivo. Sin embargo, para evitar que las personas que no sean administradores cambien la configuración, la aplicación Configuración requiere credenciales de administrador local para abrir la aplicación y cambiar la configuración.</p>
<p>La aplicación Configuración requiere credenciales de administrador local para abrirla.</p></td>
</tr>
</tbody>
</table>

## Más información

- [Entrada de blog: Lista de dominios de confianza de Surface Hub y Skype Empresarial](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [Entrada de blog: Surface Hub en un entorno de varios dominios](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [Entrada de blog: Configurar un servidor proxy para Surface Hub](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 






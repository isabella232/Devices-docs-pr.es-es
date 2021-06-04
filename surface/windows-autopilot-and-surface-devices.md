---
title: Dispositivos Windows Autopilot y Surface
ms.reviewer: ''
manager: laurawi
description: Descubre las opciones de implementación de Windows Autopilot para dispositivos Surface.
keywords: autopilot, windows 10, surface, implementación
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271107"
---
# Dispositivos Windows Autopilot y Surface

Windows Autopilot es una tecnología de implementación basada en la nube en Windows 10. Puedes usar Windows Autopilot para implementar y configurar dispositivos de forma remota en un proceso sin entrada táctil directamente desde el primer momento.

Tradicionalmente, los profesionales de IT dedican mucho tiempo a crear y personalizar imágenes que más adelante se implementarán en dispositivos que ya vienen con un sistema operativo perfectamente bueno ya instalado en ellos. Windows Autopilot presenta un nuevo enfoque de implementación sin entrada táctil con una colección de tecnologías para configurar y configurar dispositivos Windows. Esto permite a un departamento de TI configurar o personalizar imágenes con poca o ninguna infraestructura para administrar y un proceso sencillo y sencillo. Desde la perspectiva del usuario, solo se necesitan unos pocos pasos sencillos para que Surface llegue a un estado productivo. De hecho, la única interacción necesaria del usuario final es conectarse a una red y comprobar sus credenciales. Todo lo que después de eso está totalmente automatizado.

Windows Autopilot te permite:

- Unir dispositivos automáticamente a Azure Active Directory (Azure AD).
- Inscribir automáticamente dispositivos en servicios MDM, como Microsoft Intune (requiere una suscripción a Azure AD Premium).
- Restringir la creación de cuentas de administrador. Autopilot es la única forma de que la primera persona que inicie sesión en Windows entre como un usuario estándar.
- Crear y asignar automáticamente dispositivos a grupos de configuración basados en perfiles de dispositivo.
- Personalice la personalización de marca y el contenido de OOBE (configuración personalizada) para satisfacer los requisitos de la organización.
- Habilitar la configuración completa del dispositivo con Intune.
- Restablecer o reiniciar dispositivos de forma remota.

##  <a name="how-it-works"></a>Cómo funciona

Los dispositivos registrados por Windows Autopilot se identifican a través de Internet en el primer inicio a través de una firma de dispositivo única que se denomina *hash de hardware.* Se inscriben y configuran automáticamente mediante soluciones de administración modernas como Azure Active Directory (Azure AD) y administración de dispositivos móviles.

Puedes registrar dispositivos Surface en el momento de la compra de un partner de Surface que esté habilitado para Windows Autopilot. Estos partners pueden enviar nuevos dispositivos directamente a los usuarios. Los dispositivos se inscribirán y configurarán automáticamente cuando se inicien por primera vez. Este proceso elimina la reimplación durante la implementación, lo que te permite implementar nuevos y ágiles métodos de administración y distribución de dispositivos.

##  <a name="modern-management"></a>Administración moderna

Autopilot es la opción de implementación recomendada para dispositivos Surface, incluidos Surface Pro 7+, Surface Laptop 3, Surface Pro 7 y Surface Pro X, que está diseñado específicamente para su implementación a través de Autopilot.

 Es mejor inscribir los dispositivos Surface con la ayuda de un proveedor de soluciones en la nube de Microsoft. Este paso te permite administrar la configuración de firmware de UEFI en Surface directamente desde Intune. Elimina la necesidad de tocar dispositivos físicamente para la administración de certificados. Consulta [la administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md) para obtener más información.

##  <a name="windows-version-considerations"></a>Consideraciones sobre la versión de Windows

La implementación amplia de dispositivos Surface a través de Windows Autopilot, incluida la inscripción por parte de partners de Surface en el momento de la compra, requiere Windows 10 versión 1709 (Fall Creators Update) o posterior.

Estas versiones de Windows admiten un valor hash de 4.000 bytes (4k) que identifica de forma única los dispositivos para Windows Autopilot, que es necesario para las implementaciones a escala. Todos los nuevos dispositivos Surface, incluidos Surface Pro 7+, Surface Pro X y Surface Laptop 3, se incluyen con Windows 10 versión 1903 o posterior.

##  <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Experiencia de Exchange en dispositivos Surface que necesitan reparación o reemplazo

Microsoft comprueba automáticamente cada Surface para la inscripción de Autopilot y anulará el registro del dispositivo del inquilino del cliente.  Microsoft garantiza que el dispositivo de reemplazo se inscribe en Windows Autopilot una vez que se envía un reemplazo al cliente. Este servicio está disponible en todos los pedidos de servicio de intercambio de dispositivos directamente con Microsoft.

> [!NOTE]
> Cuando los clientes usan un partner para devolver dispositivos, el partner es responsable de administrar el proceso de intercambio, incluido el registro e inscripción de dispositivos en Windows Autopilot.

##  <a name="microsoft-support-registration"></a>Registro del soporte técnico de Microsoft

Los clientes y los proveedores de soluciones en la nube de Microsoft (CSP) tienen la opción de registrar dispositivos Surface enviando solicitudes al Soporte técnico de Microsoft. Para obtener más información, consulta [Soporte de registro de Surface para Windows Autopilot.](surface-autopilot-registration-support.md)

##  <a name="surface-partners-enabled-for-windows-autopilot"></a>Partners de Surface habilitados para Windows Autopilot

Los partners de Surface seleccionados pueden inscribir dispositivos Surface en Windows Autopilot en el momento de la compra. También pueden enviar dispositivos inscritos directamente a los usuarios. Los dispositivos se pueden configurar completamente a través de un proceso sin entrada táctil mediante Windows Autopilot, Azure AD y la administración de dispositivos móviles.

Los partners de Surface que están habilitados para Windows Autopilot incluyen:

| Socios de EE. UU. | Partners globales | Distribuidores de EE. UU. |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [TAMBIÉN](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Conexión](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [DESO](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F1](https://www.functiononeit.com/#empower)  |   |  |
| * [Confianza protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

##  <a name="learn-more"></a>Más información

Para obtener más información sobre Windows Autopilot, consulta:
- [Introducción a WindowsAutopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos de Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Soporte del registro de Surface para Windows Autopilot](surface-autopilot-registration-support.md)
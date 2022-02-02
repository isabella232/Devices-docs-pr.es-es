---
title: Dispositivos Windows Autopilot y Surface
ms.reviewer: ''
manager: laurawi
description: Encontrará información sobre Windows de implementación de Autopilot para dispositivos Surface.
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
ms.openlocfilehash: bfcb8c09b3228730e3255c4f92948dc4acfea506
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338543"
---
# <a name="windows-autopilot-and-surface-devices"></a>Dispositivos Windows Autopilot y Surface

Windows Autopilot es una tecnología de implementación basada en la nube en Windows 10. Puedes usar Windows Autopilot para implementar y configurar dispositivos de forma remota en un proceso sin contacto desde el primer momento.

Tradicionalmente, los profesionales de IT pasan mucho tiempo creando y personalizando imágenes que posteriormente se implementarán en dispositivos que ya vienen con un sistema operativo perfectamente bueno ya instalado en ellos. Windows Autopilot presenta un nuevo enfoque de implementación sin contacto mediante una colección de tecnologías para configurar y configurar Windows dispositivos. Esto permite que un departamento de TI configure o personalice imágenes con poca o ninguna infraestructura que administrar y un proceso fácil y sencillo. Desde la perspectiva del usuario, solo se necesitan algunos pasos sencillos para que Surface llegue a un estado productivo. De hecho, la única interacción necesaria para el usuario final es conectarse a una red y comprobar sus credenciales. Todo después de eso está totalmente automatizado.

Windows Autopilot le permite:

- Unir automáticamente dispositivos a Azure Active Directory (Azure AD).
- Inscribir automáticamente dispositivos en servicios MDM, como Microsoft Intune (requiere una Azure AD Premium suscripción).
- Restringir la creación de cuentas de administrador. Autopilot es la única forma de que la primera persona que inicie sesión en Windows escriba como un usuario estándar.
- Crear y asignar automáticamente dispositivos a grupos de configuración basados en perfiles de dispositivo.
- Personalización de marca y contenido de OOBE (experiencia de salida de caja) para satisfacer los requisitos de la organización.
- Habilitar la configuración completa del dispositivo con Intune.
- Restablecer o reiniciar dispositivos de forma remota.

## <a name="how-it-works"></a>Cómo funciona

Windows dispositivos registrados por Autopilot se identifican a través de Internet en el primer inicio a través de una firma de dispositivo única que se denomina *hash de hardware*. Se inscriben y configuran automáticamente mediante soluciones de administración modernas, como Azure Active Directory (Azure AD) y administración de dispositivos móviles.

Puedes registrar dispositivos Surface en el momento de la compra de un partner de Surface que esté habilitado para Windows Autopilot. Estos partners pueden enviar nuevos dispositivos directamente a los usuarios. Los dispositivos se inscribirán y configurarán automáticamente cuando estén activados por primera vez. Este proceso elimina el reimaging durante la implementación, lo que te permite implementar nuevos y ágiles métodos de administración y distribución de dispositivos.

## <a name="modern-management"></a>Administración moderna

Autopilot es la opción de implementación recomendada para dispositivos Surface, incluidos Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Pro 7+, Surface Laptop 4 y Surface Pro X, que está diseñado específicamente para su implementación a través de Autopilot.

 Es mejor inscribir los dispositivos Surface con la ayuda de un Proveedor de soluciones en la nube de Microsoft. Este paso te permite administrar la configuración de firmware de UEFI en Surface directamente desde Intune. Elimina la necesidad de tocar físicamente dispositivos para la administración de certificados. Consulta [Administración de Intune de la configuración de UEFI de Surface](surface-manage-dfci-guide.md) para obtener más información.

## <a name="windows-version-considerations"></a>Windows consideraciones sobre la versión

La implementación general de dispositivos Surface Windows través de Windows Autopilot, incluida la inscripción de socios de Surface en el momento de la compra, requiere Windows 10 versión 1709 (Fall Creators Update) o posterior.

Estas Windows admiten un valor hash de 4.000 bytes (4k) que identifica de forma única los dispositivos para Windows Autopilot, que es necesario para implementaciones a escala.

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange experiencia en dispositivos Surface que necesitan reparación o reemplazo

Microsoft comprueba automáticamente cada inscripción de Surface para Autopilot y anulará el registro del dispositivo desde el inquilino del cliente.  Microsoft garantiza que el dispositivo de reemplazo se inscriba en Windows Autopilot una vez que un reemplazo se envía de vuelta al cliente. Este servicio está disponible en todos los pedidos de servicio de intercambio de dispositivos directamente con Microsoft.

> [!NOTE]
> Cuando los clientes usan un partner para devolver dispositivos, el partner es responsable de administrar el proceso de intercambio, incluido el registro y la inscripción de dispositivos en Windows Autopilot.

## <a name="microsoft-support-registration"></a>Registro de soporte técnico de Microsoft

Los clientes y los proveedores de soluciones en la nube de Microsoft (CSP) tienen la opción de registrar dispositivos Surface enviando solicitudes al Soporte técnico de Microsoft. Para obtener más información, consulta [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Partners de Surface habilitados para Windows Autopilot

Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase. También pueden enviar dispositivos inscritos directamente a los usuarios. Los dispositivos se pueden configurar por completo a través de un proceso sin contacto mediante Windows administración de dispositivos móviles, Azure AD y autopilot.

Los partners de Surface que están habilitados para Windows Autopilot incluyen:

| Socios de EE. UU. | Partners globales | Distribuidores de EE. UU. |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [TAMBIÉN](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [Conexión](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI Conectar](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [Confianza protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>Obtén más información

Para obtener más información Windows Autopilot, vea:

- [Introducción a Windows Autopilot](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos de Windows AutoPilot](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Soporte del registro de Surface para Windows Autopilot](surface-autopilot-registration-support.md)

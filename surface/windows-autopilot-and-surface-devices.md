---
title: Dispositivos Windows Autopilot y Surface
ms.reviewer: ''
manager: laurawi
description: Para obtener más información sobre las opciones de implementación de Windows AutoPilot para dispositivos Surface.
keywords: autopiloto, Windows 10, superficie, implementación
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834618"
---
# Dispositivos Windows Autopilot y Surface

Windows AutoPilot es una tecnología de implementación basada en la nube en Windows 10. Puede usar el piloto automático de Windows para implementar y configurar de forma remota dispositivos en un proceso de toque cero inmediatamente fuera de la caja.

Los dispositivos con la prueba piloto automática de Windows se identifican a través de Internet en el primer inicio a través de una firma de dispositivo única que se denomina *hash de hardware*. Se inscribió y configuran automáticamente mediante soluciones de administración modernas, como Azure Active Directory (Azure AD) y administración de dispositivos móviles.

Puede registrar dispositivos de Surface en el momento de la compra a través de un socio de Surface que está habilitado para Windows AutoPilot. Estos socios pueden enviar nuevos dispositivos directamente a los usuarios. Los dispositivos se inscribirán y configurarán automáticamente cuando se activen por primera vez. Este proceso elimina el reprocesamiento de imágenes durante la implementación, lo que le permite implementar nuevos métodos ágiles de administración y distribución de dispositivos.

## Administración moderna

AutoPilot es la opción de implementación recomendada para dispositivos Surface, incluidos Surface Pro 7, Surface Laptop 3 y Surface Pro X, que se ha diseñado específicamente para su implementación a través de AutoPilot.

 Es mejor inscribir sus dispositivos de Surface con la ayuda de un proveedor de soluciones en la nube de Microsoft. Este paso le permite administrar la configuración del firmware UEFI directamente desde Intune. Elimina la necesidad de tocar físicamente los dispositivos para la administración de certificados. Para obtener más información, consulta la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md) .

## Consideraciones sobre la versión de Windows

La amplia implementación de dispositivos Surface a través de Windows AutoPilot, incluida la inscripción de socios Surface en el momento de la compra, requiere Windows 10 versión 1709 (Fall Creators Update) o posterior.

Estas versiones de Windows admiten un valor hash de 4.000 bytes (4k) que identifica exclusivamente dispositivos para Windows AutoPilot, que es necesario para las implementaciones a escala. Todos los nuevos dispositivos Surface, incluidos Surface Pro 7, Surface Pro X y Surface Laptop 3, se suministran con Windows 10 versión 1903 o posterior.

## Experiencia de Exchange en dispositivos Surface que necesitan reparación o sustitución

Microsoft verifica automáticamente todas las superficies para la inscripción de piloto automático y elimina el registro del dispositivo del inquilino del cliente.  Microsoft garantiza que el dispositivo de sustitución se ha inscrito en Windows AutoPilot una vez que el reemplazo se envía al cliente. Este servicio está disponible en todas las órdenes de servicio de intercambio de dispositivos directamente con Microsoft.

> [!NOTE]
> Cuando los clientes usan un partner para devolver dispositivos, el socio es responsable de administrar el proceso de Exchange, incluido el registro y la inscripción de dispositivos en el piloto automático de Windows.

## Socios de Surface habilitados para Windows AutoPilot

Seleccione Surface Partners puede inscribir dispositivos Surface en Windows AutoPilot por usted en el momento de la compra. También pueden enviar dispositivos inscritos directamente a los usuarios. Los dispositivos se pueden configurar por completo a través de un proceso sin interacción mediante el uso de Windows AutoPilot, Azure AD y la administración de dispositivos móviles.

Entre los socios de superficie habilitados para Windows AutoPilot se incluyen:

| Socios de Estados Unidos | Socios internacionales | Distribuidores de Estados Unidos |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [TAMBIÉN](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [Conexión](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [Valiosa](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [CAMISETA](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI Connect](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [F10](https://www.functiononeit.com/#empower)  |   |  |
| * [Confianza protegida](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## Obtén más información

Para obtener más información sobre Windows AutoPilot, consulte:
- [Introducción a WindowsAutopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Requisitos de Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
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
ms.date: 9/14/2020
ms.openlocfilehash: d2a948d236ffa286192937cc5ca71099b6eeeafb
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016429"
---
# Dispositivos Windows Autopilot y Surface

Windows AutoPilot es una tecnología de implementación basada en la nube en Windows 10. Puede usar el piloto automático de Windows para implementar y configurar de forma remota dispositivos en un proceso de toque cero inmediatamente fuera de la caja.

Tradicionalmente, los profesionales de ti gastan mucho tiempo construyendo y personalizando imágenes que se implementarán más adelante en dispositivos que ya tienen un sistema operativo perfectamente instalado. Windows AutoPilot presenta un nuevo enfoque de implementación sin interacción con un conjunto de tecnologías para configurar y configurar dispositivos Windows. Esto permite a un departamento de ti configurar/personalizar imágenes con poca o ninguna infraestructura de administración y un proceso que es fácil y simple. Desde el punto de vista del usuario, solo se necesitan unos pocos pasos para obtener un estado de producción. De hecho, la única interacción necesaria del usuario final es conectarse a una red y comprobar sus credenciales. Todo lo que haya después es totalmente automatizado.

El piloto automático de Windows le permite:

- Unir dispositivos automáticamente a Azure Active Directory (Azure AD).
- Inscriba dispositivos automáticamente en servicios MDM, como Microsoft Intune (requiere una suscripción de Azure AD Premium).
- Restringir la creación de cuentas de administrador. AutoPilot es la única forma de hacer que la primera persona que inicia sesión en Windows se introduzca como usuario estándar.
- Cree y autoasigne dispositivos a grupos de configuración basándose en perfiles de dispositivos.
- Personalizar el contenido de OOBE (experiencia rápida) y la marca para cumplir los requisitos de la organización.
- Habilitar la configuración completa de dispositivos con Intune.
- Restablecer o reiniciar dispositivos de forma remota.

## Cómo funciona

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

## Registro de soporte técnico de Microsoft

Los clientes y los proveedores de soluciones en la nube de Microsoft (CSP) tienen la opción de registrar dispositivos de Surface enviando solicitudes al soporte técnico de Microsoft. Para obtener más información, consulte [compatibilidad con el registro de superficies para Windows AutoPilot](surface-autopilot-registration-support.md).

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
- [Compatibilidad de Surface registration para Windows AutoPilot](surface-autopilot-registration-support.md)
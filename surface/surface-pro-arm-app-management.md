---
title: Implementación, administración y mantenimiento de Surface Pro X
description: En este artículo se ofrece una descripción general de las principales consideraciones para implementar, administrar y mantener SurfaceProX.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 4/15/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: d1e7aa41f8219f0ae6ccd81a36fa0fc142dd1c3c
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835578"
---
# Implementación, administración y mantenimiento de Surface Pro X

## Introducción

Surface Pro X, con un diseño para satisfacer los requisitos comerciales de alto rendimiento, innova al incorporar el procesador más potente que se ha incluido hasta ahora en un dispositivo ARM, el conjunto de chips ARM MicrosoftSQ1.

SurfaceProX, con una CPU de 3GHz y una GPU de 2,1 teraflops, ofrece una experiencia de Windows completa. Las 13horas de duración de la batería y 4GLTE integrado permiten que sea ideal para los trabajadores de primera línea y profesionales que trabajan en el campo financiero, jurídico y médico, o cualquier cargo que exija una larga duración de la batería y capacidades de conectividad continua.

SurfaceProX se ha diseñado casi exclusivamente para un entorno moderno, basado en la nube, centrado en Microsoft365, Intune y Windows Autopilot. En este artículo se reseña su apariencia y se describen las principales consideraciones para implementar, administrar y mantener SurfaceProX.

## Implementación de Surface Pro X

Para disfrutar de la mejor experiencia posible, implementa SurfaceProX con Windows Autopilot con la ayuda de un Proveedor de soluciones en la nube de Microsoft, o con aprovisionamiento automático con perfiles de implementación de Autopilot y características relacionadas. Para más información, consulta:

- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md)
- [Introducción a WindowsAutopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

La implementación de Autopilot tiene varias ventajas: te permite usar el sistema operativo aprovisionado de fábrica, optimizado para la implementación sin interacción, para incluir la preinstalación de Office Pro Plus.

Las organizaciones que ya usan soluciones modernas de administración, seguridad y productividad están bien posicionadas para aprovechar las características de rendimiento únicas de SurfaceProX. Los clientes que usan aplicaciones de línea de negocio modernas, aplicaciones de Microsoft Store (UWP) o soluciones de escritorio remoto también pueden beneficiarse.

## Consideraciones de implementación basada en imagen

Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager (anteriormente System Center Configuration Manager) no admiten actualmente SurfaceProX para la implementación de sistemas operativos. Los clientes que dependen de la implementación basada en imagen deben pensar en SurfacePro7 mientras continúan evaluando el momento adecuado para realizar la transición a la nube.

## Administración de dispositivos SurfaceProX

### Intune

Intune, componente de Microsoft Enterprise Mobility + Security, se integra en Azure Active Directory para control de identidades y de acceso, y proporciona una administración granular de los dispositivos SurfaceProX inscritos. Las directivas de administración de dispositivos móviles (MDM) de Intune tienen varias ventajas sobre las anteriores herramientas locales, como la directiva de grupo de Windows. Esto incluye tiempos de inicio de sesión de dispositivo más rápidos y un catálogo de directivas más optimizado que permite la administración completa de dispositivos desde la nube. Por ejemplo, puedes administrar LTE con perfiles de eSIM para configurar los planes de datos e implementar códigos de activación en varios dispositivos.<br> 

Para más información sobre el uso de Intune, consulta la [documentación de Intune](https://docs.microsoft.com/intune/).

### Administración conjunta

Una vez que se haya implementado en Autopilot, puedes unir dispositivos SurfaceProX a AzureAD o Active Directory (Unión a Azure AD híbrido), donde podrás administrar los dispositivos con Intune o administrarlos de manera conjunta con Endpoint Configuration Manager, que instalará el cliente de ConfigMgrx86 de 32bits.

### Soluciones MDM de terceros

Es posible que puedas usar herramientas MDM de terceros para administrar dispositivos SurfaceProX. Para más información, ponte en contacto con tu proveedor de MDM.

### Software antivirus

Windows Defender te ayudará a proteger Windows10 en equipos basados en ARM para la duración admitida del dispositivo con Windows10. 

No se puede instalar el software antivirus de algunos terceros en un equipo con Windows10 que se ejecute en un procesador basado en ARM. La colaboración con proveedores de software antivirus de terceros continúa para que las aplicaciones antivirus estén disponibles en PC basados en ARM. Ponte en contacto con tu proveedor de software antivirus para saber cuándo estarán disponibles sus aplicaciones.

## Mantenimiento de Surface Pro X

Surface Pro X admite Windows 10, versión 1903 y versiones posteriores. Como dispositivo basado en ARM, tiene requisitos específicos para mantener los controladores y el firmware más recientes. 

SurfaceProX se ha diseñado para usar Windows Update para simplificar el proceso de mantener actualizados los controladores y el firmware tanto para los usuarios domésticos como para los usuarios de pequeñas empresas. Usa la configuración predeterminada para recibir actualizaciones automáticas.  Para verificarlo:

1. Ve a **Inicio** > **Configuración > Actualización y seguridad > Windows Update** > **Opciones avanzadas**.
2. En **Elegir cómo se instalan las actualizaciones**, selecciona **Automático (recomendado)**.

### Recomendaciones para clientes comerciales

- Usa Windows Update o Windows Update para empresas para mantener los controladores y el firmware más recientes. Para obtener más información, consulta [Implementar actualizaciones con Windows Update para empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).
- Si los procedimientos requieren el uso de un archivo .msi de Windows Installer, ponte en contacto con el [soporte técnico de Surface para empresas](https://support.microsoft.com/help/4037645). 
- Para más información sobre la implementación y la administración de actualizaciones en dispositivos Surface, consulte [Administrar e implementar actualizaciones de drivers y firmware de Surface](manage-surface-driver-and-firmware-updates.md).
- Ten en cuenta que Windows Server Update Services (WSUS) no admite la capacidad de entregar controladores y firmware a SurfaceProX.

## Ejecución de aplicaciones en Surface Pro X

La mayoría de las aplicaciones se ejecutan en PC Windows10 basados en ARM con exclusiones limitadas.

### Aplicaciones compatibles

- La mayoría de las aplicaciones Win32 x86 se ejecutan en SurfaceProX.
- Las aplicaciones para UWP de Microsoft Store y ARM64 nativas ofrecen una excelente experiencia de usuario, que usa la velocidad nativa completa del procesador basado en ARM, a la vez que optimiza la duración de la batería.
- Aplicaciones que usan controladores diseñados para PC Windows10 que se ejecuta en un procesador basado en ARM.

### No se admite

- Las aplicaciones x64 no se ejecutan en un equipo con Windows10 en un procesador basado en ARM.

Para más información sobre cómo ejecutar aplicaciones en SurfaceProX, consulta:

- [Preguntas frecuentes sobre los PC basados en ARM con Windows 10](https://support.microsoft.com/help/4521606)
- [Documentación de Windows 10 en ARM](https://docs.microsoft.com/windows/arm)

## Escritorios virtuales (VDI)

Windows Virtual Desktop permite el acceso a escritorios, aplicaciones y datos de Windows en cualquier dispositivo o plataforma informáticos, desde cualquier ubicación. Para más información, consulta el [sitio de Windows Virtual Desktop](https://aka.ms/wvd). 

## Exploración con Surface Pro X

Los exploradores populares se ejecutan en Surface Pro X:

- Las versiones de Edge incluidas, Firefox, Chrome e Internet Explorer se ejecutan en SurfaceProX.
- Las versiones de Edge incluidas y Firefox se ejecutan de forma nativa y, por lo tanto, tienen un rendimiento mejorado en PC Windows10 en un procesador basado en ARM.

## Instalación y uso de Microsoft Office

- Usa Office 365 para disfrutar de la mejor experiencia en PC Windows10 en un procesador basado en ARM.
- "Hacer clic para ejecutar" de Office365 instala Outlook, Word, Excel y PowerPoint, optimizados para ejecutarse en PC Windows10 en un procesador basado en ARM.
- Microsoft Teams se ejecuta a la perfección en SurfaceProX.
- Para las "versiones perpetuas" de Office, como Office 2019, instala la versión de 32bits.

## VPN

Para confirmar si una VPN de terceros específica admite PC Windows10 en un procesador basado en ARM, ponte en contacto con el proveedor de la VPN.

## Comparación de características clave

En las tablas siguientes se muestra la disponibilidad de las características clave seleccionadas en SurfaceProX con Windows10 en ARM en comparación con SurfacePro7 basado en Intel.

| Implementación                              | Surface Pro 7 | Surface Pro X | Notas                                                                                                                           |
| --------------------------------------- | ------------- | ------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| WindowsAutopilot                       | Sí           | Sí           |                                                                                                                                 |
| Compatibilidad con arranque de red (PXE)          | Sí           | No           |                                                                                                                                 |
| Diseñador de configuraciones de Windows          | Sí           | No            | No se recomienda para Surface Pro X.                                                                                              |
| WinPE                                   | Sí           | Sí           | No se recomienda para Surface Pro X. Microsoft no proporciona el archivo .ISO y controladores necesarios para admitir WinPE con SurfaceProX. |
| Endpoint Configuration Manager: Implementación de sistema operativo (OSD) | Sí           | No            | No se admite en SurfaceProX.                                                                                              |
| MDT                                     | Sí           | No            | No se admite en SurfaceProX.                                                                                              |


| Administración                                    | Surface Pro 7       | Surface Pro X | Notas                                                                                 |
| --------------------------------------------- | ------------------- | ------------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Sí                 | Sí           | Administrar LTE con perfiles de eSIM.                                                        |
| WindowsAutopilot                             | Sí                 | Sí           |                                                                                       |
| Azure AD (administración conjunta)                      | Sí                 | Sí           | Capacidad de unir SurfaceProX a Azure AD o Active Directory (Unión a Azure AD híbrido). |
| Endpoint Configuration Manager                                          | Sí               | Sí           |                                                                                       |
| Encendido con restauración de CA                      | Sí                 | Sí           |                                                                                   |
| Kit de herramientas de diagnóstico de Surface (SDT) para empresas | Sí                 | Sí           |                                                                                   |
| Actualización de firmware de Surface Dock                  | Sí                 | No           |                                                                                   |
| Utilidad de etiqueta de activo                             | Sí                 | Sí           |                                                                                   |
| Modo de administración de Surface Enterprise (SEMM)     | Sí | Parcial       | No hay ninguna opción para deshabilitar el hardware en SurfaceProX en el nivel de firmware.                 |
| Configurador de UEFI de Surface                     | Sí |   No            | No hay ninguna opción para deshabilitar el hardware en Surface Pro X en el nivel de firmware.                |
| Administrador de UEFI de Surface                          | Sí | Parcial       | No hay ninguna opción para deshabilitar el hardware en SurfaceProX en el nivel de firmware.                 |


| Seguridad                          | Surface Pro 7 | Surface Pro X | Notas                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | ------------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BitLocker                         | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows Defender                  | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                      |
| Compatibilidad con antivirus de terceros | Sí           | Consulta la nota      |No se puede instalar el software antivirus de algunos terceros en un equipo con Windows10 que se ejecute en un procesador basado en ARM. La colaboración con proveedores de software antivirus de terceros continúa para que las aplicaciones antivirus estén disponibles en PC basados en ARM. Ponte en contacto con tu proveedor de software antivirus para saber cuándo estarán disponibles sus aplicaciones. |
| Acceso condicional                | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                      |
| Arranque seguro                       | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                      |
| Windows Information Protection    | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                      |
| Surface Data Eraser (SDE)         | Sí           | Sí           |                                                                                                                                                                                                                                                                                                                                                     
## Preguntas más frecuentes

### ¿Puedo implementar Surface Pro X con MDT o Endpoint Configuration Manager?

Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager actualmente no admiten SurfaceProX para la implementación de sistemas operativos. Los clientes que tengan una implementación basada en imagen deben pensar en SurfacePro7 mientras siguen evaluando el momento adecuado para realizar la transición a la nube.

### ¿cómo puedo implementar Surface Pro X?

Implementa Surface Pro X con Windows Autopilot.

### ¿Estará BMR disponible?

Sí.

### ¿Se requiere Intune para administrar Surface Pro X?

Intune se recomienda, pero no es obligatorio. Una vez que se haya implementado en Autopilot, puedes unir dispositivos SurfaceProX a AzureAD o Active Directory (Unión a Azure AD híbrido), donde podrás administrar los dispositivos con Intune o administrarlos de manera conjunta con Endpoint Configuration Manager, que instalará el cliente de ConfigMgrx86 de 32bits.

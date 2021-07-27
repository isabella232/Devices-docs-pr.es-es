---
title: Implementación, administración y mantenimiento de Surface Pro X
description: En este artículo se ofrece una descripción general de las principales consideraciones para implementar, administrar y mantener Surface Pro X.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 83b3db2e9fa3da253c16d208b752bd7b6e6be771
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676424"
---
# <a name="deploying-managing--servicing-surface-pro-x"></a>Implementar, administrar y mantener Surface Pro X

## <a name="introduction"></a>Introducción

Surface Pro X, con un diseño para satisfacer los requisitos comerciales de alto rendimiento, innova al incorporar el procesador más potente de su clase, los conjuntos de chips Microsoft SQ1 y Microsoft SQ1 ARM.

Surface Pro X, con una CPU de 3 GHz y una GPU de 2,1 teraflops, ofrece una experiencia de Windows completa. Las 15 horas de duración de la batería Gigabit LTE incorporada y la versatilidad del dispositivo táctil, lápiz, tableta y portátil lo hacen ideal para los trabajadores de primera línea y profesionales que trabajan en el campo financiero, jurídico y médico, o cualquier cargo que exija una larga duración de la batería y capacidades de conectividad continua.

Surface Pro X se ha diseñado casi exclusivamente para un entorno moderno, basado en la nube y funciona mejor cuando se combina con Microsoft 365, Intune y Windows Autopilot. En este artículo se reseña su apariencia y se describen las principales consideraciones para implementar, administrar y mantener Surface Pro X.

## <a name="deploying-surface-pro-x"></a>Implementación de Surface Pro X

Para disfrutar de la mejor experiencia posible, implementa Surface Pro X con Windows Autopilot con la ayuda de un Proveedor de soluciones en la nube de Microsoft, o con aprovisionamiento automático con perfiles de implementación de Autopilot y características relacionadas. Para más información, consulta:

- [Dispositivos Windows Autopilot y Surface](windows-autopilot-and-surface-devices.md)
- [Introducción a Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)

La implementación de Autopilot tiene varias ventajas: te permite usar el sistema operativo aprovisionado de fábrica, optimizado para la implementación sin interacción, para incluir la preinstalación de Office Pro Plus.

Las organizaciones que ya usan soluciones modernas de administración, seguridad y productividad están bien posicionadas para aprovechar las características de rendimiento únicas de Surface Pro X. Los clientes que usan aplicaciones de línea de negocio modernas, aplicaciones de Microsoft Store (UWP) o soluciones de escritorio remoto también pueden beneficiarse.

## <a name="image-based-deployment-considerations"></a>Consideraciones de implementación basada en imagen

Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager (anteriormente System Center Configuration Manager) no admiten actualmente Surface Pro X para la implementación de sistemas operativos. Los clientes que dependen de la implementación basada en imagen deberían considerar Surface Pro 7+ mientras continúan evaluando el momento más adecuado para hacer la transición a soluciones de implementación modernas. 

## <a name="managing-surface-pro-x-devices"></a>Administración de dispositivos Surface Pro X

### <a name="intune"></a>Intune

Intune, componente de Microsoft Enterprise Mobility + Security, se integra en Azure Active Directory para control de identidades y de acceso, y proporciona una administración granular de los dispositivos Surface Pro X inscritos. Las directivas de administración de dispositivos móviles (MDM) de Intune tienen varias ventajas sobre las anteriores herramientas locales, como la directiva de grupo de Windows. Esto incluye tiempos de inicio de sesión de dispositivo más rápidos y un catálogo de directivas más optimizado que permite la administración completa de dispositivos desde la nube. Por ejemplo, puedes administrar LTE con perfiles de eSIM para configurar los planes de datos e implementar códigos de activación en varios dispositivos.<br> 

Para más información sobre el uso de Intune, consulta la [documentación de Intune](/intune).

### <a name="co-management"></a>Administración conjunta

Una vez que se haya implementado en Autopilot, puedes unir dispositivos Surface Pro X a Azure AD o Active Directory (Unión a Azure AD híbrido), donde podrás administrar los dispositivos con Intune o administrarlos de manera conjunta con Endpoint Configuration Manager, que instalará el cliente de ConfigMgr x86 de 32 bits.

### <a name="third-party-mdm-solutions"></a>Soluciones MDM de terceros

Es posible que puedas usar herramientas MDM de terceros para administrar dispositivos Surface Pro X. Para más información, ponte en contacto con tu proveedor de MDM.

### <a name="antivirus-software"></a>Software antivirus

Windows Defender te ayudará a proteger Windows 10 en equipos basados en ARM para la duración admitida del dispositivo con Windows 10. 

No se puede instalar el software antivirus de algunos terceros en un equipo con Windows 10 que se ejecute en un procesador basado en ARM. La colaboración con proveedores de software antivirus de terceros continúa para que las aplicaciones antivirus estén disponibles en PC basados en ARM. Ponte en contacto con tu proveedor de software antivirus para saber cuándo estarán disponibles sus aplicaciones.

## <a name="servicing-surface-pro-x"></a>Mantenimiento de Surface Pro X

Surface Pro X incluye la versión 2004 de Windows 10 y es compatible con Windows 10, versión 1903 o posterior. Como dispositivo basado en ARM, tiene requisitos específicos para mantener los controladores y el firmware más recientes. 

Surface Pro X se ha diseñado para usar Windows Update para simplificar el proceso de mantener actualizados los controladores y el firmware tanto para los usuarios domésticos como para los usuarios de pequeñas empresas. Usa la configuración predeterminada para recibir actualizaciones automáticas.  Para verificarlo:

1. Ve a **Inicio** > **Configuración > Actualización y seguridad > Windows Update** > **Opciones avanzadas**.
2. En **Elegir cómo se instalan las actualizaciones**, selecciona **Automático (recomendado)**.

### <a name="recommendations-for-commercial-customers"></a>Recomendaciones para clientes comerciales

- Usa Windows Update o Windows Update para empresas para mantener los controladores y el firmware más recientes. Para obtener más información, consulta [Implementar actualizaciones con Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb).
- Para más información sobre la implementación y la administración de actualizaciones en dispositivos Surface, consulte [Administrar e implementar actualizaciones de drivers y firmware de Surface](manage-surface-driver-and-firmware-updates.md).
- Ten en cuenta que Windows Server Update Services (WSUS) no admite la capacidad de entregar controladores y firmware a Surface Pro X.

## <a name="running-apps-on-surface-pro-x"></a>Ejecución de aplicaciones en Surface Pro X

La mayoría de las aplicaciones se ejecutan en PC Windows 10 basados en ARM con exclusiones limitadas.

### <a name="supported-apps"></a>Aplicaciones compatibles

- La mayoría de las aplicaciones Win32 x86 se ejecutan en Surface Pro X.
- Las aplicaciones para UWP de Microsoft Store y ARM64 nativas ofrecen una excelente experiencia de usuario, que usa la velocidad nativa completa del procesador basado en ARM, a la vez que optimiza la duración de la batería.
- Aplicaciones que usan controladores diseñados para PC Windows 10 que se ejecuta en un procesador basado en ARM.

> [!NOTE]
> Con la emulación de 64-bit la cual pronto estará en la vista previa a través del programa Windows Insider, podrá ejecutar aplicaciones de 64 bits (x64) en Surface Pro X.

### <a name="fasttrack-app-assure"></a>App Assure de FastTrack 

El programa App Assure está disponible para clientes comerciales para sus aplicaciones LOB, ISV y originales de Microsoft dirigidas a Windows 10 en ARM. Si los clientes comerciales experimentan un problema de compatibilidad de aplicaciones con Windows 10 en ARM, Microsoft proporcionará recursos para desarrolladores para solucionar problemas y asistir en las correcciones de aplicaciones, sin coste adicional. Para más información, visite [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

Para más información sobre cómo ejecutar aplicaciones en Surface Pro X, consulta:

- [Preguntas frecuentes sobre los PC basados en ARM con Windows 10](https://support.microsoft.com/help/4521606)
- [Documentación de Windows 10 en ARM](/windows/arm)

## <a name="virtual-desktops-vdi"></a>Escritorios virtuales (VDI)

Windows Virtual Desktop permite el acceso a escritorios, aplicaciones y datos de Windows en cualquier dispositivo o plataforma informáticos, desde cualquier ubicación. Para más información, consulta el [sitio de Windows Virtual Desktop](https://aka.ms/wvd). 

## <a name="browsing-with-surface-pro-x"></a>Exploración con Surface Pro X

Los exploradores populares se ejecutan en Surface Pro X:

- Las versiones de Edge incluidas, Firefox, Chrome e Internet Explorer se ejecutan en Surface Pro X.
- Firefox y Microsoft Edge basado en Chromium se ejecutan de forma nativa y, por lo tanto, tienen un rendimiento mejorado en PC Windows 10 en un procesador basado en ARM.

## <a name="installing-and-using-microsoft-office"></a>Instalación y uso de Microsoft Office

- Usa Office 365 para disfrutar de la mejor experiencia en PC Windows 10 en un procesador basado en ARM.
- "Hacer clic para ejecutar" de Office 365 instala Outlook, Word, Excel y PowerPoint, optimizados para ejecutarse en PC Windows 10 en un procesador basado en ARM.
- Microsoft Teams se ejecuta a la perfección en Surface Pro X.
- Para las "versiones perpetuas" de Office, como Office 2019, instala la versión de 32 bits.

## <a name="vpn"></a>VPN

Para confirmar si una VPN de terceros específica admite PC Windows 10 en un procesador basado en ARM, ponte en contacto con el proveedor de la VPN.

## <a name="feature-summary"></a>Resumen de características

En las tablas siguientes se muestra la disponibilidad de las características clave seleccionadas en Surface Pro X con Windows 10 en ARM.


**Implementación**

| Característica                                                           | S/N | Notas                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Sí |                                                                                                                                   |
| Compatibilidad con arranque de red (PXE)                                    | No  |                                                                                                                                   |
| Diseñador de configuraciones de Windows                                    | No  | No se recomienda para Surface Pro X.                                                                                                |
| WinPE                                                             | Sí | No se recomienda para Surface Pro X. Microsoft no proporciona el archivo .ISO y controladores necesarios para admitir WinPE con Surface Pro X. |
| Endpoint Configuration Manager: Implementación de sistema operativo (OSD) | No  | No se admite en Surface Pro X.                                                                                                   |
| MDT                                                               | No  | No se admite en Surface Pro X.                                                                                                   |

 
 
 **Management**
 

| Característica                                       | S/N     | Notas                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Sí     | Administrar LTE con perfiles de eSIM.                                                        |
| Windows Autopilot                             | Sí     |                                                                                       |
| Azure AD (administración conjunta)                      | Sí     | Capacidad de unir Surface Pro X a Azure AD o Active Directory (Unión a Azure AD híbrido). |
| Endpoint Configuration Manager                | Sí     |                                                                                       |
| Encendido con restauración de CA                      | Sí     |                                                                                       |
| Kit de herramientas de diagnóstico de Surface (SDT) para empresas | Sí     |                                                                                       |
| Herramienta Etiqueta de activo de Surface                        | Sí     |                                                                                       |
| Modo de administración de Surface Enterprise (SEMM)     | Parcial | No hay ninguna opción para deshabilitar el hardware en Surface Pro X en el nivel de firmware.                 |
| Configurador de UEFI de Surface                     | No      | No hay ninguna opción para deshabilitar el hardware en Surface Pro X en el nivel de firmware.                |
| Administrador de UEFI de Surface                          | Parcial | No hay ninguna opción para deshabilitar el hardware en Surface Pro X en el nivel de firmware.                 |

 

**Seguridad**
 

 Característica                                       | S/N     | Notas                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | Sí     |                                                       |
| Windows Defender                              | Sí     |                                                                                       |
| Compatibilidad con antivirus de terceros             | Consulta la nota| No se puede instalar el software antivirus de algunos terceros en un equipo con Windows 10 que se ejecute en un procesador basado en ARM. La colaboración con proveedores de software antivirus de terceros continúa para que las aplicaciones antivirus estén disponibles en PC basados en ARM. Ponte en contacto con tu proveedor de software antivirus para saber cuándo estarán disponibles sus aplicaciones. |
| Arranque seguro               | Sí     |                                                                                       |
| Windows Information Protection                      | Sí     |                                                                                       |
| Surface Data Eraser (SDE)     | Sí     |                                                                                       |




## <a name="faq"></a>Preguntas más frecuentes

### <a name="can-i-deploy-surface-pro-x-with-mdt-or-endpoint-configuration-manager"></a>¿Puedo implementar Surface Pro X con MDT o con el Administrador de configuración de Endpoint?

Microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager actualmente no admiten Surface Pro X para la implementación de sistemas operativos. Los clientes que dependen de la implementación basada en imagen deberían considerar Surface Pro 7+ mientras continúan evaluando el momento más adecuado para hacer la transición a la nube.

### <a name="how-can-i-deploy-surface-pro-x"></a>¿Cómo puedo implementar Surface Pro X?

Implementa Surface Pro X con Windows Autopilot.

### <a name="is-a-bmr-available"></a>¿Hay disponible un BMR?

Sí, consulte [Descargar una imagen de recuperación para su Surface](https://support.microsoft.com/surfacerecoveryimage).

### <a name="is-intune-required-to-manage-surface-pro-x"></a>¿Se requiere Intune para administrar Surface Pro X?

Intune se recomienda, pero no es obligatorio. Una vez que se haya implementado en Autopilot, puedes unir dispositivos Surface Pro X a Azure AD o Active Directory (Unión a Azure AD híbrido), donde podrás administrar los dispositivos con Intune o administrarlos de manera conjunta con Endpoint Configuration Manager, que instalará el cliente de ConfigMgr x86 de 32 bits.

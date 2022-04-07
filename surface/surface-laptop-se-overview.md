---
title: Introducción a Surface Laptop SE
description: En este artículo se proporciona información general sobre Surface Laptop SE para la educación.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: laurawi
audience: itpro
appliesto:
- Windows 11
ms.openlocfilehash: 2d16d63dda53bbfffbf5d7d9cb080c4e595217a5
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472589"
---
# <a name="surface-laptop-se-overview"></a>Introducción a Surface Laptop SE

Surface Laptop SE proporciona una experiencia de dispositivo administrada que simplifica el aprendizaje de los alumnos a un costo asequible. Ejecuta Windows 11 SE, un sistema operativo primero en la nube, y [viene cargado previamente con aplicaciones ampliamente usadas](#pre-installed-apps), como Microsoft Teams, Word, PowerPoint, Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid , y mucho más. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop SE que muestra Windows 11 SE menú Inicio":::<br>
*Figura 1. Surface Laptop SE que muestra Windows 11 SE menú Inicio*

Surface Laptop SE admite la mayoría de las aplicaciones que los alumnos y educadores necesitan, como la Web Apps progresiva (PWA), las aplicaciones de Plataforma universal de Windows (UWP) y un [conjunto seleccionado de aplicaciones & Microsoft Store Win32](#install-optional-apps). A diferencia de otros dispositivos Surface, Surface Laptop SE impide que los usuarios instalen sus propias aplicaciones. En su lugar, los administradores de TI o los responsables técnicos administran Surface Laptop SE dispositivos mediante Microsoft Endpoint Manager, que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune), [Microsoft Intune para Educación](https://www.microsoft.com/education/intune) y el nuevo [Portal de administración de Surface](surface-management-portal.md). 

> [!NOTE]
> Este artículo está pensado para administradores de TI y personal educativo que implementan y administran dispositivos para los usuarios de la escuela. Para obtener información general o para ordenar, consulte [Surface Laptop SE Slim Laptop for Students](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>Implementación simplificada, administración & seguridad

- Complete la implementación táctil para nuevos dispositivos mediante Windows Autopilot, aplicando rápidamente directivas e instalando aplicaciones. Windows Autopilot proporciona una implementación y una creación de imágenes poco táctiles, con muchas aplicaciones y directivas preinstaladas y preconfiguradas. El equipo de TI puede ajustar fácilmente la configuración del dispositivo, incluida la configuración de firmware, e instalar las aplicaciones que los alumnos necesitan para que todo esté listo cuando enciendan el dispositivo por primera vez.
- Una vez implementados los dispositivos, Microsoft Intune ofrece una administración remota simplificada durante todo el año escolar, lo que proporciona a TI la capacidad de administrar aplicaciones, controlar la seguridad y la privacidad y generar informes de cumplimiento.
- Bloquee el sistema operativo con bloqueo de tapa cuando el portátil esté cerrado y controle el acceso físico con la ranura™ de seguridad Nano de Kensington integrada.
- Una bisagra no expuesta recientemente diseñada, un chasis de plástico y un borde plástico que rodea la pantalla que sale hacia el bisel proporcionan durabilidad adicional para satisfacer mejor las necesidades y demandas de uso de los estudiantes.
- Intune y DFCI admiten actualizaciones y administración seguras de dispositivos en la capa de firmware. Los administradores de TI pueden controlar elementos de hardware, como micrófonos, puertos USB, cámaras y Bluetooth, y quitar energía a los periféricos. El empaquetado único de Surface escaneable permite la identificación sencilla de los dispositivos, con el número de id. de dispositivo que permanece igual cuando llega el momento de volver a inscribirse.

### <a name="surface-management-portal"></a>Portal de administración de Surface

Al inscribir Surface Laptop SE para la administración en la nube y los usuarios inician sesión por primera vez, la información de estos dispositivos Surface fluye automáticamente al [Portal de administración de Surface](surface-management-portal.md), lo que le proporciona un único panel de cristal para las actividades de administración de dispositivos específicos de Surface. Puede obtener información sobre el cumplimiento de dispositivos, la actividad de soporte técnico y la cobertura de garantía. Vea rápidamente el estado de cada dispositivo, que todavía está en garantía o expirando pronto, y el estado de las solicitudes de soporte técnico activas.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Portal de administración de Surface que muestra la cobertura de garantía para Surface Laptop SE":::
*Figura 2. Portal de administración de Surface que muestra la cobertura de garantía para Surface Laptop SE*

## <a name="common-admin-scenarios"></a>Escenarios comunes de administración

| Escenario                                                            | Descripción                                                                                                                                                                                                                                                                                                                          | Obtén más información                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Configuración remota de dispositivos Surface Laptop SE con Windows Autopilot | Windows Autopilot proporciona una implementación y una creación de imágenes poco táctiles, con muchas aplicaciones y directivas preinstaladas y preconfiguradas. El equipo de TI puede ajustar fácilmente la configuración del dispositivo, incluida la configuración de firmware, e instalar las aplicaciones que los alumnos necesitan para que todo esté listo cuando enciendan el dispositivo por primera vez.                 |[Configuración de Intune para dispositivos educativos con Windows Autopilot](/intune-education/windows-autopilot-setup)<br><br>[¿Cómo debo inscribir mis dispositivos?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Implementación de actualizaciones a través de Intune para Educación                             | Los administradores de TI pueden usar Microsoft Intune para insertar actualizaciones del sistema operativo y de la aplicación en Surface Laptop SE dispositivos en toda la escuela durante todo el año. Si es necesario, pueden deshabilitar elementos de hardware como la cámara o Bluetooth en un dispositivo individual o restablecer un dispositivo específico si un alumno experimenta problemas técnicos. |[Administración de dispositivos que ejecutan Windows 11 SE](/intune-education/windows-11-se-overview)<br><br>[Documentación y recursos de Microsoft Education](/microsoft-365/education/)<br><br>[Comenzar con Intune para educación](/microsoft-365/education/deploy/intune-for-education)<br><br>[Usar Intune for Education para administrar los grupos, las aplicaciones y la configuración](/microsoft-365/education/deploy/use-intune-for-education) |
| Reemplazar dispositivos según sea necesario                                           | Si los alumnos rompen la pantalla o dañan el dispositivo, los administradores de TI pueden implementar rápidamente dispositivos de reserva, lo que transfiere las identidades en la nube de los alumnos a los nuevos dispositivos.                                                                                                  |[Acciones de dispositivo remoto en Intune para Educación](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Implementación de nuevas aplicaciones a través de Intune                                          | Si los profesores solicitan una nueva aplicación, los administradores de TI pueden instalarla de forma remota en todos los dispositivos de los alumnos mediante Intune.                                                                                                                                                                                                                            |[Instalar aplicaciones para todos los usuarios](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Restablecimiento de dispositivos a través de Intune                                            | Cuando los alumnos entregan sus dispositivos Surface Laptop SE al final del año escolar, los administradores de TI pueden usar Intune para restablecer los dispositivos de la siguiente clase que los necesitarán al comienzo del próximo año escolar.                                                                                                           |[Uso del restablecimiento de Autopilot para volver a configurar dispositivos con Intune para Educación](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>Aplicaciones preinstaladas

Surface LaptopSE incluye las siguientes aplicaciones preinstaladas:  

- Microsoft Excel
- Flipgrid
- Música groove
- Mapas
- Microsoft Edge
- Noticias de Microsoft
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft Education Edition
- Bloc de notas
- Microsoft Office
- OneDrive
- OneNote
- Outlook en la Web
- Paint
- Fotos
- PowerPoint
- Herramienta de recorte
- Notas pegajosos
- Aplicación Surface
- Surface Diagnostic Toolkit
- Sugerencias
- Grabadora de voz
- Clima
- Word

## <a name="install-optional-apps"></a>Instalación de aplicaciones opcionales

Los administradores de TI pueden instalar [aplicaciones adicionales](/education/windows/windows-11-se-overview#available-apps) como Chrome o Zoom a través de Intune. Tenga en cuenta que no hay ninguna tienda de aplicaciones para Surface Laptop SE. Consulte las siguientes instrucciones para completar la implementación de la aplicación: 

- [Implementación de la aplicación](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>Reparabilidad

Surface Laptop SE Surface Laptop SE está diseñado para permitir que los técnicos cualificados puedan atender los dispositivos localmente reemplazando rápidamente los componentes principales:

- Mostrar módulo  
- Cubo de & de teclado
- Speaker & Wi-Fi Module
- Batería
- Pies

Las escuelas pueden usar un proveedor de servicios autorizado o sus propios técnicos cualificados para reparar dispositivos in situ siguiendo la "Guía de servicio de Surface Laptop SE" proporcionada por Microsoft, disponible en [las Guías de servicio de Surface](https://www.microsoft.com/download/100440).

Para obtener más información, consulte:

- [vídeo de reparación de Surface Laptop SE](https://youtu.be/fVjjSqfp75g)
- [Soluciones principales de soporte técnico para dispositivos Surface](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE especificaciones técnicas

| Característica                     | Descripción                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dimensiones**              | - 11,17" x 7,6" x 0,70" (283,70 mm x 193,05 mm x 17,85 mm)                                                                                                                                                |
| ****<sup>Storage 1</sup>     | - A bordo, tarjeta multimedia incrustada (eMMC) 64 GB o 128 GB                                                                                                                                                 |
| **Pantalla**                 | - Pantalla: 11.6" TFT Liquid Crystal Display Module<br>- Resolución de pantalla: 1366 x 768 (135 PPI)<br>- Relación de aspecto: 16:9<br>- Relación de contraste: 800:1 (típico)<br>- Luminancia: 220 nits<br>- Sin tapa de vidrio |
| **Batería**                 | - 35Wh (nominal), 33,9Wh (min)<br>- 16 horas de duración <sup>de la batería 2</sup>                                                                                                                                              |
| **Memoria**                  | - 4 GB o 8 GB DDR4 (2400 MHz min)                                                                                                                                                                          |
| **CPU/Gráficos**          | - Procesador Intel® Celeron® N4020 / Intel® UHD Graphics 600<br>- Procesador Intel® Celeron® N4120 / Gráficos Intel® UHD 600                                                                                |
| **Conexiones**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x conector dc de tipo Barril<br>- 1 x 3,5 mm auriculares/toma de micrófono                                                                                                           |
| **Seguridad**                | - TPM de firmware en todas las configuraciones (comercial)<br>- Ranura de bloqueo de nanoseguridad                                                                                                                        |
| **Cámaras, vídeo, & audio** | - Cámara frontal de 1MP con vídeo de hasta 720p 30fps<br>- Altavoces estéreo de 2W<br>- Micrófono digital único                                                                                              |
| **Software**                | - Windows 11 SE<br>- Microsoft 365 para Educación3<sup></sup>                                                                                                                                                         |
| **Conexión inalámbrica**                | - Wi-Fi: 802.11ac (2x2)<br>- Bluetooth Wireless 5.0 LE                                                                                                                                                    |
| **Sensores**                 | - 1 x sensor de efecto Hall                                                                                                                                                                                  |
| **Exterior**                | - Carcasa: todo el cuerpo de plástico sin pintar<br>- Colores: Glaciar<br>- Botones físicos: Encendido y volumen en el teclado<br>- Bisagra: ángulo abierto de 135 grados                                                          |
| **Grosor**                  | - 2.45 lb. (1.111.3 g)                                                                                                                                                                                    |
| **Teclado y panel de seguimiento**   | - Teclado de Windows estándar para 11,6" sin retroiluminación<br>- Control de pista estándar sin precisión flotante                                                                                                      |
| **Térmicas**                | - Enfriado pasivamente                                                                                                                                                                                        |
| **Fuente de alimentación**            | - En caja, 45W con cargador DC Barrel                                                                                                                                                                      |
| **En el cuadro**              | - Dispositivo Surface<br>- Fuente de alimentación<br>- Guía de inicio rápido<br>- Documentos de seguridad y garantía                                                                                                              |
| **Garantía**<sup> 4</sup>    | - Garantía limitada de hardware de un año                                                                                                                                                                      |

## <a name="references"></a>Referencias

1. El software del sistema y las actualizaciones usan un espacio de almacenamiento significativo. El almacenamiento disponible está sujeto a cambios en función del software del sistema y las actualizaciones y el uso de aplicaciones. 1 GB = 1 billón de bytes. 1 TB = 1000 GB. Consulta [Surface Storage](https://support.microsoft.com/help/4023513/surface-surface-storage?) para obtener más detalles.
2. La duración de la batería varía significativamente en función del uso, la configuración de la red y las características, la intensidad de la señal, la configuración y otros factores. Consulta [Pruebas de batería de Surface y rendimiento estimado](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) para obtener más información.
3. Requiere licencia de Microsoft 365 o Office 365 válida; se vende por separado. [Compare Microsoft 365 planes educativos](https://aka.ms/EDU-Plan-Comparison).
4. La garantía limitada de Microsoft se suma a los derechos de la ley del consumidor.


## <a name="learn-more"></a>Obtén más información

- [Surface Laptop SE de pedidos](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Introducción a Surface Laptop SE for Education](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows11SE para educación](/education/windows/windows-11-se-overview)
- [Administración de dispositivos que ejecutan Windows 11 SE](/intune-education/windows-11-se-overview)
- [Configuración de Intune para dispositivos educativos con Windows Autopilot](/intune-education/windows-autopilot-setup)
- [Documentación y recursos de Microsoft Education](/microsoft-365/education/)
- [Outlook en la Web](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [Una solución de software de hardware & específica para educación](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)
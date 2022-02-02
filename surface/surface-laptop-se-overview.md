---
title: Surface Laptop SE introducción
description: En este artículo se proporciona información general Surface Laptop SE para educación.
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
ms.openlocfilehash: 2496c50db10454674f80aec03734849bacf63f38
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338669"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE introducción

Surface Laptop SE proporciona una experiencia de dispositivo administrado que simplifica el aprendizaje de los alumnos a un costo asequible. Se ejecuta Windows 11 SE, un sistema operativo de primera nube, y viene precargado con aplicaciones [](#pre-installed-apps) muy usadas como Microsoft Teams, Word, PowerPoint, Excel, OneNote, Edge, Minecraft: Education Edition, Flipgrid , y mucho más. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop SE muestra Windows 11 SE menú Inicio":::<br>
*Figura 1. Surface Laptop SE muestra Windows 11 SE menú Inicio*

Surface Laptop SE admite la mayoría de las aplicaciones que los alumnos y los profesores necesitan, incluidas las aplicaciones web progresivas (PWA), las aplicaciones de plataforma universal de Windows (UWP) y un conjunto seleccionado de [aplicaciones & Microsoft Store Win32](#install-optional-apps). A diferencia de otros dispositivos Surface, Surface Laptop SE impide que los usuarios instalen sus propias aplicaciones. En su lugar, los administradores de TI o los responsables técnicos administran Surface Laptop SE dispositivos con Microsoft Endpoint Manager, que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune), [Microsoft Intune para](https://www.microsoft.com/education/intune) Educación y el nuevo Portal de administración [de Surface](surface-management-portal.md). 

> [!NOTE]
> Este artículo está dirigido a los administradores de TI y al personal educativo que implementan y administran dispositivos para usuarios de centros educativos. Para obtener información general o ordenar, [consulte Surface Laptop SE Portátil delgado para estudiantes](https://www.microsoft.com/surface/business/surface-laptop-se).

## <a name="simplified-deployment-management--security"></a>Implementación simplificada, administración y & seguridad

- Completa la implementación táctil para nuevos dispositivos con Windows Autopilot, aplicando rápidamente directivas e instalando aplicaciones. Windows Autopilot proporciona una implementación y una creación de imágenes sin problemas, con muchas aplicaciones y directivas preinstaladas y preconfiguradas. It can easily adjust device settings (including firmware settings) and install the apps students need so that everything is ready to go when they first power on their device.
- Una vez implementados los dispositivos, Microsoft Intune proporciona una administración remota optimizada durante todo el año escolar, lo que proporciona a LA LA la capacidad de administrar aplicaciones, controlar la seguridad y la privacidad y generar informes de cumplimiento.
- Bloquee el sistema operativo con bloqueo de tapa cuando se cierre el portátil y controle el acceso físico con la ranura de seguridad Kensington Nano integrada™.
- Una bisagra no expuesta recién diseñada, un chasis de plástico y un borde de plástico que rodea la pantalla que sale al bisel proporcionan una durabilidad adicional para satisfacer mejor las necesidades y las demandas de uso de los alumnos.
- Intune y DFCI admiten actualizaciones de dispositivos seguras y administración en la capa de firmware. Los administradores de TI pueden controlar elementos de hardware como micrófonos, puertos USB, cámaras y Bluetooth y quitar energía a los periféricos. El empaquetado único de Surface escaneable permite una identificación sencilla de los dispositivos, con el número de id. de dispositivo que permanece igual cuando llega el momento de volver a inscribirse.

### <a name="surface-management-portal"></a>Portal de administración de Surface

Al inscribir Surface Laptop SE para la administración en la nube y los usuarios inician sesión por primera vez, la información de estos dispositivos Surface fluye automáticamente al [Portal](surface-management-portal.md) de administración de Surface, lo que te ofrece un único panel de cristal para las actividades de administración de dispositivos específicos de Surface. Puedes obtener información sobre el cumplimiento del dispositivo, la actividad de soporte técnico y la cobertura de garantía. Vea rápidamente el estado de cada dispositivo, cuáles aún están en garantía o expiran pronto, y el estado de las solicitudes de soporte técnico activas.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Management Portal que muestra la cobertura de garantía para Surface Laptop SE":::
*Figura 2. Surface Management Portal que muestra la cobertura de garantía para Surface Laptop SE*

## <a name="common-admin-scenarios"></a>Escenarios de administración comunes

| Escenario                                                            | Descripción                                                                                                                                                                                                                                                                                                                          | Obtén más información                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Configurar de forma remota Surface Laptop SE dispositivos con Windows Autopilot | Windows Autopilot proporciona una implementación y una creación de imágenes sin problemas, con muchas aplicaciones y directivas preinstaladas y preconfiguradas. It can easily adjust device settings (including firmware settings) and install the apps students need so that everything is ready to go when they first power on their device.                 |[Configurar dispositivos de Intune para Educación con Windows Autopilot](/intune-education/windows-autopilot-setup)<br><br>[¿Cómo debo inscribir mis dispositivos?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Implementar actualizaciones a través de Intune para Educación                             | Los administradores de TI pueden usar Microsoft Intune para enviar actualizaciones del sistema operativo y la aplicación a Surface Laptop SE dispositivos en toda la escuela durante todo el año. Si es necesario, pueden deshabilitar elementos de hardware como la cámara o Bluetooth en un dispositivo individual o restablecer un dispositivo específico si un alumno está experimentando problemas técnicos. |[Administrar dispositivos que Windows 11 SE](/intune-education/windows-11-se-overview)<br><br>[Documentación y recursos de Microsoft Education](/microsoft-365/education/)<br><br>[Introducción a Intune for Education](/microsoft-365/education/deploy/intune-for-education)<br><br>[Usar Intune for Education para administrar los grupos, las aplicaciones y la configuración](/microsoft-365/education/deploy/use-intune-for-education) |
| Reemplazar dispositivos según sea necesario                                           | Si los alumnos rompen la pantalla o dañan el dispositivo, los administradores de TI pueden implementar rápidamente dispositivos de reserva, transfiriendo las identidades de nube de los alumnos a los nuevos dispositivos.                                                                                                  |[Acciones de dispositivo remoto en Intune for Education](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Implementar nuevas aplicaciones a través de Intune                                          | Si los profesores solicitan una nueva aplicación, los administradores de TI pueden instalarla de forma remota en todos los dispositivos de estudiantes mediante Intune.                                                                                                                                                                                                                            |[Instalar aplicaciones para todos los usuarios](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Restablecer dispositivos a través de Intune                                            | Cuando los alumnos entren en sus dispositivos Surface Laptop SE al final del año escolar, los administradores de TI pueden usar Intune para restablecer los dispositivos de la siguiente clase que los necesitarán al principio del próximo año escolar.                                                                                                           |[Usar Restablecimiento de Piloto automático para volver a configurar dispositivos con Intune para Educación](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>Aplicaciones preinstaladas

Surface LaptopSE viene con las siguientes aplicaciones preinstaladas:  

- Microsoft Excel
- Flipgrid
- Groove música
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
- Herramienta Despedaz
- Notas pegajosas
- Aplicación Surface
- Surface Diagnostic Toolkit
- Sugerencias
- Grabadora de voz
- Clima
- Word

## <a name="install-optional-apps"></a>Instalar aplicaciones opcionales

Los administradores de TI pueden instalar [aplicaciones](/education/windows/windows-11-se-overview#available-apps) adicionales como Chrome o Zoom a través de Intune. Ten en cuenta que no hay ninguna tienda de aplicaciones para Surface Laptop SE. Consulte las siguientes instrucciones para completar la implementación de la aplicación: 

- [Implementación de la aplicación](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>Reparabilidad

Surface Laptop SE Surface Laptop SE está diseñado para permitir que los técnicos cualificados puedan dar servicio a los dispositivos localmente reemplazando rápidamente los componentes principales:

- Módulo de visualización  
- Cubo de & teclado
- Módulo de & Wi-Fi altavoz
- Batería
- Pies

Los centros educativos pueden usar un proveedor de servicios autorizado o sus propios técnicos cualificados para reparar dispositivos en el sitio siguiendo la "Guía de servicio de Surface Laptop SE" proporcionada por Microsoft, disponible en las Guías de servicio de [Surface](https://www.microsoft.com/download/100440).

Para obtener más información, vea:

- [Surface Laptop SE reparar vídeo](https://youtu.be/fVjjSqfp75g)
- [Soluciones principales de soporte técnico para dispositivos Surface](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE técnicas

| Característica                     | Descripción                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dimensiones**              | - 11,17" x 7,6" x 0,70" (283,70 mm x 193,05 mm x 17,85 mm)                                                                                                                                                |
| ****<sup>Storage 1</sup>     | - Abordo, tarjeta multimedia incrustada (eMMC) de 64 GB o 128 GB                                                                                                                                                 |
| **Pantalla**                 | - Pantalla: módulo de pantalla de cristal líquido TFT de 11,6"<br>- Resolución de pantalla: 1366 x 768 (135 PPI)<br>- Relación de aspecto: 16:9<br>- Relación de contraste: 800:1 (típico)<br>- Luminance: 220 nits<br>- Sin cristal de portada |
| **Batería**                 | - 35Wh (nominal), 33,9Wh (min)<br>- 16 horas de duración de la batería <sup>2</sup>                                                                                                                                              |
| **Memoria**                  | - 4 GB o 8 GB DDR4 (2400 MHz min)                                                                                                                                                                          |
| **CPU / Gráficos**          | - Procesador Intel® Celeron® N4020 / Intel® UHD Graphics 600<br>- Procesador Intel® Celeron® N4120 / Intel® UHD Graphics 600                                                                                |
| **Conexiones**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x conector cc tipo barril<br>- 1 x 3,5 mm Auriculares/Conector de micrófono                                                                                                           |
| **Seguridad**                | - TPM de firmware en todas las configuraciones (Comercial)<br>- Ranura de bloqueo de nanoseguridad                                                                                                                        |
| **Cámaras, vídeo, & audio** | - Cámara frontal de 1 MP con vídeo de hasta 720p 30fps<br>- Altavoces estéreo de 2W<br>- Micrófono digital único                                                                                              |
| **Software**                | - Windows 11 SE<br>- Microsoft 365 para Education3<sup></sup>                                                                                                                                                         |
| **Conexión inalámbrica**                | - Wi-Fi: 802.11ac (2x2)<br>- Bluetooth Wireless 5.0 LE                                                                                                                                                    |
| **Sensores**                 | - 1 x sensor de efecto Hall                                                                                                                                                                                  |
| **Exterior**                | - Cubierta: todo el cuerpo de plástico sin pintar<br>- Colores: Glacial<br>- Botones físicos: Encendido y volumen en el teclado<br>- Bisagra: ángulo de apertura de 135 grados                                                          |
| **Grosor**                  | - 2,45 lb (1.111,3 g)                                                                                                                                                                                    |
| **Teclado y trackpad**   | - Teclado Windows estándar para 11,6" sin retroiluminación<br>- Estándar sin trackpad de precisión flotante                                                                                                      |
| **Térmicas**                | - Refrigerado pasivamente                                                                                                                                                                                        |
| **Fuente de alimentación**            | - In-box, 45W with DC Barrel charger                                                                                                                                                                      |
| **En el cuadro**              | - Dispositivo Surface<br>- Fuente de alimentación<br>- Guía de inicio rápido<br>- Documentos de seguridad y garantía                                                                                                              |
| **Garantía**<sup> 4</sup>    | - Garantía limitada de hardware de un año                                                                                                                                                                      |

## <a name="references"></a>Referencias

1. El software del sistema y las actualizaciones usan un espacio de almacenamiento significativo. El almacenamiento disponible está sujeto a cambios en función del software del sistema y las actualizaciones y el uso de aplicaciones. 1 GB = 1.000 millones de bytes. 1 TB = 1.000 GB. Consulta [Surface Storage](https://support.microsoft.com/help/4023513/surface-surface-storage?) para obtener más detalles.
2. La duración de la batería varía considerablemente en función del uso, la configuración de red y características, la intensidad de la señal, la configuración y otros factores. Consulta [Pruebas de batería de Surface y rendimiento estimado](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) para obtener más información.
3. Requiere una licencia Microsoft 365 o Office 365 válida; se vende por separado. [Comparar Microsoft 365 de educación](https://aka.ms/EDU-Plan-Comparison).
4. La garantía limitada de Microsoft se suma a los derechos de la ley del consumidor.


## <a name="learn-more"></a>Obtén más información

- [Orden Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Introducción a Surface Laptop SE educación](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows11SE para educación](/education/windows/windows-11-se-overview)
- [Administrar dispositivos que Windows 11 SE](/intune-education/windows-11-se-overview)
- [Configurar dispositivos de Intune para Educación con Windows Autopilot](/intune-education/windows-autopilot-setup)
- [Documentación y recursos de Microsoft Education](/microsoft-365/education/)
- [Outlook en la Web](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)

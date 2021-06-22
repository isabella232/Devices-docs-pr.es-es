---
title: Introducción a la seguridad de Surface
description: En este artículo se proporciona información general sobre la seguridad de dispositivos Surface
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/04/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 67ba96129d69cafaa7a1b24ce3dde98767b676ef
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614157"
---
# <a name="surface-security-overview"></a>Introducción a la seguridad de Surface

Los avances recientes en la investigación de seguridad muestran que a medida que se van construyendo más protecciones en el sistema operativo y los servicios conectados, los atacantes buscan otras vías de explotación con el firmware emergente como destino principal.

Hoy en día, la administración del firmware del dispositivo es una experiencia incoherente y a menudo implica proveedores de terceros que dificultan la supervisión del firmware y son complicados de mantener. En última instancia, esto puede limitar la capacidad de los fabricantes de hardware para detectar y enviar actualizaciones a tiempo en respuesta a las amenazas.

Microsoft Surface ha estado usando un enfoque unificado de protección de firmware y seguridad de dispositivos desde 2015 a través de la propiedad completa de un extremo a otro del diseño de hardware, el desarrollo de firmware local y un enfoque holístico de las actualizaciones y la administración de dispositivos.

Para Surface, nuestra interfaz unificada de firmware extensible (UEFI) 1 se mantiene localmente, se actualiza periódicamente a través de Windows Update y se implementa sin problemas para la administración a través de <sup> [](#references) Windows Autopilot, minimizando los riesgos y maximizando el control en el nivel de firmware antes de que se inicie el </sup> dispositivo. Microsoft proporciona transparencia total de la base de código en nuestra UEFI a través de la Project de código [abierto mu](https://microsoft.github.io/mu/) en GitHub, administrado por Microsoft Endpoint Manager.

## <a name="microsoft-designed-and-built-components"></a>Componentes diseñados y creados de Microsoft

Microsoft desarrolla y mantiene todas las capas de Surface desde el chip hasta la nube, lo que te ofrece el control último, la protección proactiva y la tranquilidad donde y sin embargo se realiza el trabajo. Los dispositivos Surface se envían con los protocolos de seguridad más sólidos que Ofrece Microsoft y permite una administración optimizada que reduce la complejidad de TI que ayuda a los usuarios a centrarse en su trabajo.

Surface impulsa la seguridad a través de un enfoque de defensa en profundidad mediante la utilización de una capa de sub-componentes defensivos independientes. De chip a nube, o una UEFI que garantiza una raíz de confianza a Microsoft Defender para endpoint con tecnología de inteligencia artificial que funciona para evitar, detectar, investigar y responder a amenazas avanzadas, Surface exige que la posición integrada de Microsoft sea mejor que la de un bloqueo.

| Característica                         | Descripción                                                                                                                                                                                                                                                                                                                         | Obtén más información                                                                                                                                                                   |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Built UEFI            | Software que configura el dispositivo y arranca Windows 10<br>Controla el arranque inicial del dispositivo y Windows 10 y, a continuación, proporciona servicios de tiempo de ejecución de firmware al sistema operativo. garantiza un mayor control sobre el hardware de un dispositivo a través de la administración de SEMM y la administración basada en la nube DFCI a través de Microsoft Endpoint Manager | [Administrar la configuración de la UEFI de Surface](manage-surface-uefi-settings.md)                                                                        |
| TPM físico 2.0                | Módulo de plataforma de confianza: microcontrolador dedicado diseñado para proteger el hardware a través de claves criptográficas integradas.<br>Cifra y almacena claves (BitLocker, Windows Hello, Credenciales de AD,)<br>PCR: registros de configuración de plataforma que protegen las medidas y métricas relevantes para detectar cambios en la configuración anterior  | [Información general sobre la tecnología del Módulo de plataforma segura](/windows/security/information-protection/tpm/trusted-platform-module-overview)                 |
| Windows Hello para empresas      | Reemplaza las contraseñas por una autenticación segura en dos fases en equipos y dispositivos móviles. Esta autenticación biométrica consta de un nuevo tipo de credencial de usuario que está vinculada a un dispositivo y usa un PIN o biométrico.                                                                                                                   | [Cómo funciona Windows Hello para empresas: Microsoft 365 seguridad](/windows/security/identity-protection/hello-for-business/hello-how-it-works) |
| Cifrado integrado           | BitLocker habilita el cifrado integrado para proteger y cifrar los datos y Windows Hello para habilitar el inicio de sesión sin contraseña, combinado con TPM físico y UEFI.                                                                                                                                                                 | [BitLocker (Windows 10): seguridad Microsoft 365 seguridad](/windows/security/information-protection/bitlocker/bitlocker-overview)                     |
| Microsoft Defender para punto de conexión | Proporciona una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas.                                                                                                                                                                               | [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)                 |

## <a name="factory-level-security-protocols-and-inspection"></a>Inspección y protocolos de seguridad a nivel de fábrica

Desde el firmware hasta el sistema operativo y todos los componentes de hardware antes del ensamblado final, los dispositivos Surface están a salvo de los ataques de la cadena de suministro en nuestras instalaciones de desarrollo y fabricación físicamente protegidas.

Por definición, una cadena de suministro segura ofrece productos terminados que cumplen los objetivos de calidad, rendimiento y funcionamiento. En pocas palabras, una cadena de suministro segura garantiza que todos los componentes sean originales y libres de manipulaciones o sabotajes no autorizados o malintencionados. Fabricamos dispositivos en fábricas de alta seguridad donde todo, desde el firmware UEFI hasta el sistema operativo, proviene directamente de Microsoft. No hay proveedores de BIOS de terceros implicados. Esta es una parte sólida de cómo protegemos contra ataques de cadena de suministro para productos Surface. Hemos reducido el ataque de Surface en nuestra UEFI quitando cualquier código no usado, incluidas las funciones SMM del modo de administración del sistema que son dispositivos que no necesitan.

Proteger las instalaciones de ataques externos basados en Internet, intrusiones y otras amenazas requiere una inversión continua en áreas clave, como:

- Inspección rigurosa y pruebas de todos los componentes en ubicaciones de ensamblado final.
- Mantener altos niveles de seguridad física en la fábrica.
- El uso de solo microsoft desarrollado & el firmware, los controladores y el sistema operativo mantenidos.
- Logística segura y entrega de portadores de confianza de dispositivos Surface directamente a revendedores de Microsoft.

Al salir de la fábrica, Surface para empresas dispositivos se protegen mediante Windows update durante todo el ciclo de vida.

## <a name="advanced-windows-security-features"></a>Características Windows seguridad avanzada

La escalada de los ataques de privilegios es el mejor amigo de un actor malintencionado y, a menudo, apuntan a información confidencial almacenada en la memoria. Estos tipos de ataques pueden convertir un riesgo de modo de usuario menor en un riesgo total del sistema operativo y el dispositivo. Para combatir estos tipos de ataques, Microsoft desarrolló la seguridad basada en virtualización (VBS) y la integridad de código protegida por hipervisor (HVCI, también conocida como integridad de memoria). VBS y HVCI usan la potencia de funcionalidades de hardware como la virtualización para proporcionar una mejor protección contra malware común y sofisticado mediante la realización de operaciones de seguridad confidenciales en un entorno aislado.

Surface incluye estas Windows de seguridad de hardware mejoradas habilitadas de forma automática para ofrecer a los clientes una seguridad aún más sólida que está integrada y activada de forma predeterminada.

## <a name="virtualization-based-security"></a>Seguridad de virtualización

La seguridad basada en virtualización o VBS usa características de virtualización de hardware para crear y aislar una región segura de memoria del sistema operativo normal. Windows puede usar este "modo seguro virtual" para hospedar una serie de soluciones de seguridad, lo que les proporciona una protección mucho mayor frente a vulnerabilidades en el sistema operativo e impide el uso de vulnerabilidades malintencionadas que intentan vencer las protecciones.

### <a name="hypervisor-enforced-code-integrity-hvci"></a>Hypervisor-Enforced integridad de código (HVCI)

HVCI usa VBS para reforzar significativamente la aplicación de directivas de integridad de código. La integridad del código del modo kernel comprueba todos los controladores y archivos binarios del modo kernel antes de que se inician y evita que los controladores sin firma o los archivos del sistema se carguen en la memoria del sistema. Como se muestra en el siguiente diagrama, HVCI se ejecuta en un entorno de ejecución aislado y comprueba la integridad del código kernel de acuerdo con la directiva de firma del kernel.

Tanto VBS como HVCI están habilitados de forma automática en los siguientes dispositivos Surface:

- Surface Laptop 4
- Surface Pro 7+
- Surface Book 3,
- Surface Laptop Go,
- Surface Pro X

## <a name="secure-boot-and-boot-guard"></a>Protección contra arranque y arranque seguro

La raíz de confianza de los dispositivos Surface comprueba las firmas y las medidas para garantizar que cada fase sea segura y auténtica antes de permitir que continúe la siguiente fase de arranque. Habilitado por UEFI y TPM 2.0, el arranque seguro garantiza que solo el código firmado, medido e implementado correctamente pueda ejecutarse en un dispositivo Surface.

Como se muestra en la figura 2, la integridad del firmware se comprueba en cada fase desde presionar el botón de encendido hasta ejecutar el sistema operativo.

 > [!div class="mx-imgBorder"]
 > ![Figura 1. Arranque seguro para dispositivos Surface ](images/secboot.png)
  *Figura 1. Arranque seguro para dispositivos Surface*

| Paso  | Fase de arranque seguro                                                                                                                                                                                                                                      |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | La seguridad se crea cada vez que se presiona el botón de encendido desde una raíz de confianza proporcionada por el TPM. Cuando un dispositivo está encendido por primera vez, el sistema ejecuta una serie de comprobaciones de seguridad para asegurarse de que el firmware del dispositivo no se ha manipulado ni dañado. |
| **2** | Cuando está activado, el SoC usa una clave de proveedor de conjuntos de chips para validar e inicia la carga de microcódigo mediante el Módulo de código autenticado (ACM) (en dispositivos basados en Intel).                                                                              |
| **3** | El ACM mide el código UEFI antes de cargarlo y lo compara con la medida conocida en el Registro de configuración de plataforma [PCR] del TPM para asegurarse de que el código UEFI no se ha modificado.                                                                |
| **4** | Antes de permitir la ejecución de UEFI, Boot Guard comprueba que la UEFI está firmada con una clave OEM de Surface. El módulo UEFI comprobado inicialmente es la seguridad sec y las secciones PRE-EFI de PEI que se muestran en el diagrama.                                                |
| **5** | La sección PEI comprueba si hay una firma de Surface en el entorno de ejecución del controlador, el módulo DXE, tal como se carga. El módulo DXE incluye la fase de selección del dispositivo de arranque.                                                                          |
| **6** | Una vez seleccionado el dispositivo de arranque, UEFI lee el dispositivo de arranque y comprueba la firma del cargador de arranque del sistema operativo antes de permitir que se ejecute.                                                                                                             |
| **7** | A continuación, el sistema operativo comprueba sus firmas en su componente principal a medida que abre el sistema operativo.

### <a name="malware-protection"></a>Protección contra malware

Para ayudar a proteger el dispositivo de ataques de software malintencionado, Surface habilita el arranque seguro para garantizar que se inicie una versión auténtica de Windows 10 y que el firmware sea tan original como cuando abandonó la fábrica.

El SoC en dispositivos Surface tiene un procesador de seguridad que es independiente de todos los demás núcleos. Cuando inicias por primera vez el dispositivo Surface, solo se inicia el procesador de seguridad antes de que se pueda cargar cualquier otra cosa. El Arranque seguro se usa para comprobar que los componentes del proceso de inicio, incluidos los controladores y el sistema operativo, se validan con una base de datos de firmas válidas y conocidas. Esto ayuda a evitar que se produzcan ataques de un sistema clonado o modificado en el que se ejecuta código malintencionado oculto en lo que parece ser una experiencia de usuario normal. Para obtener más información, consulte [Información sobre el arranque seguro](/windows-hardware/design/device-experiences/oem-secure-boot).

Una vez que el sistema operativo se comprueba como originado por Microsoft y el dispositivo Surface completa correctamente el proceso de arranque, el dispositivo examina el código ejecutable. Nuestro método para proteger el sistema operativo consiste en identificar la firma de código de todos los archivos ejecutables, de modo que solo los que superen las restricciones se carguen en tiempo de ejecución. Este método de firma de código permite al sistema operativo comprobar el autor y confirmar que el código no se ha modificado antes de ejecutarse en el dispositivo.

## <a name="drtm-protection-in-amd-devices"></a>Protección de DRTM en dispositivos AMD

Los dispositivos Surface que contienen procesadores AMD implementan el arranque seguro de forma equivalente. Surface Laptop 4 con el procesador AMD Ryzen Microsoft Surface Edition protege el firmware de la encendido inicial mediante dynamic root of trust measurements (DRTM). DRTM controla todas las CPU, forzando la ejecución a lo largo de una ruta de acceso medida y restablece la confianza en varias etapas para comprobar la integridad del firmware o software del sistema. La transición a este estado de confianza al principio proporciona protección adicional contra posibles ataques en las fases de arranque.

DRTM protege las medidas asegurándose de que se cifran mediante el cifrado total de memoria del sistema (TSME). Una vez que TSME se establece si no se puede borrar excepto por un restablecimiento del sistema. Una nueva clave de cifrado para cada restablecimiento garantiza el cifrado de un solo uso para la seguridad.

Las llamadas en tiempo de ejecución al modo de administración del sistema (SMM) se ejecutan en el nivel más alto, lo que puede ser arriesgado si el código SMM tiene algún problema. Surface Laptop 4 con AMD Ryzen protege el sistema interceptando las interrupciones de administración del sistema (SMI) y distribuye la ejecución del código SMM a un nivel inferior (usuario) para proteger el sistema del acceso no válido a código y datos. La protección de SMM usa protecciones de hardware para restringir el código, los datos y los recursos del sistema a los que se puede tener acceso, lo que hace que se aproteja aún más la protección contra incidentes involuntarios o malintencionados.

Surface Laptop 4 con AMD Ryzen admite [nist 800-193 Platform Firmware Resiliency Guidelines,](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-193.pdf)además de la sólida compatibilidad con la actualización de firmware. El mecanismo de actualización resistente para el firmware de arranque usa un mecanismo de recuperación A-B que proporciona recuperación automática a una copia de seguridad del firmware en caso de que la secuencia de arranque detecte una copia dañada del firmware durante el arranque.

Para obtener más información sobre DRTM y SMM, consulte [How a Windows Defender System Guard helps protect Windows 10 - Windows security | Microsoft Docs](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)

## <a name="remote-device-management-control"></a>Control remoto de administración de dispositivos

Los administradores de TI pueden administrar dispositivos Surface de forma remota sin tener que tocar físicamente todos los dispositivos. Microsoft Endpoint Manager Con Intune y Windows Autopilot permite la administración remota completa de dispositivos Surface desde azure cloud, entregando dispositivos totalmente configurados a los usuarios al iniciarse. Las características de borrar y retirar permiten a TI reutilizar un dispositivo fácilmente para un nuevo usuario remoto y borrar un dispositivo que ha sido robado. Esto permite capacidades de respuesta rápidas y seguras en caso de pérdida o robo de un dispositivo Surface, lo que te permite quitar de forma remota todos los datos de la empresa y volver a configurar Surface como un dispositivo totalmente nuevo.

| Característica                                        | Descripción                                                                                                                                                                                                                                                                                                                                                                                                        | Obtén más información                                                                                                                                                                                                                                                              |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| DCFI (interfaz de configuración de firmware de dispositivo) | Ofrece administración remota de firmware a escala de nube con aprovisionamiento de dispositivos sin intervención. La UEFI de Microsoft permite una implementación de DCFI más sólida, lo que permite a las organizaciones deshabilitar los elementos de hardware y bloquear de forma remota UEFI con Intune. ¹                                                                                                                                                                          | [Administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md)<br> <br>[Administrar la configuración de la UEFI de Surface](manage-surface-uefi-settings.md)                                          |
| SEMM (Surface Enterprise Management Mode)      | Habilita la participación empresarial centralizada de la configuración de firmware uefi en entornos locales, híbridos y en la nube.¹                                                                                                                                                                                                                                                                                           | [Modo de administración de Surface Enterprise](surface-enterprise-management-mode.md)                                                                                                                                                       |
| Windows Update para empresas                    | Permite a los administradores de TI mantener los dispositivos Windows 10 de su organización siempre actualizados con las últimas defensas de seguridad, las características de Windows y el firmware de Surface conectando directamente estos sistemas al servicio de actualización Windows. Puedes usar la directiva de grupo o las soluciones MDM como Microsoft Intune para configurar la configuración de actualización de Windows para empresas que controla cómo y cuándo se actualizan los dispositivos Surface. | [Windows Update para empresas](/windows/deployment/update/waas-manage-updates-wufb)<br> <br>[Administrar e implementar actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md) |

## <a name="references"></a>Referencias

1. Surface Go y Surface Go 2 usan una UEFI de terceros y no admiten DFCI. DFCI está disponible actualmente para Surface Laptop 4, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7+, Surface Pro 7 y Surface Pro X. 

## <a name="learn-more"></a>Obtén más información

- [Los nuevos equipos Surface habilitan la seguridad basada en virtualización (VBS) de forma predeterminada para permitir a los clientes hacer más y de forma segura](https://www.microsoft.com/security/blog/2021/01/11/new-surface-pcs-enable-virtualization-based-security-vbs-by-default-to-empower-customers-to-do-more-securely/)
- [El estudio destaca el rol crítico de la protección del firmware de Surface](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/study-highlights-critical-role-of-surface-firmware-protection/ba-p/2245244)
- [Mejorar la seguridad y el cumplimiento con Microsoft Surface y Microsoft 365](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/enhancing-security-and-compliance-with-microsoft-surface-and/ba-p/2283062)
- [Administrar la configuración de la UEFI de Surface](manage-surface-uefi-settings.md)
- [Administración de Intune de la configuración de la UEFI de Surface](surface-manage-dfci-guide.md)
- [Project Mu](https://microsoft.github.io/mu/)

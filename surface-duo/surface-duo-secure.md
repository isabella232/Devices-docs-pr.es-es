---
title: Introducción a la seguridad de Surface Duo
description: En este artículo se destaca cómo Surface Duo ofrece seguridad de nivel empresarial en un dispositivo móvil a través del sistema operativo Android y uefi de ingeniería de Microsoft.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 91eb893dbdc6dae93cf402a602b64a83309388e8
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326264"
---
# Introducción a la seguridad de Surface Duo

Surface Duo tiene protección integrada en cada capa con hardware, firmware y software profundamente integrados para proteger los dispositivos, las identidades y los datos. Como dispositivo Android 10, Surface Duo usa características de seguridad de Android en el nivel del sistema operativo y en la capa de servicios de Google. El sistema operativo Android aprovecha los controles de seguridad del sistema operativo tradicionales para proteger los datos de usuario y los recursos del sistema, protege la integridad del dispositivo contra malware y proporciona aislamiento de aplicaciones. Además, Google proporciona una serie de servicios en capas sobre el sistema operativo que, cuando se combinan con la seguridad del sistema operativo Android, ayudan a proteger continuamente al usuario de Android.

- **UEFI de ingeniería personalizada.** Exclusivo de Surface Duo, entre dispositivos Android, es la interfaz de firmware extensible unificada (UEFI) de microsoft, que permite el control total sobre los componentes de firmware. Microsoft ofrece seguridad de nivel empresarial a Surface Duo escribiendo o revisando cada línea de código de firmware en la empresa, lo que permite a Microsoft responder de forma directa y ágil a posibles amenazas de firmware y mitigar los riesgos de seguridad de la cadena de suministro.
- **Arranque comprobado.** A partir del nivel de hardware tras el inicio de sesión, el arranque verificado se esfuerza por asegurarse de que el código ejecutado solo proviene de un origen de confianza. Establece una cadena de confianza completa: desde la raíz de confianza protegida por hardware hasta el cargador de arranque, la partición de arranque y otras particiones comprobadas. Cuando Surface Duo arranca, cada fase comprueba la integridad y autenticidad de la siguiente fase antes de entregar la ejecución.
- **Separación de la aplicación.** El espacio aislado de aplicaciones aísla y protege las aplicaciones de Android, evitando que las aplicaciones malintencionadas accedan a información privada. El cifrado obligatorio y siempre on y el control de claves ayudan a proteger los datos en tránsito y en reposo, incluso si los dispositivos están en manos equivocadas. El cifrado está protegido con claves de almacén de claves, que almacenan claves criptográficas en un contenedor, lo que dificulta la extracción de un dispositivo.
- **Google Play Protect.** En el nivel de software, Surface Duo usa la detección de amenazas de Google Play Protect, que examina todas las aplicaciones, incluidas las aplicaciones públicas de Google Play, las aplicaciones del sistema actualizadas por Microsoft y los operadores, y las aplicaciones de instalación local.
- **ATP de Microsoft Defender.** El antivirus de nivel empresarial y el software de protección contra malware para Windows 10 ahora está disponible para dispositivos Android administrados desde Intune. Para obtener más información, vea [ATP de Microsoft Defender para Android.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android) 


## Seguridad de administración de dispositivos móviles

Surface Duo está protegido en un entorno corporativo con una solución de Administración de movilidad empresarial (EMM) que proporciona un conjunto coherente de herramientas de protección, tecnologías y procedimientos recomendados que puedes adaptar para satisfacer los requisitos de cumplimiento normativo y organizativo. Una amplia gama de API de administración ofrece a los departamentos de TI las herramientas para ayudar a evitar la fuga de datos y aplicar el cumplimiento en una variedad de escenarios. La compatibilidad con varios perfiles y las opciones de administración de dispositivos permiten la separación de datos personales y de trabajo, lo que ayuda a mantener la seguridad de los datos de la empresa.

La seguridad de MDM se basa en un conjunto en expansión de tecnologías de configuración para permitir a los usuarios ser productivos sobre la marcha, a la vez que protege la propiedad intelectual corporativa crítica. Esto incluye las directivas de protección de aplicaciones, las directivas de restricción de dispositivos y las tecnologías relacionadas diseñadas para permitirle cumplir objetivos específicos en función de su entorno, independientemente de si su empresa consiste en entregar pedidos de comidas, administrar servicios de TI para oficinas locales o administrar información de seguridad nacional confidencial. 

Por ejemplo, es posible que quieras reforzar la autenticación de dispositivos exigiendo a los usuarios que escriban una patilla alfanumérica de 6 dígitos junto con la autenticación de 2 factores.  es posible que desee restringir los dispositivos que los usuarios pueden inscribir para ayudar a garantizar que cumple con los límites de licencia o evitar conceder acceso a teléfonos "liberados" u otros tipos de dispositivos no compatibles.
Intune y otros EMMs proporcionan a las organizaciones la flexibilidad para administrar dispositivos según sus necesidades.

## Directivas de protección de aplicaciones

Las directivas de protección de aplicaciones (APP) son reglas que garantizan que los datos de una organización permanezcan seguros o contenidos en una aplicación administrada. Una directiva puede ser una regla que se aplica cuando el usuario intenta acceder o mover datos "corporativos", o un conjunto de acciones que están prohibidas o supervisadas cuando el usuario está dentro de la aplicación. Una aplicación administrada es una aplicación que tiene aplicadas directivas de protección de aplicaciones y que Intune puede administrar.

Las directivas de protección de aplicaciones permiten administrar y proteger los datos de la organización dentro de una aplicación. Muchas aplicaciones de productividad, como las aplicaciones de Microsoft Office, se pueden administrar mediante Mam de Intune. Consulta la lista oficial de aplicaciones [protegidas de Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps) disponibles para uso público.

## Consideraciones de seguridad para administrar Surface Duo

El creciente número de configuraciones de directivas disponibles en las soluciones de administración de dispositivos móviles permite a las organizaciones ajustar los niveles de protección para satisfacer sus necesidades específicas. Para ayudar a las organizaciones a priorizar la configuración de seguridad de Surface Duo (o cualquier otro dispositivo Android), Intune ha introducido su marco de configuración de seguridad de [Android Enterprise](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework) organizado en varios escenarios de configuración distintos, lo que proporciona instrucciones para el perfil de trabajo y los escenarios totalmente administrados.
 

| Nivel Seguridad                                                                                                       | Dirigido a                                                                                                                                                                      | Resumen                                                                                                                                                                                     | Información de configuración                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Seguridad básica de perfil de trabajo - Nivel 1                                                                                | Dispositivos personales con acceso a datos de trabajo o escuela.                                                                                                                             | Presenta los requisitos de contraseña, separa los datos personales y de trabajo, y valida la atestación de dispositivo Android.                                                                               | [Configuración del nivel de perfil de trabajo 1](https://microsoft.sharepoint.com/teams/EpsilonAdminGuide/Shared%20Documents/General/•%09https:/docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-basic-security) |
| Alta seguridad de perfil de trabajo - Nivel 3<br>(Debido a las convenciones de marco, este es el siguiente nivel por encima del nivel 1).<br> ** | Dispositivos usados por usuarios o grupos que son exclusivamente de alto riesgo. Por ejemplo, los usuarios que manejan datos altamente confidenciales en los que la divulgación no autorizada causa una pérdida material considerable. | Presenta la defensa contra amenazas móviles o ATP de Microsoft Defender, establece la versión mínima de Android en 8.0, establece directivas de contraseñas más seguras y restringe aún más la separación personal y el trabajo. | [Configuración del nivel de perfil de trabajo 3](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| Seguridad básica totalmente administrada - Nivel 1                                                                                | Configuración de seguridad mínima para un dispositivo empresarial, aplicable a la mayoría de los usuarios móviles que acceden a datos de trabajo o escuela.                                                          | Introduce los requisitos de contraseña, establece la versión mínima de Android en 8.0 y establece ciertas restricciones de dispositivo.                                                                          | [Configuración de nivel 1 totalmente administrada](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| Nivel 2 de seguridad mejorada totalmente administrada                                                                              | Dispositivos en los que los usuarios tienen acceso a información confidencial o confidencial.                                                                                                                | Aprueba directivas de contraseñas más seguras y deshabilita las capacidades de usuario/cuenta.                                                                                                                   | [Settngs de nivel 2 totalmente administrado](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| Nivel 3 de alta seguridad totalmente administrado                                                                                  | Dispositivos usados por usuarios o grupos que son exclusivamente de alto riesgo. Por ejemplo, los usuarios que manejan datos altamente confidenciales en los que la divulgación no autorizada causa una pérdida material considerable. | Aumenta la versión mínima de Android a 10.0, presenta la defensa contra amenazas móviles o ATP de Microsoft Defender y aplica restricciones de dispositivos adicionales.                                     | [Configuración de nivel 3 totalmente administrada](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |
 
Al igual que con cualquier marco, es posible que las configuraciones dentro de un nivel correspondiente deban ajustarse en función de las necesidades de la organización, ya que la seguridad debe evaluar el entorno de amenazas, el riesgo y el impacto en la facilidad de uso.
 
 
**Más información**


- [Marco de configuración de seguridad de Android Enterprise](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework)
- [Introducción a las directivas de protección de aplicaciones](https://docs.microsoft.com/mem/intune/apps/app-protection-policy)
- [Configuración de directiva de protección de aplicaciones de Android en Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)
- [Establecer restricciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)
- [Documento técnico de Seguridad empresarial de Android](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
 
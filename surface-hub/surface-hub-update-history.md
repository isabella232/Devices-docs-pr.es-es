---
title: Historial de actualizaciones de SurfaceHub
description: Historial de actualizaciones de SurfaceHub
ms.assetid: d66a9392-2b14-4cb2-95c3-92db0ae2de34
keywords: ''
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: dpandre
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 9d48779195702952314baf07636749b70ce000ab
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497953"
---
# <a name="surface-hub-update-history"></a>Historial de actualizaciones de SurfaceHub

Windows se ha diseñado como un servicio, lo que significa que va mejorando automáticamente a través de actualizaciones de software periódicas. Normalmente no es necesario hacer nada para obtener las últimas actualizaciones de Windows10, ya que se descargarán e instalarán cada vez que estén disponibles.

La mayoría de las actualizaciones de Windows se centran en las mejoras de rendimiento y seguridad. En la lista que aparece a continuación, aparece en primer lugar la actualización más reciente de Windows con mejoras específicas para el Surface Hub. Las actualizaciones son acumulativas, por lo que la instalación de la última actualización disponible de Windows (incluso si no está en la lista de abajo) garantiza que también se beneficie de las mejoras de cualquier actualización anterior. Las aplicaciones de Microsoft Store se actualizan a través de Microsoft Store (gestionado por el administrador del sistema de Surface Hub). Para cada app se proporciona información detallada sobre las actualizaciones.

> [!TIP]
> Esta página se actualiza a medida que se publican nuevas actualizaciones. Consulta la página [Información importante de Surface Hub](https://support.microsoft.com/products/surface-devices/surface-hub) para ver temas relacionados con las versiones actuales y anteriores que podrían requerir atención.

## <a name="windows-10-team-2020-update-20h2"></a>Actualización de Windows 10 Team 2020 (20H2)

<details>
<summary>21 de abril de 2022: actualización de Team basada en KB5011831* (compilación del SO 19042.1679)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Corrección que impide que "Finalizar sesión" desencadene el mensaje "El dispositivo necesita una actualización. Reiniciar para finalizarlo..." y el reinicio posterior en algunos escenarios.
* Corrección que garantiza que el [CSP de SurfaceHub](/windows/client-management/mdm/surfacehub-csp#deviceaccount) se pueda usar con directivas SyncML que configuran cuentas de dispositivo en formato `DOMAIN\username`.
 
Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5011831](https://support.microsoft.com/help/5011831)
</details>

<details>
<summary>22 de marzo de 2022: actualización para Team basada en KB5011543* (compilación del sistema operativo 19042.1620)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Agrega la capacidad para que los administradores [instalen aplicaciones web progresivas](install-pwa-surface-hub.md) (PWA).
* Resuelve un problema por el que los Surface Hubs unidos a Azure AD o configurados con una cuenta de administrador local podrían no sincronizar el reloj del equipo.
* Resuelve un problema por el que el uso de las sugerencias de inicio de sesión de Reuniones y Archivos con la aplicación Authenticator podría obligar al usuario a que repita el proceso de inicio de sesión.
 
Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5011543](https://support.microsoft.com/help/5011543)
</details>

<details>
<summary>15 de febrero de 2022: actualización para Team basada en KB5010415* (compilación del sistema operativo 19042.1566)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones clave de Surface Hub se describen en [Windows 10 Team 2020 Actualización 2](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-2) y también incluyen lo siguiente:

* Corrección que permite deshabilitar los servicios de Exchange durante la configuración de la cuenta de dispositivo.
* Mejora la confiabilidad para algunos escenarios de configuración de cuentas de dispositivos cuando se usa un buzón de Exchange local.
* Mejora la confiabilidad de algunos escenarios de configuración de directivas MDM al usar el CSP de SurfaceHub.
* Mejora la confiabilidad de los escenarios de llamadas entrantes al usar Skype Empresarial.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5010415](https://support.microsoft.com/help/5010415)
</details>

<details>
<summary>25 de enero de 2022 – Actualización para Team basada en KB5009596* (compilación del sistema operativo 19042.1503)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Resuelve un problema por el que los Surface Hubs no podían informar de los datos a sus áreas de trabajo configurados de Azure Log Analytics.
* Resuelve un problema por el que iniciar una reunión de Skype Empresarial desde la pantalla de bienvenida de Surface Hub podría generar un cliente SfB totalmente maximizado que no se podía minimizar.
* Resuelve un problema por el que los Surface Hubs unidos a Azure AD no rellenaban previamente el inicio de sesión de Reuniones y Archivos con una lista de invitados a la reunión.
* Resuelve un problema por el cual la rotación de contraseñas de cuentas de dispositivos no se podía habilitar en algunos escenarios locales.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5009596](https://support.microsoft.com/help/5009596)
</details>

<details>
<summary>21 de enero de 2022 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización de UEFI de Surface – 694.3924.768.0
  * Mejora la seguridad y estabilidad del sistema.
* Controlador de interfaz del motor de administración Intel(R) – 2120.100.0.1085
  * Mejora la seguridad y estabilidad del sistema.
</details>

<details>
<summary>22 de noviembre de 2021 – Actualización para Team basada en KB5007253* (compilación del sistema operativo 19042.1387)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Corrección que impone un límite de 32 caracteres cuando se usa la política de MDM para configurar el 'Nombre descriptivo' en un Surface Hub.
* Corrección que corrige el comportamiento de la política “AllowStorageCard” MDM cuando se revierte a un valor de 1 (tarjetas de almacenamiento permitidas) desde 0.
* Actualiza para permitir que el navegador Edge (Chromium) acceda a las mismas ubicaciones de archivos accesibles en el Explorador de archivos, incluida una unidad USB adjunta.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5007253](https://support.microsoft.com/help/5007253)
</details>

<details>
<summary>30 de septiembre de 2021 – KB5004196, KB5004198 y KB5004199</summary>

Estas actualizaciones del Surface Hub ofrecen el cliente de salas de Teams, el agente del Centro de administración de Teams y el agente de salas de reuniones gestionadas. Las características clave se describen en [La sala de Teams en Surface Hub](surface-hub-teams-rooms.md).
 
Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
</details>

<details>
<summary>30 de septiembre de 2021 – Actualización para Team basada en KB5005611* (compilación del sistema operativo 19042.1266)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Reemplaza el Modo de reunión 1 (Teams preferido/SfB disponible) con la funcionalidad del Modo 2 (solo Teams); se puede utilizar cualquiera de los dos ajustes, pero ambos tienen el mismo efecto.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5005611](https://support.microsoft.com/help/5005611)
</details>

<details>
<summary>1 de septiembre de 2021 – Actualización para Team basada en KB5005101* (compilación del sistema operativo 19042.1202)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones clave de Surface Hub se describen en [Windows 10 Team 2020 Actualización 1](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-1) y también incluyen lo siguiente:

* Mejora la confiabilidad para algunos escenarios de configuración de cuentas de dispositivos cuando se usa un buzón de Exchange local.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5005101](https://support.microsoft.com/help/5005101)
</details>

<details>
<summary>29 de julio de 2021 – Actualización para Team basada en KB5004296* (compilación del sistema operativo 19042.1151)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Actualiza a la función "Recopilar registros" para incluir datos de diagnóstico de Windows en formato de archivo csv.
* Corrección que garantiza que la limpieza al final de la sesión elimina completamente todos los datos relacionados con el servidor perimetral Chromium.
* Mejora algunos escenarios de inicio de sesión personal con Surface Hubs unidos a Azure AD cuando se usa la aplicación Authenticator.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5004296](https://support.microsoft.com/help/5004296)
</details>

<details>
<summary>10 de junio de 2021 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización de UEFI de Surface – 694.3751.768.0
  * Aborda la vulnerabilidad de seguridad crítica y mejora la estabilidad del sistema.
* Actualización del firmware de Surface ME – 11.8.86.3877
  * Aborda la vulnerabilidad de seguridad crítica y mejora la estabilidad del sistema.
* Controlador de interfaz del motor de administración de Intel(R) – 2102.100.0.1044
  * Aborda la vulnerabilidad de seguridad crítica y mejora la estabilidad del sistema.
</details>

<details>
<summary>13 de abril de 2021 – Actualización para Team basada en KB5001330* (compilación del sistema operativo 19042.928)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Resuelve un problema por el que algunos dispositivos Surface Hub solo instalaban actualizaciones de seguridad mensuales de Windows, en lugar de todas las actualizaciones acumulativas de Windows.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB5001330](https://support.microsoft.com/help/5001330)
</details>

<details>
<summary>13 de marzo de 2021 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Controlador de Bluetooth Intel(R) – 22.30.0.4
  * Mejora la seguridad y estabilidad del sistema.
* Controlador de gráficos Intel(R) – 27.20.100.8682
  * Mejora la seguridad y estabilidad del sistema.
* Controlador de Wi-Fi Intel(R) – 22.30.0.11
  * Mejora la seguridad y estabilidad del sistema.
</details>

<details>
<summary>2 de febrero de 2021 – Actualización para Team basada en KB4598291* (compilación del sistema operativo 19042.789)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Corrección que permite que la sincronización del calendario con Exchange funcione cuando el UPN de la cuenta del dispositivo no coincida con su SMTP.
* Agrega la capacidad para que los administradores [deshabiliten el uso de la autenticación moderna](/windows/client-management/mdm/surfacehub-csp#deviceaccount-exchangemodernauthenabled) durante la sincronización del calendario con Exchange.
* Garantiza que a los usuarios de Surface Hub no se les pida que ingresen las credenciales de proxy después de que se haya habilitado la característica "Usar las credenciales de la cuenta del dispositivo".
* Resuelve un problema en el que las comprobaciones de actualización de Windows Update y Store nunca se completaban si se usaba un proxy que requería autenticación.
* Mejora la confiabilidad de la aplicación Connect durante escenarios de ingesta por cable.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB4598291](https://support.microsoft.com/help/4598291)
</details>

<details>
<summary>15 de enero de 2021 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización del firmware de Surface SMC – 3.93.139.0
* Actualización de UEFI de Surface – 694.3473.768.0
</details>

<details>
<summary>11 de diciembre de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización del firmware de Surface SMC – 3.92.139.0
* Actualización de UEFI de Surface – 694.3447.768.0
</details>

<details>
<summary>30 de noviembre de 2020 – Actualización para Team basada en KB4586853* (compilación del sistema operativo 19042.662)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), incluyen:

* Actualiza la página “Configuración de privacidad” para proporcionar opciones adicionales.
* Resuelve un problema por el que las reuniones que ya habían comenzado no se mostraban en la pantalla de Bienvenida/Inicio.
* Resuelve un problema con la recuperación en la nube para configuraciones regionales que no son de EE. UU.
* Skype Empresarial
  * Mejora el rendimiento del audio direccional.
  * Reducción de los sonidos de "pulsación del lápiz" al usar el lápiz durante las llamadas de Skype Empresarial.
* Mejora la confiabilidad al inscribirse en el programa Windows Insider.
* Mejora la confiabilidad del shell de Windows Team.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos. *[KB4586853](https://support.microsoft.com/help/4586853)
</details>

<details>
<summary>24 de noviembre de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización del firmware de Surface SMC – 3.91.139.0
  * Mejore la confiabilidad del modo de espera conectado.
* Actualización del firmware de Surface Touch – 3.91.139.0
  * Mejora la respuesta táctil en modo de espera conectado.
* Actualización del firmware de audio USB de Surface – 3.91.139.0
* Actualización del firmware del lápiz de Surface – 3.91.139.0
</details>

<details>
<summary>27 de octubre de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización del firmware del agregador de Surface System – 4.14.139.0
* Actualización de UEFI de Surface – 694.3386.768.0
</details>

<details>
<summary>Actualización de Windows 10 Team 2020 para Surface Hub – notas generales de la versión (compilación del sistema operativo 19042.572)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones clave de Surface Hub, que aún no se describen en el [historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4581839/windows-10-update-history), se indican en la página "[Novedades de Windows 10 Team 2020 Update](/surface-hub/surface-hub-2020-update-whats-new)".

Consulta la página "[Instalar actualización de Windows 10 Team 2020](/surface-hub/surface-hub-2020-update)" para obtener más información sobre la disponibilidad de actualizaciones por región, método de distribución y tipo de dispositivo.
</details>

## <a name="windows-10-team-creators-update-1703"></a>Actualización de creadores de equipos de Windows 10 (1703)

<details>
<summary>1 de septiembre de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Actualización del firmware de Surface SMC – 1.177.139.0
  * Mejora los escenarios de reparación de campos.
* Actualización de firmware de SSD de superficie – 5.14.139.0
  * Mejora la estabilidad del sistema.
* Controlador de Surface Serial Hub – 9.40.139.0
  * Mejora la estabilidad del sistema.
</details>

<details>
<summary>4 de mayo de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Controlador de audio USB de Surface – 15.3.6.0
  * Mejora el rendimiento del audio direccional.
* Controlador de audio de pantalla Intel(R) – 10.27.0.5
  * Mejora los escenarios para compartir pantalla.
* Controlador de gráficos Intel(R) – 26.20.100.7263
  * Mejora la estabilidad del sistema.
* Controlador de Surface System – 1.7.139.0
  * Mejora la estabilidad del sistema.
* Actualización del firmware de Surface SMC – 1.176.139.0
  * Mejora la estabilidad del sistema.
</details>

<details>
<summary>28 de febrero de 2020 – Actualización para Surface Hub 2S</summary>

Esta actualización es específica para Surface Hub 2S y proporciona las actualizaciones de controlador y firmware que se describen a continuación:

* Controlador de integración de Surface – 13.46.139.0 
  * Mejora los escenarios de brillo de la pantalla.
* Controlador de interfaz del motor de administración Intel(R) – 1914.12.0.1256
  * Mejora la estabilidad del sistema.
* Actualización del firmware de Surface SMC – 1.161.139.0
  * Mejora el rendimiento de la batería del lápiz.
* Actualización de UEFI de Surface – 694.2938.768.0
  * Mejora la estabilidad del sistema.
</details>

<details>
<summary>11 de febrero de 2020 – Actualización para Team basada en KB4537765* (compilación del sistema operativo 15063.2284)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Resuelve un problema por el que otros participantes no pueden escuchar bien el Hub 2S durante las llamadas de Skype Empresarial.
* Mejora la confiabilidad para algunos escenarios de uso de árabe, hebreo y otros idiomas RTL en Surface Hub.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4537765](https://support.microsoft.com/help/4537765)
</details>

<details>
<summary>14 de enero de 2020 – actualización para Team basada en KB4534296* (compilación del sistema operativo 15063.2254)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Soluciona un problema con la recopilación de registros para Microsoft Surface Hub 2S.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4534296](https://support.microsoft.com/help/4534296)
</details>

<details>
<summary>24 de septiembre de 2019 – Actualización para Team basada en KB4516059* (compilación del sistema operativo 15063.2078)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

 * Actualiza la página “Configuración de recuperación” de Surface Hub 2S para reflejar con precisión las opciones de recuperación.
 * Actualiza la pantalla de bienvenida de Surface Hub 2S para mejorar el reconocimiento del dispositivo.
 * Se ha corregido un problema con el fondo del shell del equipo de Windows que se mostraba incorrectamente.
 * Se ha corregido un problema con la persistencia del diseño del menú Inicio cuando se configuraba con la política de MDM.
 * Se ha corregido un problema en Microsoft Edge que ocurre al navegar por algunos sitios web internos.
 * Se ha corregido un problema en Skype Empresarial que ocurre cuando se presenta en modo de pantalla completa.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>17 de agosto de 2019 – Actualización para Team basada en KB4512474* (compilación del sistema operativo 15063.2021)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

 * Garantiza que Video Out en Hub 2S esté predeterminado en el modo "Duplicado".
 * Mejora la confiabilidad para algunos escenarios de uso del idioma árabe en Surface Hub.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4503289](https://support.microsoft.com/help/4503289)
 </details>

<details>
<summary>18 de junio de 2019 – Actualización para Team basada en KB4503289* (compilación del sistema operativo 15063.1897)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Soluciona un problema que impide que un usuario inicie sesión en un dispositivo Microsoft Surface Hub con una cuenta de Azure Active Directory. Este problema se produce porque una sesión anterior no finalizó correctamente.
* Agrega compatibilidad con conexiones TLS 1.2 para proveedores de identidades y Exchange en escenarios de configuración de la cuenta del dispositivo.
* Correcciones para mejorar la confiabilidad de la aplicación de diagnóstico de hardware en Hub 2S. 
* Corrección para mejorar la consistencia de la experiencia de configuración de primera ejecución en Hub 2S. 

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>28 de mayo de 2019 – Actualización para Team basada en KB4499162* (compilación del sistema operativo 15063.1835)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Garantiza que a los usuarios de Surface Hub no se les pida que ingresen las credenciales de proxy después de que se haya habilitado la característica "Usar las credenciales de la cuenta del dispositivo".
* Resuelve un problema en el que las conexiones de Skype generan errores periódicamente porque el audio o el vídeo no está usando el proxy correcto.
* Agrega compatibilidad con TLS 1.2 en Skype Empresarial.
* Resuelve un error de conexión SIP en el cliente de Skype cuando el servidor de Skype tiene TLS 1.0 o TLS 1.1 deshabilitado.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4499162](https://support.microsoft.com/help/4499162)
</details>

<details>
<summary>25 de abril de 2019 – Actualización para Team basada en KB4493436* (compilación del sistema operativo 15063.1784)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Resuelve el problema de sincronización de audio y vídeo con algunos dispositivos USB que están conectados a Surface Hub.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4493436](https://support.microsoft.com/help/4493436)
</details>

<details>
<summary>27 de noviembre de 2018 – Actualización para Team basada en KB4467699* (compilación del sistema operativo 15063.1478)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Soluciona un problema que impide que algunos usuarios inicien sesión en "Mis reuniones y archivos".

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KBKB4467699](https://support.microsoft.com/help/KB4467699)
</details>

<details>
<summary>18 de octubre de 2018 – Actualización para Team basada en KB4462939* (compilación del sistema operativo 15063.1418)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Correcciones de Skype Empresarial: 
  * Resuelve el problema de conexión de Skype Empresarial al reanudar desde el estado de suspensión
  * Resuelve el problema de conexión de red de Skype Empresarial, cuando el dispositivo está conectado a Internet
  * Resuelve el bloqueo de Skype Empresarial al buscar usuarios del directorio
* Resuelve el problema que provocaba que el concentrador informara erróneamente de “Sin conexión a Internet” en entornos empresariales de proxy.
* Se ha implementado una función que permite a los clientes optar por una nueva experiencia de Whiteboard.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4462939](https://support.microsoft.com/help/4462939)
</details>

<details>
<summary>31 de agosto de 2018 – Actualización para Team basada en KB4343889* (compilación del sistema operativo 15063.1292)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se agrega soporte técnico para Microsoft Teams
* Se resuelve el problema de administración de tareas con el registro de Intune
* Se permite a los administradores deshabilitar los servicios de mensajería instantánea y correo electrónico para el Hub
* Otras correcciones de errores y mejoras de confiabilidad para la aplicación Skype Empresarial de Surface Hub

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4343889](https://support.microsoft.com/help/4343889)
</details>

<details>
<summary>21 de junio de 2018 – Actualización para Team basada en KB4284830* (compilación del sistema operativo 15063.1182)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Cambio de telemetría en apoyo de los requisitos de GDPR en EMEA

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4284830](https://support.microsoft.com/help/KB4284830)
</details>

<details>
<summary>17 de abril de 2018 – Actualización para Team basada en KB4093117* (compilación del sistema operativo 15063.1058)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se resuelve un problema de proyección cableada
* Se permite la actualización en bloque para determinadas directivas MDM (Administración de dispositivos móviles).
* Se resuelve el problema del marcador telefónico con las llamadas internacionales
* Se corrige el problema de resolución de imagen cuando 2 Surface Hub se unen a la misma reunión.
* Se resuelve el error de control de certificados OMS (Operations Management Suite)
* Se corrige un problema de seguridad al borrar al final de una sesión.
* Se resuelve el problema de Miracast, cuando se especifica Surface Hub para los canales del 149al 165
  * Los canales 149al 165 seguirán siendo inutilizables en Europa, Japón o Israel debido a la normativa gubernamental regional

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4093117](https://support.microsoft.com/help/4093117)
</details>

<details>
<summary>23 de febrero de 2018 – Actualización para Team basada en KB4077528* (compilación del sistema operativo 15063.907)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se resuelve un problema por el que la configuración de MDM no se aplicaba correctamente
* Proceso de limpieza mejorado

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4077528](https://support.microsoft.com/help/4077528)
</details>

<details>
<summary>16 de enero de 2018 – Actualización para Team basada en KB4057144* (compilación del sistema operativo 15063.877)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se agrega la capacidad de administrar el diseño de iconos del menú Inicio a través de MDM
* Corrección de error de MDM en la configuración de rotación de contraseña

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4057144](https://support.microsoft.com/help/4057144)
</details>

<details>
<summary>12 de diciembre de 2017 – Actualización para Team basada en KB4053580* (compilación del sistema operativo 15063.786)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se solucionan los parpadeos del vídeo de la cámara (fragmentación o parpadeos) durante las llamadas de Skype Empresarial
* Se soluciona el problema de Id. de SSD del centro de notificaciones

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4053580](https://support.microsoft.com/help/4053580)
</details>

<details>
<summary>14 de noviembre de 2017 – Actualización para Team basada en KB4048954* (compilación del sistema operativo 15063.726)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Actualización de función que permite a los clientes habilitar la autenticación de red cableada 802.1x mediante la directiva MDM.
* Actualización de función que permite a los usuarios seleccionar de forma dinámica la aplicación que quieran al abrir un archivo.
* Corrección que garantiza que la limpieza de Finalizar sesión elimine completamente todas las conexiones entre la cuenta del usuario y el dispositivo.
* Corrección de rendimiento que mejora el tiempo de limpieza, así como el tiempo de conexión de Miracast.
* Introduce la utilización de la autenticación fácil durante las reuniones ad-hoc.
* Corrección que garantiza que los componentes de servicio usen el mismo proxy configurado en el dispositivo.
* Se reduce y protege de forma más exhaustiva la telemetría transmitida por el dispositivo, reduciendo el uso del ancho de banda.
* Se habilita una función que permite a los usuarios facilitar comentarios a Microsoft al finalizar las reuniones.

Consulta la [Guía de administración de SurfaceHub](/surface-hub/) para habilitar o deshabilitar funciones y servicios de dispositivos.
*[KB4048954](https://support.microsoft.com/help/4048954)
</details>

<details>
<summary>10 de octubre de 2017 – Actualización para Team basada en KB4041676* (compilación del sistema operativo 15063.674)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Skype Empresarial
  * Se resuelve el problema que requería el reinicio del dispositivo al reanudar desde estado de suspensión.
  * Se corrige el problema en el que los contactos externos no se resolvían a través de la cuenta de Skype Online Hub.
* PowerPoint
  * Se corrige el problema en el que algunas presentaciones de PowerPoint no se proyectaban en Hub.
* General
  * Se corrige el problema en el que el puerto USB no podía deshabilitarlo el administrador del sistema.

*[KB4041676](https://support.microsoft.com/help/4041676)
</details>

<details>
<summary>12 de septiembre de 2017 – Actualización para Team basada en KB4038788* (compilación del sistema operativo 15063.605) </summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Seguridad
  * Se resuelve el problema con Bitlocker cuando el dispositivo se reanuda desde el estado de suspensión.
* General
  * Se reduce la frecuencia y cantidad de telemetría de estado del dispositivo, mejorando el rendimiento del sistema.
  * Se corrige el problema que evitaba que el dispositivo recopilara registros del sistema.

*[KB4038788](https://support.microsoft.com/help/4038788)
</details>

<details>
<summary>1 de agosto de 2017 – Actualización para Team basada en KB4032188* (compilación del sistema operativo 15063.498)</summary>

* Skype Empresarial 
  * Se soluciona el problema de inicio de sesión de Skype Empresarial, que requería otro intento o el reinicio del sistema.
  * Se soluciona la visualización incorrecta de hora de reuniones de Skype Empresarial.
  * Correcciones para mejorar la confiabilidad de Skype Empresarial en SurfaceHub.

*[KB4032188](https://support.microsoft.com/help/4032188)
</details>

<details>
<summary>27 de junio de 2017 – Actualización para Team basada en KB4022716* (compilación del sistema operativo 15063.442)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Solución de bloqueos del controlador NVIDIA que podrían necesitar el apagado del Surface Hub de 84” desde la suspensión, requiriendo reinicio manual.
* Se ha resuelto un problema por el que algunas aplicaciones no se inician en Surface Hub de 84".

*[KB4022716](https://support.microsoft.com/help/4022716)
</details>

<details>
<summary>13 de junio de 2017 – Actualización para Team basada en KB4022725* (compilación del sistema operativo 15063.413)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* General
  * Se han resuelto los problemas de goteo de tinta de los lápices
  * Se ha resuelto el problema que provocaba un tiempo prolongado de “limpieza” de reuniones

*[KB4022725](https://support.microsoft.com/help/4022725)
</details>

<details>
<summary>24 de mayo de 2017 – Actualización para Team basada en KB4021573* (compilación del sistema operativo 15063.328)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* General
  * Se ha resuelto un problema con la retención de la configuración de proxy durante un problema de actualización

*[KB4021573](https://support.microsoft.com/help/4021573)
</details>

<details>
<summary>9 de mayo de 2017 – Actualización para Team basada en KB4016871* (compilación del sistema operativo 15063.296)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* General
  * Se ha resuelto el problema del ciclo de suspensión y reactivación
  * Se han resuelto varios problemas de recuperación y restablecimiento
  * Se ha resuelto el problema de la pestaña Historial de actualizaciones
  * Se ha resuelto el problema de inicio del servicio Miracast
* Aplicaciones
  * Se ha solucionado un error de actualización del paquete de la aplicación

*[KB4016871](https://support.microsoft.com/help/4016871)
</details>

<details>
<summary>Windows 10 Team Creators Update 1703 para Surface Hub – Notas de la versión generales (compilación del sistema operativo 15063.0)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Evolución de la experiencia de pantalla grande 
  * Se ha mejorado el carrusel de reunión en la página principal y la pantalla Inicio
  * Es posible unirse a reuniones y finalizar la sesión directamente desde el menú Inicio
  * Las aplicaciones pueden usar una parte mayor de la pantalla durante una sesión
  * Controles de Skype simplificados
  * Mecanismos mejorados para facilitar comentarios
* Acceder a “Mi Contenido Personal”*
  * Inicio de sesión único personal desde la página principal o la pantalla Inicio
  * Es posible unirse a reuniones y finalizar la sesión directamente desde el menú Inicio
  * Acceso a los archivos personales a través de OneDrive para la Empresa directamente desde Inicio
  * Inicio de sesión de asistentes rellenado previamente
  * Flujos de autenticación simplificados con la aplicación "Authenticator"**
* Implementación y administración 
  * Experiencia OOBE simplificada a través del aprovisionamiento en bloque
  * Servicio de recuperación de dispositivos basado en la nube
  * Compatibilidad con certificados de cliente de empresa
  * Compatibilidad mejorada con credenciales de proxy
  * Se ha agregado y mejorado la compatibilidad con la configuración de calidad de servicio (QoS) de Skype
  * Se ha agregado la posibilidad de establecer el volumen predeterminado del dispositivo en Configuración
  * Compatibilidad mejorada con MDM para la [configuración](/surface-hub/remote-surface-hub-management) de Surface Hub
* Seguridad mejorada 
  * Se ha agregado la posibilidad de restringir solo las unidades USB para BitLocker
  * Se ha agregado la posibilidad de deshabilitar los puertos USB a través de MDM
  * Se ha agregado la posibilidad de deshabilitar la funcionalidad “Reanudar sesión” en tiempo de espera
  * Adición de compatibilidad con el estándar 802.1X cableado
* Audio y proyección
  * Mejoras de sonido Dolby del “Altavoz humano”
  * Reducción de los sonidos de “punteo del lápiz” al usar el Lápiz durante las llamadas de Skype Empresarial
  * Agregada compatibilidad con conexiones de infraestructura de Miracast
* Correcciones de confiabilidad y rendimiento
  * Se han resuelto varios problemas de recuperación y restablecimiento
  * Se ha resuelto un problema de autenticación de Exchange en Surface Hub al usar certificados de cliente
  * Mayor estabilidad para credenciales y conexión de redes Wi-Fi
  * Se han corregido los problemas de sincronización y aparición de audio de Miracast durante la reproducción de video
  * Incluido un ajuste para deshabilitar el comportamiento de conexión automática

*La función de inicio de sesión único requiere el uso de Office365 y OneDrive Empresarial **Consulte la Guía de administración para conocer los requisitos del servicio

</details>

## <a name="windows-10-team-anniversary-update-1607"></a>Actualización de aniversario del equipo de Windows 10 (1607)

<details>
<summary>14 de marzo de 2017 – Actualización para Team basada en KB4013429* (compilación del sistema operativo 14393.953)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* General
  * Corrección de seguridad para que el Explorador de archivos impida la navegación a ubicaciones de archivo restringidas
* Skype Empresarial
  * Corrección de la latencia de direcciones durante el uso compartido de pantalla basado en Escritorio remoto

*[KB4013429](https://support.microsoft.com/help/4013429)
</details>

<details>
<summary>10 de enero de 2017 – Actualización para Team basada en KB4000825* (compilación del sistema operativo 14393.693)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se ha habilitado la selección de las distribuciones del teclado 106/109 para usarlas con teclados físicos de japonés

*[KB4000825](https://support.microsoft.com/help/4000825)
</details>

<details>
<summary>13 de diciembre de 2016 – Actualización para Team basada en KB3206632* (compilación del sistema operativo 14393.576)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Resuelve un problema de distorsión de audio con conexión cableada

*[KB3206632](https://support.microsoft.com/help/3206632)
</details>

<details>
<summary>4 de noviembre de 2016 – Actualización para Team basada en KB3200970* (compilación del sistema operativo 14393.447)</summary>

Esta actualización aplica la Actualización de aniversario de Windows 10 Team (versión 1607) a Surface Hub e incluye mejoras de calidad y revisiones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se han solucionado problemas de Skype Empresarial para mejorar su confiabilidad

*[KB3200970](https://support.microsoft.com/help/3200970)
</details>

<details>
<summary>25 de octubre de 2016 – Actualización para Team basada en KB3197954* (compilación del sistema operativo 14393.351)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se ha habilitado una nueva característica de reposo del sistema operativo y del BIOS para reducir el consumo de energía de Surface Hub y mejorar su fiabilidad a largo plazo
* General
  * Se han resuelto aquellos casos en los que el teclado en pantalla a veces no aparecía
  * Se ha resuelto el cambio a la aplicación de pizarra interactiva que, en ocasiones, se produce cuando se abre una reunión programada
  * Se ha resuelto un problema que impedía que los administradores cambiaran la contraseña de administrador local, una vez que se restablecía el dispositivo
  * Se ha hecho un cambio en el BIOS que resuelve el problema del seguimiento de la barra de estado durante el restablecimiento del dispositivo
  * Se ha actualizado la UEFI para resolver problemas de apagado

*[KB3197954](https://support.microsoft.com/help/3197954)
</details>

<details>
<summary>11 de octubre de 2016 – Actualización para Team basada en KB3194496* (compilación del sistema operativo 14393.222)</summary>

Esta actualización aplica la Actualización de aniversario de Windows 10 Team a Surface Hub e incluye mejoras de calidad y revisiones de seguridad. (Su dispositivo ejecutará Windows 10, versión 1607 después de instalarlo). Las actualizaciones clave de Surface Hub, que aún no se describen en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Skype Empresarial
  * Mejoras de rendimiento al unirse a reuniones, incluidos los problemas al unirse a una reunión con cuentas federadas
  * La característica Uso compartido de la pantalla basado en vídeo (VBSS) ahora está disponible en Skype Empresarial para Surface Hub
  * Se ha resuelto el problema de desconexión tras cinco minutos de tiempo de inactividad
  * Se ha resuelto el error de uso compartido de la pantalla de concentrador a concentrador de Skype
  * Se han realizado mejoras en el vídeo de Skype, incluidas las siguientes:
    * Pérdida de vídeo durante la reunión con varios moderadores de vídeo
    * Vídeo entrecortado durante las llamadas
    * No se muestra la videollamada saliente para otros participantes
  * Se ha resuelto el problema con el inicio de sesión de UPN
  * Se ha resuelto el problema con el teclado de marcado durante las llamadas SIP (Protocolo de inicio de sesión)
* Pizarra
  * El usuario ahora puede guardar y recuperar las sesiones de Pizarra interactiva con el servicio online de OneDrive (a través de la funcionalidad de uso compartido)
  * Se ha mejorado el inicio de la Pizarra interactiva cuando se quita el lápiz de la base
* Aplicaciones
  * Aplicación OneDrive preinstalada para que puedas acceder a tus archivos personales y del trabajo
  * Aplicación Fotos preinstalada para que puedes ver tus fotos y vídeos
  * Aplicación PowerBI preinstalada para que puedas ver los paneles
  * Las aplicaciones de Office (Word, Excel, PowerPoint) están habilitadas para la entrada de lápiz
  * Edge en Surface Hub admite ahora sitios web basados en Flash
* General
  * Selección de dispositivos de audio habilitada (para instancias de Surface Hub conectadas mediante dispositivos de audio externos)
  * Compatibilidad con HDCP habilitada en el conector de salida de DisplayPort
  * Cambios en la interfaz de usuario del sistema para la configuración de la optimización de facilidad de uso (consulta las [guías del usuario y del administrador](https://www.microsoft.com/surface/support/surface-hub) para obtener información adicional)
  * Se han corregido errores y se ha optimizado el rendimiento para acelerar el flujo de inicio de sesión en Azure Active Directory
  * Se ha mejorado considerablemente el tiempo necesario para restablecer y restaurar Surface Hub
  * Se ha agregado la interfaz de usuario de Windows Defender en la configuración
  * Se ha mejorado la experiencia del usuario táctil inicial
  * Se ha habilitado la compatibilidad con proyecciones inalámbricas de más de 1080p a través de Miracast, en dispositivos compatibles
  * Se ha resuelto el error de la emisión de notificaciones falsas "No hay conexión a Internet" y "Es posible que las citas estén obsoletas"
  * Confiabilidad mejorada del teclado en pantalla
  * Se ha agregado compatibilidad para crear paquetes de aprovisionamiento de Surface Hub mediante el Diseñador de imágenes y configuraciones de Windows (ICD) y se ha mejorado la solución de supervisión de Surface Hub en Operations Management Suite (OMS)

*[KB3194496](https://support.microsoft.com/help/3194496)
</details>

## <a name="updates-for-windows-10-version-1511"></a>Actualización de aniversario del equipo de Windows 10 (1511)

<details>
<summary>4 de noviembre de 2016 – Actualización para Team basada en KB3198586* (compilación del sistema operativo 10586.679)</summary>

Esta actualización del Equipo de Windows 10 (versión 1511) para Surface Hub incluye mejoras de calidad y correcciones de seguridad que se describen en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history). En esta actualización, no hay ningún elemento específico para Surface Hub.

*[KB3198586](https://support.microsoft.com/help/3198586)
</details>

<details>
<summary>12 de julio de 2016 – Actualización para Team basada en KB3172985* (compilación del sistema operativo 10586.494)</summary>

Esta actualización incluye mejoras de calidad y correcciones de seguridad. En esta actualización no se han introducido nuevas funciones del sistema operativo. Los cambios clave específicos de Surface Hub (aquellos que aún no están incluidos en el [historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)) incluyen:

* Se ha solucionado un problema que causaba el bloqueo del sistema Windows
* Se ha solucionado un problema que causaba bloqueos repetidos de Edge
* Se ha solucionado un problema que causaba bloqueos del servicio antes del apagado
* Se ha solucionado un problema que provocaba que algunos datos de aplicaciones no se eliminaran correctamente después de una sesión
* Se ha actualizado el controlador NFC de Broadcom para mejorar el rendimiento de NFC
* Se ha actualizado el controlador Wi-Fi de Marvell para mejorar el rendimiento de Miracast
* Se ha actualizado el controlador de Nvidia para solucionar un error de pantalla que provocaba que los dispositivos Surface Hub de 84 pulgadas mostraran contenido atenuado o borroso
* Se han solucionado muchos problemas de Skype Empresarial, incluidos los siguientes: 
  * Problema que causaba que Skype Empresarial se desconectara durante las reuniones
  * Problema que impedía a los usuarios unirse a las reuniones cuando el organizador de la reunión estaba en una configuración federada
  * Se ha habilitado el uso compartido de aplicaciones en Skype Empresarial
  * Problema que causaba bloqueos de la aplicación Skype
* Se ha agregado un mensaje en “Configuración” para informar a los usuarios de que el sistema operativo puede dañarse si se interrumpe el restablecimiento del dispositivo antes de que finalice

*[KB3172985](https://support.microsoft.com/help/3172985)
</details>

<details>
<summary>14 de junio de 2016 – actualización para Team basada en KB3163018* (compilación del sistema operativo 10586.420)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. En esta actualización no se han introducido nuevas funciones del sistema operativo. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Lanzamiento restringido. Consulte el 12 de julio de 2016 – [KB3172985](https://support.microsoft.com/en-us/help/3172985) (compilación del sistema operativo 10586.494) para obtener detalles específicos del paquete de Surface Hub

*[KB3163018](https://support.microsoft.com/help/3163018)
</details>

<details>
<summary>10 de mayo de 2016 – Actualización para Team basada en KB3156421* (compilación del sistema operativo 10586.318)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. En esta actualización no se han introducido nuevas funciones del sistema operativo. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se ha solucionado un problema que impedía instalar algunas aplicaciones de la Store (OneDrive)
* Se ha solucionado un problema que causaba que la entrada táctil dejara de responder en las aplicaciones

*[KB3156421](https://support.microsoft.com/help/3156421)
</details>

<details>
<summary>12 de abril de 2016 – Actualización para Team basada en KB3147458* (compilación del sistema operativo 10586.218)</summary>

Esta actualización para Surface Hub incluye mejoras de calidad y correcciones de seguridad. En esta actualización no se han introducido nuevas funciones del sistema operativo. Las actualizaciones principales para Surface Hub, aún no incluidas en el [Historial de actualizaciones de Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history), incluyen:

* Se ha solucionado un problema que provocaba que el nivel de volumen no se restableciera correctamente de una sesión a otra

*[KB3147458](https://support.microsoft.com/help/3147458)
</details>

## <a name="related-topics"></a>Temas relacionados

* [Información de versión de Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=724328)
* [Actualización de noviembre de Windows 10: preguntas frecuentes](https://windows.microsoft.com/windows-10/windows-update-faq)
* [Historial de actualizaciones de Microsoft Surface](https://go.microsoft.com/fwlink/p/?LinkId=724327)
* [Historial de actualizaciones de Microsoft Lumia](https://go.microsoft.com/fwlink/p/?LinkId=785968)
* [Obtén Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=616447)

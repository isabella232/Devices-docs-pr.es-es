---
title: Supervisar Microsoft Surface Hub
description: La supervisión de dispositivos Microsoft Surface Hub se habilita a través de Microsoft Operations Management Suite (OMS).
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: supervisar Surface Hub, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836178"
---
# Supervisar Microsoft Surface Hub

La supervisión de dispositivos Microsoft Surface Hub se habilita a través de Microsoft Operations Management Suite (OMS). [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) es la solución de administración de TI de Microsoft que te ayuda a administrar y proteger toda la infraestructura de TI, incluidos los dispositivos Surface Hub.


Surface Hub se ofrece como una solución de Log Analytics en OMS, lo que permite recopilar y ver datos de uso y confiabilidad en todos los dispositivos Surface Hub. Usa la solución Surface Hub para lo siguiente:
- Realizar un inventario de dispositivos Surface Hub.
- Ver una instantánea de datos de uso y confiabilidad de las reuniones de Skype, las proyecciones inalámbricas y cableadas y las aplicaciones en los Surface Hub.
- Crear alertas personalizadas para responder con rapidez si los Surface Hub notifican errores de software o hardware.

## Agregar Surface Hub a Operations Management Suite

1. **Inicia sesión en Operations Management Suite (OMS)**. Puedes usar una cuenta de Microsoft o una cuenta profesional o educativa para crear un área de trabajo. Si tu empresa ya usa Azure Active Directory (Azure AD), usa una cuenta profesional o educativa al iniciar sesión en OMS. Una cuenta profesional o educativa te permite usar identidades de Azure AD para administrar los permisos en OMS.
2. **Crea una nueva área de trabajo de OMS**. Escribe un nombre para el área de trabajo, selecciona la región del área de trabajo y proporciona la dirección de correo que quieras asociar a esta área de trabajo. Selecciona **Crear**.
3. **Vincula la suscripción de Azure al área de trabajo**. Si la organización ya tiene una suscripción de Azure, puedes vincularla al área de trabajo. Ten en cuenta que es posible que tengas que solicitar acceso al administrador de Azure de la organización.

    > [!NOTE] 
    > Si la organización no tiene una suscripción de Azure, crea una nueva o selecciona la suscripción de Azure de OMS predeterminada en la lista. Se abrirá el área de trabajo.

4. **Agrega la solución Surface Hub**. En la Galería de soluciones, selecciona el icono **Surface Hub** de la galería y luego selecciona **Agregar** en la página de detalles de la solución. La solución se mostrará en el área de trabajo.

## Usa el panel de Surface Hub
En la página **Introducción** del área de trabajo de OMS, haz clic en el icono Surface Hub para ver el panel de Surface Hub. Usa el panel para obtener una instantánea de los datos de uso y confiabilidad de los dispositivos Surface Hub. Haz clic en cada vista del panel para ver datos detallados, modificar la consulta que quieras y crear alertas.

> [!NOTE]
> La mayoría de estas vistas muestran datos de los últimos 30 días, pero esto depende de la directiva de retención de datos de la suscripción.

**Surface Hub activos**

Usa esta vista para obtener un inventario de todos tus Surface Hub. Una vez conectado a OMS, cada Surface Hub envía periódicamente un evento de "latido" al servidor. Esta vista muestra los Surface Hub que han notificado un latido en las últimas 24 horas.

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**Proyección inalámbrica**

Usa esta vista para obtener datos de uso y confiabilidad de la proyección inalámbrica en los últimos 30 días. El gráfico muestra el número total de conexiones inalámbricas en todos los Surface Hub, lo que indica si las personas de la organización usan esta característica. Si el número es bajo, podría sugerir la necesidad de proporcionar entrenamiento para ayudar a que los usuarios de la organización aprendan a conectarse de forma inalámbrica a un Surface Hub.
 
Además, el gráfico muestra un desglose de las conexiones correctas e incorrectas. Si ves un gran número de conexiones incorrectas, es posible que los dispositivos no admitan correctamente la proyección inalámbrica a través de Miracast. Para lograr un rendimiento óptimo, Microsoft sugiere que los dispositivos ejecuten un controlador WDI Wi-Fi y un controlador de gráficos WDDM2.0. Usa la vista de detalles para saber si los problemas de proyección inalámbrica son habituales en determinados dispositivos.
 
Cuando se produce un error de conexión, los usuarios también pueden hacer lo siguiente si usan un teléfono o un portátil Windows:
- Quita el dispositivo emparejado en **Configuración** > **Dispositivos** > **Dispositivos conectados** e intenta conectarlo de nuevo.
- Reinicia el dispositivo.
 
**Proyección cableada**

Usa esta vista para obtener datos de uso y confiabilidad de la proyección cableada en los últimos 30 días. Si el gráfico muestra un gran número de conexiones incorrectas, podría indicar un problema de conectividad en la canalización audiovisual. Por ejemplo, si usas un repetidor HDMI o un panel de control de centro de la sala, es posible que deban reiniciarse.
 
**Uso de aplicaciones**

Usa esta vista para obtener datos de uso de las aplicaciones incluidas en los dispositivos Surface Hub en los últimos 30 días. Los datos proceden de los inicios de las aplicaciones de los Surface Hub, excluido Skype Empresarial. Esta vista ayuda a comprender qué aplicaciones de Surface Hub son más valiosas en la organización. Si vas a implementar nuevas aplicaciones de línea de negocio en el entorno, esta vista también puede ayudarte a comprender la frecuencia de su uso.
 
**Bloqueos de aplicaciones**

Usa esta vista para obtener datos de confiabilidad de las aplicaciones incluidas en los dispositivos Surface Hub en los últimos 30 días. Los datos proceden de los bloqueos de las aplicaciones de los Surface Hub. Esta vista ayuda a detectar el comportamiento deficiente de las aplicaciones integradas y de línea de negocio y notificarlo a los desarrolladores de aplicaciones.
 
**Consultas de ejemplo**

Usa esta vista para crear alertas personalizadas en función de un conjunto de consultas recomendado. Las alertas ayudan a responder rápidamente si los Surface Hub notifican problemas de software o hardware. Para obtener más información, consulta la sección [Configurar alertas con consultas de ejemplo](#set-up-alerts-with-sample-queries).

## Configurar alertas con consultas de ejemplo

Usa las alertas para responder rápidamente si los Surface Hub notifican problemas de software o hardware. Las reglas de alerta ejecutan automáticamente búsquedas de registros según una programación y ejecutan una o varias acciones si los resultados cumplen criterios específicos. Para obtener más información, consulta [Alertas de Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/).
 
La solución Log Analytics de Surface Hub incluye un conjunto de consultas de ejemplo que ayudan a configurar las alertas adecuadas y a comprender cómo resolver los problemas que pueden producirse. Usa estos ejemplos como punto de partida para planear la estrategia de supervisión y compatibilidad.

En la siguiente tabla se describen las consultas de ejemplo de la solución Surface Hub:

| Tipo de alerta | Impacto | Corrección recomendada | Detalles |
| ---------- | ------ | ----------------------- | ------- |
| Software   | Error  | **Reinicia el dispositivo**. <br> Reinicia manualmente o mediante el [Proveedor de servicios de configuración de reinicio](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx). <br> Sugiere realizar este procedimiento entre reuniones para minimizar el impacto en los usuarios de la organización. | Condiciones del desencadenador: <br> - Un proceso crítico en el sistema operativo de Surface Hub, como el shell, la proyección o Skype, se bloquea o deja de responder. <br> - El dispositivo no ha notificado un latido en las últimas 24 horas. Esto puede deberse a un problema de conectividad de red, un error de hardware relacionado con la red o un error con el sistema de informes de datos de diagnóstico. |
| Software   | Error  | **Comprobar los servicios de Exchange**. <br> Comprueba lo siguiente: <br> - Si el servicio está disponible. <br> - Si la contraseña de la cuenta del dispositivo está actualizada. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más detalles.| Se desencadena cuando hay un error de sincronización del calendario del dispositivo con Exchange. |
| Software   | Error  | **Comprobar el servicio de Skype Empresarial**. <br> Comprueba lo siguiente: <br> - Si el servicio está disponible. <br> - Si la contraseña de la cuenta del dispositivo está actualizada. Consulta [Administración de contraseñas](password-management-for-surface-hub-device-accounts.md) para obtener más detalles. <br> - Si el nombre de dominio de Skype Empresarial está configurado correctamente. Consulta [Configurar un nombre de dominio](use-fully-qualified-domain-name-surface-hub.md). | Se desencadena cuando no se puede iniciar sesión en Skype. |
| Software   | Error  | **Restablecer el dispositivo**. <br> Esto puede tardar un poco, por lo que es conveniente mantener el dispositivo sin conexión. <br> Para obtener más información, consulta [Restablecimiento del dispositivo (Surface Hub)](device-reset-surface-hub.md).| Se desencadena cuando hay un error al limpiar los datos del usuarios y de la aplicación al final de una sesión. Cuando el error se produce repetidamente con esta operación, el dispositivo se bloquea para proteger los datos del usuario. Debes restablecer el dispositivo para continuar. |
| Hardware   | Advertencia | **Ninguna**. Indica que tiene un impacto mínimo en la funcionalidad.| Se desencadena cuando se produce un error con cualquiera de los siguientes componentes de hardware: <br> - Ranuras de lápiz virtual <br> - Controlador de NFC <br> - Controlador de concentrador USB <br> - Controlador de Bluetooth <br> - Sensor de proximidad <br> - Rendimiento gráfico (controlador de tarjeta de vídeo) <br> - Unidad de disco duro no coincidente <br> - Ningún teclado o mouse detectado |
| Hardware   | Error | **Ponerse en contacto con Soporte técnico de Microsoft**. <br> Indica un impacto en la funcionalidad clave (por ejemplo, Skype, proyección, función táctil y conexión a Internet). <br> **Nota**: Algunos eventos, incluidos el latido, contienen el número de serie del dispositivo que puedes usar cuando te pones en contacto con el soporte técnico.| Se desencadena cuando se produce un error con cualquiera de los siguientes componentes de hardware. <br> **Componentes que afectan a Skype**: <br> - Controlador de altavoces <br> - Controlador de micrófono <br> - Controlador de cámara <br> **Componentes que afectan a la proyección cableada e inalámbrica**: <br> - Controlador touchback cableado <br> - Controlador de ingesta de cableada <br> - Controlador de adaptador inalámbrico <br> - Error de Wi-Fi Direct <br> **Otros componentes**: <br> - Controlador de digitalizador táctil <br> - Error de adaptador de red (no se notifica a OMS)|

**Para configurar una alerta**
1. En la solución Surface Hub, selecciona una de las consultas de ejemplo.
2. Modifica la consulta según tus preferencias. Para obtener más información, consulta la referencia de búsqueda de Log Analytics.
3. Haz clic en **Alerta** en la parte superior de la página para abrir la pantalla **Agregar regla de alerta**. Consulta [Alertas de Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/) para obtener información detallada sobre las opciones para configurar alertas.
4. Haz clic en **Guardar** para completar la regla de alerta. Comenzará a ejecutarse inmediatamente.

## Inscribir el dispositivo Surface Hub

Para que Surface Hub se conecte al servicio de OMS y se registre en él, debe tener acceso al número de puerto de tus dominios y a las direcciones URL. En la siguiente tabla se detallan los puertos que necesita el servicio de OMS. Para obtener más información, consulta [Configuración del proxy y del firewall (opcional) en Log Analytics](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/).

>[!NOTE]
>Surface Hub no admite actualmente el uso de un servidor proxy para comunicarse con el servicio de OMS.

| Recurso de agente              | Puertos | ¿Omitir la inspección de HTTPS? |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | Sí |
| *.oms.opinsights.azure.com  | 443   | Sí |
| *.blob.core.windows.net     | 443   | Sí |
| ods.systemcenteradvisor.com | 443   | No  |

Microsoft Monitoring Agent, que se usa para conectar dispositivos a OMS, está integrado con el sistema operativo de Surface Hub, por lo que no es necesario instalar clientes adicionales para conectar Surface Hub a OMS.
 
Una vez configurada el área de trabajo de OMS, hay varias formas de inscribir los dispositivos Surface Hub:
- [Aplicación Configuración](#enroll-using-the-settings-app)
- [Paquete de aprovisionamiento](#enroll-using-a-provisioning-package)
- [Proveedor de MDM](#enroll-using-a-mdm-provider), por ejemplo, MicrosoftInTune y ConfigurationManager
 
Necesitarás el id. del área de trabajo y la clave principal del área de trabajo de OMS. Puedes obtenerlos en el portal de OMS.
 
### Inscribir mediante la aplicación Configuración

**Para inscribir mediante la aplicación Configuración**

1. En Surface Hub, inicia **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Selecciona **Este dispositivo** y navega a **Administración de dispositivos**.
4. En **Supervisión**, selecciona **Configurar opciones de OMS**.
5. En el cuadro de diálogo de configuración de OMS, selecciona **Habilitar supervisión**.
6. Escribe el id. de área de trabajo y la clave principal de tu área de trabajo de OMS. Puedes obtenerlos en el portal de OMS.
7. Haz clic en **Aceptar** para completar la configuración.
 
Aparecerá un cuadro de diálogo de confirmación que indicará si la configuración de OMS se aplicó correctamente al dispositivo. Si es así, el dispositivo iniciará el envío de datos a OMS.

### Inscribir mediante un paquete de aprovisionamiento
Puedes usar un paquete de aprovisionamiento para inscribir el dispositivo Surface Hub. Para obtener más información, consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md).
 
### Inscribir mediante un proveedor de MDM
Puedes inscribir el dispositivo Surface Hub en OMS a través del CSP de SurfaceHub. InTune y Configuration Manager proporcionan experiencias integradas para ayudar a crear plantillas de directivas para Surface Hub. Para obtener más información, consulta [Administrar la configuración con un proveedor de MDM (Surface Hub)](manage-settings-with-mdm-for-surface-hub.md).

## Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 






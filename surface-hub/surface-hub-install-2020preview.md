---
title: Instalar Windows 10 Team 2020 Update Preview compilación
description: La actualización más reciente del sistema operativo Surface Hub, Windows 10 Team 2020, ahora está disponible.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894116"
---
# Instalar Windows 10 Team 2020 Update Preview compilación 

La actualización más reciente del sistema operativo Surface Hub, **Windows 10 Team 2020**, ahora está disponible sin costo adicional para los dispositivos surface Hub 50-pulgadas y Surface Hub 2s de 55 pulgadas del [programa Windows Insider](https://insider.windows.com). El modelo de 84 de Surface Hub se admitirá en la versión final de la actualización de Windows 10 Teams 2020.

Windows 10 Team 2020 Update ofrece mejoras importantes en la implementación y administración de dispositivos junto con las características más recientes de Windows 10. Para obtener más información sobre las novedades, consulte la siguiente entrada de blog: [nueva actualización del sistema operativo de Surface Hub publicada para la versión preliminar pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) Para obtener los problemas conocidos, consulte la sección "problemas conocidos" a continuación.
 
## Requisitos previos

- Regístrate en el [programa Windows Insider](https://insider.windows.com/).
- Descargue la compilación vista previa de Windows 10 Team 2020 desde el canal rápido del programa Windows Insider.
- Después de instalar la versión preliminar, descargue las actualizaciones de firmware necesarias. Nota: las actualizaciones de firmware no se pueden desinstalar incluso si decide abandonar el programa Windows Insider.

## Preparar su Surface Hub

Antes de empezar, compruebe que su Surface Hub tenga las actualizaciones más recientes de Windows Update y asegúrese de que guarda la clave de BitLocker asociada con el dispositivo.

**Para buscar actualizaciones de forma manual:**

1. En Surface Hub, Abra **configuración** y escriba sus credenciales de administrador cuando se le solicite.
2. Vaya a **Actualizar & seguridad**de  >  **Windows Update** y, después, seleccione **Buscar actualizaciones**.

Para obtener más información, vea [administrar actualizaciones de Windows en Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**Para guardar manualmente la clave de BitLocker:**

1. Inserte una unidad USB en Surface Hub.
2. En Surface Hub, Abra **configuración** y escriba sus credenciales de administrador cuando se le solicite.
3. Vaya a **Actualizar &** la  >  **recuperación**de seguridad.
4. En **BitLocker**, seleccione **Guardar**. La clave de BitLocker se guarda en un archivo de texto en la unidad USB.

Para obtener más información, vea [guardar la clave de BitLocker](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Instalar la compilación de Windows 10 Team 2020 Update Preview

1. En Surface Hub, Abra **configuración** y escriba sus credenciales de administrador cuando se le solicite.
2. Vaya a **Actualizar &** programa de seguridad de  >  **Windows Insider** y, a continuación, seleccione **Introducción**.
3. Siga las indicaciones para registrarse como Windows Insider con su cuenta profesional (recomendado) o con su cuenta personal de Microsoft. Para obtener más información sobre las ventajas de registrarse con su cuenta del trabajo, consulte [registrarse para el programa Windows Insider para empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
4. En **elegir la configuración de Insider**, seleccione **rápido**.
5. Permitir que Surface Hub instale automáticamente la versión preliminar y las actualizaciones de firmware necesarias durante los próximos 3 a 4 días. El dispositivo descargará e instalará automáticamente las actualizaciones durante las [ventanas de mantenimiento](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)diario. Por ejemplo:

- Durante la primera ventana de mantenimiento, Surface Hub comienza a descargar la versión preliminar de Windows Update.
- Durante una segunda ventana de mantenimiento, el dispositivo se reinicia para completar la actualización.
- Durante una tercera ventana de mantenimiento, el dispositivo descarga e instala las actualizaciones de firmware necesarias.

> [!IMPORTANT]
> Microsoft recomienda reservar el Surface Hub durante 3-4 días para permitir que el dispositivo termine de instalar la versión preliminar y las actualizaciones de firmware necesarias. Es posible que se produzcan problemas de gráficos, audio y interfaz de usuario si usas el dispositivo durante este proceso.

### Si opta por instalar manualmente la compilación de vista previa y las actualizaciones de firmware necesarias:

1. Una vez que te hayas registrado con el programa Windows Insider, ve a **configuración**  >  **Update & seguridad**de  >  **Windows Update** y selecciona **Buscar actualizaciones** para instalar la versión preliminar.
2. Una vez que se instale la compilación de versión preliminar (puede demorar hasta 14 horas), seleccione **reiniciar ahora** para completar la instalación.
3. Después de que se reinicie el dispositivo, vaya a **configuración**  >  **Update & seguridad**de  >  **Windows Update**y seleccione **Buscar actualizaciones para instalar las actualizaciones de firmware necesarias**.
4. Una vez que el firmware se instale, seleccione **reiniciar ahora**.

> [!WARNING]
> Es posible que vea problemas de gráficos, audio y interfaz de usuario si instala la versión preliminar sin instalar las actualizaciones de firmware necesarias.

> [!NOTE]
> Si decides abandonar el programa Windows Insider y revertir tu Surface Hub a una versión anterior del sistema operativo, primero debes [restablecer el dispositivo](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Después, tendrá que pasar por el [primer programa](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) para volver a configurar el dispositivo.
 
## Problemas conocidos: compilación de Windows 10 Team 2020 Update Preview

### Problemas de interfaz de usuario, audio y gráficos 

Puede experimentar diversos problemas de la interfaz de usuario y los gráficos si instala la compilación de vista previa, pero no instale inmediatamente las actualizaciones de firmware necesarias más adelante. Microsoft planea resolver estos problemas en la versión de compilación de Windows 10 Team 2020 Update.

### Surface Hub 84-pulgadas: problemas de la interfaz de usuario y los gráficos

Puede experimentar diversos problemas de la interfaz de usuario y los gráficos si instala la versión preliminar en un dispositivo de 84 pulgadas de primera generación. Surface Hub 84-pulgadas será compatible con la versión final de la actualización de Windows 10 Teams 2020.

### El inicio de sesión se ve afectado cuando se aplican las directivas de acceso condicional

- Se produce un error en iniciar sesión cuando se intenta iniciar sesión en aplicaciones como Microsoft whiteboard. Los usuarios deben iniciar sesión en [mis reuniones y archivos](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) desde el menú Inicio.

- Se produce un error en el inicio de sesión si su cuenta de usuario está registrada en otro inquilino de Azure AD que el usado por Surface hub para unirse a Azure AD.

Microsoft planea resolver estos problemas en la versión de compilación de Windows 10 Team 2020 Update.

### Windows Update solicita la instalación de nuevos drivers cuando no hay ninguno disponible

Cuando vaya a **configuración**  >  **Actualizar & seguridad**de  >  **Windows Update** después de instalar la actualización 2020 de Windows 10 y las actualizaciones de firmware necesarias, es posible que vea el siguiente error: 

- "Es posible que un controlador actual de tu PC sea mejor que el controlador que estamos tratando de instalar. Seguiremos intentando instalarlo. 

Este error puede ignorarse de forma segura. Microsoft está investigando de forma activa este problema.

### No se pueden instalar las directivas de Surface Hub con paquetes de aprovisionamiento

No se pueden instalar los paquetes de aprovisionamiento que usan directivas del proveedor de servicio de configuración (CSP) Surface Hub. Por ahora, use Microsoft Intune u otro proveedor de administración de dispositivos móviles (MDM) para aplicar las directivas de Surface Hub. Microsoft planea resolver este problema en la compilación de la versión de Windows 10 Team 2020 Update.

### Pregunta para quitar la unidad USB antes de tiempo durante la primera ejecución

Al usar un paquete de aprovisionamiento para configurar Surface Hub durante la primera ejecución, se le pedirá que quite la unidad USB antes de que el dispositivo pueda leer el archivo de configuración de Surface Hub. Si está usando un archivo para configurar su cuenta de dispositivo, ignore el mensaje. Microsoft está investigando de forma activa este problema.
 
### No se puede establecer la configuración de proxy durante la primera ejecución

Si usa un proxy para conectarse a Internet, es posible que tenga conexión a Internet limitada durante el primer programa de ejecución. Microsoft planea resolver este problema en la compilación de la versión de Windows 10 Team 2020 Update.
 
### Se muestra un error al descargar aplicaciones desde Microsoft Store

Para descargar una aplicación de Microsoft Store, verá un mensaje que le pedirá que inicie sesión. Un problema conocido hace que aparezca un error durante el inicio de sesión, pero esto no afecta a su capacidad de descargar aplicaciones. Microsoft está investigando de forma activa este problema.

### Surface Hub 2S pierde intermitentemente la conexión WiFi

Desconecta el dispositivo y vuelve a conectarlo, o usa un cable de Ethernet para conectarte a Internet. Microsoft está investigando de forma activa este problema.

### Surface Hub 2S no se puede reanudar de forma intermitente desde la suspensión

Surface Hub 2S es posible que no se reinicie por error de forma intermitente y parezca que deja de responder en una pantalla que muestra el logotipo de Microsoft. Intenta desconectar el dispositivo y volver a conectarlo. 

Para evitar este problema:

1. En Surface Hub, Abra **configuración** y escriba sus credenciales de administrador cuando se le solicite.
2. Desplácese a la sesión **Surface Hub**  >  **& energía**. 
3. En **cuando el dispositivo vaya a suspender, use esta configuración de energía**y seleccione **conectado al modo de espera.**
4. En **cuando no haya nadie presente, ponga el dispositivo en suspender después**de, seleccione **nunca.**

Microsoft planea resolver este problema en una actualización de firmware antes de la versión final de la actualización 2020 del equipo de Windows 10.

### Problemas de proyección cuando la aplicación conectar no está en la vista

- Cuando usas un cable para proyectar en Surface Hub, Touchback deja de funcionar si navegas fuera de la aplicación de Connect.
- Cuando proyectas en Surface Hub con Miracast, la conexión inalámbrica se interrumpe muy poco después de salir de la aplicación Connect.

Microsoft está investigando de forma activa estos problemas.

### Skype empresarial no está usando el proxy para el tráfico multimedia

Para algunos dispositivos que usan un proxy, Skype empresarial puede iniciar sesión, pero no usará el servidor proxy para el tráfico de medios. Microsoft está investigando de forma activa este problema.

Te invitamos a compartir tus ideas y sugerencias con el soporte técnico de Microsoft.

## Obtén más información

- [Nueva actualización del sistema operativo Surface Hub publicada para la versión preliminar pública.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Tareas iniciales con el programa Windows Insider para empresas](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)
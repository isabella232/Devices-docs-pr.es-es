---
title: Instalar aplicaciones en Microsoft Surface Hub
description: Los administradores pueden instalar aplicaciones desde la Microsoft Store o la Tienda Microsoft para Empresas.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: instalar aplicaciones, Microsoft Store, Tienda Microsoft para Empresas
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 462b76451bd12547d1c1560054a51bb88c218f96
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835778"
---
# Instalar aplicaciones en Microsoft Surface Hub

Puedes instalar aplicaciones adicionales en tu Surface Hub para ajustarse a las necesidades de tu equipo u organización. Existen distintos métodos para instalar aplicaciones en función de si estás desarrollando y probando una aplicación o implementando una aplicación publicada. Este tema describe los métodos para instalar aplicaciones para cualquiera de esos escenarios.

Algunas cosas que debes saber sobre aplicaciones de Surface Hub:
- Surface Hub solo puede ejecutar [aplicaciones de la Plataforma universal de Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Las aplicaciones creadas con [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) no se ejecutarán en Surface Hub.
- Las aplicaciones deben elegirse para la [familia de dispositivos universales](https://msdn.microsoft.com/library/windows/apps/dn894631) o la familia de dispositivos del Equipo de Windows.
- Surface Hub solo admite [aplicaciones con licencia sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de [Microsoft Store para empresas](https://businessstore.microsoft.com/store).
- De manera predeterminada, deben ser aplicaciones firmadas por la Store para poder instalarse. Durante la fase de desarrollo y prueba, también puedes elegir ejecutar aplicaciones para UWP firmadas por el desarrollador colocando el dispositivo en modo de desarrollador.
- Al enviar una aplicación a Microsoft Store, los desarrolladores necesitan establecer la disponibilidad de la familia de dispositivos y las opciones de licencia organizacional para asegurarse de que una aplicación estará disponible para ejecutarse en Surface Hub.
- Necesitas credenciales de administrador para instalar aplicaciones en el Surface Hub. Dado que el dispositivo está diseñado para usarse en espacios comunes como salas de reuniones, las personas no pueden acceder a la Microsoft Store para descargar e instalar aplicaciones.


## Desarrollar y probar aplicaciones
Cuando estés desarrollando tu propia aplicación, hay varias opciones para probar aplicaciones en Surface Hub.

### Modo de desarrollador
De manera predeterminada, Surface Hub solo ejecuta aplicaciones para UWP que hayan sido publicadas y firmadas por la Microsoft Store. Las aplicaciones enviadas a la Microsoft Store se someten a pruebas de seguridad y cumplimiento como parte del [proceso de certificación de la aplicación](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process) y esto permite proteger tu Surface Hub frente a aplicaciones malintencionadas.
 
Al habilitar el modo de desarrollador, también puedes instalar aplicaciones para UWP firmadas por el desarrollador.
 
> [!IMPORTANT]
> Una vez habilitado el modo de desarrollador, deberás restablecer el Surface Hub para deshabilitarlo. Al restablecer el dispositivo se eliminan todas las configuraciones y los archivos de usuario locales y, a continuación, se vuelve a instalar Windows.

**Activar el modo de desarrollador** 
1. En tu Surface Hub, inicia **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Navega hasta **Actualización y seguridad**  > ** Para desarrolladores**.
4. Selecciona **Modo de desarrollador** y acepta la advertencia.

### VisualStudio
Durante el desarrollo, la forma más sencilla de probar tu aplicación en un Surface Hub es usando Visual Studio. La característica de depuración remota de Visual Studio te ayuda a detectar problemas en tu aplicación antes de su implementación general. Para obtener más información, consulta [Probar aplicaciones de Surface Hub con Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

### Paquete de aprovisionamiento
Usa Visual Studio para [crear un paquete de la aplicación](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) para tu aplicación para UWP, firmada mediante un certificado de prueba. A continuación, usa Diseñador de imágenes y configuraciones de Windows (ICD) para crear un paquete de aprovisionamiento que contenga el paquete de la aplicación. Para obtener más información, consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md).


## Enviar aplicaciones a la Microsoft Store
Cuando una aplicación está lista para publicarse, los desarrolladores necesitan enviarla y publicarla en la Microsoft Store. Para obtener más información, consulta [Publicar aplicaciones de Windows](https://developer.microsoft.com/store/publish-apps).

Durante el envío de la aplicación, los desarrolladores deben establecer la **disponibilidad de familias de dispositivos** y las opciones de **licencias de organización** para asegurarse de que la aplicación estará disponible para su ejecución en Surface Hub.

**Establecer la disponibilidad de familias de dispositivos**  
1. En el [centro de desarrollo de Windows](https://developer.microsoft.com), ve a la página de envío de la aplicación.
2. Selecciona **Paquetes**.
3. En **Disponibilidad de familias de dispositivos**, selecciona estas opciones:
    
    - **Windows 10 Team**
    - **Permitir que Microsoft decida si quiere que la aplicación esté disponible para futuras familias de dispositivos**
  
![Imagen que muestra la página de la disponibilidad de familias de dispositivos: parte del proceso de envío de aplicación de la Microsoft Store.](images/device-family.png)  
    
Para obtener más información, consulta [Disponibilidad de familias de dispositivos](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).

**Establecer licencias de organización**
1. En el [centro de desarrollo de Windows](https://developer.microsoft.com), ve a la página de envío de la aplicación.
2. Selecciona **Precios y disponibilidad**.
3. En licencias de organización, selecciona **Permitir la compra de licencias en desconexión (sin conexión) para empresas**.

![Imagen que muestra la página de licencias de organización: parte del proceso de envío de aplicación de la Microsoft Store.](images/sh-org-licensing.png)

> [!NOTE]
> **Hacer que mi aplicación esté disponible para organizaciones mediante la concesión de licencias administradas por Store (en línea) y distribución** está seleccionada de forma predeterminada.

> [!NOTE]
> Los desarrolladores también pueden publicar aplicaciones de línea de negocio directamente en las empresas sin necesidad de que estén ampliamente disponibles en la Store. Para obtener más información, consulta [Distribuir aplicaciones de LOB a empresas](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).

Para obtener más información, consulta [Opciones de licencias de organización](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).


## Implementar aplicaciones publicadas

Hay varias opciones para la instalación de aplicaciones que se han publicado en la Microsoft Store en función de si quieres evaluarlas en algunos dispositivos o implementarlas ampliamente en tu organización.

Para instalar aplicaciones publicadas:
- Descarga la aplicación con la aplicación de la Microsoft Store, o
- Descarga el paquete de la aplicación de la Tienda Microsoft para Empresas y distribúyelo usando un paquete de aprovisionamiento o un proveedor de MDM compatible.

### Aplicación de la Microsoft Store
Para evaluar aplicaciones publicadas de la Microsoft Store, usa la aplicación de la Microsoft Store en el Surface Hub para buscar y descargar aplicaciones.

> [!NOTE]
> El uso de la aplicación de la Microsoft Store no es el método recomendado para implementar aplicaciones a escala en tu organización:
> - Para descargar aplicaciones, debes iniciar sesión en la aplicación de la Microsoft Store con una cuenta de Microsoft u organizativa. Sin embargo, solo puedes conectar una cuenta a un máximo de 10 dispositivos al mismo tiempo. Si tienes más de 10 Surface Hubs, deberás crear varias cuentas o quitar dispositivos de tu cuenta entre las instalaciones de las aplicaciones.
> - Para instalar aplicaciones, tendrás que iniciar sesión manualmente en la aplicación de la Microsoft Store en cada Surface Hub del que seas propietario.

**Examinar la Microsoft Store en Surface Hub** 
1. En Surface Hub, inicia **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Navega a **Este dispositivo** > **Aplicaciones y características**.
4. Selecciona **Abrir Store**.

### Descargar paquetes de la aplicación de la Tienda Microsoft para Empresas
Para descargar el paquete de la aplicación que necesitas para instalar aplicaciones en el Surface Hub, visita la [Tienda Microsoft para Empresas](https://www.microsoft.com/business-store). La Tienda para empresas es el lugar donde puedes buscar, comprar y administrar aplicaciones para los dispositivos Windows 10 de tu organización, incluido el Surface Hub.
 
> [!NOTE]
> Actualmente, Surface Hub solo es compatible con aplicaciones con licencia sin conexión disponibles a través de la Tienda Microsoft para Empresas. Los desarrolladores de aplicaciones establecen la disponibilidad de la licencia sin conexión cuando envían las aplicaciones.

Busca y compra la aplicación que quieras y, a continuación, descarga:
- El paquete de la aplicación con licencia sin conexión (un .appx o un .appxbundle)
- El archivo de licencia *sin codificar* (si usas paquetes de aprovisionamiento para instalar la aplicación)
- La archivo de licencia *codificado* (si usas MDM para distribuir la aplicación)
- Los archivos de dependencia necesarios

Para obtener más información, consulta [Descargar una aplicación con licencia sin conexión](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### Paquete de aprovisionamiento
Puedes instalar manualmente las aplicaciones con licencia sin conexión que hayas descargado de la Tienda para empresas en varios Surface Hubs mediante paquetes de aprovisionamiento. Usa Diseñador de imágenes y configuraciones de Windows (ICD) para crear un paquete de aprovisionamiento que contenga el paquete de la aplicación y el archivo de licencia *sin codificar* que descargaste de la Tienda para empresas. Para obtener más información, consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md).

### Proveedor de MDM compatible
Para implementar aplicaciones en un gran número de Surface Hubs de tu organización, usa un proveedor de MDM compatible. La siguiente tabla muestra qué proveedores de MDM admiten la implementación de paquetes de aplicaciones con licencia sin conexión.

| Proveedor de MDM                | Compatible con paquetes de aplicaciones con licencia sin conexión |
|-----------------------------|----------------------------------------|
| MDM local con Configuration Manager (a partir de la versión 1602) | Sí |
|
| Proveedor de MDM de terceros    | Comprueba que tu proveedor de MDM admite la implementación de paquetes de aplicaciones con licencia sin conexión. |

**Para implementar aplicaciones de forma remota con el administrador de configuración de Microsoft Endpoint**

> [!NOTE]
> Estas instrucciones se basan en la rama actual de Microsoft Endpoint Configuration Manager.

1. Inscriba sus Surface Hub en Configuration Manager. Para obtener más información, consulta [Inscribir un Surface Hub en MDM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm).
2. Descarga el paquete de la aplicación con licencia sin conexión, el archivo de licencia *codificado* y los archivos de dependencia necesarios de la Tienda Microsoft para Empresas. Para obtener más información, consulta [Descargar una aplicación con licencia sin conexión](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app). Coloca los archivos descargados en la misma carpeta en un recurso compartido de red.
3. En el área de trabajo de la **biblioteca de software** de la consola de Configuration Manager, haz clic en **Introducción** > **Administración de aplicaciones** > **Aplicaciones**.
4. En la pestaña **Inicio**, en el grupo **Crear**, haz clic en **Crear aplicación**.
5. En la página **General** del **Asistente para crear aplicaciones**, selecciona la casilla de verificación **Detectar automáticamente la información acerca de esta aplicación a partir de archivos de instalación**.
6. En la lista desplegable **Tipo**, selecciona **Paquete de aplicación de Windows (\*.appx, \*.appxbundle)**.
7. En el campo **Ubicación**, especifique la ruta de acceso UNC en el formulario \\server\share\\filename para el paquete de la aplicación con licencia sin conexión que has descargado de la Tienda Microsoft para Empresas. Como alternativa, haz clic en **Examinar** para buscar el paquete de la aplicación.
8. En la página **Importar información**, revisa la información que se ha importado y, a continuación, haz clic en **Siguiente**. Cuando sea necesario, puedes hacer clic **Anterior** para volver atrás y corregir los errores.
9. En la página **Información general**, completa los detalles adicionales sobre la aplicación. Puede que parte de esta información ya esté rellenada si se obtuvo automáticamente a partir del paquete de la aplicación.
10. Haz clic en **Siguiente**, revisa la información de la aplicación en la página Resumen y, a continuación, completa el Asistente para crear aplicaciones. 
11. Crea un tipo de implementación para la aplicación. Para obtener más información, consulta [Crear tipos de implementación para la aplicación](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).
12. Implementa la aplicación en los Surface Hubs. Para obtener más información, consulte [implementar aplicaciones con Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).
13. Según sea necesario, actualiza la aplicación descargando un nuevo paquete de la Tienda Microsoft para Empresas y publicando una revisión de la aplicación en Configuration Manager. Para obtener más información, vea [actualización y retirada de aplicaciones con Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx). 

> [!NOTE] 
> Si está usando Microsoft Endpoint Configuration Manager (rama actual), puede omitir los pasos anteriores conectando el almacén para empresas con Configuration Manager. Al hacerlo, puede sincronizar la lista de aplicaciones que ha comprado con Configuration Manager, verlas en la consola de Configuration Manager e implementarlas como lo haría con cualquier otra aplicación. Para obtener más información, vea [Administrar aplicaciones de Microsoft Store para empresas con Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).


## Resumen

Hay varias formas diferentes de instalar aplicaciones en Surface Hub, en función de si está desarrollando aplicaciones, evaluando aplicaciones en un pequeño número de dispositivos o implementando aplicaciones de forma general en su organización. En esta tabla se resumen los métodos admitidos:

| Método de instalación             | Desarrollo de aplicaciones | Evaluación de aplicaciones en <br> algunos dispositivos | Implementación de aplicaciones ampliamente <br> en su organización |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| VisualStudio              | X |   |   |
| Paquete de aprovisionamiento       | X | X |   |
| Aplicación de la Microsoft Store          |   | X |   |
| Proveedor de MDM compatible     |   |   | X |

## Más información

- [Entrada de blog: Implementar aplicaciones de la Tienda Windows en Surface Hub con Intune](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## Artículos relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 






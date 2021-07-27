---
title: Instalar aplicaciones en Microsoft Surface Hub
description: Los administradores pueden instalar aplicaciones desde la Microsoft Store o la Tienda Microsoft para Empresas.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: dpandre
manager: laurawi
keywords: instalar aplicaciones, Microsoft Store, Tienda Microsoft para Empresas
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/16/2021
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a8c11406c7786e379999ff32f482815d6b180b24
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676664"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>Instalar aplicaciones en Microsoft Surface Hub

Puedes instalar aplicaciones adicionales en tu Surface Hub para ajustarse a las necesidades de tu equipo u organización. Existen distintos métodos para instalar aplicaciones en función de si estás desarrollando y probando una aplicación o implementando una aplicación publicada. Este tema describe los métodos para instalar aplicaciones para cualquiera de esos escenarios.

## <a name="supported-app-guidelines"></a>Directrices de la aplicación admitidas

- Surface Hub solo puede ejecutar [aplicaciones de la Plataforma universal de Windows (UWP)](/windows/uwp/get-started/universal-application-platform-guide). Las aplicaciones creadas con [la herramienta de empaquetado MSIX](/windows/msix/packaging-tool/tool-overview) no se ejecutarán en Surface Hub.
- Las aplicaciones deben elegirse para la [familia de dispositivos universales](/windows/uwp/get-started/universal-application-platform-guide) o la familia de dispositivos del Equipo de Windows.
- Surface Hub solo admite [aplicaciones con licencia](/microsoft-store/distribute-offline-apps) sin conexión desde [Microsoft Store para Empresas](https://businessstore.microsoft.com/store/private-store).
- De manera predeterminada, deben ser aplicaciones firmadas por la Store para poder instalarse. Durante la fase de desarrollo y prueba, también puedes elegir ejecutar aplicaciones para UWP firmadas por el desarrollador colocando el dispositivo en modo de desarrollador.
- Al enviar una aplicación al Microsoft Store, los desarrolladores deben establecer la disponibilidad de la familia de dispositivos y las opciones de licencias organizativas para asegurarse de que una aplicación estará disponible para ejecutarse en Surface Hub.
- Necesitas credenciales de administrador para instalar aplicaciones en el Surface Hub. Dado que el dispositivo está diseñado para usarse en espacios comunes como salas de reuniones, las personas no pueden acceder a la Microsoft Store para descargar e instalar aplicaciones.

## <a name="deploy-released-apps"></a>Implementar aplicaciones publicadas

Hay varias opciones para la instalación de aplicaciones que se han publicado en la Microsoft Store en función de si quieres evaluarlas en algunos dispositivos o implementarlas ampliamente en tu organización.

Para instalar aplicaciones publicadas:

- Descarga la aplicación con la aplicación de la Microsoft Store, o
- Descarga el paquete de la aplicación de la Tienda Microsoft para Empresas y distribúyelo usando un paquete de aprovisionamiento o un proveedor de MDM compatible.

### <a name="microsoft-store-app"></a>Aplicación de la Microsoft Store

Para evaluar aplicaciones publicadas de la Microsoft Store, usa la aplicación de la Microsoft Store en el Surface Hub para buscar y descargar aplicaciones.

> [!NOTE]
> El uso de la aplicación de la Microsoft Store no es el método recomendado para implementar aplicaciones a escala en tu organización:
>
> - Para descargar aplicaciones, debes iniciar sesión en la aplicación de la Microsoft Store con una cuenta de Microsoft u organizativa. Sin embargo, solo puedes conectar una cuenta a un máximo de 10 dispositivos al mismo tiempo. Si tienes más de 10 Surface Hubs, deberás crear varias cuentas o quitar dispositivos de tu cuenta entre las instalaciones de las aplicaciones.
> - Para instalar aplicaciones, tendrás que iniciar sesión manualmente en la aplicación de la Microsoft Store en cada Surface Hub del que seas propietario.

#### <a name="to-browse-the-microsoft-store-on-surface-hub"></a>Examinar la Microsoft Store en Surface Hub

1. En Surface Hub, inicia **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Vaya a **Surface Hub**  >  **aplicaciones & características**.
4. Selecciona **Abrir tienda** y busca la aplicación que estás buscando.

### <a name="download-app-packages-from-microsoft-store-for-business"></a>Descargar paquetes de la aplicación de la Tienda Microsoft para Empresas

Para descargar el paquete de la aplicación que necesitas para instalar aplicaciones en el Surface Hub, visita la [Tienda Microsoft para Empresas](https://www.microsoft.com/business-store). La Tienda para empresas es el lugar donde puedes buscar, comprar y administrar aplicaciones para los dispositivos Windows 10 de tu organización, incluido el Surface Hub.

> [!NOTE]
> Actualmente, Surface Hub solo es compatible con aplicaciones con licencia sin conexión disponibles a través de la Tienda Microsoft para Empresas. Los desarrolladores de aplicaciones establecen la disponibilidad de la licencia sin conexión cuando envían las aplicaciones.

Busca y compra la aplicación que quieras y, a continuación, descarga:

- El paquete de la aplicación con licencia sin conexión (un .appx o un .appxbundle)
- El archivo de licencia *sin codificar* (si usas paquetes de aprovisionamiento para instalar la aplicación)
- La archivo de licencia *codificado* (si usas MDM para distribuir la aplicación)
- Los archivos de dependencia necesarios

Para obtener más información, consulta [Descargar una aplicación con licencia sin conexión](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### <a name="install-offline-licensed-apps-via-provisioning-package"></a>Instalar aplicaciones con licencia sin conexión a través del paquete de aprovisionamiento

Puedes instalar manualmente las aplicaciones con licencia sin conexión que hayas descargado de la Tienda para empresas en varios Surface Hubs mediante paquetes de aprovisionamiento. Usa Diseñador de imágenes y configuraciones de Windows (ICD) para crear un paquete de aprovisionamiento que contenga el paquete de la aplicación y el archivo de licencia *sin codificar* que descargaste de la Tienda para empresas. Para obtener más información, consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md).

### <a name="supported-mdm-provider"></a>Proveedor de MDM compatible

Para implementar aplicaciones en un gran número de Surface Hubs de tu organización, usa un proveedor de MDM compatible. La siguiente tabla muestra qué proveedores de MDM admiten la implementación de paquetes de aplicaciones con licencia sin conexión.

| Proveedor de MDM                | Compatible con paquetes de aplicaciones con licencia sin conexión |
|-----------------------------|----------------------------------------|
| MDM local con Configuration Manager (a partir de la versión 1602) | Sí |
|
| Proveedor de MDM de terceros    | Comprueba que tu proveedor de MDM admite la implementación de paquetes de aplicaciones con licencia sin conexión. |

> [!NOTE]
> Para implementar aplicaciones sin conexión de forma remota mediante Microsoft Intune, consulte [Manage VPP apps from Microsoft Store para Empresas](/mem/intune/apps/windows-store-for-business). Surface Hub implementación de aplicaciones solo admite aplicaciones sin conexión que están asignadas a un grupo de dispositivos y usan el tipo de licencia Dispositivo.

## <a name="develop-and-test-apps"></a>Desarrollar y probar aplicaciones

En esta sección se proporciona información a los desarrolladores de aplicaciones para probar aplicaciones en Surface Hub.

### <a name="developer-mode"></a>Modo de desarrollador

De manera predeterminada, Surface Hub solo ejecuta aplicaciones para UWP que hayan sido publicadas y firmadas por la Microsoft Store. Las aplicaciones enviadas a la Microsoft Store se someten a pruebas de seguridad y cumplimiento como parte del [proceso de certificación de la aplicación](/windows/uwp/publish/the-app-certification-process) y esto permite proteger tu Surface Hub frente a aplicaciones malintencionadas.

Al habilitar el modo de desarrollador, también puedes instalar aplicaciones para UWP firmadas por el desarrollador.

> [!IMPORTANT]
> Una vez habilitado el modo de desarrollador, deberás restablecer el Surface Hub para deshabilitarlo. Al restablecer el dispositivo se eliminan todas las configuraciones y los archivos de usuario locales y, a continuación, se vuelve a instalar Windows.

#### <a name="to-turn-on-developer-mode"></a>Activar el modo de desarrollador

1. En tu Surface Hub, inicia **Configuración**.
2. Escribe las credenciales de administrador del dispositivo cuando se solicite.
3. Navega hasta **Actualización y seguridad**  > ** Para desarrolladores**.
4. Selecciona **Modo de desarrollador** y acepta la advertencia.

### <a name="visual-studio"></a>VisualStudio

Durante el desarrollo, la forma más sencilla de probar tu aplicación en un Surface Hub es usando Visual Studio. La característica de depuración remota de Visual Studio te ayuda a detectar problemas en tu aplicación antes de su implementación general. Para obtener más información, consulta [Probar aplicaciones de Surface Hub con Visual Studio](/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

#### <a name="create-provisioning-package"></a>Crear paquete de aprovisionamiento

Usa Visual Studio para crear un paquete de la aplicación para tu aplicación para UWP, firmada mediante un certificado de prueba. A continuación, usa Diseñador de imágenes y configuraciones de Windows (ICD) para crear un paquete de aprovisionamiento que contenga el paquete de la aplicación. Para obtener más información, consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md).

## <a name="submit-apps-to-the-microsoft-store"></a>Enviar aplicaciones a la Microsoft Store

Cuando una aplicación está lista para publicarse, los desarrolladores necesitan enviarla y publicarla en la Microsoft Store. Para obtener más información, [consulta Publicar Windows aplicaciones y juegos](/windows/uwp/publish).

Durante el envío de la aplicación, los desarrolladores deben establecer la **disponibilidad de familias de dispositivos** y las opciones de **licencias de organización** para asegurarse de que la aplicación estará disponible para su ejecución en Surface Hub.

### <a name="to-set-device-family-availability"></a>Establecer la disponibilidad de familias de dispositivos

1. En el [centro de desarrollo de Windows](https://developer.microsoft.com/windows), ve a la página de envío de la aplicación.
2. Selecciona **Paquetes**.
3. En **Disponibilidad de familias de dispositivos**, selecciona estas opciones:

    - **Windows 10 Team**
    - **Permitir que Microsoft decida si quiere que la aplicación esté disponible para futuras familias de dispositivos**
  
   ![Imagen que muestra la página de la disponibilidad de familias de dispositivos: parte del proceso de envío de aplicación de la Microsoft Store.](images/device-family.png)  

   Para obtener más información, consulta [Disponibilidad de familias de dispositivos](/windows/uwp/publish/upload-app-packages#device-family-availability).

### <a name="to-set-organizational-licensing"></a>Establecer licencias de organización

1. En el [centro de desarrollo de Windows](https://developer.microsoft.com/windows), ve a la página de envío de la aplicación.

2. Selecciona **Precios y disponibilidad**.

3. En licencias de organización, selecciona **Permitir la compra de licencias en desconexión (sin conexión) para empresas**.

   ![Imagen que muestra la página de licencias de organización: parte del proceso de envío de aplicación de la Microsoft Store.](images/sh-org-licensing.png)

   > [!NOTE]
   > **Hacer que mi aplicación esté disponible para organizaciones mediante la concesión de licencias administradas por Store (en línea) y distribución** está seleccionada de forma predeterminada.

   > [!NOTE]
   > Los desarrolladores también pueden publicar aplicaciones de línea de negocio directamente en las empresas sin necesidad de que estén ampliamente disponibles en la Store. Para obtener más información, consulta [Distribuir aplicaciones de LOB a empresas](/windows/uwp/publish/distribute-lob-apps-to-enterprises).

   Para obtener más información, consulta [Opciones de licencias de organización](/windows/uwp/publish/organizational-licensing).

## <a name="summary"></a>Resumen

Hay varias formas diferentes de instalar aplicaciones en tu Surface Hub según si estás desarrollando aplicaciones, evaluando aplicaciones en un número reducido de dispositivos o implementando aplicaciones de forma general en tu organización. En esta tabla se resumen los métodos admitidos:

| Método de instalación             | Desarrollo de aplicaciones | Evaluación de aplicaciones en <br> algunos dispositivos | Implementación de aplicaciones ampliamente <br> en su organización |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| VisualStudio              | X |   |   |
| Paquete de aprovisionamiento       | X | X |   |
| Aplicación de la Microsoft Store          |   | X |   |
| Proveedor de MDM compatible     |   |   | X |

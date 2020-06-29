---
title: Implementar aplicaciones en Surface Hub 2S con Intune
description: Obtenga información sobre cómo puede implementar aplicaciones en Surface Hub 2S con Intune.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835689"
---
# Implementar aplicaciones en Surface Hub 2S con Intune

Puede instalar aplicaciones adicionales para satisfacer las necesidades de su equipo o de la organización.

## Pautas para desarrolladores

- Surface Hub solo puede ejecutar [aplicaciones de la Plataforma universal de Windows (UWP)](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp). Las aplicaciones creadas con [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) no se ejecutarán en Surface Hub.
- Las aplicaciones deben elegirse para la [familia de dispositivos universales](https://msdn.microsoft.com/library/windows/apps/dn894631) o la familia de dispositivos del Equipo de Windows.
- Surface Hub solo admite [aplicaciones con licencia sin conexión](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) de [Microsoft Store para empresas](https://businessstore.microsoft.com/store).
- De manera predeterminada, deben ser aplicaciones firmadas por la Store para poder instalarse. Durante la fase de desarrollo y prueba, también puedes elegir ejecutar aplicaciones para UWP firmadas por el desarrollador colocando el dispositivo en modo de desarrollador.
- Al desarrollar y enviar aplicaciones a Microsoft Store, establezca disponibilidad de familia de dispositivos y opciones de licencia organizacional para asegurarse de que las aplicaciones estén disponibles para su ejecución en Surface Hub.
- Necesita credenciales de administrador para instalar aplicaciones en Surface Hub. Diseñado para su uso en salas de reuniones y otros espacios compartidos, Surface Hub impide que los usuarios normales tengan acceso a Microsoft Store para descargar e instalar aplicaciones.

## Instrucciones de implementación

Puedes implementar aplicaciones de la plataforma universal de Windows (UWP) en Surface Hub 2S con Intune, lo que facilita la implementación de aplicaciones en dispositivos.

1. Para implementar aplicaciones, habilite MDM para su organización. En el portal de Intune, seleccione **Intune** como su autoridad de MDM (recomendado). <br>

    ![Elegir la autoridad de MDM](images/sh2-set-intune5.png)

2. Habilitar Microsoft Store para empresas en Intune. Abra Intune, seleccione **aplicaciones**  >  **de cliente Microsoft Store para empresas.** <br>

    ![Habilitar tienda para empresas](images/sh2-deploy-apps-sync.png)

3. En Intune, Abra **Microsoft Store para empresas** y seleccione **configuración**  >  **distribuir**  >  **herramientas de administración**. Elija **Microsoft Intune** como la herramienta de administración. <br>

    ![Agregar Intune como herramienta de administración](images/sh2-set-intune8.png)

4. En Microsoft Store para empresas, seleccione **configuración**evaluación de la  >  **Shop**  >  **compra**y, a continuación, seleccione **Mostrar aplicaciones sin conexión**. Las aplicaciones sin conexión hacen referencia a las aplicaciones que se pueden sincronizar a Intune y a implementar de forma centralizada en un dispositivo.
5. Después de habilitar las compras sin conexión, puede adquirir licencias sin conexión para las aplicaciones que puede sincronizar con Intune e implementar como licencias de dispositivos.
6. En aplicaciones cliente de **Intune**  >  **Client apps**  >  ,**Microsoft Store para empresas**, seleccione **sincronizar**.
7. En la página aplicaciones cliente, busque la aplicación en la lista de aplicaciones. Asigne las aplicaciones al grupo o grupos de dispositivos que desee. Seleccione **tareas**  >  **Agregar grupo**. <br>

![* Asignar aplicaciones a grupos *](images/sh2-assign-group.png) <br>

8. En tipo de asignación, elija **obligatorio**. <br>

![* Asignar aplicaciones a grupos *](images/sh2-add-group.png) <br>

9. Para los grupos seleccionados, elija **licencias de dispositivo** y, después, haga clic en **Aceptar** y guarde la asignación. <br>
 
![* Asignar aplicaciones a grupos *](images/sh2-apps-assign.png)

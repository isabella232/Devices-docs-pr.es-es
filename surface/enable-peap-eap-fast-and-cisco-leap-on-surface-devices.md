---
title: Habilitar PEAP, EAP-FAST y Cisco LEAP en dispositivos Surface (Surface)
description: Averigua cómo habilitar la compatibilidad con los protocolos PEAP, EAP-FAST o Cisco LEAP en tu dispositivo Surface.
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: red, inalámbrica, dispositivo, implementar, autenticación, protocolo
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: e887a449fb00b76c14de5b8ede51a1ba91a6b4c4
ms.sourcegitcommit: 6d531906c36da51cb4032a220d70182e686114a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2021
ms.locfileid: "11721250"
---
# <a name="enable-peap-eap-fast-and-cisco-leap-on-surface-devices"></a>Habilitar PEAP, EAP-FAST y Cisco LEAP en dispositivos Surface

Averigua cómo habilitar la compatibilidad con los protocolos PEAP, EAP-FAST o Cisco LEAP en tu dispositivo Surface.

Si usas PEAP, EAP-FAST o Cisco LEAP en tu red de empresa, probablemente ya sabes que estos tres protocolos de autenticación inalámbrica no son compatibles con dispositivos Surface de fábrica. Algunos usuarios pueden descubrir esto cuando intenten conectarse a la red inalámbrica; otros pueden descubrirlo cuando no puedes obtener acceso a recursos de red, como recursos compartidos de archivos y sitios internos. Para obtener más información, consulta [Extensible Authentication Protocol](/windows-server/networking/technologies/extensible-authentication-protocol/network-access) (Protocolo de autenticación extensible).

Para agregar compatibilidad para cada uno de los protocolos, puedes ejecutar un pequeño paquete MSI desde un stick USB o desde un recurso compartido de archivos. Para las organizaciones que desean habilitar la compatibilidad con EAP en sus dispositivos Surface, el formato de paquete MSI admite la implementación con muchas herramientas de administración e implementación, como microsoft Deployment Toolkit (MDT) y Microsoft Endpoint Configuration Manager.

## <a name="download-peap-eap-fast-or-cisco-leap-installation-files"></a><a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>Descargar archivos de instalación de PEAP, EAP-FAST o Cisco LEAP

Puedes descargar los archivos de instalación de MSI para PEAP, EAP-FAST o Cisco LEAP en un único archivo zip desde el Centro de descarga de Microsoft. Para descargar este archivo, ve a la página [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) en el Centro de descarga de Microsoft, haz clic en **Download** (Descargar) y luego selecciona el archivo **Cisco EAP-Supplicant Installer.zip**.

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-mdt"></a>Implementar PEAP, EAP-FAST o Cisco LEAP con MDT

Si ya estás realizando una implementación de Windows en dispositivos Surface en tu organización, es rápido y fácil agregar los archivos de instalación para cada protocolo en el recurso compartido de implementación y configurar la instalación automática durante la implementación. Incluso puedes configurar una secuencia de tareas que actualice los dispositivos Surface implementados anteriormente para proporcionar compatibilidad con estos protocolos mediante el mismo proceso.

Para habilitar la compatibilidad con PEAP, EAP-FAST o Cisco LEAP en dispositivos Surface recientemente implementados, sigue estos pasos:

1. Descarga y extrae los archivos de instalación para cada protocolo en carpetas independientes en una ubicación de fácil acceso.

2. Abre Deployment Workbench de MDT y expande el recurso compartido de implementación en la **Aplicaciones**.

3. Selecciona **Nueva aplicación** desde el panel **Acción**.

4. Elige **Aplicación con archivos de origen** para copiar los archivos MSI en el recurso compartido de implementación.

5. Selecciona la carpeta que creaste en el paso 1 del protocolo deseado.

6. Asigna un nombre a la carpeta en el recurso compartido de implementación donde se almacenarán los archivos de instalación.

7. Especifica la línea de comandos para implementar la aplicación:

    - Para PEAP, usa **EAP-PEAP.msi /qn /norestart**.

    - Para LEAP, usa **EAP-LEAP.msi /qn /norestart**.

    - Para EAP-FAST, usa **FAST.msi EAP/qn /norestart**.

8. Usa las opciones predeterminadas para completar el Asistente para nueva aplicación.

9. Repite los pasos 3 a 8 para cada protocolo deseado.

Una vez que hayas realizado estos pasos para importar los tres paquetes MSI como aplicaciones en MDT, estarán disponibles para la selección en la página Aplicaciones del Asistente para la implementación de Windows. Aunque en algunos escenarios de implementación sencillos puede ser suficiente que los técnicos seleccionen cada paquete en el momento de la implementación, no se recomienda. Este procedimiento introduce la posibilidad de que un técnico intentara aplicar estos paquetes en equipos que no sean dispositivos Surface o que se implemente en un dispositivo Surface sin compatibilidad EAP debido a errores humanos.

Para ocultar estas aplicaciones desde la página Instalar aplicaciones, selecciona la casilla **Ocultar esta aplicación en el Asistente para la implementación ** en las propiedades de cada aplicación. Después de ocultar las aplicaciones, no aparecerán como aplicaciones opcionales durante la implementación. Para implementarlas en la secuencia de tareas de implementación de Surface, deben definirse explícitamente para la instalación a través de un paso independiente en la secuencia de tareas.

Para especificar los protocolos de forma explícita, sigue estos pasos:

1. Abre las propiedades de la secuencia de tareas de implementación de Surface desde Deployment Workbench de MDT.

2. En la pestaña **Secuencia de tareas**, selecciona el paso **Instalar aplicaciones** en **Restaurar estado**. Normalmente se encuentra entre los pasos previos y posteriores a la aplicación de Windows Update.

3. Usa el botón **Agregar** para crear un nuevo paso **Instalar aplicación** desde la categoría **General**.

4. Selecciona **Instalar una sola aplicación** en la pestaña **Propiedades**.

5. Selecciona el protocolo EAP deseado de la lista.

6. Repite los pasos 2 a 5 para cada protocolo deseado.

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-configuration-manager"></a>Implementar PEAP, EAP-FAST o Cisco LEAP con Configuration Manager

Para las organizaciones que administran dispositivos Surface con Configuration Manager, es incluso más fácil implementar la compatibilidad de PEAP, EAP-FAST o Cisco LEAP en dispositivos Surface. Simplemente importa cada archivo MSI como una aplicación desde la biblioteca de software y configura una implementación en tu colección de dispositivos Surface.

Para obtener más información sobre cómo implementar aplicaciones con Configuration Manager, vea [Create and deploy an application with Configuration Manager](/mem/configmgr/apps/get-started/create-and-deploy-an-application.md).

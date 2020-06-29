---
title: Configuración de primera vez para Surface Hub 2S
description: Más información sobre cómo completar la configuración por primera vez para Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836122"
---
# Configuración de primera vez para Surface Hub 2S

La primera vez que inicie Surface Hub 2S, el dispositivo entra automáticamente en modo de configuración para guiarle por la configuración de la cuenta y la configuración relacionada.

## Configuración de la cuenta de Surface Hub 2S

1. **Configure su configuración regional.** Escriba la región, el idioma, la distribución del teclado y la información de la zona horaria. Selecciona **Siguiente**.

   ![* Configura tu configuración regional *](images/sh2-run1.png) <br>
1. **Conéctate a una red inalámbrica.** Elija su red inalámbrica preferida y seleccione **siguiente.**

- Esta opción no se muestra si está conectada usando un cable de Ethernet.
- No puedes conectarte a una red inalámbrica en puntos de acceso público (portales cautivos) que redirijan solicitudes de inicio de sesión al sitio web de un proveedor.

3. **Escribe la información de la cuenta del dispositivo.** Use **dominio\usuario** para entornos locales e híbridos y el **usuario \ @example. com** para entornos en línea. Seleccione **siguiente.**

   ![* Escribe la información de la cuenta del dispositivo *](images/sh2-run2.png) <br>
1. **Escriba información adicional.** Si se le solicita, escriba la dirección del servidor de Exchange y, a continuación, seleccione **siguiente.**

    ![* Escribe más información; por ejemplo, nombre de servidor de Exchange *](images/sh2-run3.png) <br>

1. **Nombre de este dispositivo.** Escriba un nombre para el dispositivo o use el sugerido según el nombre para mostrar y el nombre principal de usuario [UPN] de su cuenta. **Seleccione siguiente**.

- El **nombre descriptivo** está visible en la esquina inferior izquierda de Surface Hub 2s y se muestra al proyectar en el dispositivo.

- El **nombre del dispositivo** identifica el dispositivo cuando se afilia a Active Directory o Azure Active Directory, y al inscribir el dispositivo con Intune.

  ![* Nombre de este dispositivo *](images/sh2-run4.png) <br>
 
## Configurar cuentas de administrador de dispositivos

Solo puedes configurar administradores de dispositivos durante la configuración de primera vez. Para obtener más información, consulte [afiliación del dispositivo Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation).

 En la ventana **administradores de la instalación de este dispositivo** , seleccione una de las siguientes opciones: servicios de dominio de Active Directory, Azure Active Directory o administrador local.

   ![* Administradores de instalación para este dispositivo *](images/sh2-run5.png) <br>

### Active Directory Domain Services

1. Escriba las credenciales de un usuario que tiene permisos para unir el dispositivo a Active Directory.

    ![* Administradores de instalación que usan unirse a un dominio *](images/sh2-run6.png) <br>

2. Seleccione el grupo de seguridad de Active Directory que contiene miembros a los que se permite iniciar sesión en la aplicación configuración de Surface Hub 2S.

    ![* Introduce un grupo de seguridad *](images/sh2-run7.png) <br>
1. Seleccione **Finalizar**. El dispositivo se reiniciará.

### Azure Active Directory

Cuando elijas afiliar su dispositivo con Azure Active Directory, el dispositivo se reiniciará inmediatamente y mostrará la siguiente página. Selecciona **Siguiente**.

![* Si su organización usa Office 365 u otros servicios empresariales de Microsoft, inscribiremos este dispositivo con su organización *](images/sh2-run8.png) <br>

1. Escriba la dirección de correo electrónico o el UPN de una cuenta **con plan 1** o superior y, después, seleccione **siguiente.**

    ![* Escriba una cuenta profesional o educativa *](images/sh2-run9.png) <br>

2. Si se redirige, autentique con la página de inicio de sesión de su organización y proporcione información de inicio de sesión adicional si se le solicita. El dispositivo se reiniciará.

## Cuenta de administrador local

- Escriba un nombre de usuario y una contraseña para el administrador local. El dispositivo se reiniciará.

     ![* Configurar una cuenta de administrador *](images/sh2-run10.png) <br>
 
## Usar paquetes de aprovisionamiento

Si inserta una unidad USB con un paquete de aprovisionamiento en uno de los puertos USB cuando inicia Surface Hub 2S, el dispositivo muestra la siguiente página.

1. Escriba la configuración solicitada y seleccione **configurar**.

    ![* Especificar la configuración regional para el paquete de aprovisionamiento *](images/sh2-run11.png) <br>

    ![* Aprovisionar este dispositivo desde medios extraíbles *](images/sh2-run12.png) <br>
2. Elige el paquete de aprovisionamiento que deseas usar.

   ![* Elige el paquete de aprovisionamiento para usar *](images/sh2-run13.png) <br>

3. Si has creado un archivo CSV de dispositivos múltiples, podrás elegir una configuración de dispositivo. Para obtener más información, consulte [crear paquetes de aprovisionamiento para Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).


    ![* Seleccione una cuenta del dispositivo y un nombre descriptivo en el archivo de configuración *](images/sh2-run14.png) <br>

4. Siga las instrucciones para completar la configuración por primera vez.

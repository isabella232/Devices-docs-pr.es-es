---
title: Configuración por primera vez para Surface Hub 2S
description: Aprende a completar la configuración por primera vez para Surface Hub 2S.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442198"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Configuración por primera vez para Surface Hub 2S

Cuando inicias Por primera vez Surface Hub 2S, el dispositivo entra automáticamente en el modo de configuración por primera vez para guiarte a través de la configuración de la cuenta y la configuración relacionada.

## <a name="configuring-surface-hub-2s-account"></a>Configuración de la cuenta de Surface Hub 2S

1. **Configure la configuración regional.** Escriba la región, el idioma, el diseño del teclado y la información de zona horaria. Selecciona **Siguiente**.

   ![* Configurar la configuración regional *](images/sh2-run1.png)

1. **Conectarse a una red inalámbrica.** Elija la red inalámbrica preferida y seleccione **Siguiente.**

   - Esta opción no se muestra si está conectada mediante un cable Ethernet.

   - No puede conectarse a una red inalámbrica en puntos de acceso (portales cautivos) que redirijan las solicitudes de inicio de sesión al sitio web de un proveedor.

3. **Escribe la información de la cuenta del dispositivo.** Use **dominio\usuario** para entornos locales e híbridos y **usuario\@example.com** entornos en línea. Seleccione **Siguiente.**

   ![* Escriba la información de la cuenta del dispositivo *](images/sh2-run2.png)

1. **Escribe información adicional.** Si se solicita, proporcione la dirección del servidor Exchange y, a continuación, **seleccione Siguiente.**

   ![* Escriba más información; por ejemplo, nombre del servidor Exchange*](images/sh2-run3.png)

1. **Asigne un nombre a este dispositivo.** Escribe un nombre para el dispositivo o usa el sugerido según el nombre para mostrar de tu cuenta y el nombre de principio de usuario [UPN]. **Seleccione Siguiente**.

   - El **nombre descriptivo** está visible en la esquina inferior izquierda de Surface Hub 2S y se muestra al proyectar al dispositivo.

   - El **nombre del dispositivo** identifica el dispositivo cuando está afiliado a Active Directory o Azure Active Directory, y al inscribir el dispositivo con Intune.

   ![* Asigne un nombre a este dispositivo*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>Configuración de cuentas de administrador de dispositivos

Solo puedes configurar administradores de dispositivos durante la configuración por primera vez. Para obtener más información, consulta Afiliación a [dispositivos Surface Hub 2S.](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)

En la **ventana Configurar administradores** de este dispositivo, seleccione una de las siguientes opciones: Servicios de dominio de Active Directory, Azure Active Directory o Administrador local.

![* Configurar administradores para este dispositivo *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. Escriba las credenciales de un usuario que tenga permisos para unirse al dispositivo a Active Directory.

    ![* Configurar administradores mediante la combinación de dominio *](images/sh2-run6.png)

2. Selecciona el grupo de seguridad de Active Directory que contiene miembros que pueden iniciar sesión en la aplicación Configuración de Surface Hub 2S.

   ![* Escriba un grupo de seguridad *](images/sh2-run7.png)

1. Seleccione **Finalizar**. El dispositivo se reiniciará.

### <a name="azure-active-directory"></a>Azure Active Directory

Al elegir asociar el dispositivo con Azure Active Directory, el dispositivo se reiniciará inmediatamente y mostrará la página siguiente.

![* Si su organización usa Office 365 u otros servicios empresariales de Microsoft, inscribiremos este dispositivo con su organización*](images/sh2-run8.png)

1. Selecciona **Siguiente**.

1. Escribe la dirección de correo electrónico o UPN de una cuenta con **el Plan 1** o posterior de Intune y, a continuación, selecciona **Siguiente.**

   ![* Escriba cuenta de trabajo o escuela*](images/sh2-run9.png)

1. Si se redirige, autentique con la página de inicio de sesión de su organización y proporcione información de inicio de sesión adicional si se solicita. El dispositivo se reiniciará.

## <a name="local-administrator-account"></a>Cuenta de administrador local

- Escriba un nombre de usuario y una contraseña para el administrador local. El dispositivo se reiniciará.

  ![* Configurar una cuenta de administrador*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>Uso de paquetes de aprovisionamiento

Si insertas una unidad usb con un paquete de aprovisionamiento en uno de los puertos USB al iniciar Surface Hub 2S, el dispositivo muestra la página siguiente.

1. Escriba la configuración solicitada y seleccione **Configurar**.

   ![* Escriba la configuración regional para el paquete de aprovisionamiento*](images/sh2-run11.png)

   ![* Aprovisionar este dispositivo desde medios extraíbles*](images/sh2-run12.png)

2. Elige el paquete de aprovisionamiento que quieras usar.

   ![* Elija el paquete de aprovisionamiento que se usará*](images/sh2-run13.png)

3. Si creaste un archivo CSV de varios dispositivos, podrás elegir una configuración de dispositivo. Para obtener más información, consulta [Crear paquetes de aprovisionamiento para Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).

   ![* Seleccione una cuenta de dispositivo y un nombre descriptivo del archivo de configuración*](images/sh2-run14.png)

4. Siga las instrucciones para completar el programa de instalación por primera vez.

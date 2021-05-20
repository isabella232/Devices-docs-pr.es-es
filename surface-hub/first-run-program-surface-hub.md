---
title: Programa de primera ejecución (Surface Hub)
description: El término \ 0034;primera ejecución \ 0034;se refiere a la serie de pasos que recorrerás la primera vez que enciendas Surface Hub y significa lo mismo que \ 0034;configuración rápida\ 0034; (OOBE). En esta sección te guiará por el proceso.
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: primera ejecución, Surface Hub, configuración rápida, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: af6f6cc71a94d075341637499fe98f8206157e49
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576580"
---
# <a name="first-run-program-surface-hub"></a>Programa de primera ejecución (Surface Hub)


El término "primera ejecución" se refiere a la serie de pasos que recorrerás la primera vez que enciendas Microsoft Surface Hub y significa lo mismo que "configuración rápida" (OOBE). En esta sección te guiará por el proceso.

En este momento deberías haber recorrido todos los pasos anteriores:

-   [Preparar el entorno para Surface Hub](prepare-your-environment-for-surface-hub.md)
-   [Instalar físicamente el dispositivo Surface Hub](physically-install-your-surface-hub-device.md) y
-   [Hoja de cálculo del programa de instalación](setup-worksheet-surface-hub.md)

Dando por hecho que este sea el caso, la primera ejecución debe ser rápida y sencilla.
El procedimiento normal atraviesa seis pasos:

1.  [Página de bienvenida](#first-page)
2.  [Configuración de tu página](#set-up-for-you)
3.  [Página de la cuenta del dispositivo](#device-account)
4.  [Página Asignar un nombre a este dispositivo](#name-this-device)
5.  [Configurar los administradores para esta página de dispositivo](#setup-admins)
6.  [Actualizar Surface Hub](#update-surface-hub)

Cada una de estas secciones también contiene información acerca de las rutas de acceso que podrías tomar cuando haya algo diferente. Por ejemplo, la mayoría de los Surface Hubs usarán una conexión de red con cable, pero algunos de ellos se configurarán mediante conexión inalámbrica en su lugar. Los detalles se describen cuando sea pertinente.

>[!NOTE]
>Debes tener el teclado independiente que venía con el Surface Hub configurado y listo antes de empezar. Consulta a la Guía de instalación de Surface Hub para obtener más información.

 

## <a name="hi-there-page"></a><a href="" id="first-page"></a>Página de bienvenida


Esta es la primera pantalla que verás al encender el Surface Hub por primera vez. Es donde se escribe la información de localización para el dispositivo.

>[!NOTE]
>Es también donde empieza el proceso opcional de implementación de un paquete de aprovisionamiento. Consulta [Crear paquetes de aprovisionamiento](provisioning-packages-for-certificates-surface-hub.md) si es lo que vas a hacer.

 Selecciona un idioma. Se mostrarán las opciones de configuración inicial.

![Imagen que muestra las opciones de la lista de comprobación de ICD.](images/setuplocale.png)

### <a name="details"></a>Detalles

Si los valores predeterminados que se muestran son correctos, puedes hacer clic en **Siguiente** para continuar. De lo contrario, deberás escribir datos en los cuadros correspondientes.

-   **País o región:** Selecciona el país o la región en el que se usará Surface Hub.
-   **Idioma de la aplicación:** Las aplicaciones y sus características se mostrarán en este idioma y este formato de idioma.
-   **Distribución del teclado:** Selecciona la distribución del teclado para los teclados físicos y en pantalla que se usarán con el dispositivo.
-   **Zona horaria:** selecciona la zona horaria en la que se usará Surface Hub.

### <a name="what-happens"></a>Qué sucede

>[!NOTE]
> Una vez que se especifiquen las opciones de configuración en esta página, no puedes volver a esta pantalla a menos que se restablezca el dispositivo (consulta [Restablecimiento del dispositivo](device-reset-surface-hub.md)). Asegúrate de que las opciones de configuración se han configurado correctamente antes de continuar.

 

Cuando se acepten las opciones de configuración, el dispositivo buscará una conexión de red con cable. Si la conexión es correcta, se mostrará la [Configuración de tu página](#set-up-for-you). Si hay un problema con la conexión por cable, el dispositivo mostrará la [Página de configuración de red](#network-setup).

Si no se encuentra ninguna conexión por cable, el dispositivo intentará establecer una conexión inalámbrica y mostrará la [Página de configuración de red](#network-setup).

## <a name="network-setup-page"></a><a href="" id="network-setup"></a>Página de configuración de red


Si el dispositivo no detecta una conexión por cable que pueda usar para conectarse a una red o a Internet, verás esta página. Aquí, puedes conectarte a una red inalámbrica u omitir la conexión de red.

![Imagen que muestra la página de configuración de red.](images/setupnetworksetup-1.png)

### <a name="details"></a>Detalles

Esta pantalla se muestra solo si el dispositivo no detecta una red por cable. Si aparece esta pantalla, tienes tres opciones:

-   Puedes seleccionar una de las redes inalámbricas que se muestran. Si la red está protegida, se te llevará a una página de inicio de sesión. Consulta [Configuración de red inalámbrica](#wireless) para obtener más información.
-   Haz clic en **Omitir este paso** para omitir la conexión a una red. Se abrirá la [Configuración de tu página](#set-up-for-you).
    >[!NOTE]
    >Si se omite esto, el dispositivo no tendrá una conexión de red y nada que requiera una conexión de red funcionará en el Surface Hub, incluidas las actualizaciones del sistema y la sincronización de correo electrónico y calendario. Puede conectarse a una red inalámbrica más adelante mediante Configuración (consulte [Administración de red inalámbrica](wireless-network-management-for-surface-hub.md)).

     

-   Puedes conectar un cable de red mientras esta pantalla esté visible. El dispositivo lo detectará y agregará **Siguiente** a la pantalla. Haz clic en **Siguiente** para continuar con la conexión por cable.

### <a name="what-happens"></a>Qué sucede

Si el dispositivo tiene una conexión por cable al iniciarse y se puede establecer una conexión de red o a Internet, no se mostrará esta página. Si quieres conectar el dispositivo a una conexión inalámbrica, asegúrate de que no haya ningún cable Ethernet enchufado en la primera ejecución, lo que te llevará a esta pantalla. Independientemente de lo que decidas configurar ahora, puedes [usar Configuración](wireless-network-management-for-surface-hub.md) para configurar conexiones diferentes más adelante.

Si quieres conectarte a una red inalámbrica segura desde esta página, haz clic en la red de tu elección y, a continuación, proporciona la información necesaria (credenciales de cuenta o contraseña) para conectarte. Consulta [Configuración de red inalámbrica](#wireless).

## <a name="wireless-network-setup"></a><a href="" id="wireless"></a>Configuración de red inalámbrica


Esta página se mostrará cuando hayas seleccionado una red inalámbrica segura.

![Imagen que muestra la página de configuración de la red inalámbrica.](images/setupnetworksetup-3.png)

### <a name="details"></a>Detalles

-   **Nombre de usuario:** Escribe el nombre de usuario para la red inalámbrica seleccionada.
-   **Contraseña:** Esta es la contraseña de la red.

### <a name="what-happens"></a>Qué sucede

El dispositivo intentará conectarse a la red especificada. Si se realiza correctamente, se abrirá la [Configuración de tu página](#set-up-for-you).

## <a name="network-proxy-setup"></a><a href="" id="proxy"></a>Configuración de proxy de red


Esta página se mostrará cuando el dispositivo detecte una conexión por cable con conectividad limitada. Tiene tres opciones:

-   Puedes seleccionar una red inalámbrica para usarla en lugar de la conexión por cable limitada.

-   Puedes omitir la conexión a una red seleccionando **Omitir este paso**. Se abrirá la [Configuración de tu página](#set-up-for-you).

    > [!NOTE]
    > Si se omite esto, el dispositivo no tendrá una conexión de red y nada que requiera una conexión de red funcionará en el Surface Hub, incluida, por ejemplo, la sincronización de correo electrónico y calendario. Puede conectarse a una red inalámbrica más adelante mediante Configuración (consulte [Administración de red inalámbrica](wireless-network-management-for-surface-hub.md)).

-   Puedes seleccionar **Introducir opciones de proxy** , lo que te permitirá especificar cómo se usa el proxy de red. Se abrirá la siguiente pantalla.

    ![Imagen que muestra la página del proxy de red.](images/setupnetworksetup-2.png)

    Esta es la pantalla que verás si has hecho clic en **Introducir opciones de proxy** en la pantalla anterior.

    ![Imagen que muestra los detalles de configuración del servidor proxy.](images/setupnetworksetup-4.png)

### <a name="details"></a>Detalles

Para realizar una conexión de red, deberás rellenar un nombre de script o la información acerca del servidor proxy y los puertos.

-   **Script de proxy:** Proporciona la dirección de un script de proxy.
-   **Servidor proxy y puerto:** Puedes proporcionar la dirección del servidor proxy y el puerto.

### <a name="what-happens"></a>Qué sucede

Al hacer clic en **Siguiente**, el dispositivo intentará conectarse al servidor proxy. Si se realiza correctamente, se abrirá la [Configuración de tu página](#set-up-for-you).

Puedes omitir la conexión a una red seleccionando **Omitir este paso**. Se abrirá la [Configuración de tu página](#set-up-for-you).

>[!NOTE]
>Si se omite esto, el dispositivo no tendrá una conexión de red y nada que requiera una conexión de red funcionará en el Surface Hub, incluida, por ejemplo, la sincronización de correo electrónico y calendario. Puede conectarse a una red inalámbrica más adelante mediante Configuración (consulte [Administración de red inalámbrica](wireless-network-management-for-surface-hub.md)).

 

## <a name="set-up-for-you-page"></a><a href="" id="set-up-for-you"></a>Configuración de tu página


Esta pantalla es meramente informativa y muestra la configuración recomendada habilitada de forma predeterminada.

![Imagen que muestra la configuración de tu página.](images/setupsetupforyou.png)

### <a name="details"></a>Detalles

Debes leer esta pantalla y tener en cuenta qué servicios están habilitados de forma predeterminada. Todos ellos pueden cambiarse mediante la aplicación Configuración si es necesario, pero debes tener cuidado con los efectos que conlleva. Consulta [Introducción a Surface Hub](intro-to-surface-hub.md) para conocer los detalles.

Una vez que hayas terminado de revisar la configuración, haz clic en **Siguiente** para continuar.

### <a name="what-happens"></a>Qué sucede

La configuración que se muestra en la página ya se ha realizado y no se puede cambiar hasta después de completarse la primera ejecución.

## <a name="device-account-page"></a><a href="" id="device-account"></a>Página de la cuenta del dispositivo


En esta página, Surface Hub pedirá las credenciales de la cuenta del dispositivo que hayas configurado anteriormente. (Consulta [Crear y probar una cuenta del dispositivo](create-and-test-a-device-account-surface-hub.md)), El Surface Hub intentará detectar varias propiedades de la cuenta y puede solicitar más información en otra página si no lo consigue.

>[!NOTE]
>Esta sección no abarca errores específicos que puedan producirse durante la primera ejecución. Consulta [Solucionar problemas de Surface Hub](troubleshoot-surface-hub.md) para obtener más información acerca de los errores.


![Imagen que muestra la página Introducir información de la cuenta del dispositivo.](images/setupdeviceacct.png)

### <a name="details"></a>Detalles

Usa un **nombre principal de usuario (UPN)** o un **dominio\\nombre de usuario** como el identificador de cuenta en el primer campo de entrada. Usa el formato que coincida con el entorno y escribe la contraseña.


|                      Entorno                      | Formato requerido para la cuenta del dispositivo |
|-------------------------------------------------------|------------------------------------|
|         La cuenta del dispositivo se hospeda solo en línea.         |        nombreusuario@dominio.com         |
|        La cuenta del dispositivo se hospeda de forma local.         |          DOMINIO\nombre de usuario           |
| La cuenta del dispositivo se hospeda en línea y de forma local (híbrida). |          DOMINIO\nombre de usuario           |

Haz clic en **Omitir configuración de una cuenta del dispositivo** para omitir la configuración de una cuenta del dispositivo. Sin embargo, si no configuras una cuenta del dispositivo, el dispositivo no estará completamente integrado en tu infraestructura. Por ejemplo, los usuarios no podrán:

-   Ver un calendario de reuniones en la pantalla de inicio de sesión
-   Iniciar una reunión desde la pantalla de inicio de sesión
-   Enviar pizarras por correo electrónico desde OneNote
-   Usar Skype Empresarial para las reuniones

Si omites la configuración ahora, puedes agregar una cuenta del dispositivo más adelante mediante la aplicación Configuración.

Si haces clic en **Omitir configuración de una cuenta del dispositivo**, el dispositivo mostrará un cuadro de diálogo que muestra lo que sucederá si el dispositivo no tiene una cuenta del dispositivo. Si eliges **Sí, deseo omitir este paso**, se abrirá la [página Asignar un nombre a este dispositivo](#name-this-device).

![Imagen que muestra el mensaje que se muestra para confirmar que quieres omitir la creación de una cuenta de dispositivo.](images/setupskipdeviceacct.png)

### <a name="what-happens"></a>Qué sucede

El dispositivo usará el UPN o el dominio\\nombre de usuario y la contraseña para que la cuenta del dispositivo realice lo siguiente:

-   Comprueba si la cuenta existe en Active Directory (AD) o Azure Active Directory (Azure AD):

    -   Si se ha escrito un UPN: el dispositivo buscará la cuenta en Azure AD.
    -   Si se ha escrito un dominio\\nombre de usuario: el dispositivo buscará la cuenta en AD.
-   Busca el servidor Microsoft Exchange para el buzón de la cuenta.
-   Busca la dirección de Protocolo de inicio de sesión (SIP) para la cuenta.
-   Extrae el nombre para mostrar de la cuenta y los atributos Alias

## <a name="exchange-server-page"></a><a href="" id="exchange-server"></a>Página del servidor Exchange


Esta página solo se mostrará si hay un problema. Por lo general, significa que se ha encontrado la cuenta del dispositivo que proporcionaras en Active Directory (AD) o Azure Active Directory (Azure AD), pero no se ha detectado el servidor Exchange para dicha cuenta.

![Imagen que muestra la página Servidor de Exchange.](images/setupexchangeserver-01.png)

### <a name="details"></a>Detalles

Escribe el nombre del servidor de Exchange donde esta hospedado el buzón de la cuenta del dispositivo.

Haz clic en **Omitir configuración de los servicios de Exchange** para omitir este paso. Si lo haces, los usuarios no podrán:

-   Ver un calendario de reuniones en la pantalla de inicio de sesión.
-   Iniciar una reunión desde la pantalla de inicio de sesión.
-   Enviar pizarras por correo electrónico desde OneNote.

Consulta [Introducción a Surface Hub](intro-to-surface-hub.md) para obtener más información acerca de las dependencias del programa de instalación.

Más adelante puedes habilitar los servicios Exchange para una cuenta del dispositivo mediante la aplicación Configuración.

Si haces clic en **Omitir configuración de los servicios de Exchange**, el dispositivo mostrará un cuadro de diálogo con lo que sucede. Si eliges **Sí, deseo omitir este paso**, no se configurarán los servicios de Exchange.

![Imagen que muestra el mensaje de confirmación que aparece cuando se omite la configuración de los servicios de Exchange.](images/setupexchangeserver-02.png)

### <a name="what-happens"></a>Qué sucede

El Surface Hub intentará validar la cuenta del dispositivo en el servidor de Exchange que especifiques aquí. Si el servidor Exchange se puede alcanzar y validar, la primera ejecución continuará.

Si decides omitir la configuración de los servicios de Exchange, el Surface Hub detendrá la búsqueda del servidor Exchange y no se habilitará ningún servicio de Exchange (correo electrónico y calendario).

## <a name="exchange-policies-page"></a><a href="" id="exchange-policies"></a>Página de directivas de Exchange


Esta página se mostrará cuando:

-   la cuenta del dispositivo esté usando una directiva de Exchange Active Sync (EAS) donde la directiva PasswordEnabled esté establecida en 1.
-   no haya ninguna conexión con Exchange.
-   Exchange devuelva un código de estado que indique un error. (Por ejemplo: la cuenta se ha aprovisionado en demasiados dispositivos).
-   Los protocolos admitidos por Exchange no son compatibles con Surface Hub.
-   Exchange devuelva un XML incorrecto.

![Imagen que muestra la página de directivas de Exchange.](images/setupexchangepolicies.png)

### <a name="details"></a>Detalles

Esta página es meramente informativa, por lo que no se requiere ninguna acción. Sin embargo, tienes dos opciones para continuar: saltar adelante o volver a intentar la validación que causó el error. Antes de decidir qué opción es mejor, lee la siguiente sección: **Qué sucede** . Es posible que puedas solucionar el problema en otro lugar antes de hacer clic en una de las opciones.

-   **Haz clic aquí para continuar usando las directivas no admitidas**: Haz clic aquí para continuar con la primera ejecución. El Surface Hub no podrá usar los servicios Exchange ni sincronizar.
-   **Reintentar**: Vuelve a comprobar la directiva en el servidor de Exchange.

### <a name="what-happens"></a>Qué sucede

El Surface Hub comprueba si la directiva EAS de la cuenta del dispositivo tiene la directiva PasswordEnabled establecida en 0 (false). Si este no es el caso, no se pueden sincronizar el correo electrónico y el calendario, y el Surface Hub no puede usar ningún servicio de Exchange. Puedes usar las herramientas de administración de Exchange desde un equipo para comprobar que la cuenta del dispositivo tiene la directiva PasswordEnabled establecida en 0. Si no es el caso, puedes volver a configurar la cuenta y hacer clic en **Reintentar** aquí.

Si ya has configurado correctamente la directiva, comprueba que el dispositivo esté correctamente conectado a la red o a Internet y que puede alcanzar tu servidor Exchange, porque esta página también se mostrará si el Surface Hub no puede alcanzar el servidor Exchange.

Otro posible motivo para no poder alcanzar Exchange es la autenticación basada en certificados. Puedes terminar en esta página debido a problemas de certificado. Ten en cuenta que si el dispositivo muestra los códigos de error 0x80072F0D o 0X800C0019, se requiere un certificado. Debido a que el aprovisionamiento se realiza en la primera página del proceso de primera ejecución, debes deshabilitar los servicios de Exchange haciendo clic en **Haz clic aquí para continuar usando las directivas no admitidas**y, después, instalar los certificados correctos mediante la aplicación Configuración.

Si decides omitir esta comprobación, el Surface Hub detendrá la búsqueda del servidor Exchange y la validación de directivas EAS, y no se habilitarán los servicios de Exchange. Consulta [Introducción a Surface Hub](intro-to-surface-hub.md) para obtener más información acerca de las dependencias del programa de instalación.

## <a name="name-this-device-page"></a><a href="" id="name-this-device"></a>Página Asignar un nombre a este dispositivo


Esta página te pide que proporciones dos nombres que se usarán para identificar el Surface Hub.

![Imagen que muestra la página Asignar un nombre a este dispositivo.](images/setupnamedevice.png)

### <a name="details"></a>Detalles

Si los valores predeterminados que se muestran son correctos, puedes hacer clic en **Siguiente** para continuar. De lo contrario, escribe datos en uno o ambos cuadros de texto.

-   **Nombre descriptivo:** Es el nombre que los usuarios verán cuando quieran conectarse de forma inalámbrica al Surface Hub.
-   **Nombre del dispositivo:** Se puede establecer en cualquier nombre único, como se describe en la pantalla.

Siempre que ambos nombres estén dentro de los requisitos de longitud y no usen caracteres restringidos, al hacer clic en **Siguiente** , aparecerá la siguiente página, [Configurar administradores para este dispositivo](#setup-admins).

### <a name="what-happens"></a>Qué sucede

El Surface Hub requiere dos nombres para el dispositivo, cuyos valores predeterminados serán:

-   **Nombre descriptivo:** El valor predeterminado es el nombre para mostrar de la cuenta del dispositivo
-   **Nombre del dispositivo:** El valor predeterminado es el alias de la cuenta del dispositivo

Aunque cualquiera de los nombres se puede cambiar más adelante, ten en cuenta que:

-   El nombre descriptivo debe ser reconocible y diferente para que los usuarios puedan distinguir un Surface Hub de otro cuando se intente conectar de forma inalámbrica.
-   Si decides unir el dispositivo a un dominio, el nombre del dispositivo no debe ser el mismo que el de cualquier otro dispositivo en el dominio de Active Directory de la cuenta. El dispositivo no se puede unir al dominio si está usando el mismo nombre que otro dispositivo unido a un dominio.

>[!NOTE]
>Si quieres habilitar [Miracast sobre infraestructura](miracast-over-infrastructure.md), el nombre del dispositivo debe ser reconocible mediante DNS. Puedes lograrlo permitiendo que Surface Hub se registre automáticamente a través de DNS dinámico, o crear manualmente un registro A o AAAA para el nombre de host del dispositivo Surface Hub.

## <a name="set-up-admins-for-this-device-page"></a><a href="" id="setup-admins"></a>Configurar los administradores para esta página de dispositivo


En esta página, podrás seleccionar una de varias opciones sobre cómo quieres configurar las cuentas de administrador para administrar el dispositivo de forma local.

Dado que cada Surface Hub puede usarlo cualquier número de empleados autenticados, la configuración está bloqueada para que no pueden cambiar de una sesión a otra. Solo los administradores pueden configurar las opciones de configuración del dispositivo y, en esta página, elegirás qué tipo de administradores de TI tendrán ese privilegio.

>[!NOTE]
>El propósito de esta página es principalmente determinar quién puede configurar el dispositivo desde su interfaz de usuario; es decir, quién puede realmente visitar un dispositivo, iniciar sesión, abrir la aplicación Configuración y realizar cambios en Configuración.

 

![Imagen que muestra la página Configurar los administradores para este dispositivo](images/setupsetupadmins.png)

### <a name="details"></a>Detalles

Elige una de las tres opciones disponibles:

-   **Usar Microsoft Azure Active Directory**
-   **Usar los Servicios de dominio de Active Directory**
-   **Usar un administrador local**

### <a name="what-happens"></a>Qué sucede

Esto es lo que sucede al seleccionar una opción.

-   **Usar Microsoft Azure Active Directory**

    Al hacer clic en esta opción podrás unir el equipo a Azure AD. Una vez que hagas clic en **Siguiente**, el dispositivo se reiniciará para aplicar algunas opciones de configuración y, a continuación, aparecerá la página [Usar Microsoft Azure Active Directory](#use-microsoft-azure) y se te pedirá que escribas las credenciales necesarias para unirte a Azure AD. Los miembros del rol Administradores globales de Azure de la organización unida podrán usar la Configuración aplicación. Los usuarios específicos que se permitirán dependerán de tu suscripción de Azure AD y de cómo hayas configurado las opciones de configuración de la organización de Azure AD.
    
    > [!IMPORTANT]
    > Para configurar quién puede usar la aplicación Configuración para administrar Surface Hubs, asegúrese de que la inscripción automática de [Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) está habilitada en el inquilino antes de unir el dispositivo a Azure AD. Las directivas de Intune se pueden usar para [configurar administradores](surface-hub-2s-nonglobal-admin.md) que no son globales en Surface Hubs.

-   **Usar Active Directory Domain Services**

    Haz clic en esta opción para unir el equipo a AD. Una vez que hagas clic en **Siguiente**, aparecerá la página [Usar los Servicios de dominio de Active Directory](#use-active-directory) y se te pedirá que escribas las credenciales necesarias para unir el dominio especificado. Después de la unión, puedes seleccionar un grupo de seguridad desde el dominio unido y los usuarios de ese grupo podrán usar la aplicación Configuración.

-   **Usar un administrador local**

    Si eliges esta opción, podrás crear un único administrador local. Este administrador no estará respaldado por ningún servicio de directorio, por lo que te recomendamos que elijas solo este caso si el dispositivo no tiene acceso a Azure AD o AD. Una vez que crees el nombre de usuario y la contraseña del administrador en la página [Usar un administrador local](#use-a-local-admin) , tendrás que volver a escribir las mismas credenciales cada vez que abras la aplicación Configuración.

    Ten en cuenta que un administrador local debe tener acceso físico al Surface Hub para iniciar sesión.

>[!NOTE]
>Después de finalizar este proceso, no podrás cambiar la opción de administración del dispositivo a menos que restablezcas el dispositivo.

 

### <a name="use-microsoft-azure-active-directory"></a><a href="" id="use-microsoft-azure"></a>Usar Microsoft Azure Active Directory

Si has decidido unir el Surface Hub a Azure Active Directory (Azure AD), verás la página **Qué sucede después**. Léela y haz clic en **Siguiente** para ir a la **página Inicia sesión**.

Unirse a Azure AD tiene dos ventajas principales:

1.  Algunos empleados de la organización podrán acceder al dispositivo como administradores y podrán iniciar la aplicación Configuración y configurar el dispositivo. Los usuarios que tengan permisos de administrador se definirán en tu suscripción de Azure AD.

2.  Si tu Azure AD está conectado a una solución de administración de dispositivos móviles (MDM), el dispositivo se inscribirá en esa solución MDM para que puedas aplicar directivas y opciones de configuración.

    ![Imagen que muestra el mensaje que aparece cuando unes Surface Hub a Azure Active Directory.](images/setupjoiningazuread-1.png)

### <a name="details"></a>Detalles

Se requiere la siguiente entrada:

-   **UPN de usuario:** El nombre principal de usuario (UPN) de una cuenta que pueda unirse a Azure AD.
-   **Contraseña:** La contraseña de la cuenta que usas para unirte a Azure AD.

![Imagen que muestra la información de inicio de sesión de la cuenta.](images/setupjoiningazuread-2.png)

Si llegas a este punto y no tienes credenciales válidas para una cuenta de Azure AD, el dispositivo te permitirá continuar mediante la creación de una cuenta de administrador local. Haz clic en **Configurar Windows con una cuenta local en su lugar**.

![Imagen que muestra la página Configurar una cuenta de administrador.](images/setupjoiningazuread-3.png)

### <a name="what-happens"></a>Qué sucede

Una vez que escribas unas credenciales válidas de una cuenta de Azure AD, el dispositivo intentará unirse a la organización de Azure AD asociada. Si se realiza correctamente, el dispositivo aprovisionará empleados en la organización para que sean administradores locales en el dispositivo. Si se configuró el inquilino de Azure AD para ello, el dispositivo también se inscribirá en MDM.

### <a name="use-active-directory-domain-services"></a><a href="" id="use-active-directory"></a>Usar los Servicios de dominio de Active Directory

Esta página te pedirá las credenciales para unirte a un dominio, de modo que el Surface Hub pueda aprovisionar un grupo de seguridad como administradores del dispositivo.

Una vez que el dispositivo esté unido a un dominio, debes especificar un grupo de seguridad desde el dominio al que te uniste. Este grupo de seguridad se aprovisionará como administradores en el Surface Hub, y cualquier persona del grupo de seguridad podrá escribir sus credenciales de dominio para acceder a Configuración.

![Imagen que muestra la página Configurar administradores que usan unión a dominio.](images/setupdomainjoin.png)

### <a name="details"></a>Detalles

Se requiere la siguiente entrada:

-   **Dominio:** Este es el nombre de dominio completo (FQDN) del dominio al que quieres unirte. Se puede usar un grupo de seguridad de este dominio para administrar el dispositivo.
-   **Nombre de usuario:** El nombre de usuario de una cuenta que tenga los permisos necesarios para unirse al dominio especificado. 
-   **Contraseña:** La contraseña de la cuenta.

Tras comprobar las credenciales, se te pedirá que escribas un nombre de grupo de seguridad. Esta entrada es obligatoria.

![Imagen que muestra la página Indicar un grupo de seguridad.](images/setupsecuritygroup-1.png)

### <a name="what-happens"></a>Qué sucede

Mediante el dominio proporcionado, las credenciales de la cuenta de la [página Usar los Servicios de dominio de Active Directory](#use-active-directory) y el nombre del dispositivo de la página [Asignar un nombre a este dispositivo](#name-this-device) , el Surface Hub intentará unirse al dominio. Si la unión se realiza correctamente, la primera ejecución continuará y te preguntará por un grupo de seguridad. Si la unión no se realiza correctamente, la primera ejecución se detendrá y te pedirá que cambies la información proporcionada.

Si la unión se realiza correctamente, verás la página **Especificar un grupo de seguridad** . Al hacer clic en el botón **Seleccionar** en esta página, el dispositivo buscará el grupo de seguridad especificado en el dominio. Si se encuentra, se comprobará el grupo. Haz clic en **Finalizar** para completar el proceso de primera ejecución.

>[!NOTE]
>Si unes el Surface Hub a un dominio, no puedes separar el dispositivo sin restablecerlo.

 

### <a name="use-a-local-admin"></a>Usar un administrador local

Si decides no usar Azure Active Directory (Azure AD) ni Active Directory (AD) para administrar el Surface Hub, debes crear una cuenta de administrador local.

![Imagen que muestra la página Configurar una cuenta de administrador para el administrador local.](images/setuplocaladmin.png)

### <a name="details"></a>Detalles

Se requiere la siguiente entrada:

-   **Nombre de usuario:** Es el nombre de usuario de la cuenta de administrador local que se creará para este Surface Hub.
-   **Contraseña:** Esta es la contraseña de la cuenta del dispositivo.
-   **Volver a escribir la contraseña:** Escribe la contraseña igual que en el cuadro anterior para verificarla.

### <a name="what-happens"></a>Qué sucede

Esta página intentará crear una nueva cuenta de administrador con las credenciales que especifiques aquí. Si se realiza correctamente, la primera ejecución finalizará. De lo contrario, se te pedirán unas credenciales distintas.

## <a name="update-the-surface-hub"></a><a href="" id="update-surface-hub"></a>Actualizar Surface Hub


>[!IMPORTANT]
>Antes de realizar las actualizaciones, asegúrate de leer [Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md) para asegurarte de que tienes una copia de seguridad de la clave.

 

Para obtener las últimas características y correcciones, debes actualizar el Surface Hub en cuanto finalices todos los pasos de primera ejecución anteriores.

1.  Asegúrate de que el dispositivo tiene acceso a los servidores Windows Update. 
2.  Abre Configuración, haz clic en **Actualización y seguridad**, luego en **Windows Update** y, a continuación, haz clic en **Buscar actualizaciones**.
3.  Si hay actualizaciones disponibles, se descargarán. Una vez completada la descarga, haz clic en el botón **Actualizar ahora** para instalar las actualizaciones.
4.  Sigue las instrucciones en pantalla después de que se instalen las actualizaciones. Necesitarás reiniciar el dispositivo.

 

 






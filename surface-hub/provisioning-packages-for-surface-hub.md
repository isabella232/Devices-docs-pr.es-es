---
title: Crear paquetes de aprovisionamiento
description: En Windows10, la configuración que usa el Registro o un proveedor de servicios de configuración (CSP) se puede configurar con paquetes de aprovisionamiento.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: add certificate, agregar certificado, provisioning package, paquete de aprovisionamiento
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/20/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 9f0f63cb44c54b6350bc478e4fc15455ba94e85f
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911825"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>Crear paquetes de aprovisionamiento para Surface Hub

Los paquetes de aprovisionamiento te permiten automatizar la implementación de características clave, lo que ayuda a ofrecer una experiencia coherente en todos los Surface Hubs de tu organización.  Con Windows Configuration Designer (WCD) en un equipo independiente, puede completar las siguientes tareas:

- Inscribirse en Active Directory o Azure Active Directory
- Crear una cuenta de administrador de dispositivos
- Agregar aplicaciones y certificados
- Definir la configuración de proxy
- Agregar un archivo de configuración de Surface Hub
- Configurar [la configuración del proveedor de servicios de configuración (CSP)](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>Introducción

1. En un equipo independiente que ejecute Windows 10, [instale Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) desde el Microsoft Store.
1. Selecciona [**Aprovisionar Surface Hub dispositivos para**](#use-surface-hub-provisioning-wizard) configurar opciones comunes mediante un asistente. O bien, [seleccione Aprovisionamiento avanzado](#use-advanced-provisioning) para ver y configurar todas las opciones posibles.
1. Cree el paquete de aprovisionamiento y guárdelo en una unidad USB.
1. Implemente el paquete en su Surface Hub durante la instalación de la primera ejecución o a través de la Configuración aplicación. Para obtener más información, vea [Create a provisioning package for Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package).

## <a name="use-surface-hub-provisioning-wizard"></a>Usar Surface Hub de aprovisionamiento

1. Abra Windows Configuration Designer y seleccione **Aprovisionar Surface Hub dispositivos**.<br>
    ![Use el asistente Surface Hub de aprovisionamiento.](images/sh-prov-start.png)
    
2. Asigne un nombre al proyecto y seleccione **Siguiente**.

### <a name="add-certificates"></a>Agregar certificados

> [!div class="mx-imgBorder"]
> ![agregar un certificado.](images/sh-prov-cert.png)

Para aprovisionar el dispositivo con un certificado, **seleccione Agregar un certificado**. Escriba un nombre para el certificado y, a continuación, busque para seleccionar el certificado que se va a usar.  Para obtener opciones avanzadas de aprovisionamiento, consulte la sección siguiente [Agregar un certificado al paquete](#add-a-certificate-to-your-package).

### <a name="configure-proxy-settings"></a>Definir la configuración de proxy

> [!div class="mx-imgBorder"]
> ![configurar la configuración de proxy.](images/sh-prov-proxy.png)

1. Alterna **Sí** o **No** para la configuración de proxy. De forma predeterminada, Surface Hub automáticamente detecta la configuración de proxy. Sin embargo, si anteriormente tu infraestructura requería el uso de un servidor proxy y ahora ha cambiado y ya no lo requiere, puedes usar un paquete de aprovisionamiento para revertir los dispositivos Surface Hub a la configuración predeterminada seleccionando **Sí** y **Detectar la configuración automáticamente**.
2. Si alterna **Sí**, puede seleccionar para detectar automáticamente la configuración de proxy o configurar manualmente la configuración especificando una de las siguientes opciones:

    - Dirección URL de un script de instalación.
    - Una dirección de servidor proxy estático e información de puerto.

3. Si desea usar un script de instalación o un servidor proxy, desactive **Detectar automáticamente la configuración**. Puede usar un script de instalación *o un* servidor proxy, no ambos.
4. Escriba excepciones (direcciones a las Surface Hub deben conectarse directamente sin usar el servidor proxy). **Ejemplo:** *.office365.com
5. Identificar si se va a usar el servidor proxy para las direcciones locales.

### <a name="set-up-device-admins"></a>Configurar administradores de dispositivos

 > [!div class="mx-imgBorder"]
 > ![Únase a Active Directory, Azure AD o cree una cuenta de administrador local.](images/sh2-wcd.png)

Puedes inscribir el dispositivo en Active Directory y especificar un grupo de seguridad para que use la aplicación Configuración, inscribirlo en Azure Active Directory para permitir que los administradores globales usen la aplicación Configuración o crear una cuenta de administrador local en el dispositivo.

1. Para inscribir el dispositivo en Active Directory, escribe las credenciales de una cuenta de usuario con privilegios mínimos para unir el equipo al dominio y especifica que el grupo de seguridad tenga credenciales de administrador en Surface Hub. Si aplica el paquete a un Surface Hub que se ha restablecido, puede usar la misma cuenta de dominio siempre que sea la misma cuenta la que configure el Surface Hub inicialmente. De lo contrario, se tiene que usar una cuenta de dominio diferente en el paquete de aprovisionamiento.
2. Antes de usar Windows Configuration Designer para configurar la inscripción masiva de Azure AD, [planee la](/azure/active-directory/devices/azureadjoin-plan)implementación de la combinación de Azure AD . La opción **Número máximo de dispositivos por usuario** del inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente.
3. Para inscribir el dispositivo en Azure AD, selecciona esa opción y escribe un nombre descriptivo para el token masivo que obtendrás mediante el asistente. Establece una fecha de expiración del token (el máximo es de 30 días a partir de la fecha de obtención del token). Seleccione **Obtener token masivo**. En la ventana **Vamos a iniciar sesión**, escribe una cuenta que tenga permisos para unir un dispositivo a AzureAD y luego la contraseña. Seleccione **Aceptar** para conceder a Windows Configuration Designer los permisos necesarios.
4. Para crear una cuenta de administrador local, selecciona esa opción y escribe un nombre de usuario y una contraseña.

> [!IMPORTANT]
> Si creas una cuenta local en el paquete de aprovisionamiento, debes cambiar la contraseña mediante la aplicación **Configuración** cada 42 días. Si la contraseña no se cambia en ese período, es posible que la cuenta se bloquee y no se pueda iniciar sesión.

### <a name="enroll-in-third-party-mdm-provider"></a>Inscribirse en un proveedor MDM de terceros

> [!div class="mx-imgBorder"]
> ![Inscríbase en la administración de dispositivos móviles de terceros.](images/sh-prov-mdm.png)

Si usas un proveedor de administración de dispositivos móviles (MDM) de terceros, puedes usar esta sección para inscribir Surface Hub. Para inscribirse en Intune, configure primero la combinación de Azure AD, tal como se describe en la sección anterior, y siga las instrucciones de la siguiente documentación de Intune: Configurar la inscripción automática para [dispositivos Windows 10.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

1. Alterna **Sí** o **No para** la inscripción en MDM de terceros.
2. Si alterna **Sí**, proporcione una cuenta de servicio y una contraseña o huella digital de certificado que esté autorizada para inscribir el dispositivo y especificar el tipo de autenticación.
3. Si el proveedor mdm lo requiere, escribe las direcciones URL del servicio de detección, el servicio de inscripción y el servicio de directivas.

 Para obtener más información, [consulta Administrar Surface Hub con un proveedor mdm.](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>Agregar aplicaciones

> [!div class="mx-imgBorder"]
> ![agregar una aplicación.](images/sh-prov-apps.png)

Puedes instalar varias aplicaciones para la Plataforma universal de Windows (UWP) en un paquete de aprovisionamiento. Para obtener más información, consulta [Aprovisionar equipos con aplicaciones.](/windows/configuration/provisioning-packages/provision-pcs-with-apps)

> [!NOTE]
> Aunque Windows de configuración te permite agregar una aplicación clásica de Win32 a un paquete de aprovisionamiento, Surface Hub solo acepta aplicaciones para UWP. Si incluyes una aplicación Win32 clásica, el aprovisionamiento fallará.

### <a name="add-a-configuration-file"></a>Agregar un archivo de configuración

Además de este paquete de aprovisionamiento, puedes usar un archivo de configuración Surface Hub para facilitar aún más la configuración de los dispositivos. Un archivo de configuración de Surface Hub contiene una lista de cuentas de dispositivo para conectarse a Exchange, Microsoft Teams o Skype Empresarial, así como "nombres descriptivos" para la proyección inalámbrica.

**Para crear un archivo Surface Hub de configuración:**

1. Abra Microsoft Excel (u otro editor de .csv), cree un archivo .csv denominado _SurfaceHubConfiguration.csv_.

2. Escribe una lista de cuentas de dispositivo y nombres descriptivos en este formato:

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > El archivo de configuración no debe contener encabezados de columna. Cuando se incluye en un paquete de aprovisionamiento aplicado a Surface Hub, puedes seleccionar la cuenta y el nombre descriptivo del dispositivo desde el archivo. Para crear el archivo .csv, use un formato de dirección UPN (rainier@contoso.com) o un formato de nombre de inicio de sesión de nivel inferior (contoso\rainier).

    rainier@contoso.com,password,Rainier Surface Hub

3. Guarde el archivo en la carpeta del proyecto y cópielo en la clave USB con el paquete de aprovisionamiento.

> [!NOTE]
> El archivo de configuración solo se puede aplicar durante la instalación de la primera ejecución.

### <a name="password-protect-provisioning-package"></a>Paquete de aprovisionamiento de protección de contraseñas

Si eliges usar una contraseña, deberás escribirla cada vez que apliques el paquete de aprovisionamiento a un dispositivo.

### <a name="complete-provisioning-wizard"></a>Asistente para aprovisionamiento completo

Si solo necesita configurar opciones comunes, seleccione **Finalizar**crear y  >  **** vaya a la sección Compilar [el paquete](#build-your-package). O bien, siga configurando la configuración cambiando al aprovisionamiento avanzado.

## <a name="use-advanced-provisioning"></a>Usar aprovisionamiento avanzado

> [!TIP]
> Usa el asistente para crear un paquete con la configuración común y después usa el editor avanzado para agregar otras configuraciones.<br><br> ![Cambie al editor avanzado.](images/icd-simple-edit.png)

1. Si continúa en la sección anterior, seleccione **Cambiar al editor** avanzado de lo **contrario, abra Windows Diseñador** de configuraciones y seleccione **Aprovisionamiento avanzado**.

   ![Usar el aprovisionamiento avanzado.](images/sh-prov-adv.png)

2. Asigne un nombre al proyecto y seleccione **Siguiente**.

3. Seleccione **Común para Windows 10 Team**, seleccione **Siguiente**y, a continuación, seleccione **Finalizar**.

   ![Nuevo proyecto WCD.](images/icd-new-project.png)

4. En el proyecto, en **Personalizaciones disponibles,** seleccione **Configuración común del equipo**.

   :::image type="content" alt-text="Configuración común de WCD." source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>Agregar un certificado al paquete

Puedes usar paquetes de aprovisionamiento para instalar certificados que permitirán que el dispositivo se autentique en MicrosoftExchange.

> [!NOTE]
> Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén de dispositivo (máquina local), pero no en el almacén del usuario. Si su organización requiere que los certificados se instalen en el almacén de usuarios, use la aplicación Central **Configuración:** **Actualizar**& certificados de seguridad  >  ****  >  **importar certificado**.
Como alternativa, puedes usar directivas  [**MDM**](manage-settings-with-mdm-for-surface-hub.md) para implementar certificados en el almacén de dispositivos o en el almacén de usuarios.

> [!TIP]
> La **sección ClientCertificates** es para los archivos .pfx con una clave privada; los archivos .cer para las CA raíz deben colocarse en la sección **RootCertificates** y para las CA intermedias en la **sección CACertificates.**

1. En **Windows Configuration Designer**  >  **Personalizaciones** disponibles, vaya a **Configuración**de tiempo de ejecución  >  **Certificados**  >  **ClientCertificates**.
2. Escriba una etiqueta para **CertificateName** y, a continuación, **seleccione Agregar**.
3. Escribe el valor **CertificatePassword**.
4. Para el valor **CertificatePath**, examina y selecciona el certificado.
5. Establece el elemento **ExportCertificate** en **False**.
6. Para **KeyLocation**, selecciona **Software solo**.

### <a name="add-a-uwp-app-to-your-package"></a>Agregar una aplicación para UWP al paquete

Para agregar una aplicación para UWP a un paquete de aprovisionamiento, necesitarás el paquete de la aplicación (archivos .appx o .appxbundle) y los archivos de dependencia. Si adquiriste la aplicación en la Microsoft Store para Empresas, también necesitarás la licencia de la aplicación *sin codificar*. Consulta [Distribuir aplicaciones sin conexión](/microsoft-store/distribute-offline-apps) para conocer cómo descargar estos elementos de la Microsoft Store para Empresas.

**Para agregar una aplicación para UWP:**

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextApp**.

2. Escriba un **PackageFamilyName** para la aplicación y, a continuación, **seleccione Agregar**. Por motivos de coherencia, usa el nombre de familia de paquete de la aplicación. Si adquiriste la aplicación en la Microsoft Store para Empresas, puedes encontrar el nombre de familia de paquete en la licencia de la aplicación. Abra el archivo de licencia con un editor de texto y use el valor entre las etiquetas PFM.

3. Para **ApplicationFile,** seleccione **Examinar** para buscar y seleccionar la aplicación de destino ( .appx o .appxbundle).

4. Para **DependencyAppxFiles,** seleccione **Examinar** para buscar y agregar cualquier dependencia para la aplicación. Para Surface Hub, solo necesitas versiones x64 de estas dependencias.

Si adquiriste la aplicación a Microsoft Store para Empresas, deberás agregar la licencia de la aplicación al paquete de aprovisionamiento.

**Para agregar una licencia de aplicación:**

1. Haz una copia de la licencia de la aplicación y cámbiale el nombre para usar una extensión **.ms-windows-store-license**. Por ejemplo, cambie el nombre de "example.xml" a "example.ms-windows-store-license".

2. En Windows Configuration Designer, ve a **Available customizations**  >  **Runtime settings**  >  **UniversalAppInstall**  >  **DeviceContextAppLicense**.

3. Escriba un **LicenseProductId** y, a continuación, **seleccione Agregar**. Por motivos de coherencia, usa el identificador de licencia de aplicación de la licencia de la aplicación. Abre el archivo de licencia con un editor de texto. A continuación, en **la etiqueta License,** use el valor del **atributo LicenseID.**

4. Selecciona el nuevo nodo **LicenseProductId**. Para **LicenseInstall,** seleccione **Examinar** para buscar y seleccionar el archivo de licencia cuyo nombre ha cambiado (example.ms-windows-store-license).

### <a name="add-a-policy-to-your-package"></a>Agregar una directiva al paquete

Surface Hub admite un subconjunto de directivas incluidas en el [Proveedor de servicios de configuración de directivas](/windows/client-management/mdm/policy-configuration-service-provider). Algunas de estas directivas se pueden configurar con Windows de configuración.

 **Para agregar [directivas csp:](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)**

1. Ve a **Personalizaciones disponibles Configuración de**  >  **tiempo de ejecución**  >  **Directivas**.
2. Seleccione el componente que desea administrar y configurar la configuración de directiva según corresponda. Por ejemplo, para impedir que los empleados utilicen la exploración del sitio web de InPrivate en Surface Hub, seleccione **AllowInPrivate** y, a continuación, **seleccione Deshabilitar**.  

   :::image type="content" alt-text="Configurar la configuración de directiva." source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>Agregar valores de configuración de Surface Hub al paquete

Puedes agregar valores de configuración del [Proveedor de servicios de configuración de SurfaceHub](/windows/client-management/mdm/surfacehub-csp) al paquete de aprovisionamiento.

1. Vaya a **Personalizaciones disponibles**  >  **Common Team Edition Configuración**.
1. Seleccione el componente que desea administrar y configurar la configuración de directiva según corresponda.
1. Cuando haya terminado de configurar el paquete de aprovisionamiento, seleccione **Guardar**  >  **archivo**.
1. Lea la advertencia de que los archivos del proyecto pueden contener información confidencial y seleccione **Aceptar**

### <a name="build-your-package"></a>Crear el paquete

Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.  Almacene los archivos del proyecto en una ubicación segura o elimine si ya no es necesario.

1. Abra **Windows paquete de aprovisionamiento de exportación del Diseñador**de  >  ****  >  **configuraciones**.

2. Cambiar **propietario a** administrador de **TI.**  

3. Establece un valor para **Versión del paquete** y luego selecciona **Siguiente**.

   > [!TIP]
   > Al establecer el propietario en Administrador de TI, se asegura de que la configuración del paquete mantenga las "propiedades de prioridad" adecuadas y permanezca en vigor en Surface Hub si otros paquetes de aprovisionamiento se aplican posteriormente desde otros orígenes.

   > [!TIP]
   > Puede modificar los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.

4. Opcional: puede elegir cifrar el paquete y habilitar la firma del paquete:

    1. Seleccione **Cifrar paquete y,** a continuación, escriba una contraseña.
    1. Seleccione **Firmar paquete**  >  **Examinar** y elija el certificado según corresponda.

    > [!IMPORTANT]
    > Se recomienda incluir un certificado de aprovisionamiento de confianza en el paquete de aprovisionamiento. Cuando el paquete se aplica a un dispositivo, el certificado se agrega al almacén del sistema, lo que permite que los paquetes posteriores se apliquen de forma silenciosa.

5. Seleccione **Siguiente** para especificar la ubicación de salida. De forma predeterminada, el Diseñador de configuraciones de Windows usa la carpeta de proyecto como la ubicación de salida. O seleccione **Examinar para** cambiar la ubicación de salida predeterminada. Selecciona **Siguiente**.

6. Seleccione **Compilar** para empezar a compilar el paquete. La información del proyecto se muestra en la página de compilación.

7. Si se produce un error en la compilación, aparecerá un mensaje de error con un vínculo a la carpeta del proyecto. Revise los registros para diagnosticar el error y vuelva a compilar el paquete.

8. Si la compilación se realiza correctamente, se muestra el nombre del paquete de aprovisionamiento, el directorio de salida y el directorio del proyecto. Seleccione **Finalizar** para cerrar el asistente y volver a la página Personalizaciones.

9. Seleccione  **la ubicación de**  salida para ir a la ubicación del paquete. Copia el archivo .ppkg a una unidad flash USB.

## <a name="apply-a-provisioning-package-to-surface-hub"></a>Aplicar un paquete de aprovisionamiento a un dispositivo Surface Hub

Hay dos formas de implementar paquetes de aprovisionamiento en un Surface Hub:

- [Ejecute el programa de instalación en primer lugar.](#apply-a-provisioning-package-during-first-run) Puedes aplicar un paquete de aprovisionamiento para personalizar varias opciones, incluidas la configuración Wi-Fi, la configuración de proxy, los detalles de la cuenta del dispositivo, la unión a Azure AD y la configuración relacionada.  
- [Configuración aplicación.](#apply-a-provisioning-package-using-settings-app) Después de ejecutar el programa de instalación por primera vez, puedes aplicar un paquete de aprovisionamiento a través Configuración aplicación. 

### <a name="apply-a-provisioning-package-during-first-run"></a>Aplicar un paquete de aprovisionamiento durante la primera ejecución

1. Cuando se activa el Surface Hub por primera vez, el programa de primera ejecución muestra [**la página Hi there**](first-run-program-surface-hub.md). Asegúrate de que las opciones de configuración se hayan configurado correctamente antes de continuar.

2. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub. Si el paquete está en el directorio raíz de la unidad, el programa de primera ejecución lo reconocerá y preguntará si quieres configurar el dispositivo. Selecciona **Configurar**.

3. La pantalla siguiente te pide que selecciones un origen de aprovisionamiento. Selecciona **Medios extraíbles** y pulsa **Siguiente**.

4. Selecciona el paquete de aprovisionamiento (*.ppkg) que quieras aplicar y pulsa **Siguiente**. Ten en cuenta que solo puedes instalar un paquete durante la primera ejecución.

5. El programa de primera ejecución mostrará un resumen de los cambios que va a aplicar el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.

6. Si un archivo de configuración se incluye en el directorio raíz de la unidad flash USB, verás **Seleccionar una configuración**. Se mostrará la primera cuenta de dispositivo en el archivo de configuración con un resumen de la información de la cuenta que se aplicará a Surface Hub.

7. En **Seleccionar una configuración,** seleccione el nombre del dispositivo que desea aplicar y, a continuación, **seleccione Siguiente**.

La configuración del paquete de aprovisionamiento se aplicará al dispositivo y se completará la configuración rápida. Una vez reiniciado el dispositivo, puedes quitar la unidad flash USB.

### <a name="apply-a-provisioning-package-using-settings-app"></a>Aplicar un paquete de aprovisionamiento mediante Configuración aplicación

1. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub.
2. Desde Surface Hub, inicie **Configuración** y escriba las credenciales de administrador cuando se le pida.
3. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento,** **seleccione Agregar o quitar un paquete de aprovisionamiento**Agregar un  >  **paquete**.
4. Elige el paquete de aprovisionamiento y selecciona **Agregar**.  Si se le pide, vuelva a escribir sus credenciales de administrador.
5. Verá un resumen de los cambios que se aplicarán. Selecciona **Sí, agrégalo**.

## <a name="learn-more"></a>Obtén más información

- [Descargar Windows de configuración](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [Crear un paquete de aprovisionamiento para Windows10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md)

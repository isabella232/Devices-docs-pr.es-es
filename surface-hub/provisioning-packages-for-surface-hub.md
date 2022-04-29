---
title: Crear paquetes de aprovisionamiento
description: Para Windows 10 o Windows 11, los valores que usan el Registro o un proveedor de servicios de configuración (CSP) se pueden configurar mediante paquetes de aprovisionamiento.
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
ms.openlocfilehash: 1f1e084b8be0ab44c853fe003236ba7f25b4ff4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497643"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>Crear paquetes de aprovisionamiento para Surface Hub

Los paquetes de aprovisionamiento te permiten automatizar la implementación de características clave, lo que ayuda a ofrecer una experiencia coherente en todos los Surface Hubs de tu organización.  Con Windows Diseñador de configuración (WCD) en un equipo independiente, puede completar las siguientes tareas:

- Inscribirse en Active Directory o Azure Active Directory
- Creación de una cuenta de administrador de dispositivos
- Agregar aplicaciones y certificados
- Definir la configuración de proxy
- Agregar un archivo de configuración de Surface Hub
- Configuración [de los valores del proveedor de servicios de configuración (CSP)](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>Información general

1. En un equipo independiente que ejecute Windows 10 o Windows 11, instale [Windows Diseñador de configuración](https://www.microsoft.com/store/apps/9nblggh4tx22) desde el Microsoft Store.
1. Seleccione [**Aprovisionar Surface Hub dispositivos**](#use-surface-hub-provisioning-wizard) para configurar valores comunes mediante un asistente. O bien, seleccione [Aprovisionamiento avanzado](#use-advanced-provisioning) para ver y configurar todas las opciones posibles.
1. Cree el paquete de aprovisionamiento y guárdelo en una unidad USB.
1. Implemente el paquete en el Surface Hub durante la instalación de la primera ejecución o a través de la aplicación de Configuración. Para más información, consulte [Creación de un paquete de aprovisionamiento](/windows/configuration/provisioning-packages/provisioning-create-package).

## <a name="use-surface-hub-provisioning-wizard"></a>Uso del asistente para el aprovisionamiento de Surface Hub

1. Abra Windows Diseñador de configuración y seleccione **Aprovisionar dispositivos Surface Hub**.<br>
    ![Use el asistente de aprovisionamiento de Surface Hub.](images/sh-prov-start.png)
    
2. Asigne un nombre al proyecto y seleccione **Siguiente**.

### <a name="add-certificates"></a>Agregar certificados

> [!div class="mx-imgBorder"]
> ![agregar un certificado.](images/sh-prov-cert.png)

Para aprovisionar el dispositivo con un certificado, seleccione **Agregar un certificado**. Escriba un nombre para el certificado y, a continuación, busque para seleccionar el certificado que se va a usar.  Para obtener opciones de aprovisionamiento avanzadas, consulte la sección siguiente [Agregar un certificado al paquete](#add-a-certificate-to-your-package).

### <a name="configure-proxy-settings"></a>Definir la configuración de proxy

> [!div class="mx-imgBorder"]
> ![configurar los valores de proxy.](images/sh-prov-proxy.png)

1. Alterna **Sí** o **No** para la configuración de proxy. De forma predeterminada, Surface Hub detecta automáticamente la configuración del proxy. Sin embargo, si anteriormente tu infraestructura requería el uso de un servidor proxy y ahora ha cambiado y ya no lo requiere, puedes usar un paquete de aprovisionamiento para revertir los dispositivos Surface Hub a la configuración predeterminada seleccionando **Sí** y **Detectar la configuración automáticamente**.
2. Si alterna **Sí**, puede seleccionar para detectar automáticamente la configuración de proxy o configurar manualmente la configuración escribiendo una de las siguientes opciones:

    - Dirección URL de un script de instalación.
    - Dirección del servidor proxy estático e información de puerto.

3. Si tiene previsto usar un script de instalación o un servidor proxy, desactive **Detectar automáticamente la configuración**. Puede usar un script de instalación *o* un servidor proxy, no ambos.
4. Escriba excepciones (direcciones a las que Surface Hub debe conectarse directamente sin usar el servidor proxy). **Ejemplo:** *.office365.com
5. Identifique si se va a usar el servidor proxy para las direcciones locales.

### <a name="set-up-device-admins"></a>Configuración de administradores de dispositivos

 > [!div class="mx-imgBorder"]
 > ![Únase a Active Directory, Azure AD o cree una cuenta de administrador local.](images/sh2-wcd.png)

Puedes inscribir el dispositivo en Active Directory y especificar un grupo de seguridad para que use la aplicación Configuración, inscribirlo en Azure Active Directory para permitir que los administradores globales usen la aplicación Configuración o crear una cuenta de administrador local en el dispositivo.

1. Para inscribir el dispositivo en Active Directory, escribe las credenciales de una cuenta de usuario con privilegios mínimos para unir el equipo al dominio y especifica que el grupo de seguridad tenga credenciales de administrador en Surface Hub. Si aplica el paquete a un Surface Hub que se restableció, puede usar la misma cuenta de dominio siempre que sea la misma cuenta que configuró la Surface Hub inicialmente. De lo contrario, se tiene que usar una cuenta de dominio diferente en el paquete de aprovisionamiento.
2. Antes de usar Windows Diseñador de configuración para configurar la inscripción masiva de Azure AD, [planee la implementación de la combinación de Azure AD](/azure/active-directory/devices/azureadjoin-plan). La opción **Número máximo de dispositivos por usuario** del inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente.
3. Para inscribir el dispositivo en Azure AD, selecciona esa opción y escribe un nombre descriptivo para el token masivo que obtendrás mediante el asistente. Establece una fecha de expiración del token (el máximo es de 30 días a partir de la fecha de obtención del token). Seleccione **Obtener token masivo**. En la ventana **Vamos a iniciar sesión**, escribe una cuenta que tenga permisos para unir un dispositivo a AzureAD y luego la contraseña. Seleccione **Aceptar** para conceder a Windows Diseñador de configuración los permisos necesarios.
4. Para crear una cuenta de administrador local, selecciona esa opción y escribe un nombre de usuario y una contraseña.

> [!IMPORTANT]
> Si creas una cuenta local en el paquete de aprovisionamiento, debes cambiar la contraseña mediante la aplicación **Configuración** cada 42 días. Si la contraseña no se cambia en ese período, es posible que la cuenta se bloquee y no se pueda iniciar sesión.

### <a name="enroll-in-third-party-mdm-provider"></a>Inscripción en un proveedor de MDM de terceros

> [!div class="mx-imgBorder"]
> ![Inscríbase en la administración de dispositivos móviles de terceros.](images/sh-prov-mdm.png)

Si usa un proveedor de administración de dispositivos móviles (MDM) de terceros, puede usar esta sección para inscribir Surface Hub. Para inscribirse en Intune, primero configure Azure AD unirse, como se describe en la sección anterior, y siga las instrucciones de la siguiente documentación de Intune: [Inicio rápido: Configuración de la inscripción automática para dispositivos Windows 10/11](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

1. Alterne **Sí** o **No** para la inscripción en MDM de terceros.
2. Si alterna **Sí**, proporcione una cuenta de servicio y una contraseña o huella digital de certificado que esté autorizada para inscribir el dispositivo y especificar el tipo de autenticación.
3. Si lo requiere el proveedor de MDM, escriba las direcciones URL del servicio de detección, el servicio de inscripción y el servicio de directivas.

 Para más información, consulte [Administración de Surface Hub con un proveedor de MDM.](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>Agregar aplicaciones

> [!div class="mx-imgBorder"]
> ![agregar una aplicación.](images/sh-prov-apps.png)

Puedes instalar varias aplicaciones para la Plataforma universal de Windows (UWP) en un paquete de aprovisionamiento. Para más información, consulte [Aprovisionamiento de equipos con aplicaciones](/windows/configuration/provisioning-packages/provision-pcs-with-apps).

> [!NOTE]
> Aunque Windows Diseñador de configuración te permite agregar una aplicación Win32 clásica a un paquete de aprovisionamiento, Surface Hub solo acepta aplicaciones para UWP. Si incluyes una aplicación Win32 clásica, el aprovisionamiento fallará.

### <a name="add-a-configuration-file"></a>Adición de un archivo de configuración

Además de este paquete de aprovisionamiento, puede usar un archivo de configuración de Surface Hub para facilitar aún más la configuración de los dispositivos. Un archivo de configuración de Surface Hub contiene una lista de cuentas de dispositivo para conectarse a Exchange, Microsoft Teams o Skype Empresarial, así como "nombres descriptivos" para la proyección inalámbrica.

**Para crear un archivo de configuración de Surface Hub:**

1. Abra Microsoft Excel (u otro editor de .csv), cree un archivo .csv denominado _SurfaceHubConfiguration.csv_.

2. Escriba una lista de cuentas de dispositivo y nombres descriptivos en este formato:

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > El archivo de configuración no debe contener encabezados de columna. Cuando se incluye en un paquete de aprovisionamiento aplicado a Surface Hub, puede seleccionar la cuenta y el nombre descriptivo del dispositivo en el archivo. Para crear el archivo .csv, use un formato de dirección UPN (rainier@contoso.com) o un formato de nombre de inicio de sesión de nivel inferior (contoso\rainier).

    rainier@contoso.com,password,Rainier Surface Hub

3. Guarde el archivo en la carpeta del proyecto y cópielo en la clave USB con el paquete de aprovisionamiento.

> [!NOTE]
> El archivo de configuración solo se puede aplicar durante la primera ejecución de la instalación.

### <a name="password-protect-provisioning-package"></a>Paquete de aprovisionamiento de protección de contraseñas

Si decide usar una contraseña, deberá escribirla cada vez que aplique el paquete de aprovisionamiento a un dispositivo.

### <a name="complete-provisioning-wizard"></a>Asistente para el aprovisionamiento completo

Si solo necesita configurar opciones comunes, seleccione **FinalizarCrear** **** >  y vaya a la sección [Compilación del paquete](#build-your-package). O continúe configurando la configuración cambiando a Aprovisionamiento avanzado.

## <a name="use-advanced-provisioning"></a>Uso del aprovisionamiento avanzado

> [!TIP]
> Usa el asistente para crear un paquete con la configuración común y después usa el editor avanzado para agregar otras configuraciones.<br><br> ![Cambie al editor avanzado.](images/icd-simple-edit.png)

1. Si continúa desde la sección anterior, seleccione **Cambiar al editor avanzado**; de lo contrario, abra **Windows Diseñador de configuración** y seleccione **Aprovisionamiento avanzado**.

   ![Use el aprovisionamiento avanzado.](images/sh-prov-adv.png)

2. Asigne un nombre al proyecto y seleccione **Siguiente**.

3. Seleccione **Común para Windows 10 Team**, seleccione **Siguiente** y, a continuación, **seleccione Finalizar**.

   ![Nuevo proyecto de WCD.](images/icd-new-project.png)

4. En el proyecto, en **Personalizaciones disponibles**, seleccione **Configuración del equipo común**.

   :::image type="content" alt-text="Configuración común de WCD." source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>Agregar un certificado al paquete

Puedes usar paquetes de aprovisionamiento para instalar certificados que permitirán que el dispositivo se autentique en MicrosoftExchange.

> [!NOTE]
> Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén de dispositivo (máquina local), pero no en el almacén del usuario. Si su organización requiere que los certificados se instalen en el almacén de usuarios, use la aplicación **Hub Configuración**: **Update &** **SecurityCertificatesImport** >  >  **Certificate**.
Como alternativa, puede usar  [**directivas MDM**](manage-settings-with-mdm-for-surface-hub.md) para implementar certificados en el almacén de dispositivos o en el almacén de usuarios.

> [!TIP]
> La sección **ClientCertificates** es para archivos .pfx con una clave privada; los archivos .cer para ca raíz deben colocarse en la sección **RootCertificates** y para las CA intermedias en la sección **CACertificates** .

1. En **Windows Diseñador** >  de configuración **Personalizaciones disponibles**, vaya a Configuración  >  del **entorno de** ejecuciónCertificatesClientCertificates**** > .****
2. Escriba una etiqueta para **CertificateName** y, a continuación, seleccione **Agregar**.
3. Escribe el valor **CertificatePassword**.
4. Para el valor **CertificatePath**, examina y selecciona el certificado.
5. Establece el elemento **ExportCertificate** en **False**.
6. Para **KeyLocation**, selecciona **Software solo**.

### <a name="add-a-uwp-app-to-your-package"></a>Agregar una aplicación para UWP al paquete

Para agregar una aplicación para UWP a un paquete de aprovisionamiento, necesitarás el paquete de la aplicación (archivos .appx o .appxbundle) y cualquier archivo de dependencia. Si adquiriste la aplicación en la Microsoft Store para Empresas, también necesitarás la licencia de la aplicación *sin codificar*. Consulta [Distribuir aplicaciones sin conexión](/microsoft-store/distribute-offline-apps) para conocer cómo descargar estos elementos de la Microsoft Store para Empresas.

**Para agregar una aplicación para UWP:**

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextApp**.

2. Escriba un **PackageFamilyName** para la aplicación y, a continuación, seleccione **Agregar**. Por motivos de coherencia, usa el nombre de familia de paquete de la aplicación. Si adquiriste la aplicación en la Microsoft Store para Empresas, puedes encontrar el nombre de familia de paquete en la licencia de la aplicación. Abra el archivo de licencia mediante un editor de texto y use el valor entre las etiquetas PFM.

3. En **ApplicationFile**, seleccione **Examinar** para buscar y seleccione la aplicación de destino ( .appx o .appxbundle).

4. En **DependencyAppxFiles**, seleccione **Examinar** para buscar y agregar las dependencias de la aplicación. Para Surface Hub, solo necesitas versiones x64 de estas dependencias.

Si adquiriste la aplicación de la Microsoft Store para Empresas, deberás agregar la licencia de la aplicación al paquete de aprovisionamiento.

**Para agregar licencia de aplicación:**

1. Haz una copia de la licencia de la aplicación y cámbiale el nombre para usar una extensión **.ms-windows-store-license**. Por ejemplo, cambie el nombre de "example.xml" a "example.ms-windows-store-license".

2. En Windows Diseñador de configuración, vaya a **Personalizaciones** >  **disponiblesConfiguración de** >  **horaUniversalAppInstallDeviceContextAppLicense** > .****

3. Escriba un **LicenseProductId** y, a continuación, seleccione **Agregar**. Por motivos de coherencia, usa el identificador de licencia de aplicación de la licencia de la aplicación. Abre el archivo de licencia con un editor de texto. A continuación, en la etiqueta **Licencia** , use el valor del atributo **LicenseID** .

4. Selecciona el nuevo nodo **LicenseProductId**. En **LicenseInstall**, seleccione **Examinar** para buscar y seleccione el archivo de licencia cuyo nombre ha cambiado (example.ms-windows-store-license).

### <a name="add-a-policy-to-your-package"></a>Agregar una directiva al paquete

Surface Hub admite un subconjunto de directivas incluidas en el [Proveedor de servicios de configuración de directivas](/windows/client-management/mdm/policy-configuration-service-provider). Algunas de esas directivas se pueden configurar con Windows Diseñador de configuración.

 **Para agregar [directivas de CSP](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub):**

1. Vaya a **Personalizaciones** >  **disponiblesConfiguración de** >  tiempo **de ejecuciónDirectivas**.
2. Seleccione el componente que desea administrar y configure la configuración de directiva según corresponda. Por ejemplo, para evitar que los empleados usen la exploración del sitio web de InPrivate en Surface Hub, seleccione **AllowInPrivate** y, a continuación, **seleccione Deshabilitar**.  

   :::image type="content" alt-text="Configure la configuración de directiva." source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>Agregar valores de configuración de Surface Hub al paquete

Puedes agregar valores de configuración del [Proveedor de servicios de configuración de SurfaceHub](/windows/client-management/mdm/surfacehub-csp) al paquete de aprovisionamiento.

1. Vaya a **Personalizaciones** >  **disponiblesCommon Team Edition Configuración**.
1. Seleccione el componente que desea administrar y configure la configuración de directiva según corresponda.
1. Cuando haya terminado de configurar el paquete de aprovisionamiento, seleccione **ArchivoGuardar****** > .
1. Lea la advertencia de que los archivos de proyecto pueden contener información confidencial y seleccione **Aceptar**.

### <a name="build-your-package"></a>Crear el paquete

Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran.  Almacene los archivos del proyecto en una ubicación segura o elimine si ya no es necesario.

1. Abra **Windows diseñador** >  **de configuracionesExportar** >  **paquete de configuración**.

2. Cambie **Propietario** a **Administrador de TI**.  

3. Establece un valor para **Versión del paquete** y luego selecciona **Siguiente**.

   > [!TIP]
   > Establecer el propietario en administrador de TI garantiza que la configuración del paquete mantenga las "propiedades de precedencia" adecuadas y permanezca en vigor en Surface Hub si se aplican posteriormente otros paquetes de aprovisionamiento desde otros orígenes.

   > [!TIP]
   > Puede modificar los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.

4. Opcional: puede optar por cifrar el paquete y habilitar la firma de paquetes:

    1. Seleccione **Cifrar paquete** y escriba una contraseña.
    1. Seleccione **Firmar** **paqueteBrowse** >  y elija el certificado según corresponda.

    > [!IMPORTANT]
    > Se recomienda incluir un certificado de aprovisionamiento de confianza en el paquete de aprovisionamiento. Cuando el paquete se aplica a un dispositivo, el certificado se agrega al almacén del sistema, lo que permite que los paquetes posteriores se apliquen de forma silenciosa.

5. Seleccione **Siguiente** para especificar la ubicación de salida. De forma predeterminada, el Diseñador de configuraciones de Windows usa la carpeta de proyecto como la ubicación de salida. O bien, seleccione **Examinar** para cambiar la ubicación de salida predeterminada. Selecciona **Siguiente**.

6. Seleccione **Compilar** para empezar a compilar el paquete. La información del proyecto se muestra en la página de compilación.

7. Si se produce un error en la compilación, aparece un mensaje de error con un vínculo a la carpeta del proyecto. Revise los registros para diagnosticar el error e intente volver a compilar el paquete.

8. Si la compilación se realiza correctamente, se muestra el nombre del paquete de aprovisionamiento, el directorio de salida y el directorio del proyecto. Seleccione **Finalizar** para cerrar el asistente y volver a la página Personalizaciones.

9. Seleccione  **la ubicación de salida**  para ir a la ubicación del paquete. Copia el archivo .ppkg a una unidad flash USB.

## <a name="apply-a-provisioning-package-to-surface-hub"></a>Aplicar un paquete de aprovisionamiento a un dispositivo Surface Hub

Hay dos maneras de implementar paquetes de aprovisionamiento en un Surface Hub:

- [Primera ejecución del programa de instalación.](#apply-a-provisioning-package-during-first-run) Puede aplicar un paquete de aprovisionamiento para personalizar varias opciones, como la configuración de Wi-Fi, la configuración de proxy, los detalles de la cuenta del dispositivo, la Azure AD unirse y la configuración relacionada.  
- [Configuración aplicación.](#apply-a-provisioning-package-using-settings-app) Después de la primera ejecución de la instalación, puede aplicar un paquete de aprovisionamiento a través de la aplicación Configuración. 

### <a name="apply-a-provisioning-package-during-first-run"></a>Aplicar un paquete de aprovisionamiento durante la primera ejecución

1. Al activar la Surface Hub por primera vez, el programa de primera ejecución muestra la [**página Hola allí**](first-run-program-surface-hub.md). Asegúrate de que las opciones de configuración se hayan configurado correctamente antes de continuar.

2. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub. Si el paquete está en el directorio raíz de la unidad, el programa de primera ejecución lo reconocerá y preguntará si quieres configurar el dispositivo. Selecciona **Configurar**.

3. La pantalla siguiente te pide que selecciones un origen de aprovisionamiento. Selecciona **Medios extraíbles** y pulsa **Siguiente**.

4. Seleccione el paquete de aprovisionamiento (*.ppkg) que desea aplicar y pulse **Siguiente**. Ten en cuenta que solo puedes instalar un paquete durante la primera ejecución.

5. El programa de primera ejecución mostrará un resumen de los cambios que va a aplicar el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.

6. Si un archivo de configuración se incluye en el directorio raíz de la unidad flash USB, verás **Seleccionar una configuración**. Se mostrará la primera cuenta de dispositivo en el archivo de configuración con un resumen de la información de la cuenta que se aplicará a Surface Hub.

7. En **Seleccionar una configuración**, seleccione el nombre del dispositivo que se va a aplicar y, a continuación, seleccione **Siguiente**.

La configuración del paquete de aprovisionamiento se aplicará al dispositivo y se completará la configuración rápida. Una vez reiniciado el dispositivo, puedes quitar la unidad flash USB.

### <a name="apply-a-provisioning-package-using-settings-app"></a>Aplicación de un paquete de aprovisionamiento mediante Configuración aplicación

1. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub.
2. Desde Surface Hub, inicie **Configuración** y escriba las credenciales de administrador cuando se le solicite.
3. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, seleccione **Agregar o quitar un paquete** >  de aprovisionamientoAgregar **un paquete**.
4. Elige el paquete de aprovisionamiento y selecciona **Agregar**.  Si se le solicita, vuelva a escribir las credenciales de administrador.
5. Verá un resumen de los cambios que se van a aplicar. Selecciona **Sí, agrégalo**.

## <a name="learn-more"></a>Obtén más información

- [Descargar Windows Diseñador de configuración](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [Crear un paquete de aprovisionamiento](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Administrar Surface Hub con un proveedor MDM](manage-settings-with-mdm-for-surface-hub.md)

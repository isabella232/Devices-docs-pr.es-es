---
title: Crear paquetes de aprovisionamiento (Surface Hub)
description: En Windows10, la configuración que usa el Registro o un proveedor de servicios de configuración (CSP) se puede configurar con paquetes de aprovisionamiento.
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: add certificate, agregar certificado, provisioning package, paquete de aprovisionamiento
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 5e0714d284cc5c8207633719ec8fb52cec9f95cb
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576990"
---
# <a name="create-provisioning-packages-surface-hub"></a>Crear paquetes de aprovisionamiento (Surface Hub)

En este tema se describe cómo crear un paquete de aprovisionamiento con el Diseñador de configuraciones de Windows y aplicarlo a dispositivos Surface Hub. En el caso de Surface Hub, puedes usar paquetes de aprovisionamiento para agregar certificados, instalar aplicaciones para la Plataforma universal de Windows (UWP), así como personalizar directivas y la configuración.

Puedes aplicar un paquete de aprovisionamiento con un stick USB durante la configuración de la primera ejecución o con la aplicación **Configuración**. 


## <a name="advantages"></a>Ventajas
-   Configuración rápida de dispositivos sin tener que usar un proveedor de administración de dispositivos móviles (MDM).

-   No se necesita conectividad de red.

-   Es fácil de aplicar.

[Más información sobre las ventajas y los usos de los paquetes de aprovisionamiento.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## <a name="requirements"></a>Requisitos 

Para crear y aplicar un paquete de aprovisionamiento en un dispositivo Surface Hub, necesitarás lo siguiente:

-   El Diseñador de configuraciones de Windows, que se puede instalar desde Microsoft Store o desde Windows 10 Assessment and Deployment Kit (ADK). [Aprende a instalar el Diseñador de configuraciones de Windows.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   Un stick USB.
-   Si aplicas el paquete mediante la aplicación **Configuración**, necesitarás credenciales de administrador de dispositivos.

El paquete de aprovisionamiento se crea en un equipo que ejecuta Windows10, se guarda en una unidad USB y luego se implementa en el dispositivo Surface Hub.


## <a name="supported-items-for-surface-hub-provisioning-packages"></a>Elementos admitidos para paquetes de aprovisionamiento de Surface Hub

Con el asistente **Aprovisionar dispositivos Surface Hub**, puedes:

- Inscribirte en Active Directory, Azure Active Directory o MDM 
- Crear una cuenta de administrador de dispositivo 
- Agregar aplicaciones y certificados
- Definir la configuración de proxy
- Agregar un archivo de configuración de Surface Hub

>[!WARNING]
>Tienes que ejecutar el Diseñador de configuraciones de Windows en Windows 10 para configurar la inscripción en Azure Active Directory con el asistente.

Con el editor de aprovisionamiento avanzado puedes agregar estos elementos a paquetes de aprovisionamiento para Surface Hub:

- **Directivas**: Surface Hub admite un subconjunto de directivas en el [Proveedor de servicios de configuración de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies). 
- **Configuración**: puedes configurar cualquier opción en el [Proveedor de servicios de configuración de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).

>[!TIP]
> Usa el asistente para crear un paquete con la configuración común y después usa el editor avanzado para agregar otras configuraciones.
>
>![abrir el editor avanzado](images/icd-simple-edit.png)

## <a name="use-the-surface-hub-provisioning-wizard"></a>Usar al asistente para aprovisionar Surface Hub

Tras [instalar el Diseñador de configuraciones de Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), puedes crear un paquete de aprovisionamiento.

### <a name="create-the-provisioning-package"></a>Crear un paquete de aprovisionamiento 

1. Abre el Diseñador de configuraciones de Windows:
   - En la pantalla Inicio o el panel de búsqueda del menú Inicio, escribe "Diseñador de configuraciones de Windows" y haz clic en el acceso directo a Diseñador de configuraciones de Windows. 
    
     o bien
    
   - Si instalaste el Diseñador de configuraciones de Windows desde ADK, navega hasta `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (en un equipo x64) o `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (en un equipo x86) y luego haz doble clic en **ICD.exe**.

2. Haz clic en **Aprovisionar dispositivos Surface Hub**.

3. Asigna un nombre al proyecto y haz clic en **Siguiente**.

### <a name="configure-settings"></a>Definir configuración

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Para aprovisionar el dispositivo con un certificado, haz clic en <strong>Agregar un certificado</strong>. Escribe un nombre de certificado y luego busca y selecciona el certificado que quieres usar.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Alterna <strong>Sí</strong> o <strong>No</strong> para la configuración de proxy. La configuración predeterminada para Surface Hub es detectar automáticamente la configuración de proxy, por lo que puedes seleccionar <strong>No</strong> si es la configuración que quieres. Sin embargo, si anteriormente tu infraestructura requería el uso de un servidor proxy y ahora ha cambiado y ya no lo requiere, puedes usar un paquete de aprovisionamiento para revertir los dispositivos Surface Hub a la configuración predeterminada seleccionando <strong>Sí</strong> y <strong>Detectar la configuración automáticamente</strong>. </br></br>Si cambias a <strong>Sí</strong>, puedes seleccionar la detección automática de la configuración de proxy o puedes configurar manualmente la configuración escribiendo una dirección URL para un script de configuración o una dirección estática de servidor proxy. También puedes identificar si quieres usar el servidor proxy para direcciones locales y escribir excepciones (direcciones a las que Surface Hub se debe conectar directamente, sin usar el servidor proxy).  </td><td><img src="images/proxy-details.png" alt="proxy configuration details"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Puedes inscribir el dispositivo en Active Directory y especificar un grupo de seguridad para que use la aplicación Configuración, inscribirlo en Azure Active Directory para permitir que los administradores globales usen la aplicación Configuración o crear una cuenta de administrador local en el dispositivo.</br></br>Para inscribir el dispositivo en Active Directory, escribe las credenciales de una cuenta de usuario con privilegios mínimos para unir el equipo al dominio y especifica que el grupo de seguridad tenga credenciales de administrador en Surface Hub. Si un paquete de aprovisionamiento que inscribe un dispositivo en Active Directory se va a aplicar a un Surface Hub que se ha restablecido, solo se puede usar la misma cuenta de dominio si la cuenta es un administrador de dominio o es la misma cuenta que ha configurado Surface Hub inicialmente. De lo contrario, se tiene que usar una cuenta de dominio diferente en el paquete de aprovisionamiento.</br></br>Antes de usar un asistente del Diseñador de configuraciones de Windows para configurar la inscripción masiva en AzureAD, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">configura la unión a Azure AD en la organización</a>. La opción <strong>Número máximo de dispositivos por usuario</strong> del inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente. Para inscribir el dispositivo en Azure AD, selecciona esa opción y escribe un nombre descriptivo para el token masivo que obtendrás mediante el asistente. Establece una fecha de expiración del token (el máximo es de 30 días a partir de la fecha de obtención del token). Haz clic en <strong>Get bulk token</strong>. En la ventana Permitir&#39;sesión, escriba una cuenta que tenga permisos para unir un dispositivo <strong> a Azure AD y, a continuación, </strong> la contraseña. Haz clic en <strong>Aceptar</strong> para dar al Diseñador de configuraciones de Windows los permisos necesarios.</br></br>Para crear una cuenta de administrador local, selecciona esa opción y escribe un nombre de usuario y una contraseña. </br></br><strong>Importante:</strong> Si creas una cuenta local en el paquete de aprovisionamiento, debes cambiar la contraseña con la aplicación <strong>Configuración</strong> cada 42 días. Si la contraseña no se cambia en ese período, es posible que se bloquee y no se pueda iniciar sesión.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Usa esta sección para inscribirte en proveedores de MDM además de Intune. Para la inscripción de Intune, use La unión de Azure AD en la sección anterior con <a href="https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment" data-raw-source="[automatic Intune enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)"> la inscripción automática de Intune </a> .</br></br>Alterna <strong>Sí</strong> o <strong>No</strong> para la inscripción en MDM. </br></br>Si cambias a <strong>Sí</strong>, tienes que proporcionar una cuenta y contraseña del servicio o la huella digital del certificado autorizado para inscribir el dispositivo, además de especificar el tipo de autenticación. Si tu proveedor MDM lo requiere, también tendrás que escribir las direcciones URL para el servicio de detección, el servicio de inscripción y el servicio de directivas. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">Obtén más información sobre cómo administrar Surface Hub con MDM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>Puedes instalar varias aplicaciones para la Plataforma universal de Windows (UWP) en un paquete de aprovisionamiento. Para ayuda con la configuración, consulta <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Aprovisionar equipos con aplicaciones</a>. </br></br><strong>Importante: Aunque la interfaz del asistente te permite seleccionar una aplicación Win32 clásica, solo incluye aplicaciones para UWP en un paquete de aprovisionamiento que se aplicará </strong> a Surface Hub. Si incluyes una aplicación Win32 clásica, el aprovisionamiento fallará. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>No puede&#39;ninguna configuración en este paso. Proporciona instrucciones para incluir un archivo de configuración que contiene una lista de cuentas del dispositivo. El archivo de configuración no debe contener encabezados de columna. Cuando se aplica el paquete de aprovisionamiento a Surface Hub, si se ha incluido un archivo de configuración de Surface Hub en la unidad USB, puedes seleccionar la cuenta y el nombre descriptivo para el dispositivo en el archivo. Consulta <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Archivo de configuración de ejemplo</a> para ver un ejemplo.</br></br><strong>Importante: El archivo de configuración solo se puede aplicar durante la experiencia de configuración lista para usar (OOBE) y solo se puede usar con paquetes de aprovisionamiento creados con el Diseñador de configuraciones de Windows publicado con Windows 10, versión </strong> 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish creating your package"/></br></br>Puedes establecer una contraseña para proteger el paquete de aprovisionamiento. Debes escribir esta contraseña cuando apliques el paquete de aprovisionamiento a un dispositivo.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Cuando haya terminado, haz clic en **Crear**. El proceso solo tarda unos pocos segundos. Cuando se genera el paquete, la ubicación donde se almacena el paquete se muestra como un hipervínculo en la parte inferior de la página.

## <a name="sample-configuration-file"></a>Archivo de configuración de ejemplo

Un archivo de configuración de Surface Hub contiene una lista de cuentas de dispositivo que tu dispositivo puede usar para conectarse a Exchange y Skype Empresarial. Al aplicar un paquete de aprovisionamiento a Surface Hub, puedes incluir un archivo de configuración en el directorio raíz de la unidad flash USB y, a continuación, seleccionar la cuenta que quieres aplicar a ese dispositivo. El archivo de configuración solo puede aplicarse durante la configuración rápida (OOBE) y solo puede usarse con paquetes de aprovisionamiento creados con el Diseñador de configuraciones de Windows publicado con Windows 10, versión 1703.

Usa Microsoft Excel u otro editor CSV para crear un archivo CSV denominado `SurfaceHubConfiguration.csv`. En el archivo, escribe una lista de cuentas de dispositivo y nombres descriptivos en este formato:

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>Puesto que el archivo de configuración almacena las contraseñas de cuentas de dispositivo en texto sin formato, te recomendamos actualizar las contraseñas después de aplicar el paquete de aprovisionamiento a tus dispositivos. Puedes usar el [nodo DeviceAccount](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) en el [proveedor de servicios de configuración (CSP) de Surface Hub](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) para actualizar las contraseñas a través de MDM.


El siguiente es un ejemplo de `SurfaceHubConfiguration.csv`. 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## <a name="use-advanced-provisioning"></a>Usar aprovisionamiento avanzado

Tras [instalar el Diseñador de configuraciones de Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), puedes crear un paquete de aprovisionamiento.

### <a name="create-the-provisioning-package-advanced"></a>Crear el paquete de aprovisionamiento (avanzado)

1. Abre el Diseñador de configuraciones de Windows:
   - En la pantalla Inicio o el panel de búsqueda del menú Inicio, escribe "Diseñador de configuraciones de Windows" y haz clic en el acceso directo a Diseñador de configuraciones de Windows. 
    
     o bien
    
   - Si instalaste el Diseñador de configuraciones de Windows desde ADK, navega hasta `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (en un equipo x64) o `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (en un equipo x86) y luego haz doble clic en **ICD.exe**.

2. Haz clic en **Aprovisionamiento avanzado**.
   
3. Asigna un nombre al proyecto y haz clic en **Siguiente**.

4. Seleccione **Común para Windows 10 Team**, haga clic en **Siguiente**y, a continuación, haga clic en **Finalizar**.

    ![Proyecto nuevo de ICD](images/icd-new-project.png)

5. En el proyecto, en **Personalizaciones disponibles,** seleccione **Configuración común del equipo**.

    ![Configuración común de ICD](images/icd-common-settings.png)


### <a name="add-a-certificate-to-your-package"></a>Agregar un certificado al paquete
Puedes usar paquetes de aprovisionamiento para instalar certificados que permitirán que el dispositivo se autentique en MicrosoftExchange.

> [!NOTE]
> Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén de dispositivo (máquina local), pero no en el almacén del usuario. Si su organización requiere que los certificados se instalen **** en el almacén de usuarios, puede usar el botón Importar certificado en la sección Actualizar certificados de seguridad **de &** de la aplicación de Configuración  >  **** hub. **** Como alternativa, las directivas de administración de dispositivos móviles [(MDM)](manage-settings-with-mdm-for-surface-hub.md) se pueden usar para implementar certificados en el almacén de dispositivos o en el almacén de usuarios.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **Certificados** > **ClientCertificates**.
   > [!NOTE]
   > La **sección ClientCertificates** es para los archivos .pfx con una clave privada; los archivos .cer para las CA raíz deben colocarse en la sección **RootCertificates** y para las CA intermedias en la **sección CACertificates.**

2. Escriba una etiqueta para **CertificateName** y, a continuación, haga clic **en Agregar**. 

2. Escribe el valor **CertificatePassword**. 

3. Para el valor **CertificatePath**, examina y selecciona el certificado. 

4. Establece el elemento **ExportCertificate** en **False**.

5. Para el objeto **KeyLocation**, selecciona **Software solo**.


### <a name="add-a-universal-windows-platform-uwp-app-to-your-package"></a>Agregar una aplicación para Plataforma universal de Windows (UWP) al paquete
Antes de agregar una aplicación para UWP a un paquete de aprovisionamiento, necesitas el paquete de la aplicación (un archivo .appx o .appxbundle) y los archivos de dependencia. Si adquiriste la aplicación en la Microsoft Store para Empresas, también necesitarás la licencia de la aplicación *sin codificar*. Consulta [Distribuir aplicaciones sin conexión](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) para conocer cómo descargar estos elementos de la Microsoft Store para Empresas.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextApp**.

2. Especifica un valor **PackageFamilyName** para la aplicación y luego haz clic en **Agregar**. Por motivos de coherencia, usa el nombre de familia de paquete de la aplicación. Si adquiriste la aplicación en la Microsoft Store para Empresas, puedes encontrar el nombre de familia de paquete en la licencia de la aplicación. Abra el archivo de licencia con un editor de texto y use el valor entre \<PFM\> las \</PFM\> etiquetas ... .

3. Para **ApplicationFile**, haz clic en **Examinar** para buscar y seleccionar la aplicación de destino (\*.appx o \*.appxbundle).

4. Para el objeto **DependencyAppxFiles**, haz clic en **Examinar** para buscar y agregar las dependencias de la aplicación. Para Surface Hub, solo necesitas versiones x64 de estas dependencias.

Si adquiriste la aplicación en la Microsoft Store para Empresas, tienes que agregar la licencia de la aplicación al paquete de aprovisionamiento.

1. Haz una copia de la licencia de la aplicación y cámbiale el nombre para usar una extensión **.ms-windows-store-license**. Por ejemplo, "ejemplo.xml" se convierte en "ejemplo.ms-windows-store-license".

2. En ICD, en el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Especifica un valor **LicenseProductId** y después haz clic en **Agregar**. Por motivos de coherencia, usa el identificador de licencia de aplicación de la licencia de la aplicación. Abre el archivo de licencia con un editor de texto. A continuación, \<License\> en la etiqueta, use el valor del **atributo LicenseID.**

4. Selecciona el nuevo nodo **LicenseProductId**. Para el elemento **LicenseInstall**, haz clic en **Examinar** para buscar y seleccionar el archivo de licencia al que cambiaste el nombre en el paso 1.


### <a name="add-a-policy-to-your-package"></a>Agregar una directiva al paquete
Surface Hub admite un subconjunto de directivas incluidas en el [Proveedor de servicios de configuración de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Algunas de estas directivas pueden configurarse con ICD.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **Directivas**.

2. Selecciona una de las áreas de directiva disponibles.

3. Selecciona y establece la directiva que quieras agregar al paquete de aprovisionamiento.


### <a name="add-surface-hub-settings-to-your-package"></a>Agregar valores de configuración de Surface Hub al paquete 

Puedes agregar valores de configuración del [Proveedor de servicios de configuración de SurfaceHub](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) al paquete de aprovisionamiento. 

1. En el **panel Personalizaciones disponibles,** ve a **Configuración de tiempo de ejecución**  >  **SurfaceHub**.

2. Selecciona una de las áreas de configuración disponibles.

3. Selecciona y establece la configuración que quieras agregar al paquete de aprovisionamiento. 


## <a name="build-your-package"></a>Compilar el paquete

1. Cuando hayas terminado de configurar el paquete de aprovisionamiento, en el menú **Archivo**, haz clic en **Guardar**.

2. Lee la advertencia en la que se indica que los archivos de proyecto pueden contener información confidencial y haz clic en **Aceptar**.

    > [!IMPORTANT]
    > Cuando compilas un paquete de aprovisionamiento, puedes incluir información confidencial en los archivos de proyecto y en el archivo del paquete de aprovisionamiento (.ppkg). Aunque tienes la posibilidad de cifrar el archivo .ppkg, los archivos de proyecto no se cifran. Debes almacenar los archivos del proyecto en una ubicación segura y eliminarlos cuando ya no sean necesarios.

3. En el menú **Exportar**, haz clic en **Paquete de aprovisionamiento**.

4. Cambia de **Propietario** a **Administrador de TI** para establecer una prioridad para este paquete de aprovisionamiento superior a la de los paquetes de aprovisionamiento aplicados a este dispositivo desde otros orígenes.

5. Establece un valor para **Versión del paquete** y luego selecciona **Siguiente**.

    > [!TIP]
    > Puedes realizar cambios en los paquetes existentes y cambiar el número de versión para actualizar los paquetes aplicados anteriormente.

6. Opcional: puedes elegir cifrar el paquete y habilitar la firma del paquete.

    -   **Habilitar el cifrado del paquete**: si seleccionas esta opción, en la pantalla se mostrará una contraseña generada automáticamente.

    -   **Habilitar la firma del paquete**: si seleccionas esta opción, debes seleccionar un certificado válido que se usará para firmar el paquete. Para especificar el certificado, haz clic en **Examinar...** y elige el certificado que quieras usar para firmar el paquete.

        > [!IMPORTANT]
        > Te recomendamos incluir un certificado de aprovisionamiento de confianza en el paquete de aprovisionamiento. Cuando el paquete se aplica a un dispositivo, el certificado se agrega al almacén del sistema y cualquier paquete firmado con dicho certificado podrá aplicarse de forma silenciosa de ahí en adelante. 

7. Haz clic en **Siguiente** para especificar la ubicación de salida donde quieras ubicar el paquete de aprovisionamiento una vez compilado. De forma predeterminada, Windows ICD usa la carpeta de proyecto como la ubicación de salida.<p>
También puedes hacer clic en **Examinar** para cambiar la ubicación de salida predeterminada.

8. Haz clic en **Siguiente**.

9. Haz clic en **Compilar** para comenzar a compilar el paquete. La información del proyecto se muestra en la página de compilación y la barra de progreso indica el estado de compilación.<p>
Si necesitas cancelar la compilación, haz clic en **Cancel**. Se cancelará el proceso de compilación actual, se cerrará el asistente y se volverá a la página **Customizations Page**.

10. Si se produce un error en la compilación, se mostrará un mensaje de error con un vínculo a la carpeta del proyecto. Puedes examinar los registros para determinar qué produjo el error. Después de solucionar el problema, intenta volver a compilar el paquete.<p>
Si la compilación es correcta, se mostrará el nombre del paquete de aprovisionamiento, el directorio de salida y el directorio del proyecto.

    -   Si quieres, puedes volver a compilar el paquete de aprovisionamiento y elegir otra ruta de acceso para el paquete de salida. Para hacerlo, haz clic en **Atrás** para cambiar el nombre y la ruta de acceso del paquete de salida y, a continuación, en **Siguiente** para iniciar otra compilación.
    
    -   Cuando hayas terminado, haz clic en **Finalizar** para cerrar el asistente y volver a la página **Personalizaciones**.

11. Selecciona el vínculo **Ubicación del resultado** para ir a la ubicación del paquete. Copia el archivo .ppkg a una unidad flash USB.


## <a name="apply-a-provisioning-package-to-surface-hub"></a>Aplicar un paquete de aprovisionamiento a un dispositivo Surface Hub

Existen dos opciones para implementar paquetes de aprovisionamiento en un Surface Hub. [Durante](#apply-a-provisioning-package-during-first-run)el asistente para la primera ejecución, puede aplicar un paquete de aprovisionamiento que instale certificados o, una vez completado el programa de primera ejecución, puede aplicar un paquete de aprovisionamiento que configure la configuración, las aplicaciones y los certificados [mediante Configuración](#apply-a-package-using-settings). 


### <a name="apply-a-provisioning-package-during-first-run"></a>Aplicar un paquete de aprovisionamiento durante la primera ejecución

> [!IMPORTANT]
> Durante el programa de primera ejecución, solo puede usar paquetes de aprovisionamiento para instalar certificados. Usa la aplicación **Configuración** para instalar aplicaciones y aplicar otras configuraciones.

1. Cuando actives el dispositivo Surface Hub por primera vez, el programa de primera ejecución mostrará la [**página de bienvenida**](first-run-program-surface-hub.md#first-page). Asegúrate de que las opciones de configuración se hayan configurado correctamente antes de continuar.

2. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub. Si el paquete está en el directorio raíz de la unidad, el programa de primera ejecución lo reconocerá y preguntará si quieres configurar el dispositivo. Selecciona **Configurar**.

    ![¿Configurar dispositivo?](images/provisioningpackageoobe-01.png)

3. La pantalla siguiente te pide que selecciones un origen de aprovisionamiento. Selecciona **Medios extraíbles** y pulsa **Siguiente**.

    ![Aprovisionar este dispositivo](images/provisioningpackageoobe-02.png)
    
4. Selecciona el paquete de aprovisionamiento (\*.ppkg) que quieras aplicar y pulsa **Siguiente**. Ten en cuenta que solo puedes instalar un paquete durante la primera ejecución.

    ![Elegir un paquete](images/provisioningpackageoobe-03.png)

5. El programa de primera ejecución mostrará un resumen de los cambios que va a aplicar el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.  

    ![¿Confías en este paquete?](images/provisioningpackageoobe-04.png)
    
6. Si un archivo de configuración se incluye en el directorio raíz de la unidad flash USB, verás **Seleccionar una configuración**. Se mostrará la primera cuenta de dispositivo en el archivo de configuración con un resumen de la información de la cuenta que se aplicará a Surface Hub.

    ![seleccionar una configuración](images/ppkg-config.png)    

7. En **Seleccionar una configuración**, selecciona el nombre del dispositivo que quieres aplicar y, a continuación, haz clic en **Siguiente**.

    ![seleccionar un nombre descriptivo del dispositivo](images/ppkg-csv.png)
    
La configuración del paquete de aprovisionamiento se aplicará al dispositivo y se completará la configuración rápida. Una vez reiniciado el dispositivo, puedes quitar la unidad flash USB.

### <a name="apply-a-package-using-settings"></a>Aplicar un paquete mediante la aplicación Configuración

1. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub.

2. En el Surface Hub, inicia **Configuración** y escribe las credenciales de administrador cuando se soliciten.

3. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, selecciona **Agregar o quitar un paquete de aprovisionamiento**.

4. Selecciona **Agregar un paquete**.

5. Elige el paquete de aprovisionamiento y selecciona **Agregar**. Es posible que tengas que volver a escribir las credenciales de administrador si se te solicitan.

6. Se mostrará un resumen de los cambios que aplicará el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.



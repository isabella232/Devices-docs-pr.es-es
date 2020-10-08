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
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103804"
---
# Crear paquetes de aprovisionamiento (Surface Hub)

En este tema se describe cómo crear un paquete de aprovisionamiento con el Diseñador de configuraciones de Windows y aplicarlo a dispositivos Surface Hub. En el caso de Surface Hub, puedes usar paquetes de aprovisionamiento para agregar certificados, instalar aplicaciones para la Plataforma universal de Windows (UWP), así como personalizar directivas y la configuración.

Puedes aplicar un paquete de aprovisionamiento con un stick USB durante la configuración de la primera ejecución o con la aplicación **Configuración**. 


## Ventajas
-   Configuración rápida de dispositivos sin tener que usar un proveedor de administración de dispositivos móviles (MDM).

-   No se necesita conectividad de red.

-   Es fácil de aplicar.

[Más información sobre las ventajas y los usos de los paquetes de aprovisionamiento.](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## Requisitos 

Para crear y aplicar un paquete de aprovisionamiento en un dispositivo Surface Hub, necesitarás lo siguiente:

-   El Diseñador de configuraciones de Windows, que se puede instalar desde Microsoft Store o desde Windows 10 Assessment and Deployment Kit (ADK). [Aprende a instalar el Diseñador de configuraciones de Windows.](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   Un stick USB.
-   Si aplicas el paquete mediante la aplicación **Configuración**, necesitarás credenciales de administrador de dispositivos.

El paquete de aprovisionamiento se crea en un equipo que ejecuta Windows10, se guarda en una unidad USB y luego se implementa en el dispositivo Surface Hub.


## Elementos admitidos para paquetes de aprovisionamiento de Surface Hub

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

## Usar al asistente para aprovisionar Surface Hub

Tras [instalar el Diseñador de configuraciones de Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), puedes crear un paquete de aprovisionamiento.

### Crear un paquete de aprovisionamiento 

1. Abre el Diseñador de configuraciones de Windows:
   - En la pantalla Inicio o el panel de búsqueda del menú Inicio, escribe "Diseñador de configuraciones de Windows" y haz clic en el acceso directo a Diseñador de configuraciones de Windows. 
    
     o bien
    
   - Si instalaste el Diseñador de configuraciones de Windows desde ADK, navega hasta `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (en un equipo x64) o `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (en un equipo x86) y luego haz doble clic en **ICD.exe**.

2. Haz clic en **Aprovisionar dispositivos Surface Hub**.

3. Asigna un nombre al proyecto y haz clic en **Siguiente**.

### Configure settings

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>To provision the device with a certificate, click <strong>Add a certificate</strong>. Enter a name for the certificate, and then browse to and select the certificate to be used.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings. La configuración predeterminada para Surface Hub es detectar automáticamente la configuración de proxy, por lo que puedes seleccionar <strong>No</strong> si es la configuración que quieres. Sin embargo, si anteriormente tu infraestructura requería el uso de un servidor proxy y ahora ha cambiado y ya no lo requiere, puedes usar un paquete de aprovisionamiento para revertir los dispositivos Surface Hub a la configuración predeterminada seleccionando <strong>Sí</strong> y <strong>Detectar la configuración automáticamente</strong>. </br></br>Si cambias a <strong>Sí</strong>, puedes seleccionar la detección automática de la configuración de proxy o puedes configurar manualmente la configuración escribiendo una dirección URL para un script de configuración o una dirección estática de servidor proxy. También puedes identificar si quieres usar el servidor proxy para direcciones locales y escribir excepciones (direcciones a las que Surface Hub se debe conectar directamente, sin usar el servidor proxy).  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>Puedes inscribir el dispositivo en Active Directory y especificar un grupo de seguridad para que use la aplicación Configuración, inscribirlo en Azure Active Directory para permitir que los administradores globales usen la aplicación Configuración o crear una cuenta de administrador local en el dispositivo.</br></br>Para inscribir el dispositivo en Active Directory, escribe las credenciales de una cuenta de usuario con privilegios mínimos para unir el equipo al dominio y especifica que el grupo de seguridad tenga credenciales de administrador en Surface Hub. Si un paquete de aprovisionamiento que inscribe un dispositivo en Active Directory se va a aplicar a un Surface Hub que se ha restablecido, solo se puede usar la misma cuenta de dominio si la cuenta es un administrador de dominio o es la misma cuenta que ha configurado Surface Hub inicialmente. Otherwise, a different domain account must be used in the provisioning package.</br></br>Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>. La opción <strong>Número máximo de dispositivos por usuario</strong> del inquilino de Azure AD determina cuántas veces se puede usar el token masivo que se obtiene en el asistente. Para inscribir el dispositivo en Azure AD, selecciona esa opción y escribe un nombre descriptivo para el token masivo que obtendrás mediante el asistente. Set an expiration date for the token (maximum is 30 days from the date you get the token). Click <strong>Get bulk token</strong>. In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password. Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</br></br>To create a local administrator account, select that option and enter a user name and password. </br></br><strong>Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days. If the password is not changed during that period, the account might be locked out and unable to sign in.  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM. </br></br>Si cambias a <strong>Sí</strong>, tienes que proporcionar una cuenta y contraseña del servicio o la huella digital del certificado autorizado para inscribir el dispositivo, además de especificar el tipo de autenticación. If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service. <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">Learn more about managing Surface Hub with MDM.</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>You can install multiple Universal Windows Platform (UWP) apps in a provisioning package. For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>. </br></br><strong>Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub. If you include a Classic Win32 app, provisioning will fail. </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>You don&#39;t configure any settings in this step. It provides instructions for including a configuration file that contains a list of device accounts. El archivo de configuración no debe contener encabezados de columna. Cuando se aplica el paquete de aprovisionamiento a Surface Hub, si se ha incluido un archivo de configuración de Surface Hub en la unidad USB, puedes seleccionar la cuenta y el nombre descriptivo para el dispositivo en el archivo. See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</br></br><strong>Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>You can set a password to protect your provisioning package. You must enter this password when you apply the provisioning package to a device.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

After you're done, click **Create**. El proceso solo tarda unos pocos segundos. Cuando se genera el paquete, la ubicación donde se almacena el paquete se muestra como un hipervínculo en la parte inferior de la página.

## Archivo de configuración de ejemplo

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

## Usar aprovisionamiento avanzado

Tras [instalar el Diseñador de configuraciones de Windows](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), puedes crear un paquete de aprovisionamiento.

### Crear el paquete de aprovisionamiento (avanzado)

1. Abre el Diseñador de configuraciones de Windows:
   - En la pantalla Inicio o el panel de búsqueda del menú Inicio, escribe "Diseñador de configuraciones de Windows" y haz clic en el acceso directo a Diseñador de configuraciones de Windows. 
    
     o bien
    
   - Si instalaste el Diseñador de configuraciones de Windows desde ADK, navega hasta `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (en un equipo x64) o `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (en un equipo x86) y luego haz doble clic en **ICD.exe**.

2. Haz clic en **Aprovisionamiento avanzado**.
   
3. Name your project and click **Next**.

4. Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.

    ![ICD new project](images/icd-new-project.png)

5. In the project, under **Available customizations**, select **Common Team settings**.

    ![ICD common settings](images/icd-common-settings.png)


### Agregar un certificado al paquete
Puedes usar paquetes de aprovisionamiento para instalar certificados que permitirán que el dispositivo se autentique en MicrosoftExchange.

> [!NOTE]
> Los paquetes de aprovisionamiento solo pueden instalar certificados en el almacén de dispositivo (máquina local), pero no en el almacén del usuario. Si la organización necesita que los certificados se instalen en el almacén de usuario, usa Administración de dispositivos móviles (MDM) para implementar estos certificados. Consulta la documentación de la solución MDM para obtener más información.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **Certificados** > **ClientCertificates**. 

2. Escribe el **CertificateName** y después haz clic en **Agregar**. 

2. Escribe el valor **CertificatePassword**. 

3. Para el valor **CertificatePath**, examina y selecciona el certificado. 

4. Establece el elemento **ExportCertificate** en **False**.

5. Para el objeto **KeyLocation**, selecciona **Software solo**.


### Agregar una aplicación para Plataforma universal de Windows (UWP) al paquete
Antes de agregar una aplicación para UWP a un paquete de aprovisionamiento, necesitas el paquete de la aplicación (un archivo .appx o .appxbundle) y los archivos de dependencia. Si adquiriste la aplicación en la Microsoft Store para Empresas, también necesitarás la licencia de la aplicación *sin codificar*. Consulta [Distribuir aplicaciones sin conexión](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) para conocer cómo descargar estos elementos de la Microsoft Store para Empresas.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextApp**.

2. Especifica un valor **PackageFamilyName** para la aplicación y luego haz clic en **Agregar**. Por motivos de coherencia, usa el nombre de familia de paquete de la aplicación. If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license. Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.

3. For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).

4. Para el objeto **DependencyAppxFiles**, haz clic en **Examinar** para buscar y agregar las dependencias de la aplicación. Para Surface Hub, solo necesitas versiones x64 de estas dependencias.

Si adquiriste la aplicación en la Microsoft Store para Empresas, tienes que agregar la licencia de la aplicación al paquete de aprovisionamiento.

1. Haz una copia de la licencia de la aplicación y cámbiale el nombre para usar una extensión **.ms-windows-store-license**. Por ejemplo, "ejemplo.xml" se convierte en "ejemplo.ms-windows-store-license".

2. En ICD, en el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **UniversalAppInstall** > **DeviceContextAppLicense**.

3. Especifica un valor **LicenseProductId** y después haz clic en **Agregar**. Por motivos de coherencia, usa el identificador de licencia de aplicación de la licencia de la aplicación. Open the license file using a text editor. Then, in the \<License\> tag, use the value in the **LicenseID** attribute.

4. Select the new **LicenseProductId** node. Para el elemento **LicenseInstall**, haz clic en **Examinar** para buscar y seleccionar el archivo de licencia al que cambiaste el nombre en el paso 1.


### Agregar una directiva al paquete
Surface Hub admite un subconjunto de directivas incluidas en el [Proveedor de servicios de configuración de directivas](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx). Algunas de estas directivas pueden configurarse con ICD.

1. En el panel **Personalizaciones disponibles**, ve a **Configuración de tiempo de ejecución** > **Directivas**.

2. Selecciona una de las áreas de directiva disponibles.

3. Selecciona y establece la directiva que quieras agregar al paquete de aprovisionamiento.


### Agregar valores de configuración de Surface Hub al paquete 

You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package. 

1. In the **Available customizations** pane, go to **Runtime settings** > **SurfaceHub**.

2. Select one of the available setting areas.

3. Selecciona y establece la configuración que quieras agregar al paquete de aprovisionamiento. 


## Compilar el paquete

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


## Aplicar un paquete de aprovisionamiento a un dispositivo Surface Hub

There are two options for deploying provisioning packages to a Surface Hub. [During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings). 


### Apply a provisioning package during first run

> [!IMPORTANT]
> During the first-run program, you can only use provisioning packages to install certificates. Use the **Settings** app to install apps and apply other settings.

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

### Aplicar un paquete mediante la aplicación Configuración

1. Inserta la unidad flash USB que contiene el archivo .ppkg en el Surface Hub.

2. En el Surface Hub, inicia **Configuración** y escribe las credenciales de administrador cuando se soliciten.

3. Navega hasta **Surface Hub** > **Administración de dispositivos**. En **Paquetes de aprovisionamiento**, selecciona **Agregar o quitar un paquete de aprovisionamiento**.

4. Selecciona **Agregar un paquete**.

5. Elige el paquete de aprovisionamiento y selecciona **Agregar**. Es posible que tengas que volver a escribir las credenciales de administrador si se te solicitan.

6. Se mostrará un resumen de los cambios que aplicará el paquete de aprovisionamiento. Selecciona **Sí, agrégalo**.



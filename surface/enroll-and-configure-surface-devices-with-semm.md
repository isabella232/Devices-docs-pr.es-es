---
title: Inscribir y configurar dispositivos Surface con SEMM (Surface)
description: Aprenda a crear un paquete de configuración de Surface UEFI para controlar la configuración de Surface UEFI, así como a inscribir un dispositivo Surface en SEMM.
keywords: Administración de Surface Enterprise
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 183eceee47eba8b8d1e794e9e7d3efffa7a9b2e0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835953"
---
# Inscribir y configurar los dispositivos Surface con SEMM

Con el modo de administración de Microsoft Surface Enterprise (SEMM), puede configurar de forma segura la configuración de Surface UEFI en un dispositivo Surface y administrar esa configuración en dispositivos Surface de su organización. Cuando SEMM administra un dispositivo Surface, ese dispositivo se considera que está *inscrito* (a veces se le conoce como activada). En este artículo se muestra cómo crear un paquete de configuración de Surface UEFI que no solo controlará la configuración de Surface UEFI, sino que también inscribirá un dispositivo Surface en SEMM.

Para obtener información general más detallada sobre SEMM, consulte [modo de administración de Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Ahora hay disponible un método optimizado de administración de firmware desde la nube en Surface Pro 7, Surface Pro X y Surface Laptop 3. Para obtener más información, consulte la [Administración de Intune de la configuración de Surface UEFI](surface-manage-dfci-guide.md).

> [!NOTE]
> SEMM es compatible con Surface Pro X a través del administrador UEFI solamente. Para obtener más información, consulte [implementación, administración y mantenimiento de Surface Pro X](surface-pro-arm-app-management.md).

#### Descargar e instalar el configurador Microsoft Surface UEFI
La herramienta que se usa para crear paquetes de SEMM es el configurador Microsoft Surface UEFI. Puede descargar Microsoft Surface UEFI configurador desde la página [Surface Tools para ti](https://www.microsoft.com/download/details.aspx?id=46703) del centro de descarga de Microsoft.
Ejecute el archivo Windows Installer (. msi) del configurador UEFI de Microsoft Surface para iniciar la instalación de la herramienta. Cuando se complete el instalador, busque el configurador Microsoft Surface UEFI en la sección todas las aplicaciones del menú Inicio.

>[!NOTE]
>El configurador UEFI de Microsoft Surface solo se admite en Windows 10.

## Crear un paquete de configuración de Surface UEFI

El paquete de configuración de Surface UEFI realiza tanto la función de aplicar una nueva configuración de los ajustes de Surface UEFI en un dispositivo Surface administrado con SEMM y la función de inscribir dispositivos Surface en SEMM. La creación de un paquete de configuración requiere que el certificado de firma se use con SEMM para asegurar la configuración de la configuración de UEFI en cada dispositivo Surface. Para obtener más información sobre los requisitos para el certificado SEMM, vea el [modo de administración de Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Para crear un paquete de configuración de Surface UEFI, siga estos pasos:

1. Abra el configurador de Microsoft Surface UEFI desde el menú Inicio.
2. Haz clic en **Inicio**.
3. Haga clic en **paquete de configuración**, como se muestra en la ilustración 1.

   ![Crear un paquete para la inscripción de SEMM](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Seleccione paquete de configuración para crear un paquete para la inscripción y configuración de SEMM*

4. Haga clic en **protección del certificado** para agregar el archivo de certificado exportado con la clave privada (. pfx), como se muestra en la ilustración 2. Vaya a la ubicación del archivo de certificado, seleccione el archivo y, a continuación, haga clic en **Aceptar**.

   ![Agregar el certificado SEM y la superficie de la contraseña UEFI al paquete de configuración](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figura 2. Agregar el certificado de SEMM y la contraseña UEFI a un paquete de configuración de Surface UEFI*

5. Cuando se le pida que confirme la contraseña del certificado, escriba y confirme la contraseña del archivo de certificado y, a continuación, haga clic en **Aceptar**.
6. Haga clic en **protección con contraseña** para agregar una contraseña a Surface UEFI. Esta contraseña será obligatoria cada vez que arranques en UEFI. Si no se introduce esta contraseña, solo se mostrará la **información del equipo**, **acerca**de, **Administración empresarial**y páginas de **salida** . Esto es opcional.
7. Cuando se le solicite, introduzca y confirme la contraseña que ha elegido para Surface UEFI y, a continuación, haga clic en **Aceptar**. Si desea borrar una contraseña de una superficie UEFI existente, deje el campo de la contraseña en blanco.
8. Si no desea que el paquete de superficie UEFI se aplique a un dispositivo en particular, en la página **elegir el tipo de superficie que desea dirigir** , haga clic en el control deslizante situado debajo de la imagen de la superficie de la superficie o de Surface Pro 4 para que esté en la posición de **apagado** . (Como se muestra en la ilustración 3).
   > [!NOTE] 
   > Debe seleccionar un dispositivo porque ninguno está seleccionado de forma predeterminada.

   ![Elegir dispositivos para la compatibilidad de paquetes](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figura 3. Elegir los dispositivos para la compatibilidad de paquetes*

9. Haz clic en **Siguiente**.
10. Si desea desactivar un componente en dispositivos de Surface administrados, en la página **Elija los componentes que desea activar o desactivar** , haga clic en el control deslizante situado junto a cualquier dispositivo o grupo de dispositivos que desee desactivar para que el control deslizante esté en la posición **desactivado** . (Se muestra en la ilustración 4). La configuración predeterminada para cada dispositivo es **activada**. Haga clic en el botón **restablecer** si desea devolver todos los controles deslizantes a la posición predeterminada.

    ![Deshabilitar o habilitar componentes de superficie](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Deshabilitar o habilitar componentes de superficie individuales*

11. Haz clic en **Siguiente**.
12. Para habilitar o deshabilitar las opciones avanzadas en Surface UEFI o la visualización de las páginas de Surface UEFI, en la página **elige la configuración avanzada de los dispositivos** , haga clic en el control deslizante situado junto al parámetro deseado para configurar esta opción como **activado** o **desactivado** (se muestra en la figura 5). En la sección de la **página frontal de UEFI** , puede usar los controles deslizantes de **seguridad**, **dispositivos**e **Inicio** para controlar qué páginas están disponibles para los usuarios que inicien en Surface UEFI. Para obtener más información sobre la configuración de Surface UEFI, consulte [administrar la configuración de Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings). Haga clic en **generar** cuando haya terminado de seleccionar las opciones para generar y guardar el paquete.

    ![Controlar la configuración de la superficie avanzada UEFI y las páginas UEFI de superficie](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar la configuración avanzada de la superficie UEFI y las páginas UEFI de superficie con SEMM*

13. En el cuadro de diálogo **Guardar como** , especifique un nombre para el paquete de configuración de Surface UEFI, busque la ubicación en la que desea guardar el archivo y, a continuación, haga clic en **Guardar**.
14. Cuando se crea y se guarda el paquete, se muestra la página **correcta** .

>[!NOTE]
>Grabe los caracteres de huella digital del certificado que se muestran en esta página, como se muestra en la ilustración 6. Para confirmar la inscripción de nuevos dispositivos Surface en SEMM, necesitarás estos caracteres. Haga clic en **Finalizar** para completar la creación del paquete y cierre Microsoft Surface UEFI configurador.

![Mostrar los caracteres de huella digital del certificado](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Figura 6. Los últimos dos caracteres de la huella digital del certificado se muestran en la página correcta*

Ahora que ha creado el paquete de configuración de Surface UEFI, puede inscribir o configurar dispositivos de Surface.

>[!NOTE]
>Cuando se crea un paquete de configuración de Surface UEFI, se crea un archivo de registro en el escritorio con detalles de la configuración y las opciones del paquete de configuración.

## Inscribir un dispositivo Surface en SEMM
Cuando se ejecuta el paquete de configuración de Surface UEFI, el certificado SEMM y los archivos de configuración de Surface UEFI se almacenan en el almacenamiento de firmware del dispositivo Surface. Cuando el dispositivo Surface se reinicia, Surface UEFI procesa estos archivos y comienza el proceso de aplicar la configuración de Surface UEFI o de inscribir el dispositivo Surface en SEMM, tal como se muestra en la figura 7.

![Proceso SEMM para la configuración de Surface UEFI o inscripción](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. El proceso SEMM para la configuración de Surface UEFI o la inscripción de un dispositivo Surface*

Antes de comenzar el proceso de inscripción de un dispositivo Surface en SEMM, asegúrate de tener a mano los dos últimos caracteres de la huella digital del certificado. Para confirmar la inscripción del dispositivo, necesitarás estos caracteres (ver la figura 6).

Para inscribir un dispositivo Surface en SEMM con un paquete de configuración de Surface UEFI, siga estos pasos:

1. Ejecuta el archivo package. msi de la configuración Surface UEFI en el dispositivo Surface en el que deseas inscribirse en SEMM. Esto aprovisionará el archivo de configuración de Surface UEFI en el firmware del dispositivo.
2. Active la casilla acepto los **términos del contrato de licencia** para aceptar el contrato de licencia para el usuario final (CLUF) y, a continuación, haga clic en **instalar** para iniciar el proceso de instalación.
3. Haga clic en **Finalizar** para completar la instalación del paquete de configuración de Surface UEFI y reinicie el dispositivo Surface cuando se le pida.
4. Surface UEFI cargará el archivo de configuración y determinará que SEMM no está habilitado en el dispositivo. Surface UEFI comenzará el proceso de inscripción SEMM de la siguiente manera:
   * Surface UEFI comprobará que el archivo de configuración SEMM contiene un certificado de SEMM.
   * Surface UEFI le pedirá que escriba los dos últimos caracteres de la huella digital del certificado para confirmar la inscripción del dispositivo Surface en SEMM, como se muestra en la ilustración 8.

      ![La inscripción de SEMM requiere los últimos dos caracteres de la huella digital del certificado](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. La inscripción en SEMM requiere los dos últimos caracteres de la huella digital del certificado*

   * Surface UEFI almacenará el certificado SEMM en firmware y aplicará los valores de configuración que se especifican en el archivo de configuración Surface UEFI.
   
5. El dispositivo Surface ya se ha inscrito en SEMM y se iniciará en Windows.

Puede comprobar que un dispositivo de superficie se ha inscrito correctamente en SEMM buscando el paquete de **configuración de surfaces de Microsoft** en **programas y características** (como se muestra en la figura 9), o en los eventos almacenados en el registro de **configuramiento UEFI de Microsoft Surface** , que se encuentra en **registros de aplicaciones y servicios** en el visor de eventos (como se muestra en la ilustración 10).

![Comprobar la inscripción del dispositivo Surface en SEMM en programas y características](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Figura 9. Comprobar la inscripción de un dispositivo Surface en SEMM en programas y características*

![Comprobar la inscripción del dispositivo Surface en SEMM en el visor de eventos](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Figura 10. Comprobar la inscripción de un dispositivo Surface en SEMM en el visor de eventos*

También puede comprobar que el dispositivo se ha inscrito en SEMM Surface UEFI: mientras el dispositivo está inscrito, Surface UEFI contendrá la página de administración de la **empresa** (como se muestra en la ilustración 11).

![Página de administración de empresa de Surface UEFI](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Figura 11. Página de administración de la superficie UEFI Enterprise*


## Configurar la configuración de Surface UEFI con SEMM

Después de que un dispositivo se haya inscrito en SEMM, puede ejecutar paquetes de configuración de Surface UEFI firmados con el mismo certificado SEMM para aplicar la nueva configuración de Surface UEFI. Esta configuración se aplicará automáticamente la próxima vez que se inicie el dispositivo, sin ninguna interacción del usuario. Puede usar soluciones de implementación de aplicaciones como Microsoft Endpoint Configuration Manager para implementar paquetes de configuración de Surface UEFI en dispositivos Surface para cambiar o administrar la configuración en Surface UEFI.

Para obtener más información sobre cómo implementar archivos de Windows Installer (. msi) con Configuration Manager, vea [implementación y administración de aplicaciones con el administrador de configuración de Microsoft Endpoint](https://technet.microsoft.com/library/mt627959).

Si la superficie protegida UEFI con una contraseña, los usuarios sin la contraseña que intente arrancar en Surface UEFI solo tendrán la información del **PC**, **sobre**, **Administración empresarial**y páginas de **salida** .

Si no ha protegido la superficie UEFI con una contraseña o un usuario la escribe correctamente, la configuración que está configurada con SEMM estará atenuada (no disponible) y el texto la organización administrará la configuración en la parte superior de la página, tal como se muestra en la ilustración 12.

![Configuración administrada por SEMM deshabilitada en Surface UEFI](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Figura 12. La configuración administrada por SEMM se deshabilitará en Surface UEFI*

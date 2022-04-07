---
title: Inscribir y configurar dispositivos Surface con SEMM (Surface)
description: Aprende a crear un paquete de configuración de UEFI de Surface para controlar la configuración de Surface UEFI, así como a inscribir un dispositivo Surface en SEMM.
keywords: administración de surface enterprise
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 6df11e1c6e0b28616cb4d365e159f134195c0ecb
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472400"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>Inscribir y configurar los dispositivos Surface con SEMM

Con el Modo de administración de Microsoft Surface Enterprise (SEMM), puedes configurar de forma segura la configuración de Surface UEFI en un dispositivo Surface y administrar esa configuración en dispositivos Surface de tu organización. Cuando se administra un dispositivo Surface mediante SEMM, ese dispositivo se considera *inscrito* (a veces denominado activado). En este artículo se muestra cómo crear un paquete de configuración de UEFI de Surface que controlará la configuración de Surface UEFI e inscribirá un dispositivo Surface en SEMM.

Para obtener información general más general sobre SEMM, consulta [Microsoft Surface Enterprise Management Mode(Modo de administración de Microsoft Surface Enterprise).](surface-enterprise-management-mode.md)

Como alternativa a SEMM, los dispositivos Surface más recientes admiten la administración remota de un subconjunto de configuraciones de firmware a través de Microsoft Intune. Para obtener más información, consulte [administración Intune de la configuración de UEFI de Surface](surface-manage-dfci-guide.md).

> [!NOTE]
> SEMM solo se admite en Surface Pro X a través de UEFI Manager. Para obtener más información, consulte [Implementación, administración y mantenimiento Surface Pro X](surface-pro-arm-app-management.md).

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>Descarga e instalación de Microsoft Surface UEFI Configurator

La herramienta que se usa para crear paquetes SEMM es Microsoft Surface UEFI Configurator. Puedes descargar Microsoft Surface UEFI Configurator desde la página [Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) del Centro de descarga de Microsoft.
Ejecute el archivo del Instalador de Windows (.msi) de Microsoft Surface UEFI Configurator para iniciar la instalación de la herramienta. Cuando se complete el instalador, busca Microsoft Surface UEFI Configurator en la sección Todas las aplicaciones de tu menú Inicio.

>[!NOTE]
>Microsoft Surface UEFI Configurator solo se admite en Windows 10 y Windows 11.

## <a name="create-a-surface-uefi-configuration-package"></a>Creación de un paquete de configuración de SURFACE UEFI

El paquete de configuración de UEFI de Surface desempeña el rol de aplicar una nueva configuración de configuración de UEFI de Surface a un dispositivo Surface administrado con SEMM y el rol de inscribir dispositivos Surface en SEMM. La creación de un paquete de configuración requiere que tengas un certificado de firma que se usará con SEMM para proteger la configuración de la configuración de UEFI en cada dispositivo Surface. Para obtener más información sobre los requisitos del certificado SEMM, consulta [Modo de administración de Microsoft Surface Enterprise](surface-enterprise-management-mode.md).

Para crear un paquete de configuración de UEFI de Surface, siga estos pasos:

1. Abra Microsoft Surface UEFI Configurator desde el menú Inicio.

2. Haz clic en **Inicio**.

3. Haga clic en **Paquete de configuración**, como se muestra en la figura 1.

   ![Cree un paquete para la inscripción de SEMM.](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Seleccione Paquete de configuración para crear un paquete para la inscripción y configuración de SEMM.*

4. Haga clic en **Protección de** certificados para agregar el archivo de certificado exportado con clave privada (.pfx), como se muestra en la figura 2. Vaya a la ubicación del archivo de certificado, seleccione el archivo y haga clic en **Aceptar**.

   ![Agregue el certificado SEM y la contraseña de UEFI de Surface al paquete de configuración.](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to the configuration package")

   *Figura 2. Agregar el certificado SEMM y la contraseña de UEFI de Surface al paquete de configuración de SURFACE UEFI*

5. Cuando se le pida que confirme la contraseña del certificado, escriba y confirme la contraseña del archivo de certificado y, a continuación, haga clic en **Aceptar**.

6. Haga clic en **Protección con contraseña** para agregar una contraseña a Surface UEFI. Esta contraseña será necesaria cada vez que arranque en UEFI. Si no se especifica esta contraseña, solo se mostrará la **información del equipo**, **Acerca** de, **administración Enterprise** y **Salir**. Esto es opcional.

7. Cuando se le solicite, escriba y confirme la contraseña elegida para Surface UEFI y, a continuación, haga clic en **Aceptar**. Deje el campo contraseña en blanco si desea borrar una contraseña UEFI de Surface existente.

8. Si no quieres que el paquete UEFI de Surface se aplique a un dispositivo determinado, en la página **Elegir qué tipo de surface quieres dirigir** , haz clic en el control deslizante situado debajo del dispositivo correspondiente para que esté en la posición **Desactivado** , como se muestra en la figura 3.
   > [!TIP] 
   > Debe seleccionar un dispositivo, ya que ninguno está seleccionado de forma predeterminada. Desplácese a la derecha para ver todos los dispositivos disponibles.

   ![Elija dispositivos para la compatibilidad de paquetes y desplácese a la derecha para ver todos los dispositivos disponibles.](images/surface-semm-enroll-fig3.png "Choose devices for package compatibility")

   ![Elija dispositivos para la compatibilidad de paquetes.](images/surface-semm-enroll-fig3a.png "Choose devices for package compatibility")


   *Figura 3. Elección de los dispositivos para la compatibilidad de paquetes*

9. Haz clic en **Siguiente**.

10. Si quieres desactivar un componente en dispositivos Surface administrados, en la página **Elegir qué componentes quieres activar o desactivar** , haz clic en el control deslizante situado junto a cualquier dispositivo o grupo de dispositivos que quieras desactivar para que el control deslizante esté en la posición **Desactivado** . (Se muestra en la figura 4). La configuración predeterminada para cada dispositivo es **On**. Haga clic en el botón **Restablecer** para devolver todos los controles deslizantes a la posición predeterminada.

    ![Deshabilita o habilita los componentes de Surface.](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Deshabilitar o habilitar componentes de Surface individuales*

11. Haz clic en **Siguiente**.

12. Para habilitar o deshabilitar las opciones avanzadas en Surface UEFI o la visualización de páginas DE UEFI de Surface, en la página **Elegir la configuración avanzada de los dispositivos** , haga clic en el control deslizante situado junto a la configuración deseada para configurar esa opción en **Activado** o **Desactivado** (que se muestra en la figura 5). En la sección **Página principal de UEFI** , puedes usar los controles deslizantes de **Seguridad**, **Dispositivos** y **Arranque** para controlar qué páginas están disponibles para los usuarios que arrancan en Surface UEFI. (Para obtener más información sobre la configuración de UEFI de Surface, consulta [Administrar la configuración de UEFI de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)). Cuando haya terminado de seleccionar las opciones para generar y guardar el paquete, haga clic en **Compilar**. 

    ![Controla la configuración avanzada de Surface UEFI y las páginas ueFI de Surface.](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar la configuración avanzada de Surface UEFI y las páginas ueFI de Surface con SEMM*

13. En el cuadro de diálogo **Guardar como** , especifique el nombre del paquete de configuración de UEFI de Surface, vaya a la ubicación donde desea guardar el archivo y haga clic en **Guardar**.

14. Cuando se crea y guarda el paquete, se muestra la página **Correcto** .

    >[!NOTE]
    >Registre los caracteres de huella digital del certificado que se muestran en esta página, como se muestra en la figura 6. Necesitarás estos caracteres para confirmar la inscripción de nuevos dispositivos Surface en SEMM. Haga clic en **Finalizar** para completar la creación de paquetes y cierre Microsoft Surface UEFI Configurator.
    
    ![Visualización de caracteres de huella digital de certificado.](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *Figura 6. Los dos últimos caracteres de la huella digital del certificado se muestran en la página Correcto*

Ahora que ha creado el paquete de configuración de UEFI de Surface, puede inscribir o configurar dispositivos Surface.

>[!NOTE]
>Cuando se crea un paquete de configuración de UEFI de Surface, se muestra un archivo de registro en el escritorio con detalles de la configuración y las opciones del paquete de configuración.

## <a name="enroll-a-surface-device-in-semm"></a>Inscripción de un dispositivo Surface en SEMM
Cuando se ejecuta el paquete de configuración de UEFI de Surface, el certificado SEMM y los archivos de configuración de UEFI de Surface se almacenan provisionalmente en el almacenamiento de firmware del dispositivo Surface. Cuando se reinicia el dispositivo Surface, Surface UEFI procesa estos archivos y comienza el proceso de aplicación de la configuración de UEFI de Surface o inscripción del dispositivo Surface en SEMM, como se muestra en la figura 7.

![Proceso SEMM para la configuración de LA UEFI de Surface o la inscripción.](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. El proceso SEMM para la configuración de Surface UEFI o la inscripción de un dispositivo Surface*

Antes de inscribir un dispositivo Surface en SEMM, asegúrese de que tiene a mano los dos últimos caracteres de la huella digital del certificado. Necesitará estos caracteres para confirmar la inscripción del dispositivo (consulte la figura 6).

Para inscribir un dispositivo Surface en SEMM con un paquete de configuración de UEFI de Surface, siga estos pasos:

1. Ejecuta el archivo de .msi del paquete de configuración de UEFI de Surface en el dispositivo Surface que quieres inscribir en SEMM. Esto aprovisionará el archivo de configuración de UEFI de Surface en el firmware del dispositivo.
2. Active la casilla **Acepto los términos en el Contrato de licencia** para aceptar el Contrato de licencia de usuario final (CLUF) y haga clic en **Instalar** para comenzar el proceso de instalación.
3. Haz clic en **Finalizar** para completar la instalación del paquete de configuración de UEFI de Surface y reinicia el dispositivo Surface cuando se te pida que lo hagas.
4. Surface UEFI cargará el archivo de configuración y determinará que SEMM no está habilitado en el dispositivo. A continuación, Surface UEFI iniciará el proceso de inscripción de SEMM, como se indica a continuación:
   * Surface UEFI comprobará que el archivo de configuración SEMM contiene un certificado SEMM.
   * Surface UEFI te pedirá que escribas los dos últimos caracteres de la huella digital del certificado para confirmar la inscripción del dispositivo Surface en SEMM, como se muestra en la figura 8.

      ![La inscripción de SEMM requiere los dos últimos caracteres de la huella digital del certificado.](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. La inscripción de SEMM requiere los dos últimos caracteres de la huella digital del certificado.*

   * Surface UEFI almacenará el certificado SEMM en el firmware y aplicará los valores de configuración especificados en el archivo de configuración de Surface UEFI.
   
5. El dispositivo Surface ahora está inscrito en SEMM y arrancará en Windows.

Para comprobar que un dispositivo Surface se ha inscrito correctamente en SEMM, busque Paquete de configuración de **Microsoft Surface** en **Programas y características** (como se muestra en la figura 9) o en los eventos almacenados en el registro **configurador de UEFI de Microsoft Surface**, que se encuentran en **Registros de aplicaciones y servicios** en Visor de eventos (como se muestra en la figura 10).

:::image type="content" alt-text="Compruebe la inscripción del dispositivo Surface en SEMM en Programas y características." source="images/surface-semm-enroll-fig9.png":::

*Figura 9. Comprobar la inscripción de un dispositivo Surface en SEMM en Programas y características*

:::image type="content" alt-text="Compruebe la inscripción del dispositivo Surface en SEMM en Visor de eventos." source="images/surface-semm-enroll-fig10.png":::

*Figura 10. Compruebe la inscripción de un dispositivo Surface en SEMM en Visor de eventos*

También puedes comprobar que el dispositivo está inscrito en SEMM en Surface UEFI; mientras el dispositivo está inscrito, Surface UEFI contendrá la página **de administración de Enterprise** (como se muestra en la figura 11).

:::image type="content" alt-text="Página de administración de Enterprise DE UEFI de Surface." source="images/surface-semm-enroll-fig11.png":::

*Figura 11. Página de administración de la Enterprise DE UEFI de Surface*


## <a name="configure-surface-uefi-settings-with-semm"></a>Configuración de la UEFI de Surface con SEMM

Después de inscribir un dispositivo en SEMM, puedes ejecutar paquetes de configuración de UEFI de Surface firmados con el mismo certificado SEMM para aplicar la nueva configuración de UEFI de Surface. Esta configuración se aplica automáticamente la próxima vez que se inicia el dispositivo, sin ninguna interacción del usuario. Puedes usar soluciones de implementación de aplicaciones como Microsoft Endpoint Configuration Manager para implementar paquetes de configuración de UEFI de Surface en dispositivos Surface para cambiar o administrar la configuración en Surface UEFI.

Para obtener más información sobre cómo implementar archivos del Instalador de Windows (.msi) con Configuration Manager, consulte [Implementación y administración de aplicaciones con Microsoft Endpoint Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications).

Supongamos que ha protegido Surface UEFI con una contraseña. En ese caso, los usuarios sin la contraseña que intenten arrancar en Surface UEFI solo tendrán la **información del equipo**, **Acerca** de, **Enterprise administración** y **Salir** de las páginas que se les muestran.

Si no has protegido Surface UEFI con una contraseña o un usuario escribe la contraseña correctamente, la configuración configurada con SEMM se atenuará (no está disponible) lo que indica que  **tu organización administra algunas configuraciones**, como se muestra en la figura 12.

:::image type="content" alt-text="Configuración administrados por SEMM están deshabilitados en Surface UEFI." source="images/surface-semm-enroll-fig12.png":::

*Figura 12. Configuración administrado por SEMM se deshabilitará en Surface UEFI*

---
title: Inscribir y configurar dispositivos Surface con SEMM (Surface)
description: Aprende a crear un paquete de configuración de UEFI de Surface para controlar la configuración de UEFI de Surface, así como a inscribir un dispositivo Surface en SEMM.
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
ms.openlocfilehash: 61b15bf1d7ae5f99d57fb4dcd7bd9f83d9eb4b0a
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337943"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>Inscribir y configurar los dispositivos Surface con SEMM

Con el Modo de administración de Microsoft Surface Enterprise (SEMM), puedes configurar de forma segura la configuración de UEFI de Surface en un dispositivo Surface y administrar esa configuración en dispositivos Surface de tu organización. Cuando se administra un dispositivo Surface mediante SEMM, ese dispositivo se considera *inscrito (a* veces denominado activado). En este artículo se muestra cómo crear un paquete de configuración de UEFI de Surface que no solo controlará la configuración de UEFI de Surface, sino que también inscribirá un dispositivo Surface en SEMM.

Para obtener una introducción más general de SEMM, consulta [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Como alternativa a SEMM, los dispositivos Surface más recientes admiten la administración remota de un subconjunto de configuraciones de firmware mediante Microsoft Intune. Para obtener más información, consulte [Administración de Intune de la configuración de UEFI de Surface](surface-manage-dfci-guide.md).

> [!NOTE]
> SEMM solo se admite Surface Pro X a través del Administrador de UEFI. Para obtener más información, consulte [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>Descargar e instalar Microsoft Surface UEFI Configurator

La herramienta usada para crear paquetes SEMM es Microsoft Surface UEFI Configurator. Puedes descargar Microsoft Surface UEFI Configurator desde la página [Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703) en el Centro de descarga de Microsoft.
Ejecute el archivo configurador de UEFI de Microsoft Surface Windows Installer (.msi) para iniciar la instalación de la herramienta. Cuando se complete el instalador, busca Microsoft Surface UEFI Configurator en la sección Todas las aplicaciones de tu menú Inicio.

>[!NOTE]
>Microsoft Surface UEFI Configurator solo se admite en Windows 10.

## <a name="create-a-surface-uefi-configuration-package"></a>Crear un paquete de configuración de UEFI de Surface

El paquete de configuración de UEFI de Surface realiza el rol de aplicar una nueva configuración de configuración de UEFI de Surface a un dispositivo Surface administrado con SEMM y el rol de inscribir dispositivos Surface en SEMM. La creación de un paquete de configuración requiere que tenga un certificado de firma que se usará con SEMM para proteger la configuración de la configuración de UEFI en cada dispositivo Surface. Para obtener más información acerca de los requisitos para el certificado SEMM, consulta [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

Para crear un paquete de configuración de UEFI de Surface, sigue estos pasos:

1. Abra Microsoft Surface UEFI Configurator desde el menú Inicio.

2. Haz clic en **Inicio**.

3. Haga **clic en Paquete de** configuración, tal como se muestra en la figura 1.

   ![Cree un paquete para la inscripción de SEMM.](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Seleccione Paquete de configuración para crear un paquete para la inscripción y configuración de SEMM*

4. Haga **clic en Protección de** certificados para agregar el archivo de certificado exportado con clave privada (.pfx), como se muestra en la figura 2. Vaya a la ubicación del archivo de certificado, seleccione el archivo y, a continuación, haga clic en **Aceptar**.

   ![Agrega el certificado SEM y la contraseña de UEFI de Surface al paquete de configuración.](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figura 2. Agregar el certificado SEMM y la contraseña de UEFI de Surface a un paquete de configuración de UEFI de Surface*

5. Cuando se le pida que confirme la contraseña del certificado, escriba y confirme la contraseña del archivo de certificado y, a continuación, haga clic en **Aceptar**.

6. Haz **clic en Protección con** contraseña para agregar una contraseña a Surface UEFI. Esta contraseña será necesaria siempre que arranque en UEFI. Si no se introduce esta contraseña, solo se mostrará la información del **equipo, Acerca** **de,****** **Enterprise administración y** Salir de las páginas. Esto es opcional.

7. Cuando se te pida, escribe y confirma la contraseña elegida para UEFI de Surface y, a continuación, haz clic en **Aceptar**. Si quieres borrar una contraseña de UEFI de Surface existente, deja el campo de contraseña en blanco.

8. Si no quieres que el paquete UEFI de Surface se aplique a un dispositivo determinado, en la página Elegir el tipo de **Surface** al que quieres dirigirte, haz clic en el control deslizante situado debajo del dispositivo **** correspondiente para que esté en la posición Desactivado, como se muestra en la figura 3.
   > [!TIP] 
   > Debes seleccionar un dispositivo porque ninguno está seleccionado de forma predeterminada.

   ![Elija dispositivos para la compatibilidad de paquetes.](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figura 3. Elegir los dispositivos para la compatibilidad de paquetes*

9. Haz clic en **Siguiente**.

10. Si quieres desactivar un componente en dispositivos Surface administrados, en la **** página Elegir qué componentes quieres activar o desactivar, haz clic en el control deslizante junto a cualquier dispositivo o grupo de dispositivos que quieras desactivar para que el control deslizante **** esté en la posición Desactivado. (Se muestra en la figura 4). La configuración predeterminada para cada dispositivo es **On**. Haga clic **en el botón** Restablecer si desea devolver todos los controles deslizantes a la posición predeterminada.

    ![Deshabilita o habilita los componentes de Surface.](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Deshabilitar o habilitar componentes individuales de Surface*

11. Haz clic en **Siguiente**.

12. Para habilitar o deshabilitar opciones avanzadas en La UEFI de Surface o en la presentación de páginas UEFI de **** Surface, en la página Elegir la configuración avanzada de los dispositivos, haga clic en el control deslizante situado junto a la configuración deseada para configurar esa opción en **Activar** o **Desactivar (que** se muestra en la figura 5). En la **sección Página principal de UEFI**, puedes usar los controles deslizantes de **Seguridad, Dispositivos** y **Arranque** para controlar qué páginas están disponibles para los usuarios que inician en UeFI de Surface. **** (Para obtener más información acerca de la configuración de UEFI de Surface, consulta [Administrar la configuración de UEFI de Surface](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)). Haga **clic en** Generar cuando haya terminado de seleccionar las opciones para generar y guardar el paquete.

    ![Controla la configuración avanzada de UEFI de Surface y las páginas uefi de Surface.](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar la configuración avanzada de UEFI de Surface y las páginas uefi de Surface con SEMM*

13. En el **cuadro de diálogo** Guardar como, especifique un nombre para el paquete de configuración de UEFI de Surface, vaya a la ubicación donde desea guardar el archivo y, a continuación, haga clic en **Guardar**.

14. Cuando se crea y guarda el paquete, se muestra **la página** Correcto.

    >[!NOTE]
    >Registre los caracteres de huella digital del certificado que se muestran en esta página, como se muestra en la figura 6. Necesitarás estos caracteres para confirmar la inscripción de nuevos dispositivos Surface en SEMM. Haz **clic en** Finalizar para completar la creación del paquete y cerrar Microsoft Surface UEFI Configurator.
    
    ![Visualización de caracteres de huella digital de certificado.](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *Figura 6. Los dos últimos caracteres de la huella digital del certificado se muestran en la página Correcto*

Ahora que has creado el paquete de configuración de Surface UEFI, puedes inscribir o configurar dispositivos Surface.

>[!NOTE]
>Cuando se crea un paquete de configuración de UEFI de Surface, se crea un archivo de registro en el escritorio con detalles de las opciones y las opciones del paquete de configuración.

## <a name="enroll-a-surface-device-in-semm"></a>Inscribir un dispositivo Surface en SEMM
Cuando se ejecuta el paquete de configuración de UEFI de Surface, el certificado SEMM y los archivos de configuración de Surface UEFI se programan en el almacenamiento de firmware del dispositivo Surface. Cuando se reinicia el dispositivo Surface, Surface UEFI procesa estos archivos e inicia el proceso de aplicar la configuración de UEFI de Surface o inscribir el dispositivo Surface en SEMM, como se muestra en la figura 7.

![Proceso SEMM para la configuración de La UEFI de Surface o la inscripción.](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. El proceso SEMM para la configuración de UEFI de Surface o la inscripción de un dispositivo Surface*

Antes de comenzar el proceso para inscribir un dispositivo Surface en SEMM, asegúrate de tener a mano los dos últimos caracteres de la huella digital del certificado. Necesitarás estos caracteres para confirmar la inscripción del dispositivo (consulta la figura 6).

Para inscribir un dispositivo Surface en SEMM con un paquete de configuración de UEFI de Surface, sigue estos pasos:

1. Ejecuta el paquete de configuración uefi de Surface .msi archivo en el dispositivo Surface que quieras inscribir en SEMM. Esto aprovisionará el archivo de configuración de UEFI de Surface en el firmware del dispositivo.
2. Active la **casilla Acepto** los términos de la casilla Contrato de licencia para aceptar el Contrato de licencia de usuario final (CLUF****) y, a continuación, haga clic en Instalar para iniciar el proceso de instalación.
3. Haz **clic en** Finalizar para completar la instalación del paquete de configuración de UEFI de Surface y reinicia el dispositivo Surface cuando se te pida que lo hagas.
4. Surface UEFI cargará el archivo de configuración y determinará que SEMM no está habilitado en el dispositivo. A continuación, UEFI de Surface iniciará el proceso de inscripción de SEMM, como se muestra a continuación:
   * La UEFI de Surface comprobará que el archivo de configuración de SEMM contiene un certificado SEMM.
   * Uefi de Surface te pedirá que escribas los dos últimos caracteres de la huella digital del certificado para confirmar la inscripción del dispositivo Surface en SEMM, como se muestra en la figura 8.

      ![La inscripción de SEMM requiere los dos últimos caracteres de huella digital del certificado.](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. La inscripción en SEMM requiere los dos últimos caracteres de la huella digital del certificado*

   * Surface UEFI almacenará el certificado SEMM en el firmware y aplicará las opciones de configuración especificadas en el archivo de configuración de Surface UEFI.
   
5. El dispositivo Surface ahora está inscrito en SEMM y se arrancará a Windows.

Puedes comprobar que un dispositivo Surface se ha inscrito correctamente en SEMM buscando el paquete de configuración de **Microsoft Surface** en Programas y **características (como** se muestra en la figura 9) o en los eventos almacenados en el registro del Configurador **UEFI de Microsoft Surface** , que se encuentra en **Registros** de aplicaciones y servicios en el Visor de eventos (como se muestra en la figura 10).

:::image type="content" alt-text="Comprueba la inscripción del dispositivo Surface en SEMM en Programas y características." source="images/surface-semm-enroll-fig9.png":::

*Figura 9. Comprobar la inscripción de un dispositivo Surface en SEMM en Programas y características*

:::image type="content" alt-text="Comprueba la inscripción del dispositivo Surface en SEMM en el Visor de eventos." source="images/surface-semm-enroll-fig10.png":::

*Figura 10. Comprobar la inscripción de un dispositivo Surface en SEMM en el Visor de eventos*

También puedes comprobar que el dispositivo está inscrito en SEMM en Surface UEFI; mientras el dispositivo está inscrito, Surface UEFI contendrá la página de administración de **Enterprise** (como se muestra en la figura 11).

:::image type="content" alt-text="Página de administración Enterprise UEFI de Surface." source="images/surface-semm-enroll-fig11.png":::

*Figura 11. Página de administración de Enterprise UEFI de Surface*


## <a name="configure-surface-uefi-settings-with-semm"></a>Configuración de la UEFI de Surface con SEMM

Después de inscribir un dispositivo en SEMM, puedes ejecutar paquetes de configuración de UEFI de Surface firmados con el mismo certificado SEMM para aplicar la nueva configuración de UEFI de Surface. Esta configuración se aplica automáticamente la próxima vez que se inicie el dispositivo, sin ninguna interacción del usuario. Puedes usar soluciones de implementación de aplicaciones como Microsoft Endpoint Configuration Manager implementar paquetes de configuración de UEFI de Surface en dispositivos Surface para cambiar o administrar la configuración en UEFI de Surface.

Para obtener más información acerca de cómo implementar Windows installer (.msi) con Configuration Manager, vea [Deploy and manage applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).

Si has protegido La UEFI de Surface con una contraseña, los usuarios sin la contraseña que intenten arrancar en UEFI de Surface solo tendrán la información del **equipo****, Información**, administración de **Enterprise** y **** Páginas de salida que se les mostrarán.

Si no has protegido La UEFI de Surface con una contraseña o un usuario escribe la contraseña correctamente, las opciones configuradas con SEMM se atenuarán (no estarán disponibles) y el texto Algunas opciones de configuración administradas por la organización se mostrarán en la parte superior de la página, como se muestra en la figura 12.

:::image type="content" alt-text="Configuración administrado por SEMM deshabilitado en Surface UEFI." source="images/surface-semm-enroll-fig12.png":::

*Figura 12. Configuración administrado por SEMM se deshabilitará en UEFI de Surface*

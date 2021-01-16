---
title: Inscribir y configurar dispositivos Surface con SEMM (Surface)
description: Aprende a crear un paquete de configuración de UEFI de Surface para controlar la configuración de la UEFI de Surface, así como inscribir un dispositivo Surface en SEMM.
keywords: administración de surface Enterprise
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
ms.openlocfilehash: f310b4a43a8a0fc0e77295344ac723770ce821bc
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271067"
---
# Inscribir y configurar los dispositivos Surface con SEMM

Con el Modo de administración de Microsoft Surface Enterprise (SEMM), puedes configurar de forma segura la configuración de la UEFI de Surface en un dispositivo Surface y administrar esa configuración en dispositivos Surface de la organización. Cuando se administra un dispositivo Surface mediante SEMM, ese dispositivo se considera inscrito *(a* veces denominado activado). En este artículo se muestra cómo crear un paquete de configuración de LA UEFI de Surface que no solo controlará la configuración de la UEFI de Surface, sino que también inscribirá un dispositivo Surface en SEMM.

Para obtener información general más detallada sobre SEMM, consulta [El modo de administración de Microsoft Surface Enterprise.](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)

Como alternativa a SEMM, los dispositivos Surface más recientes admiten la administración remota de un subconjunto de configuraciones de firmware a través de Microsoft Intune. Para obtener más información, consulta la administración [de Intune de la configuración de LA UEFI de Surface.](surface-manage-dfci-guide.md)

> [!NOTE]
> SEMM solo se admite en Surface Pro X a través del Administrador de UEFI. Para obtener más información, consulta [Implementación, administración y mantenimiento de Surface Pro X.](surface-pro-arm-app-management.md)

#### Descargar e instalar el Configurador de UEFI de Microsoft Surface

La herramienta que se usa para crear paquetes SEMM es Microsoft Surface UEFI Configurator. Puedes descargar el Configurador de UEFI de Microsoft Surface desde la página Herramientas [de Surface](https://www.microsoft.com/download/details.aspx?id=46703) para TI en el Centro de descarga de Microsoft.
Ejecuta el archivo del Configurador de UEFI de Microsoft Surface para Windows Installer (.msi) para iniciar la instalación de la herramienta. Cuando se complete el instalador, busca el Configurador de UEFI de Microsoft Surface en la sección Todas las aplicaciones del menú Inicio.

>[!NOTE]
>El Configurador de UEFI de Microsoft Surface solo se admite en Windows 10.

## Crear un paquete de configuración de LA UEFI de Surface

El paquete de configuración de LA UEFI de Surface realiza el rol de aplicar una nueva configuración de la configuración de LA UEFI de Surface a un dispositivo Surface administrado con SEMM y el rol de inscribir dispositivos Surface en SEMM. La creación de un paquete de configuración requiere que tenga un certificado de firma que se usará con SEMM para proteger la configuración de las opciones de UEFI en cada dispositivo Surface. Para obtener más información sobre los requisitos para el certificado SEMM, consulta El modo de administración [de Microsoft Surface Enterprise.](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)

Para crear un paquete de configuración de UEFI de Surface, sigue estos pasos:

1. Abre el Configurador de UEFI de Microsoft Surface desde el menú Inicio.
2. Haz clic en **Inicio**.
3. Haga **clic en Paquete de**configuración, como se muestra en la figura 1.

   ![Crear un paquete para la inscripción de SEMM](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *Figura 1. Selecciona Paquete de configuración para crear un paquete para la inscripción y configuración de SEMM*

4. Haga **clic en Protección de** certificados para agregar el archivo de certificado exportado con clave privada (.pfx), como se muestra en la figura 2. Vaya a la ubicación del archivo de certificado, seleccione el archivo y, a continuación, haga clic en **Aceptar.**

   ![Agregar el certificado SEM y la contraseña de la UEFI de Surface al paquete de configuración](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *Figura 2. Agregar el certificado SEMM y la contraseña de LA UEFI de Surface a un paquete de configuración de LA UEFI de Surface*

5. Cuando se le pida que confirme la contraseña del certificado, escriba y confirme la contraseña del archivo de certificado y, a continuación, haga clic en **Aceptar**.
6. Haz **clic en Protección con** contraseña para agregar una contraseña a la UEFI de Surface. Esta contraseña será necesaria siempre que arranques en UEFI. Si no se introduce esta contraseña, solo se mostrará **** la información del **equipo** **,** Acerca de , **Administración**empresarial y Salir de las páginas. Esto es opcional.
7. Cuando se te solicite, escribe y confirma la contraseña elegida para UEFI de Surface y, a continuación, haz clic en **Aceptar.** Si quieres borrar una contraseña de UEFI de Surface existente, deja el campo de contraseña en blanco.
8. Si no quieres que el paquete de UEFI de Surface se aplique a un dispositivo concreto, en la página Elegir el tipo de **Surface** al que quieres dirigirte, haz clic en el control deslizante debajo de la imagen correspondiente de Surface Book o Surface Pro 4 para que esté en la posición Fuera. **** (Como se muestra en la figura 3).
   > [!NOTE] 
   > Debes seleccionar un dispositivo ya que ninguno está seleccionado de forma predeterminada.

   ![Elegir dispositivos para la compatibilidad de paquetes](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *Figura 3. Elegir los dispositivos para la compatibilidad de paquetes*

9. Haz clic en **Siguiente**.
10. Si quieres desactivar un componente en dispositivos **** Surface administrados, en la página Elegir qué componentes quieres activar o desactivar, haz clic en **** el control deslizante junto a cualquier dispositivo o grupo de dispositivos que quieras desactivar para que el control deslizante esté en la posición Desactivado. (Se muestra en la figura 4). La configuración predeterminada para cada dispositivo está **activa.** Haz clic **en el** botón Restablecer si quieres devolver todos los controles deslizantes a la posición predeterminada.

    ![Deshabilitar o habilitar componentes de Surface](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *Figura 4. Deshabilitar o habilitar componentes individuales de Surface*

11. Haz clic en **Siguiente**.
12. Para habilitar o deshabilitar opciones avanzadas en la UEFI de **** Surface o en la visualización de páginas de UEFI de **** Surface, en la página Elegir la configuración avanzada de los dispositivos, haz clic en el control deslizante situado junto a la configuración deseada para configurar esa opción en Activar o desactivar **(se** muestra en la figura 5). En la sección página frontal de **UEFI,** puedes **** usar **** los controles deslizantes de **seguridad,** dispositivos y arranque para controlar qué páginas están disponibles para los usuarios que arrancan en la UEFI de Surface. (Para obtener más información sobre la configuración de LA UEFI de Surface, consulta [Administrar la configuración de LA UEFI de Surface).](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings) Haz **clic en** Generar cuando termines de seleccionar las opciones para generar y guardar el paquete.

    ![Controlar la configuración avanzada de LA UEFI de Surface y las páginas de UEFI de Surface](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *Figura 5. Controlar la configuración avanzada de la UEFI de Surface y las páginas de LA UEFI de Surface con SEMM*

13. En el **cuadro de diálogo** Guardar como, especifica un nombre para el paquete de configuración de LA UEFI de Surface, busca la ubicación donde quieres guardar el archivo y, a continuación, haz clic en **Guardar**.
14. Cuando se crea y se guarda el paquete, **se** muestra la página Correcto.

>[!NOTE]
>Registre los caracteres de huella digital del certificado que se muestran en esta página, como se muestra en la figura 6. Necesitarás estos caracteres para confirmar la inscripción de nuevos dispositivos Surface en SEMM. Haz **clic en Finalizar** para completar la creación del paquete y cerrar el Configurador de UEFI de Microsoft Surface.

![Visualización de caracteres de huella digital de certificado](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*Figura 6. Los dos últimos caracteres de la huella digital del certificado se muestran en la página Correcto*

Ahora que has creado el paquete de configuración de LA UEFI de Surface, puedes inscribir o configurar dispositivos Surface.

>[!NOTE]
>Cuando se crea un paquete de configuración de UEFI de Surface, se crea un archivo de registro en el escritorio con detalles de las opciones y opciones del paquete de configuración.

## Inscribir un dispositivo Surface en SEMM
Cuando se ejecuta el paquete de configuración de LA UEFI de Surface, el certificado SEMM y los archivos de configuración de LA UEFI de Surface se ejecutan por fases en el almacenamiento de firmware del dispositivo Surface. Cuando el dispositivo Surface se reinicia, La UEFI de Surface procesa estos archivos y comienza el proceso de aplicar la configuración de la UEFI de Surface o inscribir el dispositivo Surface en SEMM, como se muestra en la figura 7.

![Proceso de SEMM para la configuración de la UEFI o la inscripción de Surface](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*Figura 7. Proceso de SEMM para la configuración de la UEFI de Surface o la inscripción de un dispositivo Surface*

Antes de comenzar el proceso para inscribir un dispositivo Surface en SEMM, asegúrate de tener a mano los dos últimos caracteres de la huella digital del certificado. Necesitarás estos caracteres para confirmar la inscripción del dispositivo (consulta la figura 6).

Para inscribir un dispositivo Surface en SEMM con un paquete de configuración de LA UEFI de Surface, sigue estos pasos:

1. Ejecuta el archivo .msi del paquete de configuración de UEFI de Surface en el dispositivo Surface que quieras inscribir en SEMM. Esto aprovisionará el archivo de configuración de LA UEFI de Surface en el firmware del dispositivo.
2. Active la **casilla Acepto los** términos de la casilla contrato de licencia **** para aceptar el Contrato de licencia para el usuario final (CLUF) y, a continuación, haga clic en Instalar para iniciar el proceso de instalación.
3. Haz **clic en** Finalizar para completar la instalación del paquete de configuración de LA UEFI de Surface y reinicia el dispositivo Surface cuando se te pida que lo hagas.
4. La UEFI de Surface cargará el archivo de configuración y determinará que SEMM no está habilitado en el dispositivo. La UEFI de Surface iniciará entonces el proceso de inscripción de SEMM, como se muestra a continuación:
   * La UEFI de Surface comprobará que el archivo de configuración de SEMM contiene un certificado SEMM.
   * La UEFI de Surface te pedirá que escribas los dos últimos caracteres de la huella digital del certificado para confirmar la inscripción del dispositivo Surface en SEMM, como se muestra en la figura 8.

      ![La inscripción de SEMM requiere los dos últimos caracteres de huella digital del certificado](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *Figura 8. La inscripción en SEMM requiere los dos últimos caracteres de la huella digital del certificado*

   * La UEFI de Surface almacenará el certificado SEMM en firmware y aplicará las opciones de configuración especificadas en el archivo de configuración de LA UEFI de Surface.
   
5. El dispositivo Surface ahora está inscrito en SEMM y arrancará en Windows.

Puedes comprobar que un dispositivo Surface se inscribió correctamente en SEMM buscando el paquete de configuración de **Microsoft Surface** en Programas y características **(como** se muestra en la figura 9) o en los eventos almacenados en el registro del Configurador de UEFI de **Microsoft Surface,** que se encuentra en Registros de aplicaciones y servicios en el Visor de eventos (como se muestra en la figura 10). ****

![Comprobar la inscripción de dispositivos Surface en SEMM en programas y características](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*Figura 9. Comprobar la inscripción de un dispositivo Surface en SEMM en programas y características*

![Comprobar la inscripción del dispositivo Surface en SEMM en el Visor de eventos](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*Figura 10. Comprobar la inscripción de un dispositivo Surface en SEMM en el Visor de eventos*

También puedes comprobar que el dispositivo está inscrito en SEMM en la UEFI de Surface: mientras el dispositivo está inscrito, la UEFI de Surface contendrá la página de administración de **Enterprise** (como se muestra en la figura 11).

![Página de administración de Surface UEFI Enterprise](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*Figura 11. Página de administración de Surface UEFI Enterprise*


## Configurar la UEFI de Surface con SEMM

Después de inscribir un dispositivo en SEMM, puedes ejecutar paquetes de configuración de UEFI de Surface firmados con el mismo certificado SEMM para aplicar nuevas opciones de configuración de LA UEFI de Surface. Esta configuración se aplica automáticamente la próxima vez que se inicia el dispositivo, sin ninguna interacción del usuario. Puedes usar soluciones de implementación de aplicaciones como Microsoft Endpoint Configuration Manager para implementar paquetes de configuración de LA UEFI de Surface en dispositivos Surface para cambiar o administrar la configuración en la UEFI de Surface.

Para obtener más información sobre cómo implementar archivos de Windows Installer (.msi) con Configuration Manager, consulta Implementar y administrar aplicaciones [con Microsoft Endpoint Configuration Manager.](https://technet.microsoft.com/library/mt627959)

Si has protegido la UEFI de Surface con una contraseña, los usuarios sin la contraseña que intenten **** arrancar en la UEFI de Surface solo tendrán la información del **equipo** **,** Acerca **de**, la administración empresarial y las páginas Salir que se les mostrarán.

Si no has protegido la UEFI de Surface con una contraseña o un usuario escribe la contraseña correctamente, las opciones configuradas con SEMM se atenuarán (no estarán disponibles) y el texto Algunas opciones de configuración que administra la organización se mostrarán en la parte superior de la página, como se muestra en la figura 12.

![Configuración administrada por SEMM deshabilitada en la UEFI de Surface](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*Figura 12. La configuración administrada por SEMM se deshabilitará en la UEFI de Surface*

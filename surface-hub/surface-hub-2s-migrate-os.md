---
title: Migrar a Windows 10 Pro o Enterprise en Surface Hub 2
description: En este artículo se describe el proceso de migración de equipo de Windows 10 en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
keywords: Equipo de escritorio Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0a74a082d1afe48c938fcc4780407d56cfdd121e
ms.sourcegitcommit: 56526c92d84dbc2cebcb8071d995efe399f306df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "11105281"
---
# Migrar a Windows 10 Pro o Enterprise en Surface Hub 2

## Introducción

Surface Hub 2S viene preinstalado con el equipo con Windows 10, una edición personalizada de Windows 10 diseñada para facilitar la colaboración en entornos de reuniones. Ahora tienes la opción de ejecutar Windows 10 Pro o Enterprise para usar Surface Hub 2 de manera similar a cualquier otro equipo. 

> [!IMPORTANT]
>A diferencia de una actualización o migración típica, este proceso requiere que siga un procedimiento prescriptivo, como se describe en esta página. Revise los [componentes](#solution-components) de la solución y el [flujo de trabajo de migración e instalación](#migration-and-installation-workflow-summary) antes de continuar.


> [!NOTE]
> Cuando instale Windows 10 Pro o Enterprise, necesitará una nueva licencia independiente de su licencia de equipo de Windows 10 existente. 


Para iniciar la migración desde el equipo de Windows 10, use un equipo independiente y una herramienta descargable, **Surface UEFI** , para crear un paquete que contenga una nueva configuración de UEFI que aplique a Surface Hub 2S.  El configurador de Surface UEFI funciona como una interfaz en el modo Surface de administración de la empresa (SEMM), diseñado para facilitar la administración centralizada de la configuración del firmware en dispositivos Surface en un entorno corporativo. Para obtener más información sobre SEMM, consulte la [documentación del modo de administración de Microsoft Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode).
 

## Componentes de la solución

- Dispositivo Surface Hub 2S que ejecuta el sistema operativo Windows 10 Teams
- Dispositivo independiente que ejecuta Windows 10
- Herramienta de configuración UEFI de Surface para crear el paquete SEMM
- Imagen del sistema operativo Windows 10 Pro o Enterprise, versión 1903 o superior
- Dos unidades USB con 16 GB de almacenamiento, formato FAT32
- Drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2, Windows Installer. Archivo MSI
- Conexión a Internet
- Solución de creación de imágenes (opcional)

 
## Resumen de flujo de trabajo de migración e instalación

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| uno | [Comprobar si la versión de Surface Hub cumple con los requisitos mínimos](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Asegúrese de que la versión de UEFI sea 694.2938.768.0 o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 1 | [Descargar el configurador de Surface UEFI y los drivers y firmware de Surface Hub 2](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Seleccione el botón Descargar en la página [herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703) , seleccione y descargue el **configurador de superficie UEFI. MSI** e instálelo en otro equipo. Descargar [drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2. MSI](https://www.microsoft.com/download/details.aspx?id=101974) y guárdelo para usarlo en el paso 5. |
| 2 | [Preparar certificado SEMM](#prepare-semm-certificate)                                                                          | Prepara el certificado necesario para ejecutar el configurador de Surface UEFI o usa tu certificado actual.                                                                                                                                                                                                                                                                                                      |
| cuatro | [Crear paquete SEMM](#create-semm-package)                                                                               | Inicie Surface configurador UEFI para crear un paquete SEMM en una unidad USB que contenga los archivos de configuración necesarios para aplicar en Surface Hub 2S. Copie estos archivos de paquete de SEMM en una carpeta de su equipo.                                                                                                                                                                                          |
| 4 | [Preparar una unidad flash USB que contenga una imagen de Windows 10, un paquete SEMM y drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Cree una única unidad USB (denominada **BOOTME** en este ejemplo) que contenga una imagen de Windows 10. Agregue sus drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2 (paso 2) y archivos de paquete SEMM (paso 4) a la unidad de **BOOTME** .                                                                                                                                                                                                  |
| 6 | [Actualice UEFI en Surface Hub 2S para habilitar la migración del sistema operativo](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use la unidad **BOOTME** para arrancar Surface Hub 2s en el menú UEFI e instale SEMM paquete.|
| siete | [Instalar Windows 10 Pro o la versión Enterprise 1903 o posterior](#install-windows-10-pro-or-enterprise)                                        | Use la unidad **BOOTME** para instalar **Windows 10 Pro o Enterprise** versión 1903 o posterior.                                                                                                                                                                                                                                                                                 |
| 4,8 | [Instalar drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarse de que el dispositivo tiene todas las actualizaciones y drivers más recientes, instale los [drivers y el firmware para Windows 10 Pro y Enterprise en Surface Hub 2. Archivo MSI](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                  |
| 99,999 | [Configurar completamente Surface Hub 2S como dispositivo de productividad personal](#next-steps)                                        |  Habilite el conjunto de opciones y aplicaciones recomendadas para optimizar el uso de Surface Hub 2S como dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### Comprobar si la versión de Surface Hub cumple con los requisitos mínimos

La versión mínima de UEFI requerida antes de migrar Surface Hub de Windows 10 Team a Windows 10 escritorio es **694.2938.768.0**.
 
**Para comprobar la versión de UEFI actual en su sistema:**

1. En la pantalla principal de Surface Hub 2S, seleccione **Inicio** y abra el **SurfaceApp** (toda la superficie de**aplicaciones**  >  **Surface**).

2. Seleccione **la superficie** para mostrar información sobre el Surface Hub, incluida la versión actual de UEFI en el dispositivo. Si la versión de UEFI es **694.2938.768.0** o posterior, como se muestra a continuación, UEFI cumple con los requisitos para crear el paquete de SEMM para habilitar la migración del sistema operativo.

    ![Abrir aplicación Surface & seleccionar la superficie](images/shm-fig1.png)
 
3. Si la versión de UEFI es anterior a la de la versión **694.2938.768.0**, tendrá que obtener una versión actual con Windows Update.

**Para actualizar UEFI desde Windows Update:**

1. En su Surface Hub 2S, inicie sesión como **Administrador**, vaya a configuración de **todas las aplicaciones**  >  **Settings** >  **actualizar y seguridad**  >  **Windows Update** e instale todas las actualizaciones y, a continuación, reinicie el dispositivo. Verifica la versión de UEFI con la aplicación Surface. Nota: Si no conoce el nombre de usuario o la contraseña de administrador, tendrá que restablecer el dispositivo. Para obtener más información, consulta [restablecer y recuperar en Surface Hub 2s](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

2. Repita estos pasos hasta que la versión de UEFI sea **694.2938.768.0** o posterior.

3. Si sigue sin ver el UEFI actualizado después de varios intentos, consulte el **historial de actualizaciones** y busque las instancias de errores de instalación de firmware. Es posible que tenga que restablecer el dispositivo (actualización de**configuración**  >  **&**  >  **dispositivo de restablecimiento**de seguridad).

### Descargar el configurador de Surface UEFI y los drivers y firmware de Surface Hub 2

En un PC diferente:

- Seleccione el botón Descargar en la [página herramientas de Surface para ti](https://www.microsoft.com/download/details.aspx?id=46703), seleccione y descargue el configurador de superficie UEFI. MSI e instálelo en otro equipo. La herramienta de configuración UEFI de Surface no se puede ejecutar en Surface Hub 2S mientras esté instalado Windows 10 Team Edition.

- Descarga [los drivers y el instalador de Windows de Surface Hub 2. Archivo MSI](https://www.microsoft.com/download/details.aspx?id=101974) que se debe aplicar al instalar el nuevo sistema operativo.

### Preparar certificado SEMM

Si esta es la primera vez que usa el configurador de Surface UEFI, tendrá que preparar un certificado. Este certificado garantiza que después de que un dispositivo se haya inscrito en SEMM, solo se podrán usar los paquetes creados con el certificado aprobado para modificar la configuración de UEFI. La forma de adquirir un certificado puede variar según el tamaño o la complejidad de su organización:

- Las organizaciones empresariales de gran tamaño suelen mantener su propia infraestructura de certificados para generar certificados por prácticas de seguridad estándar.

- Las empresas medianas y otras pueden optar por obtener un certificado de proveedores de terceros. Esta es la opción recomendada para organizaciones sin suficiente experiencia de ti o equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado con un script de PowerShell por la siguiente documentación: [requisitos de certificados del modo de administración de Enterprise Surface](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). También puede usar PowerShell para crear su propio certificado por la siguiente documentación: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).

El paquete SEMM creado con la herramienta de configuración Surface UEFI debe protegerse con un certificado para comprobar la firma de los archivos de configuración antes de que se pueda aplicar la configuración de UEFI. Para obtener más información, consulte la documentación del [modo de administración de Surface Enterprise](https://docs.microsoft.com/surface/surface-enterprise-management-mode) .
 
 
### Crear paquete SEMM

1. Instala la herramienta de **configuración de Surface UEFI** descargada anteriormente en un equipo independiente. 

2. Abra el **configurador UEFI de superficie** y seleccione **Inicio**.

   ![Configurador de Surface abierto UEFI](images/shm-fig2.png)
   
3. Seleccione **Surface Devices** y, después, **siguiente**.

   ![Seleccionar dispositivos de Surface](images/shm-fig3.png)
  
4. Seleccione **paquete de configuración**.

   ![Seleccionar paquete de configuración](images/shm-fig4.png)
  
5. Seleccione **protección de certificado**.

   ![Seleccionar protección de certificado](images/shm-fig5.png)

6. Se le pedirá que agregue el archivo Certificate. pfx.

   ![Se le pedirá que agregue su certificado](images/shm-fig6.png)
   
7. Escriba la **contraseña del certificado** y seleccione **Aceptar**.

   ![Escriba la contraseña del certificado y seleccione Aceptar.](images/shm-fig7.png)

8. Seleccione **protección con contraseña** para agregar una contraseña a Surface UEFI. Esta contraseña será obligatoria cada vez que arranques en UEFI. Es **muy recomendable** establecer una contraseña de UEFI que usarás en Surface Hub 2S.

   ![Haga clic en protección con contraseña](images/shm-fig8.png)
   
9. Establezca una **contraseña de UEFI** y seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarde la contraseña en una ubicación segura accesible para los administradores de TI de su organización responsables de administrar Surface Hub. Si la contraseña se pierde, no hay proceso de recuperación. 

   ![Escribe tu contraseña de UEFI](images/shm-fig9.png)

10. Seleccione **Surface Hub 2s**y, a continuación, seleccione **siguiente**.

    ![Seleccionar Surface Hub 2S](images/shm-fig10.png)
   
11. Selecciona **Siguiente**.

    ![Seleccione siguiente](images/shm-fig10a.png)

12. Para permitir la instalación de Windows 10 Pro o Enterprise, seleccione **EnableOsMigration.**

    ![Seleccione habilitar la migración del sistema operativo](images/shm-fig11.png)
    
13. Establezca **EnableOSMigration** en **on (encendido** ) y seleccione **Next (siguiente**).

    ![Establecer habilitar la migración del sistema operativo en activado](images/shm-fig12.png)

> [!NOTE]
> Después de aplicar un paquete de SEMM, todos los ajustes de UEFI aparecerán en gris (bloqueado) en el menú de UEFI del dispositivo. Esto incluye los valores predeterminados para otras opciones, como IPv6 para el arranque PXE. Para modificar la configuración de UEFI una vez completada la migración, tendrá que aplicar otro paquete de SEMM o anular la inscripción del dispositivo de SEMM. Si aplica otro paquete de SEMM para modificar la configuración de UEFI, debe usar el certificado original al crear el nuevo paquete SEMM con la herramienta de configuración UEFI. 

#### Guardar el paquete SEMM en la unidad USB

1. Conecte una unidad USB a su PC. Elija **Hub 2** y, después, **siguiente**.

   ![Seleccionar USB](images/shm-fig13.png)
   
2. Seleccione **generar**.

   ![Seleccionar compilación](images/shm-fig14.png)

3. Capture una captura de pantalla de esta página y, a continuación, seleccione **fin**. El paquete SEMM está listo y contiene el paquete SEMM **DfciUpdate. DFI** y un archivo de texto con la huella digital SEMM (los dos últimos caracteres de la huella digital del certificado).

   ![Seleccione fin](images/shm-fig15.png)
   
4. Guarde los 2 últimos caracteres de la huella digital del certificado, que es necesario para activar SEMM al aplicar el paquete en Surface Hub 2S.

### Preparar una unidad flash USB que contenga la imagen de Windows 10, el paquete SEMM y el firmware y los drivers de Surface Hub 2

Puede instalar una imagen de Windows 10 Pro o Enterprise (versión 1903 o posterior) con una de las siguientes opciones:

- La solución de imagen actual.

- El [acelerador de implementación de Surface](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) le permite crear una imagen de Windows 10 de arranque que puede incluir todas las actualizaciones actuales de Windows 10, Office, otras aplicaciones de su elección, así como los drivers y el firmware requeridos. 

- Unidad flash USB con imagen de Windows 10 Pro o Enterprise seguida de la instalación de  [drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
Este procedimiento describe la creación de una unidad flash USB desde medios de instalación y, después, la incorporación de los archivos y los drivers y el firmware de SEMM para Windows 10 Pro y Enterprise en Surface Hub 2. Archivo MSI. Si usa otros métodos de implementación, continúe con la siguiente sección: [actualice UEFI en Surface Hub 2S para habilitar la migración del sistema operativo](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> Una vez instalado, necesitarás una licencia válida para Windows 10 Pro o Windows 10 Enterprise.

1. Para crear una instalación de Windows 10 Pro, siga las instrucciones de la página [Descargar Windows 10](https://www.microsoft.com/software-download/windows10) para usar la herramienta de **creación de medios** . Para descargar Windows 10 Enterprise, vaya al [centro de servicios de licencias por volumen de Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx).

2. Inserte una nueva unidad de **almacenamiento USB** . Inicie la herramienta de **creación de medios** , seleccione **crear medios de instalación** y, después, haga clic en **siguiente**.

   ![Crear medios de instalación](images/shm-fig16.png)
   
3. Seleccione el idioma, Windows 10 y 64 bits (x64) y, a continuación, seleccione **siguiente**.

   ![Seleccione el idioma, Windows 10 y 64 bits & Seleccione siguiente](images/shm-fig17.png)
   
4. Seleccione **unidad flash USB** y haga clic en **siguiente**.

   ![Seleccione unidad flash USB y, a continuación, siguiente](images/shm-fig18.png)
   
5. Una vez completada la descarga, seleccione **Finalizar**.

   ![Seleccione finalizar](images/shm-fig19.png)
   
6. Copie los archivos y los drivers y firmware de SEMM para Windows 10 Pro y Enterprise en Surface Hub 2 (. MSI) en la raíz de la unidad flash USB (**BOOTME**) que contiene la imagen de Windows 10. La unidad USB de BOOTME contiene:

    - Su imagen de inicio de Windows 10
    
    - Archivos de paquete SEMM (se copian en la raíz de la unidad USB)
    
      - DfciUpdate. DFI
      - Archivo de texto con la huella digital SEMM. (En este ejemplo: SurfaceUEFI_2020Aug25_1058.txt. La marca de tiempo de fecha generada automáticamente corresponde a la fecha en la que se creó el archivo con el configurador Surface UEFI.)
      - Drivers y firmware para Windows 10 Pro y Enterprise en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)

### Actualice UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserte la unidad de **BOOTME** en el puerto USB-a en Surface Hub 2S.

2. Para arrancar en UEFI:

   1. Primer apagado (apagado) de Surface Hub 2S.
   1. Mantén pulsado el **volumen +** y, a continuación, pulsa y suelta el botón de **encendido** .
   1. Mantenga pulsado **volumen +** hasta que aparezca el menú UEFI.
   
      ![Mantener en espera el volumen hasta que aparezca el menú UEFI](images/shm-fig20.png)
      
3. Cuando se reinicie el dispositivo, escriba la contraseña de UEFI que creó anteriormente, si procede (muy recomendable).

   ![Cuando se reinicie el dispositivo, escribe tu paassword UEFI](images/shm-fig22.png)
   
4. En el menú UEFI, seleccione **Management**  >  **instalación de administración desde USB**.

   ![Seleccionar administración & instalar desde USB](images/shm-fig21.png)
   
5. Seleccione **reiniciar ahora**, como se muestra a continuación. El dispositivo se reiniciará y mostrará el logotipo blanco de 4 cuadrados en el medio de la pantalla y, a continuación, se cerrará.

   ![Seleccione reiniciar ahora](images/shm-fig25.png)
   
6. Pulsa y suelta el botón de encendido, aparece una pantalla roja que te pide que actives el modo de administración de Surface Enterprise. 

7. Escriba la **huella digital del certificado**de dos caracteres, la **contraseña de configuración de UEFI** y, después, seleccione **Aceptar**.

   ![Escribe tu huella digital de certificado de 2 caracteres](images/shm-fig23.png)
 
   > [!NOTE]
   > Una vez que actives SEMM en tu dispositivo, se aplicará la nueva **EnableOSMigration** de configuración UEFI. Ya no podrás acceder al equipo de Windows 10 y deberás continuar con el siguiente paso e instalar Windows 10 Pro o Windows 10 Enterprise. 

8. El dispositivo se reiniciará, se mostrará el logotipo blanco de 4 cuadrados en el centro de la pantalla y, a continuación, se cerrará

### Instalar Windows 10 Pro o Enterprise

1. Si la unidad de inicio de Windows 10 Pro o de la empresa no está ya en el puerto Hub 2 USB-A, insértela ahora y, después, presione y suelte el botón de encendido.

2. El dispositivo se iniciará, verá el blanco de 4 cuadrados en el centro de la pantalla y, a continuación, verá un círculo giratorio debajo del logotipo blanco de cuatro cuadrados.

3. Si el dispositivo no arranca automáticamente en la unidad USB, apague el dispositivo (desenchufe el cable de alimentación y conéctelo de nuevo). Después de conectar el cable de alimentación de regreso, el dispositivo debe arrancar después de unos segundos en el logotipo blanco de 4 cuadrados en el medio de la pantalla, o puede presionar y soltar el botón de encendido para encender el dispositivo. Inmediatamente después de ver el logotipo de 4 cuadrados en el medio de la pantalla, pulse y mantenga presionado el botón bajar volumen hasta que vea el círculo giratorio debajo del logotipo blanco de cuatro cuadrados.
 
   ![Arranque en Windows 10 desde USB](images/shm-fig26.png)
   
4. Cuando se inicie el programa de instalación de la configuración rápida (OOBE), siga las instrucciones para instalar Windows 10 Pro o Enterprise (versión 1903 o posterior).

### Instalar drivers y firmware de Surface Hub 2

 - Para asegurarse de que el dispositivo tiene todas las actualizaciones y drivers más recientes, instale los [drivers y el firmware para Windows 10 Pro y Enterprise en Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
### Pasos siguientes

Para configurar Surface Hub 2S como dispositivo de productividad personal, consulte [configurar Windows 10 Pro o Enterprise en Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Si seguir los pasos descritos en este documento no se realiza correctamente al migrar el dispositivo a Windows 10 Pro o Enterprise para Surface Hub 2, póngase en contacto [con el soporte de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

### Volver al equipo de Windows 10

Si deseas restaurar tu dispositivo en el equipo con Windows 10, consulta [restablecer y recuperar en Surface Hub 2s](surface-hub-2s-recover-reset.md)

## Historial de versiones

| Versión | Date               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1,2  | 29 de septiembre de 2020 | Comentarios sobre actualizaciones varias por uso.                                                        |
| v. 1,1  | 15 de septiembre de 2020 | Se ha colocado notas adicionales en la introducción clarificando los requisitos de licencia para instalar un nuevo sistema operativo. |
| v. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

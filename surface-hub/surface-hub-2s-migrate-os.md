---
title: Migrar a Windows 10 Pro o Enterprise en Surface Hub 2
description: En este artículo se describe cómo migrar del equipo de Windows 10 en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
keywords: Equipo de escritorio Surface Hub, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195405"
---
# Migrar a Windows 10 Pro o Enterprise en Surface Hub 2

Surface Hub 2S viene preinstalado con el equipo con Windows 10. Esta edición personalizada de Windows 10 está diseñada para facilitar la colaboración en entornos de reuniones. Ahora tienes la opción de ejecutar Windows 10 Pro o Enterprise para usar Surface Hub 2 de manera similar a cualquier otro equipo. 

> [!IMPORTANT]
>A diferencia de una actualización o migración típica, este proceso requiere que siga un procedimiento prescriptivo, como se describe en este artículo. Revise los [componentes](#solution-components) de la solución y el [flujo de trabajo de migración e instalación](#migration-and-installation-workflow-summary) antes de continuar.


> [!NOTE]
> Al instalar Windows 10 Pro o Enterprise, necesitarás una nueva licencia independiente de tu licencia de equipo de Windows 10 existente. 


Inicia la migración desde el equipo de Windows 10 con un equipo independiente y el *configurador de Surface*de la herramienta descargada UEFI. Use la herramienta para crear un paquete que contenga una nueva configuración de UEFI que aplique a Surface Hub 2S.  

El configurador de Surface UEFI funciona como una interfaz en el modo de administración de empresa de Surface (SEMM). Está diseñado para facilitar la administración centralizada de la configuración del firmware en dispositivos Surface en un entorno corporativo. Para obtener más información, consulte la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentación de Microsoft SEMM</a>
 

## Componentes de la solución

- Dispositivo Surface Hub 2S que ejecuta el sistema operativo Windows 10 Team
- Dispositivo independiente que ejecuta Windows 10
- Herramienta de configuración UEFI de Surface para crear el paquete SEMM
- Imagen del sistema operativo Windows 10 Pro o Enterprise, versión 1903 o posterior
- Dos unidades USB que tienen 16 GB de almacenamiento, formato FAT32
- Drivers y firmware para Windows 10 Pro y el sistema operativo empresarial en un archivo de Microsoft Windows Installer (MSI) de Surface Hub 2
- Conexión a Internet
- Solución de creación de imágenes (opcional)

 
## Resumen de flujo de trabajo de migración e instalación

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| uno | [Compruebe que la versión de UEFI en Surface Hub 2S cumple los requisitos mínimos.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Asegúrese de que la versión de UEFI sea 694.2938.768.0 o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 1 | [Descarga el configurador de Surface UEFI y los drivers y firmware de Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página **herramientas de Surface para ti** </a> , seleccione **Descargar**. A continuación, selecciona y descarga el **configurador de Surface UEFI. MSI** e instálelo en otro equipo. Descargue los <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en el archivo MSI Surface Hub 2.</a> Guárdelo para usarlo en el paso 5. |
| 2 | [Prepare el certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare el certificado necesario para ejecutar el configurador de Surface UEFI. O usa tu certificado actual.                                                                                                                                                                                                                                                                                                      |
| cuatro | [Crear paquete SEMM.](#create-a-semm-package)                                                                               | Iniciar Surface: configurador UEFI para crear un paquete SEMM en una unidad USB, que contendrá los archivos de configuración que necesita para aplicar en Surface Hub 2S. Copie estos archivos de paquete de SEMM en una carpeta de su equipo.                                                                                                                                                                                          |
| 4 | [Prepara una unidad flash USB que contenga una imagen de Windows 10, un paquete SEMM y firmware y drivers para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Cree una única unidad USB que contenga una imagen de Windows 10. En este ejemplo, la unidad se denomina *BOOTME*. Agregue sus drivers y firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2 (paso 2) y archivos de paquete SEMM (paso 4) a la unidad de *BOOTME* .                                                                                                                                                                                                  |
| 6 | [Actualice UEFI en Surface Hub 2S para habilitar la migración del sistema operativo.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use la unidad *BOOTME* para arrancar Surface Hub 2s en el menú UEFI e instale el paquete SEMM.|
| siete | [Instale Windows 10 Pro o Enterprise versión 1903 o posterior.](#install-windows-10-pro-or-enterprise)                                        | Use la unidad *BOOTME* para instalar Windows 10 Pro o Enterprise versión 1903 o posterior.                                                                                                                                                                                                                                                                                 |
| 4,8 | [Instale los drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarse de que el dispositivo tiene todas las actualizaciones y los drivers más recientes, instale los <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en el archivo MSI de Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 99,999 | [Configura completamente Surface Hub 2S como dispositivo de productividad personal.](#configure-recommended-settings)                                        |  Habilita la configuración y las aplicaciones recomendadas para optimizar Surface Hub 2S como un dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### Comprobar si la versión de Surface Hub cumple con los requisitos mínimos

Antes de migrar Surface Hub de equipo de Windows 10 a escritorio de Windows 10, necesitas una versión de UEFI que sea al menos de *694.2938.768.0*.
 
**Para comprobar la versión UEFI de su sistema:**

1. En la página de inicio de Surface Hub 2S, seleccione **Inicio**y, después, abra la aplicación Surface (toda la superficie de**aplicaciones**  >  **Surface**).

2. Seleccione **la superficie** para mostrar información sobre Surface Hub, incluida la versión UEFI actual en el dispositivo. 
   - Si la versión UEFI es *694.2938.768.0* o posterior, como se muestra en la siguiente imagen, puede crear el paquete SEMM para habilitar la migración del sistema operativo.

       ![Captura de pantalla que muestra la página de la superficie en la aplicación de Surface.](images/shm-fig1.png)
 
   - Si la versión UEFI es anterior a la versión 694.2938.768.0, tendrá que obtener una versión actual instalando la imagen de la ventana 10 Team 2020 (BMR, Bare Metal Recovery) o mediante Windows Update.
   
**Para actualizar UEFI a través de Windows Update:**

1. En Surface Hub 2S, inicie sesión como **Administrador**. 
    >[!Note]
    > Si no conoce el nombre de usuario o la contraseña de administrador, tendrá que restablecer el dispositivo. Para obtener más información, consulte <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> restablecer y recuperar en Surface Hub 2S.</a>

1. Vaya a configuración de **todas las aplicaciones**  >  **Settings**  >  **y actualice**  >  **Windows Update**y, a continuación, instale todas las actualizaciones. 
1. Reinicia el dispositivo. 
1. Verifica la versión UEFI con la aplicación Surface. 
1. En este punto, si la versión de UEFI aún no es la versión 694.2938.768.0 o posterior, puede repetir los pasos anteriores o puede obtener el UEFI más reciente instalando la imagen de recuperación de hardware de Windows 10 Team 2020 (BMR).

**Para actualizar UEFI a través de la imagen de recuperación de hardware (BMR):**

1.  Vaya al [sitio de recuperación de superficie](https://support.microsoft.com/surfacerecoveryimage) y seleccione **Surface Hub 2s** .
3.  Escribe el número de serie del concentrador (ubicado en la parte posterior del concentrador junto a la conexión de alimentación).
4.  Siga las instrucciones para descargar la imagen en una unidad USB con formato a través de la instalación de la actualización 2020 del equipo de Windows 10.
5.  Una vez completada la actualización y cuando el dispositivo entra en la configuración de primera vez de OOBE, no es necesario completar OOBE, la versión de UEFI se actualizará. En su lugar, apague el dispositivo manteniendo presionado el botón de encendido hasta que se apague la pantalla. 

### Descargar el configurador de Surface UEFI y los drivers y firmware de Surface Hub 2

En un PC diferente:

1. En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página herramientas de Surface para ti </a> , seleccione **Descargar**.  
1. Seleccione y descargue el archivo MSI del configurador de Surface UEFI e instálelo en un equipo independiente. La herramienta de configuración UEFI de Surface no se puede ejecutar en Surface Hub 2S mientras esté instalado Windows 10 Teams.

1. Descargar los <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers y los archivos MSI de Windows Installer de Surface Hub 2 </a> . Usará este archivo al instalar el nuevo sistema operativo.

### Preparar el certificado SEMM

Si aún no ha usado Surface UEFI Configurator, debe preparar un certificado. Este certificado garantiza que después de que un dispositivo se haya inscrito en SEMM, solo podrá modificar la configuración de UEFI con paquetes que se crean con el certificado aprobado. 

La forma de obtener un certificado depende del tamaño o de la complejidad de su organización:

- Las organizaciones empresariales suelen mantener su propia infraestructura para generar certificados según las prácticas de seguridad estándar.

- Las empresas medianas y otras pueden optar por obtener certificados de proveedores asociados. Esta opción es recomendable para organizaciones que no tienen suficiente experiencia de ti o un equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado usando un script de PowerShell. Para obtener más información, consulte los requisitos de certificados del modo de administración de la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> empresa </a> . También puede usar PowerShell para crear su propio certificado. Para obtener más información, consulte la <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> documentación de New-SelfSignedCertificate </a> .

El paquete SEMM que crea Surface del configurador UEFI debe protegerse con un certificado. El certificado verifica la firma de los archivos de configuración antes de que se pueda aplicar la configuración de UEFI. Para obtener más información, consulte la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentación de SEMM </a> .
 
 
### Crear un paquete de SEMM

1. En un equipo diferente, instala la herramienta del configurador de Surface UEFI que descargaste anteriormente. 

2. Abra el configurador UEFI de superficie y, a continuación, seleccione **iniciar**.

   ![Configurador de Surface de apertura UEFI.](images/shm-fig2.png)
   
3. Seleccione **Surface Devices**y, a continuación, seleccione **siguiente**.

   ![Seleccione Surface Devices.](images/shm-fig3.png)
  
4. Seleccione **paquete de configuración**.

   ![Seleccione paquete de configuración.](images/shm-fig4.png)
  
5. Seleccione **protección de certificado**.

   ![Seleccione protección de certificado.](images/shm-fig5.png)

   Se le pedirá que agregue el archivo Certificate. pfx.

   ![Agregue el certificado.](images/shm-fig6.png)
   
7. Escriba la contraseña del certificado y, después, seleccione **Aceptar**.

   ![Escriba la contraseña del certificado y seleccione Aceptar.](images/shm-fig7.png)

8. Seleccione **protección con contraseña** para agregar una contraseña a Surface UEFI. Necesitarás esta contraseña siempre que arranques en UEFI. Le *recomendamos encarecidamente* que establezca una contraseña de UEFI que usará en Surface Hub 2S.

   ![Seleccione protección con contraseña.](images/shm-fig8.png)
   
9. Establezca una contraseña de UEFI y, después, seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarde la contraseña en un lugar seguro accesible para los administradores de ti que administran Surface Hub. Si la contraseña se pierde, no se puede recuperar. 

   ![Escribe tu contraseña de UEFI.](images/shm-fig9.png)

10. Seleccione **Surface Hub 2s**y, a continuación, seleccione **siguiente**.

    ![Seleccione Surface Hub 2S.](images/shm-fig10.png)
   
11. Selecciona **Siguiente**.

    ![Selecciona Siguiente.](images/shm-fig10a.png)

12. Para permitir la instalación de Windows 10 Pro o Enterprise, Active **EnableOsMigration**y, a continuación, seleccione **siguiente**.

    ![Seleccione Habilitar migración O S.](images/shm-fig11.png)
    
    ![Establezca habilitar la migración de OS en activado.](images/shm-fig12.png)

### Administración de la inscripción de SEMM

La inscripciones de dispositivos a SEMM afecta la manera en que puede administrar el dispositivo hacia adelante. Por ejemplo, después de aplicar un paquete SEMM, en el menú UEFI del dispositivo, la configuración de UEFI no está disponible (está bloqueada). Los valores predeterminados para otras opciones como **IPv6 para el arranque PXE** tampoco están disponibles. 

Para cambiar la configuración de UEFI después de finalizar la migración, aplique otro paquete de SEMM o desinscriba el dispositivo de SEMM. Si aplica otro paquete de SEMM para cambiar la configuración de UEFI, debe usar el certificado original cuando compile el nuevo paquete de SEMM. Use la herramienta de configurador UEFI y deje **EnableOSMigration** desactivado (no activado, como se muestra en los pasos de la migración original).

#### Trabajar con socios

Si su empresa subcontrata la migración a Windows 10 Pro o Enterprise en Surface Hub 2, es posible que quiera que el socio transfiera el certificado SEMM, el paquete SEMM y la contraseña de UEFI.  Como alternativa, después de migrar el Hub, puede anular inmediatamente la inscripción de la SEMM, lo que permitirá la administración local de UEFI y la transferencia del dispositivo a otra persona. Sin embargo, se recomienda encarecidamente usar una contraseña de UEFI, que puede configurarse después de la migración. Para obtener más información, vea [administrar la configuración de Surface UEFI](https://docs.microsoft.com/surface/manage-surface-uefi-settings). 

#### Volver al equipo de Windows 10

Si, después de migrar, elige restaurar el dispositivo a Windows 10 Team, [tal como se describe a continuación](#roll-back-to-windows-10-team), se recomienda anular la inscripción del Hub de semm. Para obtener más información, vea [anular la inscripción de dispositivos de Surface desde SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).


#### Guardar el paquete SEMM en una unidad USB

1. Conecte una unidad USB a su PC. 
1. Elija **Hub 2**y, a continuación, seleccione **siguiente**.

   ![Seleccionar USB](images/shm-fig13.png)

   > [!WARNING]
   > Todos los datos existentes en la unidad USB se borran cuando se genera el paquete SEMM. Antes de crear el paquete SEMM, quite todos los archivos de la unidad USB que quiera guardar.
   
2. Seleccione **generar**.

   ![Seleccione generar.](images/shm-fig14.png)

3. Capture una captura de pantalla de esta página y, a continuación, seleccione **fin**. Tu paquete de SEMM está listo. Contiene el paquete SEMM *DfciUpdate. DFI* y un archivo de texto que incluye la huella digital de SEMM (los dos últimos caracteres de la huella digital del certificado).

   ![Seleccione fin.](images/shm-fig15.png)
   
4. Guarde los últimos dos caracteres de la huella digital del certificado. Necesitarás estos caracteres para activar SEMM cuando apliques el paquete en Surface Hub 2S.

### Preparar una unidad flash USB que contiene una imagen de Windows 10, un paquete SEMM y el firmware y los drivers de Surface Hub 2

Puede instalar una imagen de Windows 10 Pro o Enterprise (versión 1903 o posterior) usando una de las siguientes opciones:

- La solución de imagen actual.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Acelerador de implementación de Surface </a> . Use esta herramienta para crear una imagen de inicio de Windows 10. La imagen puede incluir todas las actualizaciones actuales de Windows 10, Office, otras aplicaciones que elija y los drivers y el firmware necesarios. 

- Unidad flash USB que contiene una imagen de Windows 10 Pro o Enterprise. A continuación, instale <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> los drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2 </a> .
 
El siguiente procedimiento describe cómo crear una unidad flash USB desde los medios de instalación y, a continuación, agregar los archivos del paquete SEMM y los drivers y firmware para Windows 10 Pro y el sistema operativo empresarial en el archivo MSI Surface Hub 2. Si usa otros métodos de implementación, vaya a la sección [Actualizar UEFI en Surface Hub 2 para habilitar la sección de migración del sistema operativo](#update-uefi-on-surface-hub-2s-to-enable-os-migration) en este artículo.

> [!NOTE]
> Una vez finalizada la instalación, necesitarás una licencia válida para Windows 10 Pro o Windows 10 Enterprise que sea independiente de tu licencia de equipo de Windows 10 existente.

1. Para crear una instalación de Windows 10 Pro, en la <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Página Descargar Windows 10 </a> , siga las instrucciones para descargar la herramienta de creación de multimedia. Para descargar Windows 10 Enterprise, vaya al <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> centro de servicios de licencias por volumen de Microsoft </a> .

2. Inserte una nueva unidad de almacenamiento USB. 
1. Abra la herramienta de creación de medios, seleccione **crear medios de instalación**y, a continuación, seleccione **siguiente**.

   ![Crear medios de instalación.](images/shm-fig16.png)
   
3. Seleccione un idioma y, a continuación, seleccione **Windows 10** y **64 bits (x64)**. Después, seleccione **siguiente**.

   ![Seleccione idioma y elija Windows 10 y 64-bit. Después, seleccione siguiente.](images/shm-fig17.png)
   
4. Seleccione **unidad flash USB**y, después, haga clic en **siguiente**.

   ![Seleccione unidad flash U S B y seleccione siguiente.](images/shm-fig18.png)
   
5. Cuando termine la descarga, seleccione **Finalizar**.

   ![Seleccione finalizar.](images/shm-fig19.png)
   
6. Copie los archivos del paquete SEMM y los drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2 (el archivo MSI) en la raíz de la unidad flash USB (*BOOTME*) que contiene la imagen de Windows 10. La unidad USB de BOOTME contiene:

    - Su imagen de inicio de Windows 10.
    
    - Archivos de paquete SEMM (se copian en la raíz de la unidad USB).
    
      - *DfciUpdate. DFI*.
      - Archivo de texto que incluye la huella digital SEMM. (En este ejemplo, el archivo es *SurfaceUEFI_2020Aug25_1058.txt*). La marca de fecha y hora generada automáticamente corresponde a la fecha en la que se creó el archivo con el configurador de Surface UEFI.

   - Drivers y firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie este archivo en la raíz de la unidad USB.

### Actualice UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserte la unidad de BOOTME en el puerto USB (un puerto en Surface Hub 2S). Para obtener una lista de los archivos necesarios, consulte la sección anterior.

2. Para arrancar en UEFI:

   1. Apague (apague) su Surface Hub 2S.
   1. Mantenga presionado el **volumen +** y, a continuación, pulse y suelte el botón de encendido.
   1. Mantenga pulsado **volumen +** hasta que aparezca el menú UEFI.
   
      ![Mantenga pulsado el botón subir el volumen hasta que aparezca el menú UEFI.](images/shm-fig20.png)
      
3. Cuando se reinicie el dispositivo, escriba la contraseña de UEFI que creó anteriormente, si corresponde (muy recomendable).

   ![Escriba la contraseña de UEFI.](images/shm-fig22.png)
   
4. En el menú UEFI, seleccione **Management**  >  **instalación de administración desde USB**.

   ![Seleccione Administración e instale desde U S B.](images/shm-fig21.png)
   
5. Seleccione **reiniciar ahora**, como se muestra en la siguiente imagen. El dispositivo se reiniciará. Muestra un logotipo de Microsoft en blanco en la parte central de la ventana y, a continuación, se apaga.

   ![Seleccione reiniciar ahora.](images/shm-fig25.png)
   
6. Presione y suelte el botón Power (encendido). En la ventana de color rojo que aparece, active el modo de administración de Surface Enterprise. 

7. Escriba la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI. Después, seleccione **Aceptar**.

   ![Escriba la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Después de activar SEMM en el dispositivo, se aplica la nueva **EnableOSMigration** de configuración UEFI. Ya no podrás acceder al equipo de Windows 10. En su lugar, debe continuar con el paso siguiente e instalar Windows 10 Pro o Windows 10 Enterprise. 

   El dispositivo se reiniciará. Muestra el logotipo blanco en la parte central de la pantalla y, a continuación, lo cierra de nuevo.

### Instalar Windows 10 Pro o Enterprise

1. Si la unidad de inicio de Windows 10 Pro o de la empresa no está ya en el puerto Hub 2 USB-A, insértela ahora. Después, pulsa y suelta el botón Power (encendido). 

    Cuando se inicie el dispositivo, verá el logotipo blanco en el medio de la pantalla. Después verás un círculo giratorio debajo del logotipo blanco.

3. Si el dispositivo no arranca automáticamente en la unidad USB, apague el dispositivo (desenchufe el cable de alimentación y, a continuación, conéctelo de nuevo). Después de volver a conectar el cable de alimentación, el dispositivo debe arrancar después de unos segundos. Después verás el logotipo blanco en el medio de la pantalla. 

    Si el dispositivo no se enciende, pulse y suelte el botón de encendido. Inmediatamente después de que vea el logotipo en el medio de la pantalla, pulse y mantenga presionado el botón volumen hasta que vea el círculo giratorio debajo del logotipo blanco.
 
   ![Arranca con Windows 10 desde la unidad U S B.](images/shm-fig26.png)
   
4. Cuando se inicie el programa de instalación de la configuración rápida (OOBE), siga las instrucciones para instalar Windows 10 Pro o Enterprise (versión 1903 o posterior).

### Instalar drivers y firmware de Surface Hub 2

Para asegurarse de que el dispositivo tiene todas las actualizaciones y drivers más recientes, instale los <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers y el firmware para Windows 10 Pro y el sistema operativo empresarial en Surface Hub 2 </a> .
 
## Establecer la configuración recomendada

Para configurar Surface Hub 2S como dispositivo de productividad personal, consulte <a href="surface-hub-2-post-install.md" target="_blank"> configurar Windows 10 Pro o Enterprise en Surface Hub 2 </a> .

> [!NOTE]
>Si los pasos indicados en este artículo no migran correctamente el dispositivo a Windows 10 Pro o Enterprise para Surface Hub 2, póngase en contacto <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> con el soporte de Surface Hub </a> .

## Volver al equipo de Windows 10

Si deseas restaurar el dispositivo en el equipo con Windows 10, consulta <a href="surface-hub-2s-recover-reset.md" target="_blank"> restablecer y recuperar en Surface Hub 2s </a> .

> [!NOTE]
> Antes de volver al equipo de Windows 10, se recomienda anular en primer lugar el Hub de SEMM. Para obtener más información, vea [anular la inscripción de dispositivos de Surface desde SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).

## Historial de versiones

En la tabla siguiente se resumen los cambios realizados en este artículo.

| Versión | Date               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1,3  | 3 de diciembre de 2020 | Actualizado con instrucciones sobre la administración de la inscripción de SEMM                                                        |
| v. 1,2  | 29 de septiembre de 2020 | Actualizaciones varias que tratan los comentarios de uso.                                                        |
| v. 1,1  | 15 de septiembre de 2020 | Se ha colocado una nota adicional en la introducción que clarifica los requisitos de licencia para instalar un nuevo sistema operativo. |
| v. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

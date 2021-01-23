---
title: Migrar a Windows 10 Pro o Enterprise en Surface Hub 2
description: Cómo migrar de Windows 10 Team en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297643"
---
# Migrar a Windows 10 Pro o Enterprise en Surface Hub 2

- [Historial de versiones de artículo](#version-history)

Surface Hub 2S viene con Windows 10 Team instalado. Esta edición personalizada de Windows 10 facilita la colaboración en entornos de salas de reuniones. Ahora puedes ejecutar Windows 10 Pro o Enterprise para usar Surface Hub 2S de forma muy parecido a cualquier otro equipo.

> [!IMPORTANT]
> Este proceso de migración requiere que siga el procedimiento específico que se describe en este artículo. Antes de continuar, lea componentes [de la solución y](#solution-components) flujo de trabajo de migración e [instalación.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Al instalar Windows 10 Pro o Enterprise, necesitas una nueva licencia independiente de la licencia existente de Windows 10 Team.

Inicia la migración desde Windows 10 Team mediante un equipo independiente y la herramienta descargable *Surface UEFI Configurator.* La herramienta crea un paquete que contiene una nueva configuración de UEFI que aplicas a Surface Hub 2S.  

El Configurador de UEFI de Surface funciona como una interfaz en el Modo de administración de Surface Enterprise (SEMM). Permite la administración centralizada de la configuración de firmware en dispositivos Surface en un entorno corporativo. Para obtener más información, consulta [El modo de administración de Microsoft Surface Enterprise.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
## Componentes de la solución

- Dispositivo Surface Hub 2S que ejecuta Windows 10 Team
- Dispositivo independiente que ejecuta Windows 10
- Herramienta configurador de UEFI de Surface para crear el paquete SEMM
- Imagen del sistema operativo Windows 10 Pro o Enterprise, versión 1903 o posterior
- Dos unidades USB con 16 GB de almacenamiento, en formato FAT32
- Controladores y firmware para Windows 10 Pro y Enterprise en un archivo Microsoft Windows Installer (MSI) de Surface Hub 2
- Conexión a Internet
- Solución de creación de imágenes (opcional)
 
## Resumen de flujo de trabajo de migración e instalación

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Comprueba la versión de UEFI en Surface Hub 2S.](#verify-the-uefi-version-on-surface-hub-2s)                                  | La versión UEFI debe ser *la versión 694.2938.768.0* o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Descarga el Configurador de UEFI de Surface y los controladores y firmware de Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | En la **[página Herramientas de Surface para TI,](https://www.microsoft.com/download/details.aspx?id=46703)** selecciona </a> **Descargar.** A continuación, selecciona y descarga el archivo MSI del **Configurador de UEFI de Surface**e instálelo en un equipo independiente. Descarga también los [controladores y el firmware para Windows 10 Pro y enterprise OS en](https://www.microsoft.com/download/details.aspx?id=101974)el archivo MSI de Surface Hub 2.</a> Guarde este paquete para usarlo en el paso 5. |
| 3 | [Prepare el certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepara el certificado necesario para ejecutar el Configurador de UEFI de Surface o usa el certificado actual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crea un paquete SEMM.](#create-a-semm-package)                                                                               | Inicia el Configurador de UEFI de Surface para crear un paquete SEMM en una unidad USB. Este paquete contendrá los archivos de configuración que debes aplicar en Surface Hub 2S. Copia estos archivos de paquete SEMM en una carpeta del equipo.                                                                                                                                                                                          |
| 5 | [Carga una unidad flash USB con la imagen de Windows 10, el paquete SEMM y controladores y firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crea una unidad USB que contenga una imagen de Windows 10. En este ejemplo, la unidad se denomina *BOOTME*. Agrega los controladores y el firmware de Windows 10 Pro y enterprise OS en Surface Hub 2 (del paso 2) y los archivos del paquete SEMM (del paso 4) a la unidad *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Actualiza la UEFI en Surface Hub 2S para habilitar la migración del sistema operativo.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Usa la *unidad BOOTME* para arrancar Surface Hub 2S en el menú UEFI e instalar el paquete SEMM.|
| 7 | [Instala Windows 10 Pro o Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Usa la *unidad BOOTME* para instalar Windows 10 Pro o Enterprise versión 1903 o posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instala controladores y firmware para Windows 10 Pro y Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarte de que el dispositivo tiene todas las actualizaciones y controladores más recientes, instala los controladores y el firmware del sistema operativo Windows 10 Pro y Enterprise en el archivo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI de Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configura Surface Hub 2S como dispositivo de productividad personal.](#configure-recommended-settings)                                        |  Habilita la configuración y las aplicaciones recomendadas para optimizar Surface Hub 2S como dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### Comprobar la versión de UEFI en Surface Hub 2S

Antes de migrar Surface Hub de Windows 10 Team a Windows 10 Desktop, necesitas UEFI versión *694.2938.768.0* o posterior.
 
**Para comprobar la versión de UEFI en el sistema:**

1. En la página principal de Surface **** Hub 2S, selecciona Inicio y, a continuación, abre la aplicación Surface **(Todas las aplicaciones**  >  **Surface).**

2. Selecciona **Tu Surface para** mostrar información sobre Surface Hub, incluida la versión actual de UEFI en el dispositivo. 
   - Si la versión de UEFI es *694.2938.768.0* o posterior, como se muestra en la siguiente imagen, puedes crear el paquete SEMM para habilitar la migración del sistema operativo.

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)
 
   - Si la versión uefi es anterior a la *versión 694.2938.768.0*, use uno de los métodos siguientes para obtener una versión más reciente
   
#### Actualizar UEFI a través de Windows Update

1. En Surface Hub 2S, inicia sesión como **administrador.**

    >[!Note]
    > Si no conoces tu nombre de usuario o contraseña de administrador, tendrás que restablecer el dispositivo. Para obtener más información, consulta [Restablecer y recuperar Surface Hub 2S.](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)

1. Ve a **Todas las aplicaciones Actualización de**  >  **configuración**  >  **y Seguridad de**Windows  >  **Update**e instala todas las actualizaciones.
1. Reinicia el dispositivo.
1. Comprueba la versión de UEFI mediante la aplicación Surface. Si la versión de UEFI no es la *versión 694.2938.768.0* o posterior, repita estos pasos o use el siguiente procedimiento para obtener la versión más reciente de UEFI.

#### Actualizar la UEFI a través de la imagen de recuperación de reconstrucción completa (BMR)

1.  Ve al sitio [de recuperación de Surface](https://support.microsoft.com/surfacerecoveryimage) y selecciona Surface Hub **2S.**
3.  Escribe el número de serie de hub. Se encuentra en la parte posterior del concentrador junto a la conexión de alimentación.
4.  Sigue las instrucciones para descargar la imagen en una unidad USB con formato mediante la instalación de Windows 10 Team 2020 Update.
5.  Después de la actualización, el dispositivo entra en la configuración rápida (OOBE). No es necesario completar la configuración. La versión uefi ya está actualizada. En su lugar, apaga el dispositivo manteniendo presionado el botón de encendido hasta que se apague la pantalla.

### Descargar controladores y firmware de Surface UEFI Configurator y Surface Hub 2

En un equipo independiente, sigue estos pasos:

1. En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página Herramientas de Surface para </a> TI, selecciona **Descargar.**  
1. Selecciona y descarga el archivo MSI del Configurador de UEFI de Surface e instálelo en un equipo independiente. La herramienta Configurador de UEFI de Surface no se puede ejecutar en Surface Hub 2S mientras esté instalada la edición Windows 10 Team.

1. Descarga los controladores [de Surface Hub 2 y el archivo MSI de Windows Installer de firmware.](https://www.microsoft.com/download/details.aspx?id=101974) Este archivo se usará al instalar el nuevo sistema operativo.

### Preparar el certificado SEMM

Si no has usado el Configurador de UEFI de Surface antes, debes preparar un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo puedes modificar la configuración de UEFI mediante paquetes creados con el certificado aprobado.

La forma en que se obtiene un certificado depende del tamaño o la complejidad de la organización:

- Las organizaciones empresariales suelen mantener su propia infraestructura para generar certificados de acuerdo con las prácticas de seguridad estándar.

- Las empresas medianas y otras suelen optar por obtener certificados de proveedores asociados. Esta opción se recomienda para organizaciones que no tienen tanta experiencia en TI o carecen de un equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado mediante un script de PowerShell. Para obtener más información, consulta los requisitos [de certificado del Modo de administración de Surface Enterprise.](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) O bien, puede usar PowerShell para crear su propio certificado. Para obtener más información, consulte [la documentación de New-SelfSignedCertificate.](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)

El paquete SEMM que crea el Configurador de UEFI de Surface debe estar protegido con un certificado. El certificado comprueba la firma de los archivos de configuración antes de que se pueda aplicar la configuración de UEFI. Para obtener más información, consulte la documentación [de SEMM.](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
 
### Crear un paquete SEMM

1. En un equipo independiente, instala la herramienta Configurador de UEFI de Surface que descargaste anteriormente.

1. Abre el Configurador de UEFI de Surface y, a continuación, selecciona **Inicio.**

   ![Pantalla de inicio del Configurador de UEFI de Surface.](images/shm-fig2.png)
   
1. Seleccione **Dispositivos Surface**y, a continuación, **seleccione Siguiente**.

   ![La captura de pantalla muestra la opción Dispositivos Surface seleccionada.](images/shm-fig3.png)
  
1. Seleccione **Paquete de configuración.**

   ![Screenshot shows "Select Configuration Package" selected.](images/shm-fig4.png)
  
1. Seleccione **Protección de certificados.**

   ![Screenshot shows were to choose "Select Certificate Protection".](images/shm-fig5.png)

   Se te pedirá que agregues el archivo .pfx del certificado.

   ![La captura de pantalla muestra dónde agregar el archivo de certificado.](images/shm-fig6.png)
   
1. Escriba la contraseña del certificado y, a continuación, **seleccione Aceptar**.

   ![Screenshot shows fields to enter and confirm your certificate password.](images/shm-fig7.png)

1. Selecciona **Protección con contraseña** para agregar una contraseña a la UEFI de Surface. Necesitarás esta contraseña siempre que arranques en la UEFI. *Te recomendamos encarecidamente que establezcas una contraseña de UEFI que usarás en Surface Hub 2S.*

   ![Screenshot shows where to select Password Protection.](images/shm-fig8.png)
   
1. Establezca una contraseña de UEFI y, a continuación, seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarda la contraseña en una ubicación segura a la que puedan acceder los administradores de TI que administran Surface Hub. *Si se pierde esta contraseña, no se puede recuperar.*

   ![Screenshot shows where you set the UEFI password.](images/shm-fig9.png)

1. Selecciona **Surface Hub 2S**y, a continuación, **selecciona Siguiente.**

    ![La captura de pantalla muestra dónde seleccionar Surface Hub 2S.](images/shm-fig10.png)
   
1. Vuelva **a seleccionar** Siguiente.

    ![Screenshot shows to select Next under "Choose which components".](images/shm-fig10a.png)

1. Para permitir la instalación de Windows 10 Pro o Enterprise, active **EnableOsMigration**y, a continuación, seleccione **Siguiente**.

    ![Screenshot shows where to select Enable O S Migration.](images/shm-fig11.png)
    
    ![Screenshot shows where to set Enable OS Migration to on.](images/shm-fig12.png)

### Administrar la inscripción de SEMM

Inscribir un dispositivo en SEMM afecta a cómo puedes administrarlo. Por ejemplo, después de aplicar un paquete SEMM, todas las configuraciones de UEFI no están disponibles (bloqueadas) en el menú UEFI del dispositivo. Los valores predeterminados de otras configuraciones, **como IPv6 para el arranque PXE,** tampoco están disponibles.

Para cambiar la configuración de UEFI después de finalizar la migración, aplica otro paquete de SEMM o desenrolla el dispositivo de SEMM. Si aplicas otro paquete de SEMM para cambiar la configuración de UEFI, debes usar el certificado original al compilar el nuevo paquete de SEMM. Use la herramienta configurador UEFI y deje **EnableOSMigration** desactivado *(no* como en los pasos de migración originales). **

#### Si trabaja con asociados

Si tu empresa subcontrata la migración de Surface Hub 2 a Windows 10 Pro o Enterprise, es posible que quieras que el partner te transfiera el certificado SEMM, el paquete SEMM y la contraseña de UEFI. O bien, después de migrar el concentrador, puede deshacer la inscripción inmediatamente de SEMM. Este paso permite la administración local de UEFI y la transferencia del dispositivo a otra parte. Sin embargo, le recomendamos que use una contraseña de UEFI, que se puede configurar después de la migración. Para obtener más información, consulta [Administrar la configuración de LA UEFI de Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Para revertir a Windows 10 Team

Si decides restaurar el dispositivo a Windows 10 Team después de la migración, como se describe más adelante en este [artículo,](#to-roll-back-to-windows-10-team)te recomendamos que primero desrolles Hub de SEMM. Para obtener más información, consulta [La inscripción de dispositivos Surface desde SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

#### Guardar el paquete SEMM en una unidad USB

1. Conecta una unidad USB al equipo.
1. Elija **Hub 2S**y, a continuación, **seleccione Siguiente.**

   ![Screenshot shows where to select Hub 2S](images/shm-fig13.png)

   > [!WARNING]
   > Todos los datos existentes en la unidad USB se borrarán cuando se haya creado el paquete SEMM. Antes de compilar el paquete SEMM, quita los archivos que necesites de la unidad USB.
   
1. Seleccione **Generar**.

   ![La captura de pantalla muestra dónde seleccionar Generar.](images/shm-fig14.png)

1. Capture una captura de pantalla de esta página y, a continuación, seleccione **Finalizar**. El paquete de SEMM ya está listo. Contiene el paquete de SEMM *DfciUpdate.dfi* y un archivo de texto que incluye la huella digital de *SEMM,* que son los dos últimos caracteres de la huella digital del certificado.

   ![La captura de pantalla muestra dónde seleccionar End.](images/shm-fig15.png)
   
4. Guarde los dos últimos caracteres de la huella digital del certificado. Necesitarás estos caracteres para activar SEMM cuando apliques el paquete en Surface Hub 2S.

### Cargar una unidad flash USB con una imagen de Windows 10, un paquete SEMM y controladores y firmware de Surface Hub 2

Puedes instalar una imagen de Windows 10 Pro o Enterprise (versión *1903* o posterior) mediante una de las siguientes opciones:

- La solución de creación de imágenes actual.

- [Acelerador de implementaciones de Surface.](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) Usa esta herramienta para crear una imagen de Arranque de Windows 10. La imagen puede incluir todas las actualizaciones actuales de Windows 10, Microsoft Office, otras aplicaciones y los controladores y firmware necesarios.

- Una unidad flash USB que contiene una imagen de Windows 10 Pro o Enterprise. A [continuación, instala controladores y firmware para Windows 10 Pro y Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) en Surface Hub 2.
 
Los siguientes pasos muestran cómo crear una unidad flash USB a partir de los medios de instalación y, a continuación, agregar los archivos del paquete SEMM y los controladores y firmware de Windows 10 Pro y Enterprise OS en el archivo MSI de Surface Hub 2. Si usas otro método de implementación, ve a la sección Actualizar UEFI en [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar la sección migración del sistema operativo de este artículo.

> [!NOTE]
> Después de finalizar la instalación, necesitarás una licencia válida para Windows 10 Pro o Windows 10 Enterprise que sea independiente de la licencia existente de Windows 10 Team.

1. Para crear una instalación de Windows 10 Pro, sigue las instrucciones para descargar la herramienta de creación de medios [en Descargar Windows 10.](https://www.microsoft.com/software-download/windows10) Para descargar Windows 10 Enterprise, vaya al Centro de servicios de [licencias por volumen de Microsoft.](https://www.microsoft.com/licensing/servicecenter/default.aspx)

1. Inserta una nueva unidad de almacenamiento USB.
1. Abra la herramienta de creación de medios, **seleccione Crear medios de instalación**y, a continuación, seleccione **Siguiente.**

   ![La captura de pantalla muestra la opción de crear medios de instalación.](images/shm-fig16.png)
   
3. Selecciona un idioma y, a continuación, **selecciona Windows 10** y **64 bits (x64).** A continuación, **seleccione Siguiente**.

   ![Screenshot shows where you select the language, O S edition, and architecture type.](images/shm-fig17.png)
   
4. Seleccione **unidad flash USB**y, a continuación, seleccione **Siguiente**.

   ![Screenshot shows where to select U S B flash drive.](images/shm-fig18.png)
   
5. Cuando finalice la descarga, seleccione **Finalizar**.

   ![La pantalla informa de que la unidad U S B está lista e incluye un botón Finalizar.](images/shm-fig19.png)
   
6. Copia los archivos del paquete SEMM y los controladores y firmware del sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (el archivo MSI) en la raíz de la unidad flash USB *(BOOTME)* que contiene la imagen de Windows 10. La unidad USB BOOTME contendrá:

    - La imagen de arranque de Windows 10.
    
    - Los archivos del paquete SEMM, copiados en la raíz de la unidad USB:
    
      - *DfciUpdate.dfi*.
      - Archivo de texto que incluye la huella digital de SEMM. (En este ejemplo, el archivo se *SurfaceUEFI_2020Aug25_1058.txt*.) La marca de fecha y hora generada automáticamente corresponde a la fecha en la que creaste el archivo mediante el Configurador de UEFI de Surface.

   - Controladores y firmware de Windows 10 Pro y Enterprise OS en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copia este archivo en la raíz de la unidad USB.

### Actualizar UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserta la unidad BOOTME en el puerto USB-A en Surface Hub 2S. Para obtener una lista de su contenido necesario, vea la sección anterior.

1. Para arrancar en UEFI:

   1. Desactiva (apaga) Surface Hub 2S.
   1. Mantén presionado **Volumen +** y, a continuación, presiona y suelta el botón de encendido. Mantén presionado **Volumen + hasta** que aparezca el menú UEFI.
   
      ![El dibujo muestra los botones de volumen y energía.](images/shm-fig20.png)
      
3. Cuando se reinicie el dispositivo, escribe la contraseña de UEFI que creaste anteriormente, si procede (recomendado).

   ![Pantalla de contraseña del sistema.](images/shm-fig22.png)
   
4. En el menú UEFI, seleccione **Administración.** A **continuación, seleccione Instalar desde USB.**

   ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)
   
5. Seleccione **Reiniciar ahora,** como se muestra en la siguiente imagen. El dispositivo se reiniciará. Se mostrará un logotipo blanco de Microsoft en medio de la ventana y, a continuación, se apagará.

   ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)
   
6. Presione y suelte el botón de encendido. En el cuadro de diálogo rojo que aparece, elige activar el Modo de administración de Surface Enterprise.

7. Escribe la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI. A continuación, **seleccione Aceptar**.

   ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)
 
   > [!NOTE]
   > Después de activar SEMM en el dispositivo, se aplica la nueva configuración de UEFI **EnableOSMigration.** Ya no puedes acceder a Windows 10 Team. En su lugar, debes continuar con el siguiente paso e instalar Windows 10 Pro o Windows 10 Enterprise.

   El dispositivo se reinicia. Muestra el logotipo blanco en medio de la pantalla y, a continuación, se apaga de nuevo.

### Instalar Windows 10 Pro o Enterprise

1. Si la unidad de arranque de Windows 10 Pro o Enterprise aún no está en el puerto USB-A de Surface Hub 2, insértela ahora. A continuación, presione y suelte el botón de encendido.

    Cuando se inicie el dispositivo, verás el logotipo blanco en medio de la pantalla. A continuación, aparece un círculo giratorio debajo del logotipo blanco.

3. Si el dispositivo Surface no arranca automáticamente en la unidad USB, apaga el dispositivo (desconecta el cable de alimentación y vuelve a conectarlo). Después de volver a conectar el cable de alimentación, el dispositivo debe arrancar después de unos segundos. A continuación, verás el logotipo blanco en medio de la pantalla.

    Si el dispositivo no se activa, presiona y suelta el botón de encendido. Inmediatamente después de ver el logotipo en medio de la pantalla, mantén presionado el botón de volumen hasta que veas el círculo giratorio debajo del logotipo blanco.
 
   ![Imagen de los botones de volumen y energía.](images/shm-fig26.png)
   
4. Cuando se inicie la configuración rápida (OOBE), sigue las instrucciones para instalar Windows 10 Pro o Enterprise (versión 1903 o posterior).

### Instalar controladores y firmware de Surface Hub 2

Para asegurarte de que Surface Hub 2 esté actualizado, instala controladores y [firmware para Windows 10 Pro y Enterprise.](https://www.microsoft.com/download/details.aspx?id=101974) A continuación, reinicia el dispositivo. Mantén surface activado durante una hora y, a continuación, reinicia de nuevo. No se te pedirá el segundo reinicio. Esta pausa y el reinicio adicional garantiza que el firmware se ha actualizado completamente.
 
## Configuración de las opciones recomendadas

Para configurar Surface Hub 2S como dispositivo de productividad personal, consulta Configurar [Windows 10 Pro o Enterprise en Surface Hub 2.](surface-hub-2-post-install.md)

> [!NOTE]
>Si no puedes migrar correctamente el dispositivo a Windows 10 Pro o Enterprise para Surface Hub 2 siguiendo los pasos descritos en este artículo, ponte en contacto con el soporte técnico [de Surface Hub.](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## Para revertir a Windows 10 Team

Si quieres restaurar el dispositivo a Windows 10 Team, consulta Restablecer y [recuperar para Surface Hub 2S.](surface-hub-2s-recover-reset.md)

> [!NOTE]
> Antes de volver a Windows 10 Team, te recomendamos que primero desenrolles Surface Hub de SEMM. Para obtener más información, consulta [La inscripción de dispositivos Surface desde SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Historial de versiones

En la tabla siguiente se resumen los cambios realizados en este artículo.

| Versión | Date               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de diciembre de 2020 | Proporciona [](#install-surface-hub-2-drivers-and-firmware) más información sobre la instalación del archivo MSI para "Controladores y firmware para windows 10 Pro y enterprise OS en Surface Hub 2", lo que aconseja que sea necesario un segundo reinicio en función del estado del sistema.                                                          |
| v. 1.3  | 3 de diciembre de 2020 | Se actualizó con instrucciones sobre [cómo administrar la inscripción de SEMM.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29 de septiembre de 2020 | Actualizaciones varias que abordan los comentarios sobre la facilidad de uso.                                                        |
| v. 1.1  | 15 de septiembre de 2020 | Se ha colocado una nota adicional en la introducción que aclara los requisitos de licencia para instalar un nuevo sistema operativo. |
| v. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

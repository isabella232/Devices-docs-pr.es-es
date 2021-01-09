---
title: Migrar a Windows 10 Pro o Enterprise en Surface Hub 2
description: En este artículo se describe cómo migrar de Windows 10 Team en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
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
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255492"
---
# Migrar a Windows 10 Pro o Enterprise en Surface Hub 2

- [Historial de versiones de artículo](#version-history)

Surface Hub 2S viene preinstalado con Windows 10 Team. Esta edición personalizada de Windows 10 está diseñada para facilitar la colaboración en entornos de salas de reuniones. Ahora tienes la opción de ejecutar Windows 10 Pro o Enterprise para usar Surface Hub 2S de forma muy parecido a cualquier otro equipo. 

> [!IMPORTANT]
>A diferencia de una actualización o migración típica, este proceso requiere que siga un procedimiento prescriptivo, como se describe en este artículo. Revise los componentes [de la solución y](#solution-components) el flujo de trabajo de migración [e](#migration-and-installation-workflow-summary) instalación antes de continuar.


> [!NOTE]
> Al instalar Windows 10 Pro o Enterprise, necesitas una nueva licencia independiente de la licencia existente de Windows 10 Team. 


Inicia la migración desde Windows 10 Team mediante un equipo independiente y la herramienta descargable *Surface UEFI Configurator*. Usa la herramienta para crear un paquete que contenga una nueva configuración de UEFI que apliques a Surface Hub 2S.  

El Configurador de UEFI de Surface funciona como una interfaz en el Modo de administración de Surface Enterprise (SEMM). Está diseñado para facilitar la administración centralizada de la configuración de firmware en dispositivos Surface en un entorno corporativo. Para obtener más información, consulte la <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> documentación de Microsoft </a> SEMM.
 

## Componentes de la solución

- Dispositivo Surface Hub 2S que ejecuta el sistema operativo Windows 10 Team
- Dispositivo independiente que ejecuta Windows 10
- Herramienta Configurador de UEFI de Surface para crear el paquete SEMM
- Imagen del sistema operativo Windows 10 Pro o Enterprise, versión 1903 o posterior
- Dos unidades USB con 16 GB de almacenamiento, en formato FAT32
- Controladores y firmware para Windows 10 Pro y el sistema operativo Enterprise en el archivo Microsoft Windows Installer (MSI) de Surface Hub 2
- Conexión a Internet
- Solución de creación de imágenes (opcional)

 
## Resumen de flujo de trabajo de migración e instalación

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Comprueba que la versión de UEFI en Surface Hub 2S cumple los requisitos mínimos.](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Asegúrate de que la versión uefi sea 694.2938.768.0 o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Descarga el firmware y los controladores de Surface UEFI Configurator y Surface Hub 2.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **página Herramientas de Surface para TI,** </a> selecciona **Descargar.** A continuación, selecciona y descarga **el Configurador de UEFI de Surface. ARCHIVO MSI** e instállo en un equipo independiente. Descarga los <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> controladores y el firmware para Windows 10 Pro y enterprise OS en el archivo MSI de Surface Hub 2.</a> Guárdelo para usarlo en el paso 5. |
| 3 | [Preparar el certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepara el certificado necesario para ejecutar el Configurador de UEFI de Surface. O bien, use el certificado actual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Crea un paquete de SEMM.](#create-a-semm-package)                                                                               | Inicia el Configurador de UEFI de Surface para crear un paquete SEMM en una unidad USB, que contendrá los archivos de configuración que debes aplicar en Surface Hub 2S. Copia estos archivos de paquete SEMM en una carpeta del equipo.                                                                                                                                                                                          |
| 5 | [Prepara una unidad flash USB que contenga la imagen de Windows 10, el paquete SEMM y los controladores y el firmware del sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2.](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crea una sola unidad USB que contenga una imagen de Windows 10. En este ejemplo, la unidad se denomina *BOOTME*. Agrega los controladores y el firmware para El sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (paso 2) y los archivos de paquete SEMM (paso 4) a la unidad *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Actualiza UEFI en Surface Hub 2S para habilitar la migración del sistema operativo.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Usa la *unidad BOOTME* para arrancar Surface Hub 2S en el menú UEFI e instalar el paquete SEMM.|
| 7 | [Instala Windows 10 Pro o Enterprise versión 1903 o posterior.](#install-windows-10-pro-or-enterprise)                                        | Usa la *unidad BOOTME* para instalar Windows 10 Pro o Enterprise versión 1903 o posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instala controladores y firmware para el sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2.](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarte de que el dispositivo tiene todas las actualizaciones y controladores más recientes, instala los controladores y el firmware para el sistema operativo Windows 10 Pro y Enterprise en el archivo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> MSI de Surface Hub 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configura completamente Surface Hub 2S como dispositivo de productividad personal.](#configure-recommended-settings)                                        |  Habilita la configuración y las aplicaciones recomendadas para optimizar Surface Hub 2S como dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### Comprobar que la versión de UEFI en Surface Hub 2S cumple los requisitos mínimos

Antes de migrar Surface Hub de Windows 10 Team a Windows 10 Desktop, necesitas una versión UEFI que sea al menos *694.2938.768.0.*
 
**Para comprobar la versión de UEFI en el sistema:**

1. En la página principal de Surface **** Hub 2S, selecciona Inicio y, a continuación, abre la aplicación Surface **(Todas las aplicaciones**  >  **Surface).**

2. Selecciona **Tu Surface para** mostrar información sobre Surface Hub, incluida la versión actual de UEFI en el dispositivo. 
   - Si la versión de UEFI es *694.2938.768.0* o posterior, como se muestra en la siguiente imagen, puedes crear el paquete SEMM para habilitar la migración del sistema operativo.

       ![Captura de pantalla que muestra la página De Surface en la aplicación Surface.](images/shm-fig1.png)
 
   - Si la versión de UEFI es anterior a la versión 694.2938.768.0, deberá obtener una versión actual instalando la imagen de Windows 10 Team 2020 Update Bare Metal Recovery (BMR) o mediante Windows Update.
   
**Para actualizar UEFI a través de Windows Update:**

1. En Surface Hub 2S, inicia sesión como **administrador.** 

    >[!Note]
    > Si no conoces tu nombre de usuario o contraseña de administrador, tendrás que restablecer el dispositivo. Para obtener más información, consulta <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> Restablecer y recuperar Surface Hub 2S.</a>

1. Ve a **Todas las aplicaciones Actualización de**  >  **configuración**y  >  **Seguridad de**Windows  >  **Update**y, a continuación, instala todas las actualizaciones. 

1. Reinicia el dispositivo. 

1. Comprueba la versión de UEFI mediante la aplicación Surface.

1. En este punto, si la versión de UEFI aún no es la versión 694.2938.768.0 o posterior, puede repetir los pasos anteriores o puede obtener la UEFI más reciente instalando la imagen de Windows 10 Team 2020 Update Bare Metal Recovery (BMR).

**Para actualizar UEFI a través de la imagen de recuperación de reconstrucción completa (BMR):**

1.  Ve al sitio [de recuperación de Surface](https://support.microsoft.com/surfacerecoveryimage) y selecciona Surface Hub **2S.**

3.  Escribe tu número de serie de concentrador (ubicado en el lado posterior del hub junto a la conexión de alimentación).

4.  Sigue las instrucciones para descargar la imagen en una unidad USB con formato mediante la instalación de Windows 10 Team 2020 Update.

5.  Una vez completada la actualización y el dispositivo entra en la configuración OOBE por primera vez, no es necesario completar la OOBE, se actualizará la versión de UEFI. En su lugar, apaga el dispositivo manteniendo presionado el botón de encendido hasta que se apague la pantalla. 

### Descargar controladores y firmware de Surface UEFI Configurator y Surface Hub 2

En un equipo independiente:

1. En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página Herramientas de Surface para </a> TI, selecciona **Descargar.**

1. Selecciona y descarga el archivo MSI del Configurador de UEFI de Surface e instálelo en un equipo independiente. La herramienta Configurador de UEFI de Surface no se puede ejecutar en Surface Hub 2S mientras esté instalada la edición Windows 10 Team.

1. Descarga el archivo MSI de Windows Installer de controladores y firmware de <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub </a> 2. Usarás este archivo al instalar el nuevo sistema operativo.

### Preparar el certificado SEMM

Si no has usado el Configurador de UEFI de Surface antes, debes preparar un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo puedes modificar la configuración de UEFI mediante paquetes creados con el certificado aprobado. 

La forma en que se obtiene un certificado depende del tamaño o la complejidad de la organización:

- Las organizaciones empresariales suelen mantener su propia infraestructura para generar certificados de acuerdo con las prácticas de seguridad estándar.

- Las empresas medianas y otras pueden optar por obtener certificados de proveedores asociados. Esta opción se recomienda para las organizaciones que no tienen suficiente experiencia en TI o un equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado mediante un script de PowerShell. Para obtener más información, consulta los requisitos <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> de certificado del Modo de administración de Surface </a> Enterprise. O bien, puede usar PowerShell para crear su propio certificado. Para obtener más información, consulte <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> la documentación de New-SelfSignedCertificate. </a>

El paquete SEMM que crea el Configurador de UEFI de Surface debe estar protegido con un certificado. El certificado comprueba la firma de los archivos de configuración antes de que se pueda aplicar la configuración de UEFI. Para obtener más información, consulte la documentación <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> de </a> SEMM.
 
 
### Crear un paquete SEMM

1. En un equipo independiente, instala la herramienta Configurador de UEFI de Surface que descargaste anteriormente. 

2. Abre el Configurador de UEFI de Surface y, a continuación, selecciona **Inicio.**

   ![Abre el Configurador de UEFI de Surface.](images/shm-fig2.png)
   
3. Seleccione **Dispositivos Surface**y, a continuación, **seleccione Siguiente**.

   ![Selecciona Dispositivos Surface.](images/shm-fig3.png)
  
4. Seleccione **Paquete de configuración.**

   ![Seleccione Paquete de configuración.](images/shm-fig4.png)
  
5. Seleccione **Protección de certificados.**

   ![Seleccione Protección de certificados.](images/shm-fig5.png)

   Se te pedirá que agregues el archivo .pfx del certificado.

   ![Agregue el certificado.](images/shm-fig6.png)
   
7. Escriba la contraseña del certificado y, a continuación, **seleccione Aceptar**.

   ![Escriba la contraseña del certificado y seleccione Aceptar.](images/shm-fig7.png)

8. Selecciona **Protección con contraseña** para agregar una contraseña a la UEFI de Surface. Necesitarás esta contraseña siempre que arranques en UEFI. Te *recomendamos encarecidamente* que establezcas una contraseña de UEFI que usarás en Surface Hub 2S.

   ![Seleccione Protección con contraseña.](images/shm-fig8.png)
   
9. Establezca una contraseña de UEFI y, a continuación, seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarda la contraseña en una ubicación segura a la que puedan acceder los administradores de TI que administran Surface Hub. Si se pierde la contraseña, no se puede recuperar. 

   ![Escribe la contraseña de UEFI.](images/shm-fig9.png)

10. Selecciona **Surface Hub 2S**y, a continuación, selecciona **Siguiente.**

    ![Selecciona Surface Hub 2S.](images/shm-fig10.png)
   
11. Selecciona **Siguiente**.

    ![Selecciona Siguiente.](images/shm-fig10a.png)

12. Para permitir la instalación de Windows 10 Pro o Enterprise, active **EnableOsMigration**y, a continuación, seleccione **Siguiente**.

    ![Seleccione Habilitar migración de O S.](images/shm-fig11.png)
    
    ![Establecer Habilitar migración del sistema operativo en Activar.](images/shm-fig12.png)

### Administración de la inscripción de SEMM

Inscribir dispositivos en SEMM afecta a cómo puedes administrar el dispositivo en el futuro. Por ejemplo, después de aplicar un paquete SEMM, en el menú UEFI del dispositivo, todas las configuraciones de UEFI no están disponibles (bloqueadas). Los valores predeterminados de otras configuraciones, **como IPv6 para el arranque PXE,** tampoco están disponibles. 

Para cambiar la configuración de UEFI después de finalizar la migración, aplica otro paquete de SEMM o desenrolla el dispositivo de SEMM. Si aplicas otro paquete de SEMM para cambiar la configuración de UEFI, debes usar el certificado original al compilar el nuevo paquete de SEMM. Use la herramienta configurador UEFI y deje **EnableOSMigration** desactivado (no habilitado, como se muestra en los pasos de migración originales).

#### Trabajar con asociados

Si tu empresa subcontrata la migración a Windows 10 Pro o Enterprise en Surface Hub 2, es posible que quieras que el partner te transfiera el certificado SEMM, el paquete SEMM y la contraseña de UEFI.  Como alternativa, después de migrar el concentrador, puedes deshacer inmediatamente la inscripción desde SEMM, lo que permitirá la administración local de UEFI y la transferencia del dispositivo a otra parte. No obstante, se recomienda encarecidamente usar una contraseña de UEFI, que se puede configurar después de la migración. Para obtener más información, consulta [Administrar la configuración de LA UEFI de Surface.](https://docs.microsoft.com/surface/manage-surface-uefi-settings) 

#### Revertir a Windows 10 Team

Si después de migrar eliges restaurar el dispositivo a Windows 10 [Team,](#roll-back-to-windows-10-team)como se describe a continuación, se recomienda que primero se desenrolle Hub de SEMM. Para obtener más información, consulta [Deshacer la inscripción de dispositivos Surface desde SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)


#### Guardar el paquete SEMM en una unidad USB

1. Conecta una unidad USB al equipo. 

1. Elija **Hub 2S**y, a continuación, **seleccione Siguiente.**

   ![Seleccionar USB](images/shm-fig13.png)

   > [!WARNING]
   > Todos los datos existentes en la unidad USB se borran cuando se ha creado el paquete SEMM. Antes de compilar el paquete SEMM, quita los archivos de la unidad USB que quieras guardar.
   
2. Seleccione **Generar**.

   ![Seleccione Generar.](images/shm-fig14.png)

3. Capture una captura de pantalla de esta página y, a continuación, seleccione **Finalizar**. El paquete de SEMM ya está listo. Contiene el paquete de SEMM *DfciUpdate.dfi* y un archivo de texto que incluye la huella digital de SEMM (los dos últimos caracteres de la huella digital del certificado).

   ![Seleccione Fin.](images/shm-fig15.png)
   
4. Guarde los dos últimos caracteres de la huella digital del certificado. Necesitarás estos caracteres para activar SEMM cuando apliques el paquete en Surface Hub 2S.

### Preparar una unidad flash USB que contenga una imagen de Windows 10, un paquete SEMM y controladores y firmware de Surface Hub 2

Puedes instalar una imagen de Windows 10 Pro o Enterprise (versión 1903 o posterior) mediante una de las siguientes opciones:

- La solución de creación de imágenes actual.

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> Acelerador de implementaciones de </a> Surface. Usa esta herramienta para crear una imagen de Arranque de Windows 10. La imagen puede incluir todas las actualizaciones actuales de Windows 10, Office, otras aplicaciones que elija y los controladores y firmware necesarios. 

- Unidad flash USB que contiene una imagen de Windows 10 Pro o Enterprise. A continuación, instala controladores y firmware para El sistema operativo <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro y Enterprise en Surface Hub 2. </a>
 
En el siguiente procedimiento se describe cómo crear una unidad flash USB a partir de medios de instalación y, a continuación, agregar los archivos del paquete SEMM y los controladores y firmware para el sistema operativo Windows 10 Pro y Enterprise en el archivo MSI de Surface Hub 2. Si estás usando otros métodos de implementación, ve a la sección Actualizar UEFI en [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar la sección migración del sistema operativo en este artículo.

> [!NOTE]
> Después de finalizar la instalación, necesitarás una licencia válida para Windows 10 Pro o Windows 10 Enterprise que sea independiente de la licencia existente de Windows 10 Team.

1. Para crear una instalación de Windows 10 Pro, en la página Descargar Windows 10, sigue las instrucciones para <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> descargar la herramienta de creación de </a> medios. Para descargar Windows 10 Enterprise, vaya al Centro de servicios <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> de licencias por volumen de </a> Microsoft.

1. Inserta una nueva unidad de almacenamiento USB. 

1. Abra la herramienta de creación de medios, **seleccione Crear medios de instalación**y, a continuación, seleccione **Siguiente.**

   ![Crear medios de instalación.](images/shm-fig16.png)
   
1. Selecciona un idioma y, a continuación, **elige Windows 10** y **64 bits (x64).** A continuación, **seleccione Siguiente**.

   ![Selecciona el idioma y elige Windows 10 y 64 bits. A continuación, seleccione Siguiente.](images/shm-fig17.png)
   
1. Seleccione **unidad flash USB**y, a continuación, seleccione **Siguiente**.

   ![Selecciona unidad flash U S B y selecciona Siguiente.](images/shm-fig18.png)
   
1. Cuando finalice la descarga, seleccione **Finalizar**.

   ![Seleccione Finalizar.](images/shm-fig19.png)
   
1. Copia los archivos del paquete SEMM y los controladores y firmware del sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (el archivo MSI) en la raíz de la unidad flash USB *(BOOTME)* que contiene la imagen de Windows 10. La unidad USB BOOTME contiene:

    - La imagen de arranque de Windows 10.
    
    - Archivos de paquete SEMM (copiados en la raíz de la unidad USB).
    
      - *DfciUpdate.dfi*.
      - Archivo de texto que incluye la huella digital de SEMM. (En este ejemplo, el archivo se *SurfaceUEFI_2020Aug25_1058.txt*.) La marca de hora de fecha generada automáticamente corresponde a la fecha en la que creaste el archivo mediante el Configurador de UEFI de Surface.

   - Controladores y firmware para el sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copia este archivo en la raíz de la unidad USB.

### Actualizar UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserta la unidad BOOTME en el puerto USB-A en Surface Hub 2S. Para obtener una lista de los archivos necesarios, consulta la sección anterior.

2. Para arrancar en UEFI:

   1. Desactiva (apaga) Surface Hub 2S.
   1. Mantén presionado **Volumen +** y, a continuación, presiona y suelta el botón de encendido.
   1. Mantén presionado **Volumen + hasta** que aparezca el menú UEFI.
   
      ![Mantén presionado el botón de subir volumen hasta que aparezca el menú UEFI.](images/shm-fig20.png)
      
3. Cuando se reinicie el dispositivo, escribe la contraseña de UEFI que creaste anteriormente, si procede (se recomienda encarecidamente).

   ![Escribe la contraseña de UEFI.](images/shm-fig22.png)
   
4. En el menú UEFI, selecciona **Instalar**  >  **administración desde USB.**

   ![Seleccione Administración e instalación desde EE. UU. B.](images/shm-fig21.png)
   
5. Seleccione **Reiniciar ahora,** como se muestra en la siguiente imagen. El dispositivo se reinicia. Muestra un logotipo blanco de Microsoft en medio de la ventana y, a continuación, se cierra.

   ![Selecciona Reiniciar ahora.](images/shm-fig25.png)
   
6. Presione y suelte el botón de encendido. En la ventana roja que aparece, activa el Modo de administración de Surface Enterprise. 

7. Escribe la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI. A continuación, **seleccione Aceptar**.

   ![Escribe la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Después de activar SEMM en el dispositivo, se aplica la nueva configuración de UEFI **EnableOSMigration.** Ya no podrás acceder a Windows 10 Team. En su lugar, debes continuar con el siguiente paso e instalar Windows 10 Pro o Windows 10 Enterprise. 

   El dispositivo se reinicia. Muestra el logotipo blanco en medio de la pantalla y, a continuación, se apaga de nuevo.

### Instalar Windows 10 Pro o Enterprise

1. Si la unidad de arranque de Windows 10 Pro o Enterprise aún no está en el puerto USB-A de Surface Hub 2, insértela ahora. A continuación, presione y suelte el botón de encendido. 

    Cuando se inicia el dispositivo, ves el logotipo blanco en medio de la pantalla. A continuación, verá un círculo giratorio debajo del logotipo blanco.

3. Si el dispositivo no arranca automáticamente en la unidad USB, apaga el dispositivo (desconecta el cable de alimentación y vuelve a conectarlo). Después de volver a conectar el cable de alimentación, el dispositivo debe arrancar después de unos segundos. A continuación, verás el logotipo blanco en medio de la pantalla. 

    Si el dispositivo no se activa, presione y suelte el botón de encendido. Inmediatamente después de ver el logotipo en medio de la pantalla, mantén presionado el botón Volumen **-** hasta que veas el círculo giratorio debajo del logotipo blanco.
 
   ![Arranque en Windows 10 desde la unidad U S B.](images/shm-fig26.png)
   
4. Cuando se inicie la configuración rápida (OOBE), sigue las instrucciones para instalar Windows 10 Pro o Enterprise (versión 1903 o posterior).

### Instalar controladores y firmware de Surface Hub 2

Para asegurarte de que el dispositivo tiene todas las actualizaciones y controladores más recientes, instala controladores y firmware para <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Windows 10 Pro y Enterprise OS en Surface Hub </a> 2. Después de instalar los controladores y firmware MSI, reinicia el dispositivo. A continuación, después de volver a encender el hub, mantén el equipo encendido durante una hora y reinicia el dispositivo de nuevo. No se te pedirá el segundo reinicio. Según el estado de la máquina antes de migrar a Windows 10 Pro o Enterprise, este segundo paso puede ser necesario para garantizar que todo el firmware se ha actualizado.
 
## Configuración de las opciones recomendadas

Para configurar completamente Surface Hub 2S como dispositivo de productividad personal, consulta Configurar <a href="surface-hub-2-post-install.md" target="_blank"> Windows 10 Pro o Enterprise en Surface Hub </a> 2.

> [!NOTE]
>Si los pasos descritos en este artículo no migran correctamente el dispositivo a Windows 10 Pro o Enterprise para Surface Hub 2, ponte en contacto con el soporte <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> técnico de Surface </a> Hub.

## Revertir a Windows 10 Team

Si quieres restaurar el dispositivo a Windows 10 Team, consulta Restablecer y <a href="surface-hub-2s-recover-reset.md" target="_blank"> recuperar para Surface Hub 2S. </a>

> [!NOTE]
> Antes de volver a Windows 10 Team, se recomienda que primero se desenrolle Hub de SEMM. Para obtener más información, consulta [Deshacer la inscripción de dispositivos Surface desde SEMM.](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)

## Historial de versiones

En la tabla siguiente se resumen los cambios realizados en este artículo.

| Versión | Date               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de diciembre de 2020 | Proporciona [](#install-surface-hub-2-drivers-and-firmware) más información sobre la instalación del archivo MSI para "Controladores y firmware para Windows 10 Pro y el sistema operativo Enterprise en Surface Hub 2", lo que aconseja que sea necesario un segundo reinicio en función del estado del sistema.                                                          |
| v. 1.3  | 3 de diciembre de 2020 | Se actualizó con instrucciones sobre [cómo administrar la inscripción de SEMM.](#managing-semm-enrollment)                                                       |
| v. 1.2  | 29 de septiembre de 2020 | Actualizaciones varias que abordan los comentarios sobre la facilidad de uso.                                                        |
| v. 1.1  | 15 de septiembre de 2020 | Se ha colocado una nota adicional en la introducción que aclara los requisitos de licencia para instalar un nuevo sistema operativo. |
| v. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

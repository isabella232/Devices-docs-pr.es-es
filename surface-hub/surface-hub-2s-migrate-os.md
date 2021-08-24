---
title: Migrar a Windows 10 Pro o Enterprise en Surface Hub 2
description: Cómo migrar de Windows 10 Team en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
keywords: Surface Hub Escritorio, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: bdf39a2e664aa9abbd2fbf4790aec0b04c084f64
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911885"
---
# <a name="migrate-to-windows-10-pro-or-enterprise-on-surface-hub-2"></a>Migrar a Windows 10 Pro o Enterprise en Surface Hub 2

- [Historial de versiones de artículo](#version-history)

Surface Hub 2S viene con Windows 10 Team instalado. Esta edición personalizada de Windows 10 facilita la colaboración en entornos de salas de reuniones. Ahora puede ejecutar en su lugar Windows 10 Pro o Enterprise para usar su Surface Hub 2S como cualquier otro equipo.

> [!IMPORTANT]
> Este proceso de migración requiere que siga el procedimiento específico que se describe en este artículo. Antes de continuar, lea [Componentes de la solución y](#solution-components) Flujo de trabajo de migración e [instalación.](#migration-and-installation-workflow-summary)

> [!NOTE]
> Cuando instalas Windows 10 Pro o Enterprise en tu Surface Hub 2S, necesitas una nueva licencia que sea distinta de la licencia Windows 10 Team existente proporcionada con el dispositivo.

Inicia la migración desde Windows 10 Team usando un equipo independiente y la herramienta descargable *Surface UEFI Configurator.* La herramienta crea un paquete que contiene una nueva configuración UEFI que se aplica al Surface Hub 2S.  

Surface UEFI Configurator funciona como una interfaz en Surface Enterprise Management Mode (SEMM). Permite la administración centralizada de la configuración de firmware en dispositivos Surface en un entorno corporativo. Para obtener más información, consulta [Microsoft Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode).
 
## <a name="solution-components"></a>Componentes de la solución

- Surface Hub dispositivo 2S que se ejecuta Windows 10 Team
- Dispositivo independiente que se ejecuta Windows 10
- Herramienta Configurador UEFI de Surface para crear el paquete SEMM
- Windows 10 Pro o Enterprise del sistema operativo, versión 1903 o posterior
- Dos unidades USB con 16 GB de almacenamiento, formato FAT32
- Controladores y firmware para Windows 10 Pro y Enterprise en un archivo Surface Hub 2 Microsoft Windows Installer (MSI)
- Conexión a Internet
- Solución de imágenes (opcional)
 
## <a name="migration-and-installation-workflow-summary"></a>Resumen de flujo de trabajo de migración e instalación

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Compruebe la versión uefi en el Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).                                  | La versión UEFI debe ser *la 694.2938.768.0* o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Descarga Surface UEFI Configurator y el Surface Hub 2 controladores y firmware.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | En la **[página Herramientas de Surface para TI,](https://www.microsoft.com/download/details.aspx?id=46703)** selecciona </a> **Descargar**. A continuación, selecciona y descarga el archivo MSI de **UEFI Configurator de Surface**e instálelo en un equipo independiente. Descargue también los [controladores y el firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub archivo MSI 2](https://www.microsoft.com/download/details.aspx?id=101974).</a> Guarde este paquete para usarlo en el paso 5. |
| 3 | [Prepare el certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare el certificado necesario para ejecutar Surface UEFI Configurator o usar el certificado actual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Cree un paquete SEMM.](#create-a-semm-package)                                                                               | Inicia Surface UEFI Configurator para crear un paquete SEMM en una unidad USB. Este paquete contendrá los archivos de configuración que necesita aplicar en Surface Hub 2S. Copie estos archivos de paquete SEMM en una carpeta del equipo.                                                                                                                                                                                          |
| 5 | [Cargue una unidad flash USB con Windows 10 imagen, el paquete SEMM, los controladores y el firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Crea una unidad USB que contenga una Windows 10 imagen. En este ejemplo, la unidad se denomina *BOOTME*. Agregue los controladores y el firmware para el sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (del paso 2) y los archivos de paquete SEMM (del paso 4) a la unidad *BOOTME.*                                                                                                                                                                                                  |
| 6 | [Actualice la UEFI en el Surface Hub 2S para habilitar la migración del sistema operativo.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use la *unidad BOOTME* para arrancar el Surface Hub 2S en el menú UEFI e instalar el paquete SEMM.|
| 7 | [Instale Windows 10 Pro o Enterprise.](#install-windows-10-pro-or-enterprise)                                        | Use la *unidad BOOTME* para instalar Windows 10 Pro o Enterprise versión 1903 o posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instale controladores y firmware para Windows 10 Pro y Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarse de que el dispositivo tiene todas las actualizaciones y controladores más recientes, instale los controladores y el firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> archivo MSI 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configura Surface Hub 2S como dispositivo de productividad personal.](#configure-recommended-settings)                                        |  Habilita la configuración y las aplicaciones recomendadas para optimizar Surface Hub 2S como dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>Comprobar la versión UEFI en Surface Hub 2S

Antes de migrar Surface Hub de Windows 10 Team a Windows 10 Desktop, necesita UEFI versión *694.2938.768.0* o posterior.
 
**Para comprobar la versión uefi en el sistema:**

1. En la Surface Hub principal de 2S, selecciona **Inicio**y, a continuación, abre la aplicación Surface (**Todas las aplicaciones**  >  **Surface**).

2. Selecciona **Tu Surface para** mostrar información sobre Surface Hub, incluida la versión actual de UEFI en el dispositivo. 
   - Si la versión UEFI es *694.2938.768.0* o posterior, como se muestra en la siguiente imagen, puede crear el paquete SEMM para habilitar la migración del sistema operativo.

       ![La captura de pantalla muestra la página "Tu Surface" en la aplicación Surface.](images/shm-fig1.png)
 
   - Si la versión uefi es anterior a la *versión 694.2938.768.0*, use uno de los métodos siguientes para obtener una versión más reciente
   
#### <a name="update-uefi-via-windows-update"></a>Actualizar UEFI a través de Windows Update

1. En el Surface Hub 2S, inicie sesión como **Administrador**.

    >[!Note]
    > Si no conoces tu nombre de usuario o contraseña de administrador, tendrás que restablecer el dispositivo. Para obtener más información, vea [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

1. Ve a **Todas las aplicaciones**  >  **Configuración**  >  **Actualización y seguridad**Windows  >  **actualización**e instala todas las actualizaciones.
1. Reinicia el dispositivo.
1. Comprueba la versión uefi mediante la aplicación Surface. Si la versión UEFI no es *la 694.2938.768.0* o posterior, repita estos pasos o use el siguiente procedimiento para obtener la versión más reciente de UEFI.

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>Actualizar la UEFI a través de la imagen de recuperación de metal desnudo (BMR)

1.  Vaya al sitio [de recuperación de Surface](https://support.microsoft.com/surfacerecoveryimage) y seleccione Surface Hub **2S**.
3.  Escriba su número de serie de Concentrador. Se encuentra en la parte posterior del concentrador junto a la conexión de energía.
4.  Siga las instrucciones para descargar la imagen en una unidad USB con formato instalando la Windows 10 Team 2020 Update.
5.  Después de la actualización, el dispositivo entra en la configuración de la experiencia rápida (OOBE). No es necesario completar la configuración. La versión UEFI ya está actualizada. En su lugar, apaga el dispositivo manteniendo presionado el botón de encendido hasta que se apague la pantalla.

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>Descargar Surface UEFI Configurator y Surface Hub 2 controladores y firmware

En un equipo independiente, siga estos pasos:

1. En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página Herramientas de Surface para </a> TI, selecciona **Descargar**.  
1. Selecciona y descarga el archivo MSI de UEFI Configurator de Surface e instálelo en un equipo independiente. La herramienta Configurador UEFI de Surface no se puede ejecutar en un Surface Hub 2S mientras Windows 10 Team edición está instalada.

1. Descargue el Surface Hub 2 controladores y [firmware Windows archivo MSI del instalador.](https://www.microsoft.com/download/details.aspx?id=101974) Usará este archivo al instalar el nuevo sistema operativo.

### <a name="prepare-the-semm-certificate"></a>Preparar el certificado SEMM

Si no has usado Surface UEFI Configurator antes, debes preparar un certificado. Este certificado garantiza que, después de inscribir un dispositivo en SEMM, solo puede modificar la configuración de UEFI mediante paquetes creados con el certificado aprobado.

La forma de obtener un certificado depende del tamaño o complejidad de la organización:

- Enterprise suelen mantener su propia infraestructura para generar certificados de acuerdo con las prácticas de seguridad estándar.

- Las empresas medianas y otras suelen optar por obtener certificados de los proveedores de partners. Esta opción se recomienda para organizaciones que no tienen tanta experiencia en TI o carecen de un equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado mediante un script de PowerShell. Para obtener más información, consulta los requisitos [del certificado Enterprise modo de administración de Surface.](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements) O puede usar PowerShell para crear su propio certificado. Para obtener más información, consulte la [documentación del certificado autofirmado.](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate)

El paquete SEMM que crea Surface UEFI Configurator debe protegerse con un certificado. El certificado comprueba la firma de los archivos de configuración antes de poder aplicar la configuración de UEFI. Para obtener más información, consulte la documentación [de SEMM.](/surface/surface-enterprise-management-mode)
 
### <a name="create-a-semm-package"></a>Crear un paquete SEMM

1. En un equipo independiente, instala la herramienta Configurador de UEFI de Surface que descargaste anteriormente.

1. Abra El Configurador UEFI de Surface y, a continuación, **seleccione Inicio**.

   ![Pantalla de inicio de Surface UEFI Configurator.](images/shm-fig2.png)
   
1. Selecciona **Dispositivos Surface**y, a continuación, **selecciona Siguiente**.

   ![La captura de pantalla muestra la opción Dispositivos Surface seleccionada.](images/shm-fig3.png)
  
1. Seleccione **Paquete de configuración**.

   ![La captura de pantalla muestra "Seleccionar paquete de configuración" seleccionado.](images/shm-fig4.png)
  
1. Seleccione **Protección de certificados**.

   ![Las capturas de pantalla muestran cómo elegir "Seleccionar protección de certificados".](images/shm-fig5.png)

   Se le pedirá que agregue el archivo .pfx del certificado.

   ![La captura de pantalla muestra dónde agregar el archivo de certificado.](images/shm-fig6.png)
   
1. Escriba la contraseña del certificado y, a continuación, **seleccione Aceptar**.

   ![La captura de pantalla muestra campos para especificar y confirmar la contraseña del certificado.](images/shm-fig7.png)

1. Selecciona **Protección con contraseña** para agregar una contraseña a la UEFI de Surface. Necesitarás esta contraseña siempre que arranques en la UEFI. *Le recomendamos encarecidamente que establezca una contraseña UEFI que usará en Surface Hub 2S.*

   ![La captura de pantalla muestra dónde seleccionar Protección con contraseña.](images/shm-fig8.png)
   
1. Establezca una contraseña uefi y, a continuación, seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarde la contraseña en una ubicación segura a la que puedan acceder los administradores de TI que administran Surface Hub. *Si se pierde esta contraseña, no se puede recuperar.*

   ![La captura de pantalla muestra dónde se establece la contraseña uefi.](images/shm-fig9.png)

1. Seleccione **Surface Hub 2S**y, a continuación, **seleccione Siguiente**.

    ![La captura de pantalla muestra dónde Surface Hub 2S.](images/shm-fig10.png)
   
1. Vuelva **a seleccionar** Siguiente.

    ![La captura de pantalla muestra para seleccionar Siguiente en "Elegir qué componentes".](images/shm-fig10a.png)

1. Para permitir la instalación de Windows 10 Pro o Enterprise, active **EnableOsMigration**y, a continuación, seleccione **Siguiente**.

    ![La captura de pantalla muestra dónde seleccionar Habilitar migración de O S.](images/shm-fig11.png)
    
    ![La captura de pantalla muestra dónde establecer habilitar la migración del sistema operativo en on.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>Administrar la inscripción de SEMM

Inscribir un dispositivo en SEMM afecta a la forma en que puedes administrarlo. Por ejemplo, después de aplicar un paquete SEMM, todas las configuraciones de UEFI no están disponibles (bloqueadas) en el menú UEFI del dispositivo. Los valores predeterminados de otras configuraciones, como **IPv6 para arranque PXE,** tampoco están disponibles.

Para cambiar la configuración de UEFI después de finalizar la migración, aplique otro paquete SEMM o desenrolle el dispositivo desde SEMM. Si aplica otro paquete SEMM para cambiar la configuración de UEFI, debe usar el certificado original al compilar el nuevo paquete SEMM. Use la herramienta Configurador UEFI y deje **EnableOSMigration** desactivado *(no* *como* en los pasos de migración originales).

#### <a name="if-you-work-with-partners"></a>Si trabaja con partners

Si su empresa subcontrata la migración de Surface Hub 2 a Windows 10 Pro o Enterprise, es posible que desee que el partner le transfiera el certificado SEMM, el paquete SEMM y la contraseña UEFI. O bien, después de migrar el concentrador, puede desenrollar inmediatamente desde SEMM. Este paso permite la administración local de UEFI y la transferencia del dispositivo a otra parte. Sin embargo, se recomienda encarecidamente que use una contraseña UEFI, que se puede configurar después de la migración. Para obtener más información, consulta [Administrar la configuración de UEFI de Surface](/surface/manage-surface-uefi-settings). 

#### <a name="to-roll-back-to-windows-10-team"></a>Para revertir a Windows 10 Team

Si eliges restaurar el dispositivo a Windows 10 Team después de la migración, como se describe más adelante en este [artículo,](#to-roll-back-to-windows-10-team)te recomendamos que primero desenrolles Hub de SEMM. Para obtener más información, consulta [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

#### <a name="save-the-semm-package-to-a-usb-drive"></a>Guardar el paquete SEMM en una unidad USB

1. Conectar una unidad USB al equipo.
1. Elija **Concentrador 2S**y, a continuación, **seleccione Siguiente**.

   ![La captura de pantalla muestra dónde seleccionar concentrador 2S.](images/shm-fig13.png)

   > [!WARNING]
   > Todos los datos existentes en la unidad USB se borrarán cuando se haya creado el paquete SEMM. Antes de crear el paquete SEMM, quite los archivos que necesite de la unidad USB.
   
1. Seleccione **Generar**.

   ![La captura de pantalla muestra dónde seleccionar Generar.](images/shm-fig14.png)

1. Captura una captura de pantalla de esta página y, a continuación, selecciona **Finalizar**. El paquete SEMM ya está listo. Contiene el paquete SEMM *DfciUpdate.dfi* y un archivo de texto que incluye la huella digital de *SEMM*, que son los dos últimos caracteres de la huella digital del certificado.

   ![La captura de pantalla muestra dónde seleccionar Finalizar.](images/shm-fig15.png)
   
4. Guarde los dos últimos caracteres de la huella digital del certificado. Necesitarás estos caracteres para activar SEMM cuando apliques el paquete en Surface Hub 2S.

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>Cargar una unidad flash USB con una imagen Windows 10, un paquete SEMM y Surface Hub 2 controladores y firmware

Puede instalar una imagen Windows 10 Pro o Enterprise (versión *1903* o posterior) mediante una de las siguientes opciones:

- La solución de imágenes actual.

- [Acelerador de implementación de Surface](/surface/microsoft-surface-deployment-accelerator). Use esta herramienta para crear una imagen Windows 10 arranque. La imagen puede incluir todas las actualizaciones Windows 10, Microsoft Office, otras aplicaciones y los controladores y firmware necesarios.

- Una unidad flash USB que contiene una Windows 10 Pro o Enterprise imagen. Esta opción no tendrá Wi-Fi disponible hasta después de la configuración de la experiencia de salida (OOBE). Una vez completada la instalación, instale el Surface Hub [2 controladores](https://www.microsoft.com/download/details.aspx?id=101974) y firmware para Windows 10 Pro y Enterprise en el dispositivo.
 
En los pasos siguientes se muestra cómo crear una unidad flash USB a partir de medios de instalación y, a continuación, agregar los archivos de paquete SEMM y los controladores y firmware para el sistema operativo Windows 10 Pro y Enterprise en un archivo MSI Surface Hub 2. Si usa otro método de implementación, vaya a la sección Actualizar UEFI en [Surface Hub 2S](#update-uefi-on-surface-hub-2s-to-enable-os-migration) para habilitar la migración del sistema operativo de este artículo.

> [!NOTE]
> Después de finalizar la instalación, necesitará una licencia válida para Windows 10 Pro o Windows 10 Enterprise que sea independiente de la licencia de Windows 10 Team existente.

1. Para crear una instalación Windows 10 Pro, siga las instrucciones para descargar la herramienta de creación de medios en [Descargar Windows 10](https://www.microsoft.com/software-download/windows10). Para descargar Windows 10 Enterprise, vaya al Centro de servicios de licencias por [volumen de Microsoft](https://www.microsoft.com/licensing/servicecenter/default.aspx).

1. Inserte una nueva unidad de almacenamiento USB.
1. Abra la herramienta de creación de medios, **seleccione Crear medios de instalación**y, a continuación, seleccione **Siguiente**.

   ![La captura de pantalla muestra la opción para crear medios de instalación.](images/shm-fig16.png)
   
3. Seleccione un idioma y, a **continuación, seleccione Windows 10** y **64 bits (x64).** A continuación, **seleccione Siguiente**.

   ![La captura de pantalla muestra dónde se selecciona el idioma, la edición O S y el tipo de arquitectura.](images/shm-fig17.png)
   
4. Seleccione **Unidad flash USB**y, a continuación, seleccione **Siguiente**.

   ![La captura de pantalla muestra dónde seleccionar la unidad flash U S B.](images/shm-fig18.png)
   
5. Cuando finalice la descarga, seleccione **Finalizar**.

   ![La pantalla informa de que la unidad U S B está lista e incluye un botón Finalizar.](images/shm-fig19.png)
   
6. Copie los archivos del paquete SEMM, los controladores y el firmware del sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2 (el archivo MSI) en la raíz de la unidad flash USB (*BOOTME*) que contiene la imagen Windows 10. La unidad USB BOOTME contendrá:

    - La Windows 10 de arranque.
    
    - Los archivos de paquete SEMM, copiados en la raíz de la unidad USB:
    
      - *DfciUpdate.dfi*.
      - Un archivo de texto que incluye la huella digital de SEMM. (En este ejemplo, el archivo *SurfaceUEFI_2020Aug25_1058.txt*.) La marca de fecha y hora generada automáticamente corresponde a la fecha en que creaste el archivo mediante Surface UEFI Configurator.

   - Controladores y firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie este archivo en la raíz de la unidad USB.

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>Actualizar UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserte la unidad BOOTME en el puerto USB-A del Surface Hub 2S. Para obtener una lista de su contenido necesario, consulte la sección anterior.

1. Para arrancar en UEFI:

   1. Desactiva (apaga) el Surface Hub 2S.
   1. Mantenga presionado **El volumen +** y, a continuación, presione y suelte el botón de encendido. Mantenga presionado **El volumen +** hasta que aparezca el menú UEFI.
   
      ![El dibujo muestra los botones de volumen y encendido.](images/shm-fig20.png)
      
3. Cuando se reinicie el dispositivo, escriba la contraseña UEFI que creó anteriormente, si procede (recomendado).

   ![Pantalla de contraseña del sistema.](images/shm-fig22.png)
   
4. En el menú UEFI, seleccione **Administración**. A  **continuación, seleccione Instalar desde USB**.

   ![La captura de pantalla muestra dónde seleccionar Administración y, a continuación, "Instalar desde U S B".](images/shm-fig21.png)
   
5. Seleccione **Reiniciar ahora**, como se muestra en la siguiente imagen. El dispositivo se reiniciará. Se mostrará un logotipo blanco de Microsoft en el centro de la ventana y, a continuación, se apagará.

   ![La captura de pantalla muestra un mensaje que le pide que se reinicie.](images/shm-fig25.png)
   
6. Presione y suelte el botón de encendido. En el cuadro de diálogo rojo que aparece, elige activar Surface Enterprise Modo de administración.

7. Escriba la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI. A continuación, **seleccione Aceptar**.

   ![La captura de pantalla muestra el cuadro de diálogo confirmar activación donde se escribe la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI.](images/shm-fig23.png)
 
   > [!NOTE]
   > Después de activar SEMM en el dispositivo, se aplica la nueva configuración de UEFI **EnableOSMigration.** Ya no puede acceder a Windows 10 Team. En su lugar, debe continuar con el siguiente paso e instalar Windows 10 Pro o Windows 10 Enterprise.

   El dispositivo se reinicia. Muestra el logotipo blanco en el centro de la pantalla y, a continuación, se apaga de nuevo.

### <a name="install-windows-10-pro-or-enterprise"></a>Instalar Windows 10 Pro o Enterprise

1. Si la unidad Windows 10 Pro o Enterprise de arranque no está ya en el puerto USB-A Surface Hub 2, insértela ahora. A continuación, presione y suelte el botón de encendido.

    Cuando se inicie el dispositivo, verás el logotipo blanco en el centro de la pantalla. A continuación, aparece un círculo giratorio debajo del logotipo blanco.

3. Si el dispositivo Surface no arranca automáticamente en la unidad USB, apaga el dispositivo (desconecta el cable de alimentación y vuelve a conectarlo). Después de volver a conectar el cable de alimentación, el dispositivo debe arrancar después de unos segundos. A continuación, verás el logotipo blanco en el medio de la pantalla.

    Si el dispositivo no se enciende, presione y suelte el botón de encendido. Inmediatamente después de ver el logotipo en el centro de la pantalla, presione y mantenga presionado el botón Bajar volumen hasta que vea el círculo giratorio debajo del logotipo blanco.
 
   ![Imagen de los botones de volumen y encendido.](images/shm-fig26.png)
   
4. Cuando se inicie la configuración de la experiencia lista para usar (OOBE), siga las instrucciones para instalar Windows 10 Pro o Enterprise (versión 1903 o posterior).

### <a name="install-surface-hub-2-drivers-and-firmware"></a>Instalar Surface Hub 2 controladores y firmware

Para asegurarse de que el Surface Hub 2 está actualizado, instale controladores y firmware para Windows 10 Pro [y Enterprise](https://www.microsoft.com/download/details.aspx?id=101974). A continuación, reinicie el dispositivo. Mantén la Surface activada durante una hora y, a continuación, vuelve a reiniciarla. No se le pedirá el segundo reinicio. Esta pausa y reinicio adicional garantiza que el firmware se haya actualizado por completo.
 
## <a name="configure-recommended-settings"></a>Configurar las opciones recomendadas

Para configurar Surface Hub 2S como dispositivo de productividad personal, consulta Configurar Windows 10 Pro [o Enterprise en Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Si no puedes migrar correctamente el dispositivo a Windows 10 Pro o Enterprise para Surface Hub 2 siguiendo los pasos descritos en este artículo, ponte en contacto Surface Hub [Soporte](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)técnico .

## <a name="to-roll-back-to-windows-10-team"></a>Para revertir a Windows 10 Team

Si quieres restaurar el dispositivo a Windows 10 Team, consulta [Restablecer y recuperar para Surface Hub 2S](surface-hub-2s-recover-reset.md).

> [!NOTE]
> Antes de volver a Windows 10 Team, le recomendamos que primero desenrolle el Surface Hub de SEMM. Para obtener más información, consulta [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

## <a name="version-history"></a>Historial de versiones

En la tabla siguiente se resumen los cambios realizados en este artículo.

| Versión | Fecha               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.4  | 14 de diciembre de 2020 | Proporciona [](#install-surface-hub-2-drivers-and-firmware) más información acerca de la instalación del archivo MSI para "Controladores y firmware para el sistema operativo Windows 10 Pro y Enterprise en Surface Hub 2", lo que aconseja que sea necesario un segundo reinicio en función del estado del sistema.                                                          |
| v. 1.3  | 3 de diciembre de 2020 | Se actualizó con instrucciones sobre [cómo administrar la inscripción de SEMM.](#manage-semm-enrollment)                                                       |
| v. 1.2  | 29 de septiembre de 2020 | Actualizaciones misceláneas que abordan los comentarios de facilidad de uso.                                                        |
| v. 1.1  | 15 de septiembre de 2020 | Se ha colocado una nota adicional en la introducción que aclara los requisitos de licencias para instalar un nuevo sistema operativo. |
| v. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

---
title: Migración a Pro o Enterprise Windows 10/11 en Surface Hub 2
description: Migración de Windows 10 Team en Surface Hub 2 a Windows 10 Pro o Windows 10 Enterprise.
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
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 7b221b6f8b4a7753a10dd974da47ce58af41d006
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497763"
---
# <a name="migrate-to-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>Migración a Pro o Enterprise Windows 10/11 en Surface Hub 2

- [Historial de versiones del artículo](#version-history)

Surface Hub 2S incluye Windows 10 Team instalados. Esta edición personalizada de Windows 10 facilita la colaboración en entornos de salas de reuniones. Ahora, en su lugar, puede ejecutar Pro o Enterprise Windows 10/11 para usar su Surface Hub 2S de forma similar a cualquier otro equipo.

> [!IMPORTANT]
> Este proceso de migración requiere que siga el procedimiento específico que se describe en este artículo. Antes de continuar, lea [Componentes de la solución](#solution-components) y [Flujo de trabajo de migración e instalación](#migration-and-installation-workflow-summary).

> [!NOTE]
> Al instalar Windows 10/11 Pro o Enterprise en el Surface Hub 2S, necesita una nueva licencia distinta de la licencia de Windows 10 Team existente proporcionada con el dispositivo.

Inicie la migración desde Windows 10 Team mediante un equipo independiente y la herramienta *configurador de UEFI de Surface* descargable. La herramienta crea un paquete que contiene una nueva configuración de UEFI que se aplica a la Surface Hub 2S.  

Surface UEFI Configurator funciona como una interfaz en el Modo de administración de Surface Enterprise (SEMM). Permite la administración centralizada de la configuración de firmware en dispositivos Surface en un entorno corporativo. Para obtener más información, consulta [Modo de administración de Microsoft Surface Enterprise](/surface/surface-enterprise-management-mode).

## <a name="solution-components"></a>Componentes de la solución

- dispositivo Surface Hub 2S que ejecuta Windows 10 Team
- Dispositivo independiente que ejecuta Windows 10
- Herramienta Surface UEFI Configurator para crear el paquete SEMM
- Windows 10/11 Pro o Enterprise imagen del sistema operativo, versión 20H2 o posterior
- Dos unidades USB que tienen 16 GB de almacenamiento, formato FAT32
- Controladores y firmware para Windows 10 Pro y Enterprise en un archivo Surface Hub 2 del Instalador de Microsoft Windows (MSI)
- Conexión a Internet
- Solución de creación de imágenes (opcional)

## <a name="migration-and-installation-workflow-summary"></a>Resumen del flujo de trabajo de instalación y migración

| Paso  | Acción                                                                                                 | Resumen                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Compruebe la versión de UEFI en el Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).                                  | La versión de UEFI debe ser *la versión 694.2938.768.0* o posterior.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Descarga Surface UEFI Configurator y el Surface Hub 2 controladores y firmware.](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | En la página</a> **[Herramientas de Surface para TI](https://www.microsoft.com/download/details.aspx?id=46703)**, seleccione **Descargar**. A continuación, seleccione y descargue el **archivo MSI de Surface UEFI Configurator** e instálelo en un equipo independiente. Descargue también [los controladores y el firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub archivo MSI 2](https://www.microsoft.com/download/details.aspx?id=101974).</a> Guarde este paquete para usarlo en el paso 5. |
| 3 | [Prepare el certificado SEMM.](#prepare-the-semm-certificate)                                                                          | Prepare el certificado necesario para ejecutar Surface UEFI Configurator o use el certificado actual.                                                                                                                                                                                                                                                                                                      |
| 4 | [Cree un paquete SEMM.](#create-a-semm-package)                                                                               | Inicie Surface UEFI Configurator para crear un paquete SEMM en una unidad USB. Este paquete contendrá los archivos de configuración que necesita aplicar en Surface Hub 2S. Copie estos archivos de paquete SEMM en una carpeta del equipo.                                                                                                                                                                                          |
| 5 | [Cargue una unidad flash USB con Windows 10 imagen, el paquete SEMM y controladores y firmware.](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Cree una unidad USB que contenga una imagen de Windows 10. En este ejemplo, la unidad se denomina *BOOTME*. Agregue los controladores y el firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2 (del paso 2) y los archivos de paquete SEMM (del paso 4) a la unidad *BOOTME*.                                                                                                                                                                                                  |
| 6 | [Actualice uefi en el Surface Hub 2S para habilitar la migración del sistema operativo.](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use la unidad *BOOTME* para arrancar el Surface Hub 2S en el menú UEFI e instalar el paquete SEMM.|
| 7 | [Instale Windows 10 Pro o Enterprise.](#install-windows-1011-pro-or-enterprise)                                        | Use la unidad *BOOTME* para instalar Windows 10 Pro o Enterprise versión *20H2* o posterior.                                                                                                                                                                                                                                                                                 |
| 8 | [Instale controladores y firmware para Windows 10 Pro y Enterprise.](#install-surface-hub-2-drivers-and-firmware)                                        | Para asegurarse de que el dispositivo tiene todas las actualizaciones y controladores más recientes, instale los controladores y el <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub archivo MSI 2.</a>                                                                                                                                                                                                                                                                                  |
| 9 | [Configure Surface Hub 2S como dispositivo de productividad personal.](#configure-recommended-settings)                                        |  Habilite la configuración y las aplicaciones recomendadas para optimizar Surface Hub 2S como dispositivo de productividad personal.                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>Comprobación de la versión de UEFI en Surface Hub 2S

Antes de migrar Surface Hub de Windows 10 Team a Windows 10 Desktop, necesita la versión *694.2938.768.0* o posterior de UEFI.

**Para comprobar la versión de UEFI en el sistema:**

1. En la página principal de Surface Hub 2S, seleccione **Inicio** y, a continuación, abra la aplicación Surface (**Todas las aplicacionesSuperficie** > ).****

2. Selecciona **Tu Surface** para mostrar información sobre Surface Hub, incluida la versión actual de UEFI en el dispositivo.
   - Si la versión de UEFI es *694.2938.768.0* o posterior, como se muestra en la imagen siguiente, puede crear el paquete SEMM para habilitar la migración del sistema operativo.

    ![Captura de pantalla que muestra la página "Tu Surface" en la aplicación Surface.](images/shm-fig1.png)

   - Si la versión de UEFI es anterior a la versión *694.2938.768.0*, use uno de los métodos siguientes para obtener una versión más reciente.

#### <a name="update-uefi-via-windows-update"></a>Actualización de UEFI a través de Windows Update

1. En el Surface Hub 2S, inicie sesión como **administrador**.

    >[!Note]
    > Si no conoce el nombre de usuario o la contraseña de administrador, tendrá que restablecer el dispositivo. Para obtener más información, consulte [Restablecimiento y recuperación de Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

1. Vaya a **Todas las aplicaciones** >  **Configuración** >  **Actualizar y seguridad** >  **Windows Update** e instale todas las actualizaciones.
1. Reinicia el dispositivo.
1. Compruebe la versión de UEFI mediante la aplicación Surface. Si la versión de UEFI no es *la versión 694.2938.768.0* o posterior, repita estos pasos o use el procedimiento siguiente para obtener la versión más reciente de UEFI.

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>Actualización de LA UEFI a través de una imagen de recuperación sin sistema operativo (BMR)

1. Vaya al [sitio de recuperación de Surface](https://support.microsoft.com/surfacerecoveryimage) y seleccione **Surface Hub 2S**.
3. Escriba el número de serie del centro. Se encuentra en la parte posterior del centro junto a la conexión de alimentación.
4. Siga las instrucciones para descargar la imagen en una unidad USB con formato mediante la instalación de la actualización de Windows 10 Team 2020.
5. Después de la actualización, el dispositivo entra en la configuración de la experiencia rápida (OOBE). No es necesario completar la configuración. La versión de UEFI ya está actualizada. En su lugar, apague el dispositivo manteniendo presionado el botón de encendido hasta que se apague la pantalla.

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>Descarga de Surface UEFI Configurator y Surface Hub 2 controladores y firmware

En un equipo independiente, siga estos pasos:

1. En la <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> página</a> Herramientas de Surface para TI, seleccione **Descargar**.  
1. Selecciona y descarga el archivo MSI de Surface UEFI Configurator e instálelo en un equipo independiente. La herramienta Surface UEFI Configurator no se puede ejecutar en un Surface Hub 2S mientras Windows 10 Team edición está instalada.

1. Descargue el [archivo MSI del instalador de Surface Hub 2 controladores y firmware Windows](https://www.microsoft.com/download/details.aspx?id=101974). Usará este archivo al instalar el nuevo sistema operativo.

### <a name="prepare-the-semm-certificate"></a>Preparación del certificado SEMM

Si no has usado Surface UEFI Configurator antes, debes preparar un certificado. Este certificado garantiza que después de inscribir un dispositivo en SEMM, solo puede modificar la configuración de UEFI mediante paquetes creados con el certificado aprobado.

La forma de obtener un certificado depende del tamaño o la complejidad de la organización:

- Enterprise las organizaciones suelen mantener su propia infraestructura para generar certificados según las prácticas de seguridad estándar.

- Las empresas medianas y otras suelen optar por obtener certificados de proveedores asociados. Esta opción se recomienda para las organizaciones que no tienen tanta experiencia en TI o carecen de un equipo de seguridad de TI dedicado.

- Como alternativa, puede generar un certificado autofirmado mediante un script de PowerShell. Para obtener más información, consulta los [requisitos de certificado del Modo de administración de Surface Enterprise](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). O bien, puede usar PowerShell para crear su propio certificado. Para obtener más información, consulte la documentación [del certificado autofirmado](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) .

El paquete SEMM que crea Surface UEFI Configurator debe protegerse con un certificado. El certificado comprueba la firma de los archivos de configuración antes de que se pueda aplicar la configuración de UEFI. Para obtener más información, consulte la documentación de [SEMM](/surface/surface-enterprise-management-mode) .

### <a name="create-a-semm-package"></a>Creación de un paquete SEMM

1. En un equipo independiente, instale la herramienta Surface UEFI Configurator que descargó anteriormente.

1. Abra Surface UEFI Configurator y, a continuación, seleccione **Iniciar**.

   ![Pantalla de inicio de Surface UEFI Configurator.](images/shm-fig2.png)

1. Seleccione **Dispositivos Surface** y, a continuación, seleccione **Siguiente**.

   ![Captura de pantalla que muestra la opción Dispositivos Surface seleccionada.](images/shm-fig3.png)
  
1. Seleccione **Paquete de configuración**.

   ![Captura de pantalla que muestra la opción "Seleccionar paquete de configuración" seleccionada.](images/shm-fig4.png)
  
1. Seleccione **Protección de certificados**.

   ![Captura de pantalla en la que se muestra cómo elegir "Seleccionar protección de certificados".](images/shm-fig5.png)

   Se le pedirá que agregue el archivo .pfx del certificado.

   ![Captura de pantalla que muestra dónde agregar el archivo de certificado.](images/shm-fig6.png)

1. Escriba la contraseña del certificado y, a continuación, seleccione **Aceptar**.

   ![Captura de pantalla que muestra los campos para escribir y confirmar la contraseña del certificado.](images/shm-fig7.png)

1. Seleccione **Protección con contraseña** para agregar una contraseña a Surface UEFI. Necesitará esta contraseña cada vez que arranque en la UEFI. *Se recomienda encarecidamente establecer una contraseña UEFI que usará en Surface Hub 2S.*

   ![Captura de pantalla que muestra dónde seleccionar Protección con contraseña.](images/shm-fig8.png)

1. Establezca una contraseña UEFI y, a continuación, seleccione **Aceptar**.

   > [!IMPORTANT]
   > Guarde la contraseña en una ubicación segura a la que puedan acceder los administradores de TI que administran Surface Hub. *Si se pierde esta contraseña, no se puede recuperar.*

   ![Captura de pantalla que muestra dónde se establece la contraseña de UEFI.](images/shm-fig9.png)

1. Seleccione **Surface Hub 2S** y, a continuación, seleccione **Siguiente**.

    ![Captura de pantalla que muestra dónde seleccionar Surface Hub 2S.](images/shm-fig10.png)

1. Vuelva a seleccionar **Siguiente** .

    ![Captura de pantalla que muestra para seleccionar Siguiente en "Elegir qué componentes".](images/shm-fig10a.png)

1. Para permitir la instalación de Pro o Enterprise de Windows 10/11, active **EnableOsMigration** y, a continuación, seleccione **Siguiente**.

    ![Captura de pantalla que muestra dónde seleccionar Habilitar migración de O S.](images/shm-fig11.png)

    ![Captura de pantalla que muestra dónde establecer Habilitar migración del sistema operativo en activado.](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>Administración de la inscripción de SEMM

La inscripción de un dispositivo en SEMM afecta a cómo puede administrarlo. Por ejemplo, después de aplicar un paquete SEMM, toda la configuración de UEFI no está disponible (bloqueada) en el menú UEFI del dispositivo. Los valores predeterminados de otras configuraciones, como **IPv6 para arranque PXE** , tampoco están disponibles.

Para cambiar la configuración de UEFI después de finalizar la migración, aplique otro paquete SEMM o desinscriba el dispositivo desde SEMM. Si aplica otro paquete SEMM para cambiar la configuración de UEFI, debe usar el certificado original al compilar el nuevo paquete SEMM. Use la herramienta UEFI Configurator y deje **EnableOSMigration** *desactivado* (no *activado* como en los pasos de migración originales).

#### <a name="if-you-work-with-partners"></a>Si trabaja con asociados

Si su empresa subcontrata la migración de Surface Hub 2 a Windows 10/11 Pro o Enterprise, es posible que desee que el asociado le transfiera el certificado SEMM, el paquete SEMM y la contraseña de UEFI. O bien, después de migrar el centro, puede anular su inscripción inmediatamente desde SEMM. Este paso permite la administración local de UEFI y la transferencia del dispositivo a otra entidad. Pero todavía se recomienda encarecidamente usar una contraseña UEFI, que se puede configurar después de la migración. Para obtener más información, consulta [Administrar la configuración de UEFI de Surface](/surface/manage-surface-uefi-settings).

#### <a name="to-roll-back-to-windows-10-team"></a>Para revertir a Windows 10 Team

Si decide restaurar el dispositivo a Windows 10 Team después de la migración[, como se describe más adelante en este artículo](#to-roll-back-to-windows-10-team), se recomienda anular la inscripción del centro en SEMM. Para obtener más información, consulta [Anular la inscripción de dispositivos Surface desde SEMM](/surface/unenroll-surface-devices-from-semm).

>[!WARNING]
>Para anular la inscripción de un dispositivo desde SEMM y restaurar el control de usuario de la configuración de UEFI de Surface, debes tener el certificado SEMM que se usó para inscribir el dispositivo en SEMM. Si este certificado se pierde o está dañado, no es posible anular la inscripción de SEMM. Realice una copia de seguridad y proteja el certificado SEMM en consecuencia.

#### <a name="save-the-semm-package-to-a-usb-drive"></a>Guardar el paquete SEMM en una unidad USB

1. Conectar una unidad USB a su PC.
1. Elija **Hub 2S** y, a continuación, seleccione **Siguiente**.

   ![Captura de pantalla que muestra dónde seleccionar Hub 2S.](images/shm-fig13.png)

   > [!WARNING]
   > Todos los datos existentes en la unidad USB se borrarán cuando se compile el paquete SEMM. Antes de compilar el paquete SEMM, quite los archivos que necesite de la unidad USB.

1. Seleccione **Compilar**.

   ![Captura de pantalla que muestra dónde seleccionar Compilar.](images/shm-fig14.png)

1. Captura de pantalla de esta página y, a continuación, seleccione **Finalizar**. El paquete SEMM ya está listo. Contiene el paquete SEMM *DfciUpdate.dfi* y un archivo de texto que incluye la *huella digital* SEMM, que es los dos últimos caracteres de la huella digital del certificado.

   ![Captura de pantalla que muestra dónde seleccionar Finalizar.](images/shm-fig15.png)

4. Guarde los dos últimos caracteres de la huella digital del certificado. Necesitará estos caracteres para activar SEMM al aplicar el paquete en Surface Hub 2S.

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>Carga de una unidad flash USB con una imagen de Windows 10, un paquete SEMM y Surface Hub 2 controladores y firmware

Puede instalar una imagen Pro o Enterprise de Windows 10/11 (versión *20H2* o posterior) mediante una de las siguientes opciones:

- La solución de creación de imágenes actual.

- [Acelerador de implementación de Surface](/surface/microsoft-surface-deployment-accelerator). Use esta herramienta para crear una imagen de Windows 10 de arranque. La imagen puede incluir todas las actualizaciones de Windows 10 actuales, Microsoft Office, otras aplicaciones y los controladores y el firmware necesarios.

- Una unidad flash USB que contiene una imagen Pro o Enterprise Windows 10/11. Esta opción no tendrá Wi-Fi disponibles hasta después de la configuración de la experiencia rápida (OOBE). Una vez completada la instalación, instale los [Surface Hub 2 controladores y firmware necesarios para Windows 10 Pro y Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) en el dispositivo.

En los pasos siguientes se muestra cómo crear una unidad flash USB a partir de los medios de instalación y, a continuación, agregar los archivos de paquete SEMM y los controladores y firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub archivo MSI 2. Si usa otro método de implementación, vaya a la sección [Actualizar UEFI en Surface Hub 2S para habilitar la migración del sistema operativo](#update-uefi-on-surface-hub-2s-to-enable-os-migration) de este artículo.

> [!NOTE]
> Una vez finalizada la instalación, necesitará una licencia válida para Windows 10 Pro o Windows 10 Enterprise que sea independiente de la licencia de Windows 10 Team existente.

1. Para crear una instalación de Windows 10 Pro, siga las instrucciones para descargar la herramienta de creación de medios en [Descargar Windows 10](https://www.microsoft.com/software-download/windows10). Para descargar Windows 10 Enterprise, vaya al Centro de servicios [de licencias por volumen de Microsoft](https://www.microsoft.com/licensing/servicecenter/default.aspx).

1. Inserte una nueva unidad de almacenamiento USB.
1. Abra la herramienta de creación de medios, seleccione **Crear medio de instalación** y, a continuación, seleccione **Siguiente**.

   ![Captura de pantalla que muestra la opción para crear medios de instalación.](images/shm-fig16.png)

3. Seleccione un idioma y, a continuación, seleccione **Windows 10** y **64 bits (x64).** A continuación, seleccione **Siguiente**.

   ![Captura de pantalla que muestra dónde se selecciona el idioma, la edición O S y el tipo de arquitectura.](images/shm-fig17.png)

4. Seleccione **Unidad flash USB** y, a continuación, seleccione **Siguiente**.

   ![Captura de pantalla que muestra dónde seleccionar la unidad flash U S B.](images/shm-fig18.png)

5. Cuando finalice la descarga, seleccione **Finalizar**.

   ![La pantalla informa de que la unidad U S B está lista e incluye un botón Finalizar.](images/shm-fig19.png)

6. Copie los archivos del paquete SEMM y los controladores y el firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2 (el archivo MSI) en la raíz de la unidad flash USB (*BOOTME*) que contiene la imagen de Windows 10. La unidad USB BOOTME contendrá:

    - La imagen de arranque Windows 10.

    - Los archivos de paquete SEMM, copiados en la raíz de la unidad USB:

      - *DfciUpdate.dfi*.
      - Un archivo de texto que incluye la huella digital SEMM. (En este ejemplo, el archivo se *SurfaceUEFI_2020Aug25_1058.txt*). La marca de fecha y hora generada automáticamente corresponde a la fecha en que creó el archivo mediante Surface UEFI Configurator.

   - Controladores y firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi). Copie este archivo en la raíz de la unidad USB.

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>Actualización de UEFI en Surface Hub 2S para habilitar la migración del sistema operativo

1. Inserte la unidad BOOTME en el puerto USB-A del Surface Hub 2S. Para obtener una lista de su contenido necesario, consulte la sección anterior.

1. Para arrancar en UEFI:

   1. Desactive (apague) el Surface Hub 2S.
   1. Mantenga presionado **Volumen +** y, a continuación, presione y suelte el botón de encendido. Mantenga presionado **Volumen +** hasta que aparezca el menú UEFI.

      ![El dibujo muestra los botones de volumen y de encendido.](images/shm-fig20.png)

3. Cuando se reinicie el dispositivo, escriba la contraseña UEFI que creó anteriormente, si procede (recomendado).

   ![Pantalla de contraseña del sistema.](images/shm-fig22.png)

4. En el menú UEFI, seleccione **Administración**. A continuación, seleccione  **Instalar desde USB**.

   ![Captura de pantalla que muestra dónde seleccionar Administración y, a continuación, "Instalar desde U S B".](images/shm-fig21.png)

5. Seleccione **Reiniciar ahora**, como se muestra en la siguiente imagen. El dispositivo se reiniciará. Mostrará un logotipo blanco de Microsoft en el centro de la ventana y, a continuación, se apagará.

   ![Captura de pantalla que muestra un mensaje que le pide que se reinicie.](images/shm-fig25.png)

6. Presione y suelte el botón de encendido. En el cuadro de diálogo rojo que aparece, elija activar El modo de administración de Surface Enterprise.

7. Escriba la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI. A continuación, seleccione **Aceptar**.

   ![Captura de pantalla que muestra el cuadro de diálogo de confirmación de activación en el que se escribe la huella digital del certificado de dos caracteres y la contraseña de configuración de UEFI.](images/shm-fig23.png)

   > [!NOTE]
   > Después de activar SEMM en el dispositivo, se aplica la nueva configuración de UEFI **EnableOSMigration** . Ya no puede acceder a Windows 10 Team. En su lugar, debe continuar con el paso siguiente e instalar Windows 10 Pro o Windows 10 Enterprise.

   El dispositivo se reinicia. Muestra el logotipo blanco en el centro de la pantalla y, a continuación, se apaga de nuevo.

### <a name="install-windows-1011-pro-or-enterprise"></a>Instalar Pro o Enterprise Windows 10/11

1. Si la unidad de Windows 10/11 de arranque Pro o Enterprise aún no está en el puerto USB-A Surface Hub 2, insérela ahora. A continuación, presione y suelte el botón de encendido.

    Cuando se inicie el dispositivo, verá el logotipo blanco en el centro de la pantalla. A continuación, aparece un círculo giratorio debajo del logotipo blanco.

3. Si el dispositivo Surface no arranca automáticamente en la unidad USB, apague el dispositivo (desenchufe el cable de alimentación y vuelva a conectarlo). Después de conectar el cable de alimentación de nuevo, el dispositivo debe arrancar después de unos segundos. A continuación, verá el logotipo blanco en medio de la pantalla.

    Si el dispositivo no se enciende, presione y suelte el botón de encendido. Inmediatamente después de ver el logotipo en el centro de la pantalla, mantenga presionado el botón Bajar volumen hasta que vea el círculo giratorio debajo del logotipo blanco.

   ![Imagen de los botones de volumen y encendido.](images/shm-fig26.png)

4. Cuando se inicie la configuración de la experiencia integrada (OOBE), siga las instrucciones para instalar Pro Windows 10/11 o Enterprise (versión *20H2* o posterior).

### <a name="install-surface-hub-2-drivers-and-firmware"></a>Instalar Surface Hub 2 controladores y firmware

Para asegurarse de que el Surface Hub 2 está actualizado, instale [controladores y firmware para Windows 10 Pro y Enterprise](https://www.microsoft.com/download/details.aspx?id=101974). A continuación, reinicie el dispositivo. Mantén la surface activada durante una hora y reiniciala de nuevo. No se le pedirá el segundo reinicio. Esta pausa y reinicio adicional garantiza que el firmware se ha actualizado por completo.

## <a name="configure-recommended-settings"></a>Configuración de las opciones recomendadas

Para configurar Surface Hub 2S como dispositivo de productividad personal, consulte [Configuración de Pro o Enterprise Windows 10/11 en Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>Si no puede migrar correctamente el dispositivo a Windows 10/11 Pro o Enterprise para Surface Hub 2 siguiendo los pasos descritos en este artículo, póngase en contacto con [el soporte técnico de Surface Hub](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

## <a name="to-roll-back-to-windows-10-team"></a>Para revertir a Windows 10 Team

Si desea restaurar el dispositivo a Windows 10 Team, consulte [Restablecer y recuperar para Surface Hub 2S](surface-hub-2s-recover-reset.md).

> [!NOTE]
> Antes de revertir a Windows 10 Team, se recomienda anular primero la inscripción del Surface Hub de SEMM. Para obtener más información, consulta [Anular la inscripción de dispositivos Surface desde SEMM](/surface/unenroll-surface-devices-from-semm).

## <a name="version-history"></a>Historial de versiones

En la tabla siguiente se resumen los cambios realizados en este artículo.

| Versión | Fecha               | Descripción                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| V. 1.5  | 1 de diciembre de 2021  | Se ha actualizado para mostrar compatibilidad con Windows 11
| V. 1.4  | 14 de diciembre de 2020 | Proporciona [más información](#install-surface-hub-2-drivers-and-firmware) sobre la instalación del archivo MSI para "Controladores y firmware para Windows 10 Pro y Enterprise sistema operativo en Surface Hub 2", y aconseja que sea necesario un segundo reinicio en función del estado del sistema.                                                          |
| V. 1.3  | 3 de diciembre de 2020 | Se ha actualizado con instrucciones sobre [cómo administrar la inscripción de SEMM](#manage-semm-enrollment).                                                       |
| V. 1.2  | 29 de septiembre de 2020 | Actualizaciones varias que abordan los comentarios de facilidad de uso.                                                        |
| V. 1.1  | 15 de septiembre de 2020 | Se ha colocado una nota adicional en la introducción que aclara los requisitos de licencia para instalar un nuevo sistema operativo. |
| V. 1.0  | 1 de septiembre de 2020  | Nuevo artículo.                                                                                           |

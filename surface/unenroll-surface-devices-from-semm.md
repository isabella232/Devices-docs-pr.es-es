---
title: Desenrollar dispositivos Surface desde SEMM (Surface)
description: Aprende a desenrollar un dispositivo de SEMM mediante un paquete de restablecimiento de UEFI de Surface o la opción Solicitud de recuperación.
keywords: administración de surface enterprise
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 4942dd5ab187b7350e5093d8d189ad52536ef5bd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448563"
---
# <a name="unenroll-surface-devices-from-semm"></a>Anular la inscripción de dispositivos Surface desde SEMM

Cuando un dispositivo Surface está inscrito en surface Enterprise Management Mode (SEMM), un certificado se almacena en el firmware de ese dispositivo. La presencia de ese certificado y la inscripción en SEMM impiden cambios no autorizados en la configuración u opciones de UEFI de Surface mientras el dispositivo está inscrito en SEMM. Para restaurar el control de la configuración de UEFI de Surface al usuario, el dispositivo Surface debe no inscribirse en SEMM, un proceso que a veces se describe como restablecimiento o recuperación. Hay dos métodos que puedes usar para desenrollar un dispositivo desde SEMM: un paquete de restablecimiento de UEFI de Surface y una solicitud de recuperación.

>[!WARNING]
>Para desenrollar un dispositivo de SEMM y restaurar el control de usuario de la configuración de UEFI de Surface, debes tener el certificado SEMM que se usó para inscribir el dispositivo en SEMM. Si este certificado se pierde o se daña, no es posible deshacer la inscripción de SEMM. Haga una copia de seguridad y proteja el certificado SEMM en consecuencia.

Para obtener más información acerca de SEMM, [consulta Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

## <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>Desenrollar un dispositivo Surface de SEMM con un paquete de restablecimiento de UEFI de Surface

El paquete de restablecimiento de UEFI de Surface es el método principal que usas para desenrollar un dispositivo Surface de SEMM. Al igual que un paquete de configuración de UEFI de Surface, el paquete de restablecimiento es un archivo Windows Installer (.msi) que configura SEMM en el dispositivo. A diferencia del paquete de configuración, el paquete de restablecimiento restablecerá la configuración de UEFI de Surface en un dispositivo Surface a su configuración predeterminada, quitará el certificado SEMM y desenrollará el dispositivo de SEMM.

Los paquetes de restablecimiento se crean específicamente para un dispositivo Surface individual. Para comenzar el proceso de creación de un paquete de restablecimiento, necesitarás el número de serie del dispositivo que quieres desenrollar, así como el certificado SEMM usado para inscribir el dispositivo. Puedes encontrar el número de serie de tu dispositivo Surface en la página de información del **equipo** de Surface UEFI, como se muestra en la figura 1. Esta página se muestra incluso si Surface UEFI está protegido con contraseña y se introduce la contraseña incorrecta.

![Se muestra el número de serie del dispositivo Surface.](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*Figura 1. El número de serie del dispositivo Surface se muestra en la página de información de surface UEFI PC*

>[!NOTE]
>Para arrancar en Surface UEFI, presiona **Subir** volumen y **Encender** simultáneamente mientras el dispositivo está apagado. Mantén **presionado el volumen** hasta que se muestre el logotipo de Surface y el dispositivo comience a arrancar.

Para crear un paquete de restablecimiento de UEFI de Surface, sigue estos pasos:

1. Abra Microsoft Surface UEFI Configurator desde el menú Inicio.
2. Haz clic en **Inicio**.
3. Haga **clic en Restablecer paquete**, tal como se muestra en la figura 2.

   ![Selecciona Restablecer paquete para crear un paquete para desenrollar el dispositivo Surface desde SEMM.](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *Figura 2. Haz clic en Restablecer paquete para crear un paquete para desenrollar un dispositivo Surface desde SEMM*

4. Haga **clic en Protección de** certificados para agregar el archivo de certificado SEMM con clave privada (.pfx), como se muestra en la figura 3. Vaya a la ubicación del archivo de certificado, seleccione el archivo y, a continuación, haga clic en **Aceptar**.

   ![Agrega el certificado SEMM al paquete de restablecimiento de UEFI de Surface.](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *Figura 3. Agregar el certificado SEMM a un paquete de restablecimiento de UEFI de Surface*

5. Haz clic en **Siguiente**.
6. Escribe el número de serie del dispositivo que quieres desenrollar desde SEMM (como se muestra en la figura 4) y****, a continuación, haz clic en Compilar para generar el paquete de restablecimiento de UEFI de Surface.

   ![Crea un paquete de restablecimiento de UEFI de Surface con el número de serie de dispositivo Surface.](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *Figura 4. Usa el número de serie de tu dispositivo Surface para crear un paquete de restablecimiento de UEFI de Surface*

7. En el **cuadro de diálogo** Guardar como, especifique un nombre para el paquete de restablecimiento uefi de Surface, vaya a la ubicación donde desea guardar el archivo y, a continuación, haga clic en **Guardar**.
8. Cuando se haya completado la generación de paquetes **, se mostrará** la página Correcto. Haz **clic en** Finalizar para completar la creación del paquete y cerrar Microsoft Surface UEFI Configurator.

Ejecuta el archivo de paquete de restablecimiento de UEFI de Surface Windows Installer (.msi) en el dispositivo Surface para desenrollar el dispositivo desde SEMM. El paquete de restablecimiento requerirá un reinicio para realizar la operación de anulación de inscripción. Una vez que el dispositivo se haya dado de baja, puedes comprobar que la eliminación se ha realizado correctamente al asegurarte de que el elemento paquete de configuración de **Microsoft Surface** en Programas y **características (que** se muestra en la figura 5) ya no esté presente.

![Pantalla que muestra que el dispositivo está inscrito en SEMM.](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*Figura 5. La presencia del elemento paquete de configuración de Microsoft Surface en Programas y características indica que el dispositivo está inscrito en SEMM*

## <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>Desenrollar un dispositivo Surface de SEMM con una solicitud de recuperación

En algunos escenarios, un paquete de restablecimiento de UEFI de Surface puede no ser una opción viable para desenrollar un dispositivo Surface desde SEMM (por ejemplo, donde Windows se ha vuelto inutilizable). En estos escenarios, puedes desenrollar el dispositivo mediante una solicitud de recuperación generada desde Surface UEFI. El proceso de solicitud de recuperación se puede iniciar incluso en dispositivos donde no tienes la contraseña uefi de Surface.

El proceso de solicitud de recuperación se inicia desde La UEFI de Surface en el dispositivo Surface, se aprueba con Microsoft Surface UEFI Configurator en otro equipo y, a continuación, se completa en UeFI de Surface. Al igual que el paquete de restablecimiento, la aprobación de una solicitud de recuperación con El configurador UEFI de Microsoft Surface requiere acceso al certificado SEMM que se usó para inscribir el dispositivo Surface.

Para iniciar una solicitud de recuperación, siga estos pasos:

1. Arranque el dispositivo Surface que se va a no inscribir de SEMM a Surface UEFI.
2. Escribe la contraseña de UEFI de Surface si se te pide que lo hagas.
3. Haga clic **en Enterprise de administración**, como se muestra en la figura 6.

   ![Enterprise de administración.](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *Figura 6. La página Enterprise administración se muestra en UEFI de Surface en dispositivos inscritos en SEMM*

4. Haga clic o presione **Introducción**.
5. Haga clic o presione **Siguiente** para iniciar el proceso de solicitud de recuperación.
   >[!NOTE]
   >Una solicitud de recuperación expira dos horas después de su creación. Si no se completa una solicitud de recuperación en este tiempo, tendrá que reiniciar el proceso de solicitud de recuperación.
6. Seleccione **Certificado SEMM** en la lista de certificados que se muestran en la página Elegir una clave de restablecimiento **de SEMM** (que se muestra en la figura 7) y, a continuación, haga clic o presione **Siguiente**.

   ![Seleccione Certificado SEMM para la solicitud de recuperación.](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *Figura 7. Elija Certificado SEMM para la solicitud de recuperación (solicitud de restablecimiento)*

7. En la página Escribir código de verificación de restablecimiento **de SEMM**, puede hacer clic **** en los botones Código **QR** o Texto para mostrar la solicitud de recuperación (solicitud de restablecimiento), como se muestra en la figura 8, o el botón **USB** para guardar la solicitud de recuperación (solicitud de restablecimiento) como un archivo en una unidad USB, como se muestra en la figura 9.

   ![Solicitud de recuperación que se muestra como código QR.](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *Figura 8. Una solicitud de recuperación (solicitud de restablecimiento) que se muestra como un código QR*

   ![Guarda una solicitud de recuperación en una unidad USB.](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *Figura 9. Guardar una solicitud de recuperación (solicitud de restablecimiento) en una unidad USB*

   * Para usar una solicitud de recuperación de código QR (solicitud de restablecimiento), usa una aplicación lectora de QR en un dispositivo móvil para leer el código. La aplicación lector de QR traducirá el código QR en una cadena alfanumérica. A continuación, puedes enviar por correo electrónico o mensaje esa cadena al administrador que producirá el código de comprobación de restablecimiento con Microsoft Surface UEFI Configurator.
   * Para usar una solicitud de recuperación (solicitud de restablecimiento) guardada en una unidad USB como archivo, usa la unidad USB para transferir el archivo al equipo donde se usará el Configurador UEFI de Microsoft Surface para generar el código de verificación Restablecer. El archivo también se puede copiar desde la unidad USB de otro dispositivo para que se envíe por correo electrónico o se transfiera a través de la red.
   * Para usar la solicitud de recuperación (solicitud de restablecimiento) como texto, simplemente escribe el texto directamente en Microsoft Surface UEFI Configurator.

8. Abre Microsoft Surface UEFI Configurator desde el menú Inicio en otro equipo.
    >[!NOTE]
    >Microsoft Surface UEFI Configurator debe ejecutarse en un entorno que pueda autenticar la cadena de certificados para el certificado SEMM.
9. Haz clic en **Inicio**.
10. Haga **clic en Solicitud de** recuperación, como se muestra en la figura 10.

    ![Iniciar el proceso para aprobar una solicitud de recuperación.](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *Figura 10. Haga clic en Solicitud de recuperación para iniciar el proceso para aprobar una solicitud de recuperación*

11. Haga **clic en Protección de** certificados para autenticar la solicitud de recuperación con el certificado SEMM.
12. Busque y seleccione el archivo de certificado SEMM y, a continuación, haga clic en **Aceptar**.
13. Cuando se le pida que escriba la contraseña del certificado como se muestra en la figura 11, escriba y confirme la contraseña del archivo de certificado y, a continuación, haga clic en **Aceptar**.

    ![Escriba la contraseña para el certificado SEMM.](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *Figura 11. Escriba la contraseña para el certificado SEMM*

14. Haz clic en **Siguiente**.
15. Escriba la solicitud de recuperación (solicitud de restablecimiento) y, a continuación, haga clic en **Generar** para crear un código de comprobación de restablecimiento (como se muestra en la figura 12).

    ![Escriba la solicitud de recuperación.](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *Figura 12. Escriba la solicitud de recuperación (solicitud de restablecimiento)*

    * Si has mostrado la solicitud de recuperación (solicitud de restablecimiento) como texto en el dispositivo Surface que se va a restablecer, usa el teclado para escribir la solicitud de recuperación (solicitud de restablecimiento) en el campo proporcionado.
    * Si has mostrado la solicitud de recuperación (solicitud de restablecimiento) como código QR y, a continuación, usaste una aplicación de mensajería o correo electrónico para enviar el código al equipo con el Configurador UEFI de Microsoft Surface, copia y pega el código en el campo proporcionado.
    * Si guardó la solicitud de recuperación (solicitud de restablecimiento) como un archivo en una unidad USB****, haga clic en el botón Importar, busque y seleccione el archivo solicitud de recuperación (solicitud de restablecimiento) y, a continuación, haga clic en **Aceptar**.

16. El código de comprobación de restablecimiento se muestra en Microsoft Surface UEFI Configurator, como se muestra en la figura 13.

    ![Mostrar el código de verificación de restablecimiento.](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *Figura 13. El código de comprobación de restablecimiento que se muestra en Microsoft Surface UEFI Configurator*

    * Haga clic en **el botón** Compartir para enviar el código de verificación de restablecimiento por correo electrónico.

17. Escribe el código de verificación de restablecimiento en el campo proporcionado en el dispositivo Surface (que se muestra en la figura 8) y, a continuación, haz clic o presiona **Comprobar** para restablecer el dispositivo y desenrollar el dispositivo desde SEMM.
18. Haga clic o presione **Reiniciar ahora** en la página Restablecer **SEMM** correctamente para completar la inscripción desde SEMM, como se muestra en la figura 14.

    ![Muestra de ejemplo de la anulación correcta de la inscripción de SEMM.](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *Figura 14. Anulación correcta de la inscripción de SEMM*

19. Haz **clic en** Finalizar en Microsoft Surface UEFI Configurator para completar el proceso de solicitud de recuperación (solicitud de restablecimiento) y cerrar El Configurador UEFI de Microsoft Surface.



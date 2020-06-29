---
title: Anular la inscripción de dispositivos de Surface desde SEMM (Surface)
description: Obtenga información sobre cómo anular la inscripción de un dispositivo de SEMM con un paquete de restablecimiento de Surface UEFI o la opción de solicitud de recuperación.
keywords: Administración de Surface Enterprise
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
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834609"
---
# Anular la inscripción de dispositivos Surface desde SEMM

Cuando un dispositivo Surface se ha inscrito en el modo de administración de empresa de Surface (SEMM), se almacena un certificado en el firmware de ese dispositivo. La presencia de ese certificado y de la inscripción en SEMM impedir que se realicen cambios no autorizados en la configuración o las opciones de Surface UEFI mientras el dispositivo está inscrito en SEMM. Para restaurar el control de la configuración de Surface UEFI para el usuario, el dispositivo Surface debe ser anulado en la inscripción de SEMM, un proceso descrito a veces como un restablecimiento o una recuperación. Existen dos métodos que puede usar para anular la inscripción de un dispositivo de SEMM: un paquete de restablecimiento de Surface UEFI y una solicitud de recuperación.

>[!WARNING]
>Para anular la inscripción de un dispositivo de SEMM y restaurar el control del usuario de la configuración de Surface UEFI, debe tener el certificado de SEMM que se usó para inscribir el dispositivo en SEMM. Si este certificado se pierde o se daña, no se puede anular la inscripción de SEMM. Haga una copia de seguridad y proteja su certificado SEMM según corresponda.

Para obtener más información sobre SEMM, consulte [modo de administración de Microsoft Surface Enterprise](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).

## Anular la inscripción de un dispositivo Surface de SEMM con un paquete de restablecimiento de Surface UEFI

El paquete de restablecimiento de Surface UEFI es el método principal que usas para anular la inscripción de un dispositivo Surface desde SEMM. Al igual que un paquete de configuración de Surface UEFI, el paquete de restablecimiento es un archivo de Windows Installer (. msi) que configura SEMM en el dispositivo. A diferencia del paquete de configuración, el paquete de restablecimiento restablece la configuración de Surface UEFI en un dispositivo Surface a su configuración predeterminada, quita el certificado SEMM y anula la inscripción del dispositivo de SEMM.

Los paquetes de restablecimiento se crean específicamente para un dispositivo Surface individual. Para comenzar el proceso de creación de un paquete de restablecimiento, necesitará el número de serie del dispositivo en el que desea anular la inscripción, así como el certificado de SEMM usado para inscribir el dispositivo. Puede encontrar el número de serie del dispositivo Surface en la página de **información de PC** de Surface UEFI, como se muestra en la ilustración 1. Esta página se muestra incluso si Surface UEFI está protegido con contraseña y se escribe la contraseña incorrecta.

![Se muestra el número de serie del dispositivo Surface](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*Figura 1. El número de serie del dispositivo Surface se muestra en la página información de Surface UEFI PC*

>[!NOTE]
>Para arrancar en Surface UEFI, pulsa **subir** y **encender** el volumen mientras el dispositivo está apagado. Mantenga el **volumen al día** hasta que se muestre el logotipo de Surface y el dispositivo empiece a arrancar.

Para crear un paquete de restablecimiento de Surface UEFI, siga estos pasos:

1. Abra el configurador de Microsoft Surface UEFI desde el menú Inicio.
2. Haz clic en **Inicio**.
3. Haga clic en **restablecer paquete**, como se muestra en la ilustración 2.

   ![Seleccione restablecer paquete para crear un paquete para anular la inscripción del dispositivo de superficie de SEMM](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *Figura 2. Haz clic en restablecer paquete para crear un paquete para anular la inscripción de un dispositivo Surface desde SEMM*

4. Haga clic en **protección del certificado** para agregar el archivo de certificado de SEMM con la clave privada (. pfx), como se muestra en la ilustración 3. Vaya a la ubicación del archivo de certificado, seleccione el archivo y, a continuación, haga clic en **Aceptar**.

   ![Agregar el certificado SEMM al paquete de restablecimiento de Surface UEFI](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *Figura 3. Agregar el certificado SEMM a un paquete de restablecimiento de Surface UEFI*

5. Haz clic en **Siguiente**.
6. Escriba el número de serie del dispositivo del que desea anular la inscripción de SEMM (como se muestra en la ilustración 4) y, a continuación, haga clic en **generar** para generar el paquete de restablecimiento de Surface UEFI.

   ![Crear un paquete de restablecimiento de Surface UEFI con el número de serie del dispositivo Surface](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *Figura 4. Usa el número de serie del dispositivo Surface para crear un paquete de restablecimiento de Surface UEFI*

7. En el cuadro de diálogo **Guardar como** , especifique un nombre para el paquete de restablecimiento de Surface UEFI, busque la ubicación en la que desea guardar el archivo y, a continuación, haga clic en **Guardar**.
8. Cuando se complete la generación del paquete, se mostrará la página **correcta** . Haga clic en **Finalizar** para completar la creación del paquete y cierre Microsoft Surface UEFI configurador.

Ejecuta el archivo de Windows Installer (. msi) de Surface UEFI RESET en el dispositivo Surface para anular la inscripción del dispositivo de SEMM. El paquete de restablecimiento necesitará un reinicio para realizar la operación de anulación de la inscripción. Una vez que se haya desactivado el dispositivo, puede comprobar que la eliminación se haya realizado asegurándose de que el elemento del **paquete de configuración de Surface de Microsoft** en **programas y características** (que se muestra en la ilustración 5) ya no está presente.

![La pantalla que muestra el dispositivo se ha inscrito en SEMM](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*Figura 5. La presencia del elemento paquete de configuración de Microsoft Surface en programas y características indica que el dispositivo se ha inscrito en SEMM*

## Anular la inscripción de un dispositivo Surface de SEMM con una solicitud de recuperación

En algunos escenarios, un paquete de restablecimiento de Surface UEFI puede no ser una opción viable para anular la inscripción de un dispositivo Surface desde SEMM (por ejemplo, cuando no se puede usar Windows). En estos escenarios, puede anular la inscripción del dispositivo mediante una solicitud de recuperación generada desde la superficie UEFI. El proceso de solicitud de recuperación se puede iniciar incluso en dispositivos en los que no se tiene la contraseña de Surface UEFI.

El proceso de solicitud de recuperación se inicia desde Surface UEFI en el dispositivo Surface, aprobado con el configurador UEFI de Microsoft Surface en otro equipo y luego se completa en Surface UEFI. Al igual que el paquete de restablecimiento, aprobar una solicitud de recuperación con el configurador Microsoft Surface UEFI requiere acceso al certificado SEMM que se usó para inscribir el dispositivo Surface.

Para iniciar una solicitud de recuperación, siga estos pasos:

1. Arranque el dispositivo Surface que se va a anular la inscripción de SEMM a Surface UEFI.
2. Escriba la contraseña de la superficie UEFI si se le solicita.
3. Haga clic en la página **Administración de empresa** , como se muestra en la ilustración 6.

   ![Página de administración de empresa](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *Figura 6. La página Administración de empresa se muestra en Surface UEFI en los dispositivos inscritos en SEMM*

4. Haga clic o pulse **Introducción.**
5. Haga clic o pulse **siguiente** para iniciar el proceso de solicitud de recuperación.
   >[!NOTE]
   >Una solicitud de recuperación vence dos horas después de su creación. Si una solicitud de recuperación no se completa en este momento, tendrá que reiniciar el proceso de solicitud de recuperación.
6. Seleccione **certificado de SEMM** de la lista de certificados que se muestra en la página **elegir una clave de restablecimiento de SEMM** (mostrada en la figura 7) y, a continuación, haga clic en o en **siguiente**.

   ![Seleccione el certificado SEMM para su solicitud de recuperación](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *Figura 7. Elija el certificado SEMM para su solicitud de recuperación (restablecer solicitud)*

7. En la página **escribir código de verificación de SEMM restablecer** , puede hacer clic en los botones **código QR** o **texto** para mostrar la solicitud de recuperación (restablecer solicitud) como se muestra en la figura 8, o el botón **USB** para guardar la solicitud de recuperación (restablecer solicitud) como un archivo en una unidad USB, como se muestra en la ilustración 9.

   ![Solicitud de recuperación mostrada como un código QR](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *Figura 8. Una solicitud de recuperación (solicitud de restablecimiento) se muestra como un código QR*

   ![Guardar una solicitud de recuperación en una unidad USB](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *Figura 9. Guardar una solicitud de recuperación (restablecer solicitud) en una unidad USB*

   * Para usar una solicitud de recuperación de código QR (solicitud de restablecimiento), use una aplicación de lector de QR en un dispositivo móvil para leer el código. La aplicación de lector de QR traducirá el código QR a una cadena alfanumérica. Después, puede enviar por correo electrónico o enviar un mensaje de correo electrónico al administrador que generará el código de verificación de restablecimiento con el configurador Microsoft Surface UEFI.
   * Para usar una solicitud de recuperación (solicitud de restablecimiento) guardada en una unidad USB como un archivo, use la unidad USB para transferir el archivo al equipo donde se usará el configurador Microsoft Surface UEFI para producir el código de verificación de restablecimiento. El archivo también se puede copiar desde la unidad USB en otro dispositivo para que se envíe por correo electrónico o se transfiera a través de la red.
   * Para usar la solicitud de recuperación (restablecer solicitud) como texto, simplemente escriba el texto directamente en Microsoft Surface UEFI configurador.

8. Abra el configurador de Microsoft Surface UEFI desde el menú Inicio en otro equipo.
    >[!NOTE]
    >El configurador Microsoft Surface UEFI debe ejecutarse en un entorno que pueda autenticar la cadena de certificados para el certificado SEMM.
9. Haz clic en **Inicio**.
10. Haga clic en **solicitud de recuperación**, como se muestra en la figura 10.

    ![Iniciar proceso para aprobar una solicitud de recuperación](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *Figura 10. Haga clic en solicitud de recuperación para comenzar el proceso de aprobación de una solicitud de recuperación.*

11. Haga clic en **protección del certificado** para autenticar la solicitud de recuperación con el certificado SEMM.
12. Busque y seleccione el archivo del certificado de SEMM y, a continuación, haga clic en **Aceptar**.
13. Cuando se le pida que escriba la contraseña del certificado, tal como se muestra en la figura 11, escriba y confirme la contraseña del archivo del certificado y, a continuación, haga clic en **Aceptar**.

    ![Escriba la contraseña para el certificado SEMM](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *Figura 11. Escriba la contraseña para el certificado SEMM*

14. Haz clic en **Siguiente**.
15. Escriba la solicitud de recuperación (restablecer solicitud) y, a continuación, haga clic en **generar** para crear un código de verificación de restablecimiento (como se muestra en la ilustración 12).

    ![Especificar la solicitud de recuperación](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *Figura 12. Especificar la solicitud de recuperación (restablecer solicitud)*

    * Si mostró la solicitud de recuperación (restablecer solicitud) como texto en el dispositivo Surface que se va a restablecer, use el teclado para escribir la solicitud de recuperación (solicitud de restablecimiento) en el campo proporcionado.
    * Si mostró la solicitud de recuperación (restablecer solicitud) como código QR y después usó un mensaje o una aplicación de correo electrónico para enviar el código al equipo con el configurador Microsoft Surface UEFI, copie y pegue el código en el campo proporcionado.
    * Si guardó la solicitud de recuperación (restablecer solicitud) como un archivo en una unidad USB, haga clic en el botón **importar** , busque y seleccione el archivo de solicitud de recuperación (restablecer solicitud) y, a continuación, haga clic en **Aceptar**.

16. El código de verificación de restablecimiento se muestra en el configurador de Surface UEFI de Microsoft, tal como se muestra en la ilustración 13.

    ![Mostrar el código de verificación de restablecimiento](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *Figura 13. El código de verificación de restablecimiento mostrado en el configurador UEFI de Surface de Microsoft*

    * Haz clic en el botón **compartir** para enviar el código de verificación de restablecimiento por correo electrónico.

17. Escriba el código de verificación de restablecimiento en el campo proporcionado en el dispositivo Surface (que se muestra en la ilustración 8) y, a continuación, haga clic en o pulse **comprobar** para restablecer el dispositivo y anular la inscripción del dispositivo de semm.
18. Haga clic o pulse **reiniciar ahora** en la página **SEMM restablecido correctamente** para completar la anulación de la inscripción de SEMM, como se muestra en la figura 14.

    ![Ejemplo de visualización de la anulación de la inscripción de SEMM](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *Figura 14. Anulación de la inscripción correcta de SEMM*

19. Haga clic en **Finalizar** en el configurador de Microsoft Surface UEFI para completar el proceso de solicitud de recuperación (restablecer solicitud) y cerrar el configurador UEFI de Microsoft Surface.



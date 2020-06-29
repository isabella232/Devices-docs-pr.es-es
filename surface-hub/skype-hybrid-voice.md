---
title: Implementación en línea o híbrida con el entorno de Skype Hybrid Voice (Surface Hub)
description: En este tema se explica cómo habilitar Skype Empresarial Cloud PBX con la conectividad de RTC local a través de Cloud Connector Edition o el grupo de Skype Empresarial 2015.
keywords: implementación híbrida, Skype Hybrid Voice
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836433"
---
# Implementación en línea o híbrida con el entorno de Skype Hybrid Voice (Surface Hub)

En este tema se explica cómo habilitar Skype Empresarial Cloud PBX con la conectividad de la red telefónica conmutada (RTC) local a través de Cloud Connector Edition o el grupo de Skype Empresarial 2015. En esta opción, tus grupos de servidores principales de Skype Empresarial y servidores de Exchange se encuentran en la nube y están conectados mediante RTC a través de un grupo local que ejecuta Skype Empresarial 2015 o Cloud Connector Edition. [Más información acerca de diferentes opciones de Cloud PBX](https://technet.microsoft.com/library/mt612869.aspx).  

Si implementaste Skype Empresarial Cloud PBX con una de las opciones de voz híbrida, sigue estos pasos para habilitar la cuenta de la sala para Surface Hub. Es importante crear una cuenta de usuario normal primero, asignar todas las opciones de voz híbrida y números de teléfono y, a continuación, convertir la cuenta en una cuenta de la sala. Si no sigues este orden, no podrás asignar a un número de teléfono híbrido.  

>[!WARNING]
>Si creas una cuenta antes de la configuración de voz híbrida (ejecutas el comando Enable-CSMeetingRoom), no podrás configurar los parámetros de voz híbrida necesarios. Para configurar parámetros de voz híbrida para una cuenta configurada anteriormente o volver a configurar un número de teléfono, elimina la licencia de complemento E5 o E3 + Cloud PBX y, a continuación, sigue los pasos siguientes, comenzando por el paso 3.

1. Crea una cuenta de usuario nueva para Surface Hub. Este ejemplo usa <strong> surfacehub2@adatum.com </strong> . La cuenta se puede crear en Active Directory local y sincronizarse con la nube o se puede crear directamente en la nube. 

    ![nuevo usuario de objeto](images/new-user-hybrid-voice.png)

2. Seleccione **La contraseña nunca expira**. Esto es importante para un dispositivo de Surface Hub.

   ![La contraseña nunca expira](images/new-user-password-hybrid-voice.png)

3. En Office 365, agrega la licencia **E5** o el complemento **E3 and Cloud PBX** a la cuenta de usuario creada para la sala. Esto es necesario para que funcione Hybrid Voice.

   ![Agregar licencia de producto](images/product-license-hybrid-voice.png)

4. Espera unos 15 minutos hasta que aparezca la cuenta de usuario para la sala en Skype Empresarial Online.

5. Después de crear la cuenta de usuario para la sala en Skype Empresarial Online, para habilitarla para Hybrid Voice en PowerShell remoto de Skype Empresarial, ejecuta el siguiente cmdlet:

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. Valida el flujo de llamadas de Hybrid Voice realizando llamadas de pruebas desde Surface Hub.

7. Inicia una sesión de PowerShell remota en un equipo y conéctate a Exchange ejecutando los siguientes cmdlets.

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. Después de establecer una sesión, modifica la cuenta de usuario para la sala para habilitarla como una **RoomMailboxAccount** ejecutando los siguientes cmdlets. Esto permite autenticar la cuenta con Surface Hub.

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. Después de configurar el buzón, debes crear una nueva directiva de Exchange ActiveSync o usar una directiva existente compatible.

   Los dispositivos Surface Hub solo son compatibles con las cuentas del dispositivo que tengan una directiva de ActiveSync donde la propiedad **PasswordEnabled** esté establecida en **False**. Si esto no se configura correctamente, no se habilitarán los servicios de Exchange en el Surface Hub (correo electrónico, calendario y unión a reuniones).
    
   Si aún no has creado una directiva compatible, usa el siguiente cmdlet (este crea una directiva denominada "Surface Hubs"). Una vez que se haya creado, puedes aplicar la misma directiva a otras cuentas del dispositivo.

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   Una vez que tengas una directiva compatible, necesitarás aplicar la directiva a la cuenta del dispositivo. Sin embargo, las directivas solo se pueden aplicar a las cuentas de usuario y no a los buzones de recursos. Ejecute los siguientes cmdlets para convertir el buzón en un tipo de usuario, aplicar la directiva y, a continuación, volver a convertirlo en un buzón (es posible que tengas que volver la cuenta y establecer la contraseña de nuevo).
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. Es necesario establecer varias propiedades de Exchange en la cuenta del dispositivo para mejorar la experiencia de la reunión. Puedes ver qué propiedades pueden establecerse en [Propiedades de Exchange](exchange-properties-for-surface-hub-device-accounts.md). Los siguientes cmdlets proporcionan un ejemplo de establecimiento de propiedades de Exchange.

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. Habilita el buzón como dispositivo de reunión en Skype Empresarial Online. Ejecute el cmdlet siguiente, que habilita la cuenta como un dispositivo de reunión. 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    Como resultado de la ejecución de este cmdlet, a los usuarios se les preguntará si se encuentran en una sala de reuniones, como se muestra en la siguiente imagen. **Sí** silenciará el micrófono y el altavoz.

    ![](images/adjust-room-audio.png)


    
En este momento la cuenta de la sala estará totalmente configurada, incluida la voz híbrida. Si usas Skype local, puedes configurar atributos adicionales, como la descripción, la ubicación, etc., local. Si creas una sala en Skype en línea, estos parámetros se pueden establecer en línea. 

En la imagen siguiente, puedes ver cómo le aparece el dispositivo a los usuarios.


![](images/select-room-hybrid-voice.png)

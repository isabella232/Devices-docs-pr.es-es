---
title: Listas de comprobación de implementación de 2 de Surface Hub
description: Verifique su implementación de Surface Hub 2S con las listas de comprobación anteriores y posteriores a la implementación.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836369"
---
# Listas de comprobación de implementación de 2 de Surface Hub

## Lista de comprobación previa a la implementación de Surface Hub 2S

|**Elemento**|**Respuesta**|
|:------ |:------ |
|**Nombre de la cuenta del dispositivo**| |
|**UPN de cuenta del dispositivo**| |
|**Directiva de ActiveSync**| |
|**Configuración de procesamiento del calendario completada**| ☐ Sí <br>  ☐ No |
|**Nombre descriptivo del dispositivo**| |
|**Nombre de host del dispositivo**| |
|**Afiliación**| ☐ Ninguno <br> ☐ Afiliación de Active Directory <br> ☐ Azure Active Directory |
|**Modo Microsoft Teams**| Modo 0 de ☐ <br> Modo 1 de ☐ <br> Modo 2 de ☐ |
|**Administración del dispositivo**| ☐ Sí, Microsoft Intune <br> ☐ Sí, otro administrador de dispositivos móviles [MDM] <br> ☐ Ninguno |  
|**Proxy**| ☐ Configuración automática <br> Servidor proxy ☐ <br> ☐ Archivo de configuración automática de proxy (PAC) |
|**Autenticación de proxy**| Credenciales de cuenta de ☐ dispositivo <br> ☐ Solicitar credenciales |
|**Rotación de contraseñas**| ☐ <br> ☐ Deshabilitado |
|**Nombres de dominio adicionales de Skype empresarial (solo local)**| |
|**Tiempo de espera de sesión**| |
|**Acción de tiempo de espera de sesión**| ☐ Finalizar sesión <br> ☐ Permitir currículum |
|**Mis reuniones y archivos**| ☐ Habilitado <br> ☐ Deshabilitado |
|**Tiempo de espera de pantalla de bloqueo**| |
|**Tiempo de espera de inactividad**| |
|**Bluetooth**| ☐ <br> ☐ Deshabilitado |
|**Usar solo unidades USB de BitLocker**| ☐ <br> ☐ Deshabilitado |
|**Instalar certificados adicionales (solo local)**| |
|**Windows Update**| ☐ Windows Update para empresas <br> ☐ Windows Server Update Services [WSUS] |
|**Configuración del altavoz de la aplicación Surface**| Soporte rodante ☐ <br> ☐ Montado en pared |
|**Dirección IP**| ☐ Cableada: DHCP <br> ☐ Cableada: reserva DHCP <br> ☐ Inalámbrica: DHCP <br> ☐ Wireless: Reserva de DHCP |

## Lista de comprobación posterior a la implementación de Surface Hub 2S

|**Comprobado**|**Respuesta**|
|:------|:---------|
|**Sincronización de la cuenta de dispositivo**| ☐ Sí <br> ☐ No |
|**Clave de BitLocker**| ☐ Guardado en el archivo (sin afiliación) <br> ☐ Guardado en Active Directory (afiliación de AD) <br>☐ Guardado en Azure AD (afiliación de Azure AD) |
|**Actualizaciones del sistema operativo del dispositivo**| ☐ Completado |
|**Actualizaciones de la tienda Windows**| ☐ Automático <br> ☐ Manual |
|**Reunión programada de Microsoft Teams**| Mensaje de confirmación de ☐ recibido <br> ☐ Reunión aparece en la pantalla Inicio <br>  ☐ Funciones de combinación con un solo toque <br> ☐ Puede unirse al audio <br> ☐ Puede unirse a vídeo <br> ☐ Capaz de compartir la pantalla ||
|**Reunión programada de Skype empresarial**| Mensaje de confirmación de ☐ recibido <br> ☐ Reunión aparece en la pantalla Inicio <br> ☐ Las funciones de combinación de un solo toque correctamente <br> ☐ Puede unirse al audio <br> ☐ Puede unirse a vídeo <br> ☐ Capaz de compartir la pantalla <br> ☐ Puede enviar o recibir mensajes instantáneos |
|**Reunión programada cuando ya se ha invitado**| ☐ Reunión rechazada |
|**Reunión ad-hoc de Microsoft Teams**| ☐ Invitar a otros usuarios <br> ☐ Puede unirse al audio <br> ☐ Puede unirse a vídeo <br> ☐ Capaz de compartir la pantalla |
|**Reunión programada de Skype empresarial**| ☐ Invitar a otros usuarios <br> ☐ Puede unirse al audio <br> ☐ Puede unirse a vídeo <br> ☐ Capaz de compartir la pantalla <br> ☐ Puede enviar o recibir mensajes instantáneos |
|**Microsoft Whiteboard**| ☐ Iniciar desde la pantalla de bienvenida o Inicio <br> ☐ Iniciar desde Microsoft Teams | 
|**Llamada entrante de Skype/Teams**| ☐ Puede unirse al audio<br>☐ Puede unirse a vídeo <br> ☐ Capaz de compartir la pantalla <br> ☐ Puede enviar o recibir mensajes instantáneos (solo para Skype empresarial) |
|**Transmisiones de video en vivo entrantes**| ☐ Máximo 2 (Skype empresarial) <br> ☐ Máximo de 4 (Microsoft Teams) |
|**Comportamiento del modo 0 de Microsoft Teams**| ☐ Mosaico de Skype empresarial en la bienvenida/pantalla de inicio <br> ☐ Puede unirse a reuniones de Skype empresarial programadas (interfaz de usuario de Skype) <br> ☐ Puede unirse a reuniones de Teams programadas (interfaz de usuario de Teams) |
|**Comportamiento del modo 1 de Microsoft Teams**| Mosaico de ☐ equipos en la pantalla de bienvenida/Inicio <br> ☐ Puede unirse a reuniones de Skype empresarial programadas (interfaz de usuario de Skype) <br> ☐ Puede unirse a reuniones de Teams programadas (interfaz de usuario de Teams) |
|**Comportamiento del modo 2 de Microsoft Teams**| Mosaico de ☐ equipos en la pantalla de bienvenida/Inicio <br> ☐ Puede unirse a reuniones de Teams programadas <br> ☐ No unirse a reuniones de Skype empresarial |

---
title: Uso de un sistema de control de la sala (Surface Hub)
description: Los sistemas de control de la sala se pueden usar con tu Microsoft Surface Hub.
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: sistema de control de la sala, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834849"
---
# Uso de un sistema de control de la sala (Surface Hub)


Los sistemas de control de la sala se pueden usar con tu Microsoft Surface Hub.

El uso de un sistema de control de la sala con el Surface Hub implica la conexión de hardware de control de la sala al Surface Hub, normalmente a través de un puerto serie RJ11 en la parte inferior del Surface Hub.

## Configuración del terminal

Para conectarte a un panel de control del sistema de control de la sala, no es necesario que configures ninguna terminal en el Surface Hub. Si quieres conectar un equipo o portátil al Surface Hub y enviar comandos de serie desde el Surface Hub, puedes usar un programa de emulador de terminal como Tera Term o PuTTY. 

| Configuración | Valor |
| --- | --- |
| Velocidad en baudios | 115200 |
| Bits de datos | 4,8 | 
| Bits de parada | uno |
| Paridad | ninguno |
| Control de flujo | ninguno |
| Avance de línea | todos los retornos de carro |
 

## Diagrama del cableado

Puedes usar un conector RJ-11 (6P6C) estándar para conectar el puerto serie del Surface Hub con un sistema de control de la sala. Este es el método recomendado. También puedes usar un cable de 4 conductores RJ-11, pero no recomendamos este método.

Este diagrama muestra el patillaje correcto usado para un RJ-11 (6P6C) al cable DB9.

![Imagen que muestra el diagrama de cableado.](images/room-control-wiring-diagram.png)

## Conjuntos de comandos

Los sistemas de control de la sala usan escenarios comunes de sala de reuniones para los comandos. Los comandos se originan en el sistema de control de la sala y se comunican a través de una conexión serie a un Surface Hub. Los comandos están basados en ASCII y el Surface Hub reconocerá cuando se produzcan cambios de estado.

Los siguientes modificadores de comandos están disponibles. Los comandos terminan en un carácter de nueva línea (/n). Las respuestas pueden presentarse en cualquier momento en respuesta a los cambios de estado no desencadenados directamente mediante un comando de puerto de administración.

| Modificador | Resultado |
| --- | --- |
| + | Incrementar un valor |
| - | Disminuir un valor |
| = | Establecer un valor discreto |
| ? | Consultas de un valor actual |
 

## Energía

El Surface Hub puede estar en uno de estos estados de energía.

| Estado | Estado de Energy Star| Descripción |
| --- | --- | --- |
| ,0 | S5 | Desactivado |
| uno | - | Encendido (indeterminado) |
| 1 | S3 | Suspensión |
| 4 | S0 | Ready |


En el modo de PC de reemplazo, los estados de energía son solo Listo y Desactivado, y solo cambian la presentación. El puerto de administración no se puede usar para encender el equipo de reemplazo. 

| Estado | Estado de Energy Star| Descripción |
| --- | --- | --- |
| ,0 | S5 | Apagado |
| 4 | S0 | Listo |

En el caso de un dispositivo de control, cualquier estado que no sea 5/Listo debería considerarse apagado. Cada comando de PowerOn da como resultado dos cambios y respuestas de estado. 

| Comando | Cambio de estado| Respuesta |
| --- | --- | --- |
| Encendido | El dispositivo se activa (pantalla + PC).</br></br>El servicio del equipo notifica a SMC que el equipo está listo. |  Energía=0</br></br>Energía=5 |
| Apagar | Transiciones del dispositivo al estado ambiental (PC encendido, atenuación de pantalla). |  Energía=0 |
| ¿Energía? |  SMC informa sobre el último estado de energía conocido. |  Energía=<#> |



## Brillo

El nivel de brillo actual está en un intervalo de 0 a 100.

Los cambios en los niveles de brillo se pueden enviar mediante un sistema de control de la sala u otro sistema.

| Comando | Cambio de estado |Respuesta |
| --- | --- | --- |
| Brightness+ | Controladora de administración del sistema (SMC) envía el comando de subir brillo.</br></br>El servicio del equipo en el sistema de control de la sala notifica a SMC del nuevo nivel de brillo. |  Brightness = 51 |
| Brightness- |  SMC envía el comando de bajar brillo.</br></br>El servicio del equipo notifica a SMC del nuevo nivel de brillo. | Brightness = 50 |

##  <a name="volume"></a>Volumen

El nivel de volumen actual está en un intervalo de 0 a 100.

Los cambios en los niveles de volumen se pueden enviar mediante un sistema de control de la sala u otro sistema.

>[!NOTE]
>El comando de volumen solo controlará el volumen para el modo incrustado o de equipo sustituto, no de [orígenes invitados](connect-and-display-with-surface-hub.md).

| Comando | Cambio de estado | Respuesta</br>(Activa en [modo de equipo sustituto](connect-and-display-with-surface-hub.md#replacement-pc-mode)) |
| --- | --- | --- |
| Volume+ |  SMC envía el comando de subir volumen.</br></br>El servicio del equipo notifica a SMC del nuevo nivel de volumen. |  Volume = 51 |
| Volume- |  SMC envía el comando de bajar volumen.</br></br>El servicio del equipo notifica a SMC del nuevo nivel de volumen. |  Volume = 50 |


 

## Silenciar audio

Se puede silenciar el audio.

| Comando | Cambio de estado | Respuesta |
| --- | --- | --- |
| AudioMute+ |  SMC envía el comando de silenciar audio.</br></br>El servicio del equipo notifica a SMC que el audio está silenciado. |  ninguno |


 

## Origen de vídeo

Se pueden usar varios orígenes de pantalla.

| Estado | Descripción | 
| --- | --- |
| ,0 |  Equipo incorporado |
| uno |  DisplayPort |
| 1 |  HDMI |
| 2 |  VGA |


 

Los cambios en el origen de pantalla los puede enviar un sistema de control de la sala u otro sistema.

| Comando | Cambio de estado | Respuesta |
| --- | --- | --- |
| Origen=# |  SMC cambia al origen deseado.</br></br>El servicio del equipo notifica a SMC que el origen de pantalla ha cambiado. |  Origen=&lt;#&gt; |
| Source+ |  SMC pasa al siguiente origen de entrada activo.</br></br>El servicio del equipo notifica a SMC del origen de entrada actual. |  Origen=&lt;#&gt; |
| Origen- | SMC pasa al origen de entrada activo anterior.</br></br>El servicio del equipo notifica a SMC del origen de entrada actual. |  Origen=&lt;#&gt; |
| Source? |  SMC consulta al servicio del equipo el origen de entrada activo.</br></br>El servicio del equipo notifica a SMC del origen de entrada actual. | Origen=&lt;#&gt; |

## Errores

Los errores se devuelven según el formato de esta tabla.

| Error | Notas |
| --- | --- |
| Error: Comando desconocido '&lt;input&gt;'. |  La instrucción contiene un comando inicial desconocido. Por ejemplo, &quot;VOL+&quot; no sería válido y se devolvería &quot; Error: Comando desconocido 'VOL'&quot;. |
| Error: Operador desconocido '&lt;input&gt;'. |  La instrucción contiene un operador desconocido. Por ejemplo, &quot;Volume!&quot; no sería válido y se devolvería &quot; Error: Operador desconocido '!'&quot;. |
| Error: Parámetro desconocido '&lt;input&gt;'. |  La instrucción contiene un parámetro desconocido. Por ejemplo, &quot;Volume=abc&quot; no sería válido y se devolvería &quot; Error: Parámetro desconocido 'abc'&quot;. |
| Error: Comando no disponible cuando está desactivado '&lt;input&gt;'. |  Cuando el Surface Hub está desactivado, los comandos que no sean Power devuelven este error. Por ejemplo, &quot;Volume+&quot; no sería válido y se devolvería &quot; Error: Comando no disponible cuando está desactivado 'Volume'&quot;. |


 

##  <a name="related-topics"></a>Temas relacionados


[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 






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
# <span data-ttu-id="014e6-104">Uso de un sistema de control de la sala (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="014e6-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="014e6-105">Los sistemas de control de la sala se pueden usar con tu Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="014e6-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="014e6-106">El uso de un sistema de control de la sala con el Surface Hub implica la conexión de hardware de control de la sala al Surface Hub, normalmente a través de un puerto serie RJ11 en la parte inferior del Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="014e6-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <span data-ttu-id="014e6-107">Configuración del terminal</span><span class="sxs-lookup"><span data-stu-id="014e6-107">Terminal settings</span></span>

<span data-ttu-id="014e6-108">Para conectarte a un panel de control del sistema de control de la sala, no es necesario que configures ninguna terminal en el Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="014e6-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="014e6-109">Si quieres conectar un equipo o portátil al Surface Hub y enviar comandos de serie desde el Surface Hub, puedes usar un programa de emulador de terminal como Tera Term o PuTTY.</span><span class="sxs-lookup"><span data-stu-id="014e6-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="014e6-110">Configuración</span><span class="sxs-lookup"><span data-stu-id="014e6-110">Setting</span></span> | <span data-ttu-id="014e6-111">Valor</span><span class="sxs-lookup"><span data-stu-id="014e6-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="014e6-112">Velocidad en baudios</span><span class="sxs-lookup"><span data-stu-id="014e6-112">Baud rate</span></span> | <span data-ttu-id="014e6-113">115200</span><span class="sxs-lookup"><span data-stu-id="014e6-113">115200</span></span> |
| <span data-ttu-id="014e6-114">Bits de datos</span><span class="sxs-lookup"><span data-stu-id="014e6-114">Data bits</span></span> | <span data-ttu-id="014e6-115">4,8</span><span class="sxs-lookup"><span data-stu-id="014e6-115">8</span></span> | 
| <span data-ttu-id="014e6-116">Bits de parada</span><span class="sxs-lookup"><span data-stu-id="014e6-116">Stop bits</span></span> | <span data-ttu-id="014e6-117">uno</span><span class="sxs-lookup"><span data-stu-id="014e6-117">1</span></span> |
| <span data-ttu-id="014e6-118">Paridad</span><span class="sxs-lookup"><span data-stu-id="014e6-118">Parity</span></span> | <span data-ttu-id="014e6-119">ninguno</span><span class="sxs-lookup"><span data-stu-id="014e6-119">none</span></span> |
| <span data-ttu-id="014e6-120">Control de flujo</span><span class="sxs-lookup"><span data-stu-id="014e6-120">Flow control</span></span> | <span data-ttu-id="014e6-121">ninguno</span><span class="sxs-lookup"><span data-stu-id="014e6-121">none</span></span> |
| <span data-ttu-id="014e6-122">Avance de línea</span><span class="sxs-lookup"><span data-stu-id="014e6-122">Line feed</span></span> | <span data-ttu-id="014e6-123">todos los retornos de carro</span><span class="sxs-lookup"><span data-stu-id="014e6-123">every carriage return</span></span> |
 

## <span data-ttu-id="014e6-124">Diagrama del cableado</span><span class="sxs-lookup"><span data-stu-id="014e6-124">Wiring diagram</span></span>

<span data-ttu-id="014e6-125">Puedes usar un conector RJ-11 (6P6C) estándar para conectar el puerto serie del Surface Hub con un sistema de control de la sala.</span><span class="sxs-lookup"><span data-stu-id="014e6-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="014e6-126">Este es el método recomendado.</span><span class="sxs-lookup"><span data-stu-id="014e6-126">This is the recommended method.</span></span> <span data-ttu-id="014e6-127">También puedes usar un cable de 4 conductores RJ-11, pero no recomendamos este método.</span><span class="sxs-lookup"><span data-stu-id="014e6-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="014e6-128">Este diagrama muestra el patillaje correcto usado para un RJ-11 (6P6C) al cable DB9.</span><span class="sxs-lookup"><span data-stu-id="014e6-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![Imagen que muestra el diagrama de cableado.](images/room-control-wiring-diagram.png)

## <span data-ttu-id="014e6-130">Conjuntos de comandos</span><span class="sxs-lookup"><span data-stu-id="014e6-130">Command sets</span></span>

<span data-ttu-id="014e6-131">Los sistemas de control de la sala usan escenarios comunes de sala de reuniones para los comandos.</span><span class="sxs-lookup"><span data-stu-id="014e6-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="014e6-132">Los comandos se originan en el sistema de control de la sala y se comunican a través de una conexión serie a un Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="014e6-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="014e6-133">Los comandos están basados en ASCII y el Surface Hub reconocerá cuando se produzcan cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="014e6-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="014e6-134">Los siguientes modificadores de comandos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="014e6-134">The following command modifiers are available.</span></span> <span data-ttu-id="014e6-135">Los comandos terminan en un carácter de nueva línea (/n).</span><span class="sxs-lookup"><span data-stu-id="014e6-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="014e6-136">Las respuestas pueden presentarse en cualquier momento en respuesta a los cambios de estado no desencadenados directamente mediante un comando de puerto de administración.</span><span class="sxs-lookup"><span data-stu-id="014e6-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="014e6-137">Modificador</span><span class="sxs-lookup"><span data-stu-id="014e6-137">Modifier</span></span> | <span data-ttu-id="014e6-138">Resultado</span><span class="sxs-lookup"><span data-stu-id="014e6-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="014e6-139">Incrementar un valor</span><span class="sxs-lookup"><span data-stu-id="014e6-139">Increment a value</span></span> |
| - | <span data-ttu-id="014e6-140">Disminuir un valor</span><span class="sxs-lookup"><span data-stu-id="014e6-140">Decrease a value</span></span> |
| = | <span data-ttu-id="014e6-141">Establecer un valor discreto</span><span class="sxs-lookup"><span data-stu-id="014e6-141">Set a discrete value</span></span> |
| <span data-ttu-id="014e6-142">?</span><span class="sxs-lookup"><span data-stu-id="014e6-142">?</span></span> | <span data-ttu-id="014e6-143">Consultas de un valor actual</span><span class="sxs-lookup"><span data-stu-id="014e6-143">Queries for a current value</span></span> |
 

## <span data-ttu-id="014e6-144">Energía</span><span class="sxs-lookup"><span data-stu-id="014e6-144">Power</span></span>

<span data-ttu-id="014e6-145">El Surface Hub puede estar en uno de estos estados de energía.</span><span class="sxs-lookup"><span data-stu-id="014e6-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="014e6-146">Estado</span><span class="sxs-lookup"><span data-stu-id="014e6-146">State</span></span> | <span data-ttu-id="014e6-147">Estado de Energy Star</span><span class="sxs-lookup"><span data-stu-id="014e6-147">Energy Star state</span></span>| <span data-ttu-id="014e6-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="014e6-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-149">,0</span><span class="sxs-lookup"><span data-stu-id="014e6-149">0</span></span> | <span data-ttu-id="014e6-150">S5</span><span class="sxs-lookup"><span data-stu-id="014e6-150">S5</span></span> | <span data-ttu-id="014e6-151">Desactivado</span><span class="sxs-lookup"><span data-stu-id="014e6-151">Off</span></span> |
| <span data-ttu-id="014e6-152">uno</span><span class="sxs-lookup"><span data-stu-id="014e6-152">1</span></span> | - | <span data-ttu-id="014e6-153">Encendido (indeterminado)</span><span class="sxs-lookup"><span data-stu-id="014e6-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="014e6-154">1</span><span class="sxs-lookup"><span data-stu-id="014e6-154">2</span></span> | <span data-ttu-id="014e6-155">S3</span><span class="sxs-lookup"><span data-stu-id="014e6-155">S3</span></span> | <span data-ttu-id="014e6-156">Suspensión</span><span class="sxs-lookup"><span data-stu-id="014e6-156">Sleep</span></span> |
| <span data-ttu-id="014e6-157">4</span><span class="sxs-lookup"><span data-stu-id="014e6-157">5</span></span> | <span data-ttu-id="014e6-158">S0</span><span class="sxs-lookup"><span data-stu-id="014e6-158">S0</span></span> | <span data-ttu-id="014e6-159">Ready</span><span class="sxs-lookup"><span data-stu-id="014e6-159">Ready</span></span> |


<span data-ttu-id="014e6-160">En el modo de PC de reemplazo, los estados de energía son solo Listo y Desactivado, y solo cambian la presentación.</span><span class="sxs-lookup"><span data-stu-id="014e6-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="014e6-161">El puerto de administración no se puede usar para encender el equipo de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="014e6-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="014e6-162">Estado</span><span class="sxs-lookup"><span data-stu-id="014e6-162">State</span></span> | <span data-ttu-id="014e6-163">Estado de Energy Star</span><span class="sxs-lookup"><span data-stu-id="014e6-163">Energy Star state</span></span>| <span data-ttu-id="014e6-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="014e6-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-165">,0</span><span class="sxs-lookup"><span data-stu-id="014e6-165">0</span></span> | <span data-ttu-id="014e6-166">S5</span><span class="sxs-lookup"><span data-stu-id="014e6-166">S5</span></span> | <span data-ttu-id="014e6-167">Apagado</span><span class="sxs-lookup"><span data-stu-id="014e6-167">Off</span></span> |
| <span data-ttu-id="014e6-168">4</span><span class="sxs-lookup"><span data-stu-id="014e6-168">5</span></span> | <span data-ttu-id="014e6-169">S0</span><span class="sxs-lookup"><span data-stu-id="014e6-169">S0</span></span> | <span data-ttu-id="014e6-170">Listo</span><span class="sxs-lookup"><span data-stu-id="014e6-170">Ready</span></span> |

<span data-ttu-id="014e6-171">En el caso de un dispositivo de control, cualquier estado que no sea 5/Listo debería considerarse apagado.</span><span class="sxs-lookup"><span data-stu-id="014e6-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="014e6-172">Cada comando de PowerOn da como resultado dos cambios y respuestas de estado.</span><span class="sxs-lookup"><span data-stu-id="014e6-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="014e6-173">Comando</span><span class="sxs-lookup"><span data-stu-id="014e6-173">Command</span></span> | <span data-ttu-id="014e6-174">Cambio de estado</span><span class="sxs-lookup"><span data-stu-id="014e6-174">State change</span></span>| <span data-ttu-id="014e6-175">Respuesta</span><span class="sxs-lookup"><span data-stu-id="014e6-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-176">Encendido</span><span class="sxs-lookup"><span data-stu-id="014e6-176">PowerOn</span></span> | <span data-ttu-id="014e6-177">El dispositivo se activa (pantalla + PC).</span><span class="sxs-lookup"><span data-stu-id="014e6-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="014e6-178">El servicio del equipo notifica a SMC que el equipo está listo.</span><span class="sxs-lookup"><span data-stu-id="014e6-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="014e6-179">Energía=0</span><span class="sxs-lookup"><span data-stu-id="014e6-179">Power=0</span></span></br></br><span data-ttu-id="014e6-180">Energía=5</span><span class="sxs-lookup"><span data-stu-id="014e6-180">Power=5</span></span> |
| <span data-ttu-id="014e6-181">Apagar</span><span class="sxs-lookup"><span data-stu-id="014e6-181">PowerOff</span></span> | <span data-ttu-id="014e6-182">Transiciones del dispositivo al estado ambiental (PC encendido, atenuación de pantalla).</span><span class="sxs-lookup"><span data-stu-id="014e6-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="014e6-183">Energía=0</span><span class="sxs-lookup"><span data-stu-id="014e6-183">Power=0</span></span> |
| <span data-ttu-id="014e6-184">¿Energía?</span><span class="sxs-lookup"><span data-stu-id="014e6-184">Power?</span></span> |  <span data-ttu-id="014e6-185">SMC informa sobre el último estado de energía conocido.</span><span class="sxs-lookup"><span data-stu-id="014e6-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="014e6-186">Energía=<#></span><span class="sxs-lookup"><span data-stu-id="014e6-186">Power=<#></span></span> |



## <span data-ttu-id="014e6-187">Brillo</span><span class="sxs-lookup"><span data-stu-id="014e6-187">Brightness</span></span>

<span data-ttu-id="014e6-188">El nivel de brillo actual está en un intervalo de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="014e6-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="014e6-189">Los cambios en los niveles de brillo se pueden enviar mediante un sistema de control de la sala u otro sistema.</span><span class="sxs-lookup"><span data-stu-id="014e6-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="014e6-190">Comando</span><span class="sxs-lookup"><span data-stu-id="014e6-190">Command</span></span> | <span data-ttu-id="014e6-191">Cambio de estado</span><span class="sxs-lookup"><span data-stu-id="014e6-191">State change</span></span> |<span data-ttu-id="014e6-192">Respuesta</span><span class="sxs-lookup"><span data-stu-id="014e6-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="014e6-193">Brightness+</span></span> | <span data-ttu-id="014e6-194">Controladora de administración del sistema (SMC) envía el comando de subir brillo.</span><span class="sxs-lookup"><span data-stu-id="014e6-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="014e6-195">El servicio del equipo en el sistema de control de la sala notifica a SMC del nuevo nivel de brillo.</span><span class="sxs-lookup"><span data-stu-id="014e6-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="014e6-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="014e6-196">Brightness = 51</span></span> |
| <span data-ttu-id="014e6-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="014e6-197">Brightness-</span></span> |  <span data-ttu-id="014e6-198">SMC envía el comando de bajar brillo.</span><span class="sxs-lookup"><span data-stu-id="014e6-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="014e6-199">El servicio del equipo notifica a SMC del nuevo nivel de brillo.</span><span class="sxs-lookup"><span data-stu-id="014e6-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="014e6-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="014e6-200">Brightness = 50</span></span> |

## <span data-ttu-id="014e6-201">Volumen</span><span class="sxs-lookup"><span data-stu-id="014e6-201">Volume</span></span>

<span data-ttu-id="014e6-202">El nivel de volumen actual está en un intervalo de 0 a 100.</span><span class="sxs-lookup"><span data-stu-id="014e6-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="014e6-203">Los cambios en los niveles de volumen se pueden enviar mediante un sistema de control de la sala u otro sistema.</span><span class="sxs-lookup"><span data-stu-id="014e6-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="014e6-204">El comando de volumen solo controlará el volumen para el modo incrustado o de equipo sustituto, no de [orígenes invitados](connect-and-display-with-surface-hub.md).</span><span class="sxs-lookup"><span data-stu-id="014e6-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="014e6-205">Comando</span><span class="sxs-lookup"><span data-stu-id="014e6-205">Command</span></span> | <span data-ttu-id="014e6-206">Cambio de estado</span><span class="sxs-lookup"><span data-stu-id="014e6-206">State change</span></span> | <span data-ttu-id="014e6-207">Respuesta</span><span class="sxs-lookup"><span data-stu-id="014e6-207">Response</span></span></br><span data-ttu-id="014e6-208">(Activa en [modo de equipo sustituto](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="014e6-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="014e6-209">Volume+</span></span> |  <span data-ttu-id="014e6-210">SMC envía el comando de subir volumen.</span><span class="sxs-lookup"><span data-stu-id="014e6-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="014e6-211">El servicio del equipo notifica a SMC del nuevo nivel de volumen.</span><span class="sxs-lookup"><span data-stu-id="014e6-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="014e6-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="014e6-212">Volume = 51</span></span> |
| <span data-ttu-id="014e6-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="014e6-213">Volume-</span></span> |  <span data-ttu-id="014e6-214">SMC envía el comando de bajar volumen.</span><span class="sxs-lookup"><span data-stu-id="014e6-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="014e6-215">El servicio del equipo notifica a SMC del nuevo nivel de volumen.</span><span class="sxs-lookup"><span data-stu-id="014e6-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="014e6-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="014e6-216">Volume = 50</span></span> |


 

## <span data-ttu-id="014e6-217">Silenciar audio</span><span class="sxs-lookup"><span data-stu-id="014e6-217">Mute for audio</span></span>

<span data-ttu-id="014e6-218">Se puede silenciar el audio.</span><span class="sxs-lookup"><span data-stu-id="014e6-218">Audio can be muted.</span></span>

| <span data-ttu-id="014e6-219">Comando</span><span class="sxs-lookup"><span data-stu-id="014e6-219">Command</span></span> | <span data-ttu-id="014e6-220">Cambio de estado</span><span class="sxs-lookup"><span data-stu-id="014e6-220">State change</span></span> | <span data-ttu-id="014e6-221">Respuesta</span><span class="sxs-lookup"><span data-stu-id="014e6-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="014e6-222">AudioMute+</span></span> |  <span data-ttu-id="014e6-223">SMC envía el comando de silenciar audio.</span><span class="sxs-lookup"><span data-stu-id="014e6-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="014e6-224">El servicio del equipo notifica a SMC que el audio está silenciado.</span><span class="sxs-lookup"><span data-stu-id="014e6-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="014e6-225">ninguno</span><span class="sxs-lookup"><span data-stu-id="014e6-225">none</span></span> |


 

## <span data-ttu-id="014e6-226">Origen de vídeo</span><span class="sxs-lookup"><span data-stu-id="014e6-226">Video source</span></span>

<span data-ttu-id="014e6-227">Se pueden usar varios orígenes de pantalla.</span><span class="sxs-lookup"><span data-stu-id="014e6-227">Several display sources can be used.</span></span>

| <span data-ttu-id="014e6-228">Estado</span><span class="sxs-lookup"><span data-stu-id="014e6-228">State</span></span> | <span data-ttu-id="014e6-229">Descripción</span><span class="sxs-lookup"><span data-stu-id="014e6-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="014e6-230">,0</span><span class="sxs-lookup"><span data-stu-id="014e6-230">0</span></span> |  <span data-ttu-id="014e6-231">Equipo incorporado</span><span class="sxs-lookup"><span data-stu-id="014e6-231">Onboard PC</span></span> |
| <span data-ttu-id="014e6-232">uno</span><span class="sxs-lookup"><span data-stu-id="014e6-232">1</span></span> |  <span data-ttu-id="014e6-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="014e6-233">DisplayPort</span></span> |
| <span data-ttu-id="014e6-234">1</span><span class="sxs-lookup"><span data-stu-id="014e6-234">2</span></span> |  <span data-ttu-id="014e6-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="014e6-235">HDMI</span></span> |
| <span data-ttu-id="014e6-236">2</span><span class="sxs-lookup"><span data-stu-id="014e6-236">3</span></span> |  <span data-ttu-id="014e6-237">VGA</span><span class="sxs-lookup"><span data-stu-id="014e6-237">VGA</span></span> |


 

<span data-ttu-id="014e6-238">Los cambios en el origen de pantalla los puede enviar un sistema de control de la sala u otro sistema.</span><span class="sxs-lookup"><span data-stu-id="014e6-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="014e6-239">Comando</span><span class="sxs-lookup"><span data-stu-id="014e6-239">Command</span></span> | <span data-ttu-id="014e6-240">Cambio de estado</span><span class="sxs-lookup"><span data-stu-id="014e6-240">State change</span></span> | <span data-ttu-id="014e6-241">Respuesta</span><span class="sxs-lookup"><span data-stu-id="014e6-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="014e6-242">Origen=#</span><span class="sxs-lookup"><span data-stu-id="014e6-242">Source=#</span></span> |  <span data-ttu-id="014e6-243">SMC cambia al origen deseado.</span><span class="sxs-lookup"><span data-stu-id="014e6-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="014e6-244">El servicio del equipo notifica a SMC que el origen de pantalla ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="014e6-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="014e6-245">Origen=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="014e6-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="014e6-246">Source+</span><span class="sxs-lookup"><span data-stu-id="014e6-246">Source+</span></span> |  <span data-ttu-id="014e6-247">SMC pasa al siguiente origen de entrada activo.</span><span class="sxs-lookup"><span data-stu-id="014e6-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="014e6-248">El servicio del equipo notifica a SMC del origen de entrada actual.</span><span class="sxs-lookup"><span data-stu-id="014e6-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="014e6-249">Origen=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="014e6-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="014e6-250">Origen-</span><span class="sxs-lookup"><span data-stu-id="014e6-250">Source-</span></span> | <span data-ttu-id="014e6-251">SMC pasa al origen de entrada activo anterior.</span><span class="sxs-lookup"><span data-stu-id="014e6-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="014e6-252">El servicio del equipo notifica a SMC del origen de entrada actual.</span><span class="sxs-lookup"><span data-stu-id="014e6-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="014e6-253">Origen=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="014e6-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="014e6-254">Source?</span><span class="sxs-lookup"><span data-stu-id="014e6-254">Source?</span></span> |  <span data-ttu-id="014e6-255">SMC consulta al servicio del equipo el origen de entrada activo.</span><span class="sxs-lookup"><span data-stu-id="014e6-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="014e6-256">El servicio del equipo notifica a SMC del origen de entrada actual.</span><span class="sxs-lookup"><span data-stu-id="014e6-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="014e6-257">Origen=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="014e6-257">Source=&lt;#&gt;</span></span> |

## <span data-ttu-id="014e6-258">Errores</span><span class="sxs-lookup"><span data-stu-id="014e6-258">Errors</span></span>

<span data-ttu-id="014e6-259">Los errores se devuelven según el formato de esta tabla.</span><span class="sxs-lookup"><span data-stu-id="014e6-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="014e6-260">Error</span><span class="sxs-lookup"><span data-stu-id="014e6-260">Error</span></span> | <span data-ttu-id="014e6-261">Notas</span><span class="sxs-lookup"><span data-stu-id="014e6-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="014e6-262">Error: Comando desconocido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="014e6-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="014e6-263">La instrucción contiene un comando inicial desconocido.</span><span class="sxs-lookup"><span data-stu-id="014e6-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="014e6-264">Por ejemplo, &quot;VOL+&quot; no sería válido y se devolvería &quot; Error: Comando desconocido 'VOL'&quot;.</span><span class="sxs-lookup"><span data-stu-id="014e6-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="014e6-265">Error: Operador desconocido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="014e6-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="014e6-266">La instrucción contiene un operador desconocido.</span><span class="sxs-lookup"><span data-stu-id="014e6-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="014e6-267">Por ejemplo, &quot;Volume!&quot; no sería válido y se devolvería &quot; Error: Operador desconocido '!'&quot;.</span><span class="sxs-lookup"><span data-stu-id="014e6-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="014e6-268">Error: Parámetro desconocido '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="014e6-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="014e6-269">La instrucción contiene un parámetro desconocido.</span><span class="sxs-lookup"><span data-stu-id="014e6-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="014e6-270">Por ejemplo, &quot;Volume=abc&quot; no sería válido y se devolvería &quot; Error: Parámetro desconocido 'abc'&quot;.</span><span class="sxs-lookup"><span data-stu-id="014e6-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="014e6-271">Error: Comando no disponible cuando está desactivado '&lt;input&gt;'.</span><span class="sxs-lookup"><span data-stu-id="014e6-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="014e6-272">Cuando el Surface Hub está desactivado, los comandos que no sean Power devuelven este error.</span><span class="sxs-lookup"><span data-stu-id="014e6-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="014e6-273">Por ejemplo, &quot;Volume+&quot; no sería válido y se devolvería &quot; Error: Comando no disponible cuando está desactivado 'Volume'&quot;.</span><span class="sxs-lookup"><span data-stu-id="014e6-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <span data-ttu-id="014e6-274">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="014e6-274">Related topics</span></span>


[<span data-ttu-id="014e6-275">Administrar Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="014e6-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="014e6-276">Guía del administrador de Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="014e6-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 






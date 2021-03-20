---
title: Wake on LAN para dispositivos Surface
description: Consulta cómo puedes usar Wake on LAN activar dispositivos de forma remota para realizar tareas de administración automáticamente.
keywords: actualizar, implementar, controlador, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442176"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="659d6-104">Wake on LAN para dispositivos Surface</span><span class="sxs-lookup"><span data-stu-id="659d6-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="659d6-105">Los dispositivos Surface que usan un adaptador Ethernet de Surface para conectarse a una red cableada pueden aprovechar Wake on LAN (WOL) desde el modo de espera conectado.</span><span class="sxs-lookup"><span data-stu-id="659d6-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="659d6-106">Con WOL, puede activar dispositivos de forma remota y realizar automáticamente tareas de administración con soluciones de administración como Microsoft Endpoint Manager/Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="659d6-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="659d6-107">Dispositivos compatibles con WOL</span><span class="sxs-lookup"><span data-stu-id="659d6-107">WOL-supported devices</span></span>

- <span data-ttu-id="659d6-108">Adaptador Ethernet de Surface</span><span class="sxs-lookup"><span data-stu-id="659d6-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="659d6-109">Adaptador USB-C a Ethernet y USB de Surface</span><span class="sxs-lookup"><span data-stu-id="659d6-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="659d6-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="659d6-110">Surface Dock 2</span></span>
- <span data-ttu-id="659d6-111">Surface Pro 6 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="659d6-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="659d6-112">Surface Book (todas las generaciones)</span><span class="sxs-lookup"><span data-stu-id="659d6-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="659d6-113">Surface Laptop (todas las generaciones)</span><span class="sxs-lookup"><span data-stu-id="659d6-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="659d6-114">Surface Go (todas las generaciones)</span><span class="sxs-lookup"><span data-stu-id="659d6-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="659d6-115">Surface Studio 2 (consulta Apéndice)</span><span class="sxs-lookup"><span data-stu-id="659d6-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="659d6-116">Uso de Surface WOL</span><span class="sxs-lookup"><span data-stu-id="659d6-116">Using Surface WOL</span></span>

<span data-ttu-id="659d6-117">Los administradores de TI pueden desencadenar dispositivos mediante una activación en una solicitud LAN (paquete mágico) que contenga la dirección MAC del equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="659d6-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="659d6-118">Para enviar un paquete mágico y activar un dispositivo mediante WOL, debes conocer la dirección MAC del dispositivo de destino y el adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="659d6-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="659d6-119">Dado que el paquete mágico no usa el protocolo de red IP, no es posible usar la dirección IP o el nombre DNS del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="659d6-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="659d6-120">Muchas soluciones de administración, como Microsoft Endpoint Configuration Manager y aplicaciones de Microsoft Store de terceros proporcionan compatibilidad integrada con WOL.</span><span class="sxs-lookup"><span data-stu-id="659d6-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="659d6-121">Ten en cuenta que los dispositivos deben estar en modo de espera conectado (suspensión) y conectados a la alimentación de CA.</span><span class="sxs-lookup"><span data-stu-id="659d6-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="659d6-122">Para obtener más información sobre cómo activar dispositivos con Endpoint Configuration Manager, consulte [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span><span class="sxs-lookup"><span data-stu-id="659d6-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="659d6-123">Para comprobar que WOL está habilitado en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="659d6-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="659d6-124">En el dispositivo conectado a Ethernet, seleccione el adaptador de red y, a continuación, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="659d6-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Adaptador Ethernet de Surface](images/surface-ethernet.png)

2. <span data-ttu-id="659d6-126">Seleccione **Configurar**  >  **opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="659d6-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="659d6-127">Desplácese **hasta Paquete mágico woL de** espera moderno y asegúrese de que **Está** habilitado está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="659d6-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![Comprobar que WOL está habilitado en el dispositivo](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="659d6-129">Apéndice: Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="659d6-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="659d6-130">Para habilitar WOL en Surface Studio 2, usa el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="659d6-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="659d6-131">Cree las siguientes claves del Registro:</span><span class="sxs-lookup"><span data-stu-id="659d6-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="659d6-132">Ejecute el siguiente comando</span><span class="sxs-lookup"><span data-stu-id="659d6-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="659d6-133">Más información</span><span class="sxs-lookup"><span data-stu-id="659d6-133">Learn more</span></span>

- [<span data-ttu-id="659d6-134">Adaptador USB-C a Ethernet y USB de Microsoft Surface</span><span class="sxs-lookup"><span data-stu-id="659d6-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="659d6-135">Adaptador Ethernet De Surface USB 3.0 Gigabit</span><span class="sxs-lookup"><span data-stu-id="659d6-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)

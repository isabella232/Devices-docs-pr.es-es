---
title: Instalar la actualización 2020 de Windows10Team
description: Obtén la actualización más reciente del sistema operativo Surface Hub, Windows 10 Team 2020 Update.
keywords: separar valores con comas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470418"
---
# <a name="install-windows-10-team-2020-update"></a>Instalar la actualización 2020 de Windows10Team 

El nuevo sistema operativo Surface Hub, **Windows 10 Team 2020 Update,** basado en Windows 10 versión 20H2, ya está disponible para Surface Hub 2S y el Surface Hub original (v1). 

- Vea también: [Problemas conocidos: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>Distribución

Puedes obtener Windows 2020 Update con uno de los siguientes métodos:

- **Windows Update para empresas**.
- **Imagen de recuperación completa de metal (BMR).** Opción recomendada para los clientes que unen sus dispositivos a Azure Active Directory o no permiten que sus dispositivos reciban actualizaciones de Internet. Para empezar, consulta [Descargar una imagen de recuperación para Surface](https://support.microsoft.com/surfacerecoveryimage).
- **Windows Update.** La disponibilidad varía según la región o el país, como se indica en la tabla siguiente:

| Fase | País/región                         | Inicio          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Australia, Canadá, Bélgica, México | Octubre de 2020  |
| 2     | Reino Unido, Japón, Suiza, Italia          | Noviembre de 2020 |
| 3     | Alemania, Países Bajos                   | Finales de febrero de 2021 |
| 4     | Global                                 | Principios de marzo de 2021 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Mantenimiento de Surface Hubs con Windows 10 Team Edition versión 1703 

El soporte técnico completo para [Windows 10 Team Edition versión 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) está programado para continuar hasta el 16 de marzo de 2021.

### <a name="2s-devices"></a>Dispositivos 2S 

Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub 2S a la actualización de 2020 a través de Windows Update, Windows Update para empresas o mediante la imagen de recuperación completa (BMR), como se explica en [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).

### <a name="v1-devices"></a>Dispositivos V1 

Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub v1 a 2020 Update a través de Windows Update, Windows Update para empresas o mediante la Herramienta de recuperación de [Surface Hub.](surface-hub-recovery-tool.md) KB5000749 debe instalarse para recibir la actualización por aire. Para obtener más información, consulta [Blog de Surface IT Pro](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Novedades

Windows 10 Team 2020 Update ofrece mejoras importantes en la implementación y la facilidad de administración de dispositivos, junto con las características más recientes de Windows 10. Para obtener más información, consulta [Novedades de Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Antes de comenzar

Antes de instalar Windows 10 Team 2020 Update, asegúrate de guardar la clave de BitLocker asociada al dispositivo. 

**Para guardar manualmente la clave de BitLocker**

1. Inserta una unidad USB en Surface Hub.
2. En Surface Hub, abre **Configuración** y escribe tus credenciales de administrador cuando se te pida.
3. Vaya a **Actualizar &**  >  **recuperación de seguridad**.
4. En **BitLocker,** seleccione **Guardar**. La clave BitLocker se guarda en un archivo de texto en la unidad USB.

Para obtener más información, [consulta Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Más información

- [Novedades de la actualización Windows10 Team 2020](surface-hub-2020-update-whats-new.md)
- [Actualización al lanzamiento de Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)

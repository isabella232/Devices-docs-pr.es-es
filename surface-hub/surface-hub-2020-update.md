---
title: Instalar la actualización 2020 de Windows 10 Team
description: Obtenga la actualización más reciente del sistema operativo Surface Hub, Windows 10 Team actualización de 2020.
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
ms.openlocfilehash: 7474787351a9371fb09fa10348ac9f6591b81f6b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497833"
---
# <a name="install-windows-10-team-2020-update"></a>Instalar la actualización 2020 de Windows 10 Team 

El nuevo sistema operativo Surface Hub, **Windows 10 Team 2020 Update**, basado en Windows 10 versión 20H2, ya está disponible para Surface Hub 2S y el Surface Hub original (v1). 

- Consulte también: [Problemas conocidos: actualización de Windows 10 Team 2020](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>Distribución

Puede obtener Windows actualización de 2020 mediante uno de los métodos siguientes:

- **Windows Update para empresas**.
- **Imagen de recuperación sin sistema operativo (BMR).** Opción recomendada para los clientes que se unen a sus dispositivos para Azure Active Directory o no permiten que sus dispositivos reciban actualizaciones de Internet. Para empezar, consulta [Descargar una imagen de recuperación para surface](https://support.microsoft.com/surfacerecoveryimage).
- **Windows Update.** La disponibilidad varía según la región o el país, como se indica en la tabla siguiente:

| Fase | País/región                         | Comenzando          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Australia, Canadá, Bélgica, México | Octubre de 2020  |
| 2     | Reino Unido, Japón, Suiza, Italia          | Noviembre de 2020 |
| 3     | Alemania, Países Bajos                   | Finales de febrero de 2021 |
| 4     | Global                                 | Principios de marzo de 2021 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>Mantenimiento de Surface Hubs con Windows 10 Team Edition versión 1703 

La compatibilidad completa con el mantenimiento de [Windows 10 Team Edition versión 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) está programada para continuar hasta el 16 de marzo de 2021.

### <a name="2s-devices"></a>Dispositivos 2S 

Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub 2S a la actualización 2020 a través de Windows Update, Windows Update para empresas o mediante la imagen de recuperación sin sistema operativo (BMR), como se explica en [Restablecimiento y recuperación para Surface Hub 2S](surface-hub-2s-recover-reset.md).

### <a name="v1-devices"></a>Dispositivos V1 

Los clientes de todas las regiones pueden actualizar sus dispositivos Surface Hub v1 a la actualización 2020 a través de Windows Update, Windows Update para empresas o [mediante la herramienta de recuperación de Surface Hub](surface-hub-recovery-tool.md). KB5000749 debe instalarse para recibir la actualización por vía inalámbrica. Para obtener más información, consulta [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## <a name="whats-new"></a>Novedades

Windows 10 Team actualización de 2020 aporta mejoras importantes a la implementación y la capacidad de administración de dispositivos junto con las características de Windows más recientes. Para más información, consulte [Novedades de Windows 10 Team actualización de 2020](surface-hub-2020-update-whats-new.md).
 
## <a name="before-you-begin"></a>Antes de empezar

Antes de instalar Windows 10 Team actualización de 2020, asegúrese de guardar la clave de BitLocker asociada al dispositivo. 

**Para guardar manualmente la clave de BitLocker**

1. Inserte una unidad USB en Surface Hub.
2. En Surface Hub, abra **Configuración** y escriba las credenciales de administrador cuando se le solicite.
3. Vaya a **Actualizar seguridad &** >  **Recovery**.
4. En **BitLocker**, seleccione **Guardar**. La clave de BitLocker se guarda en un archivo de texto de la unidad USB.

Para más información, consulte [Guardar la clave de BitLocker](save-bitlocker-key-surface-hub.md).

## <a name="learn-more"></a>Obtén más información

- [Novedades de la actualización Windows 10 Team 2020](surface-hub-2020-update-whats-new.md)
- [Actualización al lanzamiento de Windows 10 Team](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)

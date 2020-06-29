---
title: Cómo usar la recuperación en la nube para BitLocker en un Surface Hub
description: Cómo usar la recuperación en la nube para BitLocker en un Surface Hub
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: Configuración de accesibilidad, aplicación Configuración, Accesibilidad
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834873"
---
# Resumen

En este artículo se describe cómo usar la función de recuperación de la nube si se lo solicita inesperadamente mediante BitLocker en un dispositivo Surface Hub.

> [!NOTE]
> Debe seguir estos pasos solo si no está disponible una clave de recuperación de BitLocker.

> [!WARNING]
> * Este proceso de recuperación elimina el contenido de la unidad interna. Si se produce un error en el proceso, la unidad interna quedará totalmente inutilizable. Si esto sucede, tendrá que registrar una solicitud de servicio con Microsoft para obtener una solución.
> * Una vez completado el proceso de recuperación, el dispositivo se restablecerá a la configuración de fábrica y se devolverá al estado de la misma.
> * Después de la recuperación, el Surface Hub debe reconfigurarse por completo.

> [!IMPORTANT]
> Este proceso requiere una conexión a Internet abierta que no use un proxy u otro método de autenticación.

## Proceso de recuperación en la nube

Para realizar una recuperación en la nube, siga estos pasos:

1. Seleccione **ESC para ver más opciones de recuperación**.

   ![Captura de pantalla de escape](images/01-escape.png)

1. Seleccione **omitir esta unidad**.

   ![Captura de pantalla de omitir esta unidad](images/02-skip-this-drive.png)

1. Seleccione **recuperar en la nube**.

   ![Captura de pantalla de la recuperación desde la nube](images/03-recover-from-cloud.png)

1. Seleccione **sí**.

   ![Captura de pantalla de sí](images/04-yes.png)

1. Seleccione **reinstalar**.

   ![Captura de pantalla de reinstalar](images/05a-reinstall.png)

   ![Captura de pantalla de la descarga](images/05b-downloading.png)

1. Una vez completado el proceso **de recuperación de**la nube, inicie la reconfiguración con la configuración rápida.

   ![Captura de pantalla de fuera del cuadro](images/06-out-of-box.png)

## Mensaje de error "se ha encontrado un error"

Este error suele deberse a problemas de red que se producen durante la descarga de la recuperación. Cuando se produzca este problema, no desactive el concentrador porque no podrá reiniciarlo. Si recibe este mensaje de error, vuelva al paso "recuperar desde la nube" y, a continuación, reinicie el proceso de recuperación.

1. Seleccione **Cancelar**.

   ![Captura de pantalla de cancelar](images/07-cancel.png)

1. Seleccione **solucionar problemas**.

   ![Captura de pantalla de solución de problemas](images/08-troubleshoot.png)

1. Seleccione **recuperar en la nube**.

   ![Captura de pantalla de la recuperación desde la nube](images/09-recover-from-cloud2.png)

1. Si se produce un error de **no se encontró la red cableada** , seleccione **Cancelar**y, a continuación, deje que Surface Hub vuelva a descubrir la red cableada.

   ![Captura de pantalla de red cableada no encontrada](images/10-cancel.png)
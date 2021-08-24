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
ms.openlocfilehash: e220be7d4613fcb6a14180e482dc4f2c66a5ddc8
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911035"
---
# <a name="summary"></a>Resumen

En este artículo se describe cómo usar la función de recuperación en la nube si BitLocker te pide inesperadamente en un Surface Hub dispositivo.

> [!NOTE]
> Solo debes seguir estos pasos si una clave de recuperación de BitLocker no está disponible.

> [!WARNING]
> * Este proceso de recuperación elimina el contenido de la unidad interna. Si se produce un error en el proceso, la unidad interna se volverá completamente inutilizable. Si esto ocurre, tendrá que registrar una solicitud de servicio con Microsoft para obtener una resolución.
> * Una vez completado el proceso de recuperación, el dispositivo se restablecerá a la configuración de fábrica y se devolverá a su estado de experiencia fuera de la caja.
> * Después de la recuperación, Surface Hub debe volver a configurarse completamente.

> [!IMPORTANT]
> Este proceso requiere una conexión a Internet abierta que no use un proxy u otro método de autenticación.

## <a name="cloud-recovery-process"></a>Proceso de recuperación en la nube

Para realizar una recuperación en la nube, siga estos pasos:

1. Seleccione **Presionar Esc para obtener más opciones de recuperación.**

   ![Captura de pantalla de Escape.](images/01-escape.png)

1. Seleccione **Omitir esta unidad**.

   ![Captura de pantalla de Omitir esta unidad.](images/02-skip-this-drive.png)

1. Seleccione **Recuperar desde la nube**.

   ![Captura de pantalla de Recuperar desde la nube.](images/03-recover-from-cloud.png)

1. Seleccione **Sí**.

   ![Captura de pantalla de Sí.](images/04-yes.png)

1. Seleccione **Reinstalar**.

   ![Captura de pantalla de Reinstalar.](images/05a-reinstall.png)

   ![Captura de pantalla de descarga.](images/05b-downloading.png)

1. Una vez completado el proceso de recuperación en la nube, inicie la reconfiguración mediante **la experiencia de inicio de la caja**.

   ![Captura de pantalla de Fuera de la caja.](images/06-out-of-box.png)

## <a name="something-went-wrong-error-message"></a>Mensaje de error "Algo salió mal"

Este error suele deberse a problemas de red que se producen durante la descarga de recuperación. Cuando se produzca este problema, no desactive el concentrador porque no podrá reiniciarlo. Si recibe este mensaje de error, vuelva al paso "Recuperar de la nube" y, a continuación, reinicie el proceso de recuperación.

1. Seleccione **Cancelar**.

   ![Captura de pantalla de Cancelar.](images/07-cancel.png)

1. Seleccione **Solucionar problemas**.

   ![Captura de pantalla de Solución de problemas.](images/08-troubleshoot.png)

1. Seleccione **Recuperar desde la nube**.

   ![Captura de pantalla de Recuperar desde la nube.](images/09-recover-from-cloud2.png)

1. Si no **se encuentra** un error en la red cableada, seleccione **Cancelar**y, a continuación, deje que el Surface Hub detección de la red cableada.

   ![No se encuentra la captura de pantalla de la red cableada.](images/10-cancel.png)
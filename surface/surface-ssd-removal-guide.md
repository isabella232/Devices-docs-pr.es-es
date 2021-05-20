---
title: Eliminación de SSD en dispositivos Surface compatibles
description: En este artículo, destinado a técnicos de TI cualificados, se describen los procedimientos recomendados para la eliminación y sustitución de los SD en Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X y Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576910"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>Procedimientos recomendados para la eliminación de SSD de dispositivos Surface compatibles

> [!IMPORTANT]
> Este artículo está pensado para su uso por técnicos de TI cualificados solo en una organización empresarial. Describe los procedimientos recomendados para su uso por técnicos de TI cualificados en la eliminación y sustitución de los SD en los siguientes dispositivos Surface compatibles: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Ir
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> Abrir dispositivos y reemplazar componentes del dispositivo puede presentar descargas eléctricas, daños en el dispositivo, riesgos de incendio y daños personales, y otros riesgos.  Tenga siempre cuidado al realizar dichas actividades. Siga las precauciones y procedimientos de seguridad que se identifican en la Guía de eliminación [de rSSD para Enterprise](https://www.microsoft.com/download/100440). Se recomienda obtener asistencia profesional si no puede seguir las precauciones y procedimientos de seguridad especificados en la "Guía de eliminación de rSSD para Enterprise".

## <a name="prerequisites"></a>Requisitos previos

> [!IMPORTANT]
> En este artículo se supone que comprende las directivas y procedimientos generales de seguridad y precauciones que se describen en la "Guía de eliminación de rSSD para Enterprise".

## <a name="prepare-for-ssd-removal"></a>Preparar la eliminación de SSD 

### <a name="install-the-latest-updates"></a>Instalar las actualizaciones más recientes 

Antes de empezar, asegúrese de que la versión de Windows tiene instaladas las actualizaciones más recientes:

1.  Vaya **a Inicio**  >  **Configuración**  >  **Actualizar & Seguridad**y seleccione Buscar **actualizaciones.**
2. Instale todas las actualizaciones disponibles.
3. Comprueba las contraseñas necesarias para acceder al dispositivo.  
 
## <a name="manage-bitlocker"></a>Administrar BitLocker 

> [!NOTE]
> En esta sección se incluyen recomendaciones para las organizaciones que han BitLocker cifrado de discos duros. Para obtener más información, [vea BitLocker guía de recuperación](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>Si BitLocker cifrado está deshabilitado durante la eliminación y reemplazo de SSD

Si el dispositivo se puede descifrar antes de la eliminación y reemplazo de SSD, siga estos pasos para desactivar BitLocker:

1.  En **Configuración**, escriba BitLocker y, a **continuación,** seleccione **Administrar BitLocker**. 
2.  Seleccione **Desactivar BitLocker**. 
3.  Apague el dispositivo. 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>Si BitLocker cifrado está habilitado durante la eliminación y reemplazo de SSD

Si el dispositivo está cifrado antes de la eliminación y reemplazo de SSD, siga estos pasos para generar una clave de recuperación BitLocker y guardarlo en el almacenamiento USB:

1.  En **Configuración**, escriba **BitLocker**.
2. Seleccione **Administrar BitLocker**Generar BitLocker clave de  > **recuperación**.
2.  Inserte una unidad USB. 
4.  Guarde la clave de recuperación en el almacenamiento USB.  
5.  Quite la unidad USB.  
6.  Apague el dispositivo. 

## <a name="remove-and-replace-ssd"></a>Quitar y reemplazar SSD 

1.  Quite el SSD mediante las instrucciones adecuadas para el dispositivo que se incluyen en la Guía de eliminación de [rSSD para Enterprise](https://www.microsoft.com/download/100440). 
2.  Coloca el SSD original en un nuevo dispositivo y conecta el nuevo dispositivo a una conexión a Internet por cable.
3.  Encienda el nuevo dispositivo. El dispositivo puede pasar por una actualización de firmware durante el inicio.  
 
## <a name="after-ssd-removal-and-replacement"></a>Después de la eliminación y reemplazo de SSD

### <a name="manage-unencrypted-ssds"></a>Administrar EDS sin cifrar 

Si el SSD no está cifrado durante la transferencia, siga estos pasos: 

1.  Ve a **Opciones de inicio de sesión**  >  **Contraseña** (representada por el icono de tecla en el lado izquierdo).  
2.  Escriba la contraseña y el inicio de sesión pendientes de la finalización de la autenticación en dos fases (si procede).
3.  Una vez que haya iniciado sesión por completo, vaya **a Inicio de**sesión  >  **de**la  >  **cuenta**.  
4.  Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida. 
    - Si el dispositivo BitLocker deshabilitado para facilitar la eliminación y reemplazo de SSD y quieres habilitar BitLocker después del reemplazo, ve a **BitLocker**Administrar BitLocker  >  ****  >  **Reanudar BitLocker**.  
6.  Ejecuta la [herramienta de diagnóstico de Microsoft Surface Toolkit para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para comprobar la funcionalidad completa del dispositivo.  
7.  Compruebe si Windows activa mediante la navegación **a Configuración**  >  **activation**.  Si ve algún mensaje de error, seleccione **Solucionar problemas.** 
8.  Compruebe la Office de correo abriendo **la aplicación Office,** vaya a **Cuenta**de archivo y, a continuación, compruebe si hay mensajes  >  **** de error.  

### <a name="managing-encrypted-ssds"></a>Administración de DS cifrados 

> [!NOTE]
> Tendrá que tener un segundo dispositivo para leer la BitLocker de recuperación que se guardó en la unidad USB. 

Si el SSD está cifrado durante la transferencia, siga estos pasos:

1.  Inserte la unidad USB que contiene la BitLocker de recuperación en el segundo dispositivo. 
2.  Abra el .txt que contiene la clave de recuperación de Bitlocker. 
3.  Escribe manualmente la clave BitLocker de recuperación en el nuevo dispositivo que contiene el SSD original.  
4.  Una vez que haya escrito correctamente la clave **** de recuperación BitLocker, vaya a Contraseña de opciones de inicio de sesión (representada por el icono de tecla en  >  **** el lado izquierdo).  
5.  Escriba la contraseña y el inicio de sesión, pendiente de la finalización de la autenticación en dos fases (si procede).
6.  Una vez que haya iniciado sesión por completo, vaya **a Inicio de**sesión  >  **de**la  >  **cuenta**.  
7.  Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN. 
8.  Si el dispositivo BitLocker deshabilitado para facilitar la eliminación y reemplazo de SSD y si quieres habilitar BitLocker después del reemplazo, ve **a Configuración**  >  **BitLocker**Administrar BitLocker Resume  >  ****  >  **BitLocker**.  
9.  Ejecute **[SDT para](surface-diagnostic-toolkit-for-business-intro.md)** comprobar la funcionalidad completa del dispositivo.  
10. Para comprobar Windows activación, **seleccione Configuración**  >  **activación**.  Si ve algún mensaje de error, seleccione **Solucionar problemas.**
11. Para comprobar el estado de la cuenta Office, abra **la aplicación Office**y, a continuación, vaya a Cuenta de archivo para comprobar si hay mensajes de ****  >  **** error.

## <a name="learn-more"></a>Obtén más información

- [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440)
- [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
---
title: Desinstalación de SSD en dispositivos de superficie compatibles
description: Cómo transferir una SSD de un dispositivo Surface a otro.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919229"
---
# Procedimientos recomendados para la eliminación de SSD de dispositivos de superficie compatibles

> [!IMPORTANT]
> Este artículo está pensado para el uso de técnicos de ti cualificados únicamente en una organización empresarial. Describe los procedimientos recomendados para que los técnicos de ti cualificados lo usen al quitar y reemplazar SSDs en dispositivos Surface que tengan SSDs extraíbles. 

> [!WARNING]
> Abrir dispositivos y reemplazar componentes de dispositivos puede presentar descargas eléctricas, daños en el dispositivo, incendio y riesgos personales y otros peligros.  Siempre tenga cuidado cuando lleve a cabo dichas actividades. Siga las precauciones de seguridad y los procedimientos que se identifican en la [Guía de eliminación de rSSD para empresas](https://www.microsoft.com/download/100440). Le recomendamos que obtenga asistencia profesional si no puede seguir las precauciones de seguridad y los procedimientos que se especifican en la "Guía de eliminación de rSSD para empresas".

## Requisitos previos

> [!IMPORTANT]
> En este artículo se presupone que usted comprende las precauciones Generales de seguridad y los procedimientos y directivas de seguridad que se describen en la "Guía de eliminación de rSSD para empresas".

## Prepararse para la eliminación de SSD 

### Instalar las últimas actualizaciones 

Antes de empezar, asegúrese de que la versión de Windows tiene los últimos cambios:

1.  Vaya a **iniciar**  >  **configuración**  >  **Actualizar & seguridad**y seleccione **Buscar actualizaciones**. Instalar todas las actualizaciones disponibles. 
2. Instalar todas las actualizaciones disponibles.
3. Compruebe que tiene contraseñas necesarias para tener acceso al dispositivo.  
 
## Administrar BitLocker 

> [!NOTE]
> Esta sección incluye recomendaciones para organizaciones que han habilitado el cifrado de BitLocker en discos duros. Para obtener más información, consulte la [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Si el cifrado de BitLocker se deshabilita durante la eliminación y sustitución de SSD

Si el dispositivo se puede descifrar antes de la eliminación y sustitución de SSD, siga estos pasos para desactivar BitLocker:

1.  En **configuración**, escriba **BitLocker**y, a continuación, seleccione **Administrar BitLocker**. 
2.  Seleccione **desactivar BitLocker**. 
3.  Apague el dispositivo. 

### Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD

Si el dispositivo está cifrado antes de la eliminación y sustitución de SSD, siga estos pasos para generar una clave de recuperación de BitLocker y guardarla en almacenamiento USB:

1.  En **configuración**, escriba **BitLocker**.
2. Seleccione **administrar**  > **clave de recuperación BitLocker generando**BitLocker.
2.  Inserte una unidad USB. 
3.  Guarde la clave de recuperación en el almacenamiento USB.  
4.  Quite la unidad USB.  
5.  Apague el dispositivo. 

## Quitar y reemplazar el SSD 

1.  Quite el SSD con las instrucciones de la [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440). 
2. Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet por cable.
2.  Encienda el nuevo dispositivo. El dispositivo puede pasar por una actualización de firmware durante el inicio.  
 
## Después de la eliminación y sustitución de SSD

### Administrar SSDs sin cifrar 

Si el SSD sigue sin cifrar durante la transferencia, siga estos pasos: 

1.  Vaya a la contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).  
2.  Escriba la contraseña e inicie sesión en espera de que se complete la autenticación en dos fases (si procede).
3.  Una vez que hayas iniciado sesión por completo, ve a **iniciar**  >  **Account**  >  **sesión**de cuenta.  
4.  Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida. 
    - Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD, y quiere habilitar BitLocker después de la sustitución, **vaya a BitLocker**  >  **Manage BitLocker**  >  **resume BitLocker**.  
6.  Ejecute el kit de herramientas de diagnóstico de Microsoft Surface para empresas (SDT) para comprobar la funcionalidad completa del dispositivo.  
7.  Para comprobar la activación de Windows, navegue hasta la activación de la **configuración**  >  **Activation**.  Si ve algún mensaje de error, seleccione **solucionar problemas**. 
8.  Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a cuenta de **archivo**  >  **Account** y, después, compruebe si hay algún mensaje de error.  

### Administrar SSDs cifradas 

> [!NOTE]
> Deberá tener un segundo dispositivo para leer la clave de recuperación de BitLocker guardada en la unidad USB. 

Si el SSD seguía cifrado durante la transferencia, sigue estos pasos:

1.  Inserte la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo. 
2.  Abra el archivo. txt que contiene la clave de recuperación de BitLocker. 
3.  Escriba manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.  
4.  Una vez que haya escrito correctamente la clave de recuperación de BitLocker, vaya a contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).  
5.  Escriba la contraseña e inicie sesión, pendiente de la finalización de la autenticación en dos fases (si procede).
6.  Una vez que hayas iniciado sesión por completo, ve a **iniciar**  >  **Account**  >  **sesión**de cuenta.  
7.  Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN. 
8.  Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD, y si quiere habilitar BitLocker después de la sustitución, vaya a **configuración**  >  **BitLocker**  >  **Manage BitLocker**  >  **Resume Bitlocker**.  
9.  Ejecute **SDT** para comprobar la funcionalidad completa del dispositivo.  
10. Para comprobar la activación de Windows, vaya a activación de **configuración**  >  **Activation**.  Si ve algún mensaje de error, seleccione **solucionar problemas**.
11. Para comprobar el estado de la cuenta de Office, abra la **aplicación de Office**y, a continuación, vaya a cuenta de **archivo**  >  **Account** para comprobar si hay algún mensaje de error.

## Más información 

Para obtener más información, consulta los artículos siguientes:

- [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440)
- [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
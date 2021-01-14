---
title: Eliminación de SSD en dispositivos Surface compatibles
description: En este artículo, destinado a técnicos de TI cualificados, se describen los procedimientos recomendados para la eliminación y sustitución de los SSD en Surface Laptop 3, Surface Pro X y Surface Laptop Go.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: b65feb24803311aba809819cd6da273ed6934c75
ms.sourcegitcommit: 41124d496abaa38a0d989159f2afec3542d562ca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269111"
---
# Procedimientos recomendados para la eliminación de SSD desde dispositivos Surface compatibles

> [!IMPORTANT]
> Este artículo está pensado para ser usado por técnicos de TI cualificados solo en una organización empresarial. Describe los procedimientos recomendados para su uso por parte de técnicos de TI cualificados en la eliminación y sustitución de los SSD en los siguientes dispositivos Surface compatibles: 

- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3

> [!WARNING]
> La apertura de dispositivos y el reemplazo de componentes del dispositivo pueden presentar descargas eléctricas, daños en el dispositivo, incendios y daños personales, y otros riesgos.  Tenga cuidado siempre cuando realice dichas actividades. Siga las precauciones y procedimientos de seguridad que se identifican en la Guía de [eliminación de rSSD para empresas.](https://www.microsoft.com/download/100440) Le recomendamos que reciba asistencia profesional si no puede seguir las precauciones y procedimientos de seguridad especificados en la "Guía de eliminación de rSSD para empresas".

## Requisitos previos

> [!IMPORTANT]
> En este artículo se supone que comprende las directivas y procedimientos generales de seguridad y precaución que se describen en la "Guía de eliminación de rSSD para empresas".

## Preparar la eliminación de SSD 

### Instalar las actualizaciones más recientes 

Antes de empezar, asegúrate de que la versión de Windows tenga instaladas las actualizaciones más recientes:

1.  Ve a **Iniciar**  >  **actualización de**configuración &  >  **seguridad**y selecciona **Buscar actualizaciones.**
2. Instale todas las actualizaciones disponibles.
3. Comprueba las contraseñas necesarias para acceder al dispositivo.  
 
## Administrar BitLocker 

> [!NOTE]
> En esta sección se incluyen recomendaciones para las organizaciones que han habilitado el cifrado de BitLocker para discos duros. Para obtener más información, consulta [guía de recuperación de BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan) 

### Si el cifrado de BitLocker está deshabilitado durante la eliminación y sustitución de SSD

Si el dispositivo se puede descifrar antes de quitar y reemplazar SSD, sigue estos pasos para desactivar BitLocker:

1.  En **Configuración,** escribe **BitLocker** y, a continuación, **selecciona Administrar BitLocker.** 
2.  Selecciona **Desactivar BitLocker**. 
3.  Apague el dispositivo. 

### Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD

Si el dispositivo está cifrado antes de quitar y reemplazar SSD, sigue estos pasos para generar una clave de recuperación de BitLocker y guardarla en el almacenamiento USB:

1.  En **Configuración,** escriba **BitLocker**.
2. Selecciona **Administrar BitLocker Generar**clave de  > **recuperación de BitLocker.**
2.  Inserta una unidad USB. 
4.  Guarda la clave de recuperación en el almacenamiento USB.  
5.  Quita la unidad USB.  
6.  Apague el dispositivo. 

## Quitar y reemplazar SSD 

1.  Quita el SSD mediante las instrucciones adecuadas para el dispositivo que se incluyen en la Guía de [eliminación de rSSD para empresas.](https://www.microsoft.com/download/100440) 
2.  Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet cableada.
3.  Encienda el nuevo dispositivo. El dispositivo puede pasar por una actualización de firmware durante el inicio.  
 
## Después de la eliminación y sustitución de SSD

### Administrar SSD sin cifrar 

Si el SSD no se cifra durante la transferencia, siga estos pasos: 

1.  Vaya a **Contraseña de opciones de inicio de**sesión  >  **** (representada por el icono de clave del lado izquierdo).  
2.  Escriba la contraseña e inicie sesión pendiente de finalización de la autenticación en dos fases (si corresponde).
3.  Una vez que haya iniciado sesión por completo, vaya **a Iniciar**sesión  >  **en la**  >  **cuenta.**  
4.  Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le pida. 
    - Si el dispositivo estaba deshabilitado para BitLocker para facilitar la eliminación y sustitución de SSD, y quieres habilitar BitLocker después del reemplazo, ve a **BitLocker**  >  **Administrar BitLocker**  >  **Reanudar BitLocker**.  
6.  Ejecuta [Microsoft Surface Diagnostic Toolkit para empresas](surface-diagnostic-toolkit-for-business-intro.md) (SDT) para comprobar la funcionalidad completa del dispositivo.  
7.  Busca la activación de Windows navegando a **Activación**  >  **de configuración.**  Si ve algún mensaje de error, seleccione **Solucionar problemas.** 
8.  Compruebe la cuenta de Office abriendo **** la aplicación **de Office,** vaya a Cuenta de archivo y, a continuación,  >  **** compruebe si hay mensajes de error.  

### Administración de SSD cifrados 

> [!NOTE]
> Tendrá que tener un segundo dispositivo para leer la clave de recuperación de BitLocker que se guardó en la unidad USB. 

Si el SSD está cifrado durante la transferencia, siga estos pasos:

1.  Inserta la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo. 
2.  Abre el archivo .txt que contiene la clave de recuperación de Bitlocker. 
3.  Escribe manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.  
4.  Después de especificar correctamente la clave de **** recuperación de BitLocker, ve a Contraseña de opciones de inicio de sesión (representada por el icono de clave del  >  **** lado izquierdo).  
5.  Escriba la contraseña e inicie sesión, pendiente de la finalización de la autenticación en dos fases (si corresponde).
6.  Una vez que haya iniciado sesión por completo, vaya **a Iniciar**sesión  >  **en la**  >  **cuenta.**  
7.  Vuelva a iniciar sesión con la contraseña y, a continuación, configure Windows Hello y agregue un PIN. 
8.  Si el dispositivo estaba deshabilitado para BitLocker para facilitar la eliminación y sustitución **** de SSD y si quieres habilitar BitLocker después del reemplazo, ve a Configuración de  >  **BitLocker**  >  **Administrar BitLocker**Reanudar  >  **BitLocker**.  
9.  Ejecuta **[SDT para](surface-diagnostic-toolkit-for-business-intro.md)** comprobar la funcionalidad completa del dispositivo.  
10. Para comprobar la activación de Windows, seleccione **Configuración**  >  **de activación.**  Si ve algún mensaje de error, seleccione **Solucionar problemas.**
11. Para comprobar el estado de la cuenta de Office, abra la aplicación **de Office**y, a continuación, vaya a Cuenta de archivo para comprobar si hay ****  >  **** mensajes de error.

## Obtén más información

- [Guía de eliminación de rSSD para empresas](https://www.microsoft.com/download/100440)
- [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

¿Aún necesitas ayuda? Vaya a [Microsoft Community.](https://answers.microsoft.com/)
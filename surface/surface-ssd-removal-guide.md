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
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918973"
---
# Procedimientos recomendados para la eliminación de SSD en dispositivos de superficie compatibles

> [!IMPORTANT]
> Este artículo está pensado para el uso de técnicos de ti cualificados únicamente en una organización empresarial. Describe los procedimientos recomendados para que los técnicos de ti cualificados los usen para quitar y reemplazar SSDs en dispositivos Surface con SSDs extraíbles. 

> [!WARNING]
> Abrir dispositivos y reemplazar componentes de dispositivos puede presentar descargas eléctricas, daños en el dispositivo, incendio y riesgos personales y otros peligros.  Tenga siempre cuidado cuando realice actividades de este tipo. Siga las precauciones de seguridad y los procedimientos identificados en la guía de eliminación de rSSD para empresas. Microsoft recomienda que solicite asistencia profesional si no puede seguir las precauciones de seguridad y los procedimientos especificados en la guía de eliminación de rSSD para empresas. 

## Requisitos previos

> [!IMPORTANT]
> Este artículo supone que usted comprende las precauciones Generales de seguridad y los procedimientos y políticas de seguridad que se describen en la [Guía de eliminación de rSSD para empresas](https://www.microsoft.com/download/100440).

## Prepararse para la eliminación de SSD 

### Instalar las últimas actualizaciones 

Antes de empezar, asegúrese de que su versión de Windows tiene las actualizaciones más recientes.

1.  Vaya a **Inicio**de  >  la actualización de**configuración**  >  **& seguridad** y seleccione **Buscar actualizaciones**. Instalar todas las actualizaciones disponibles.  

2.  Confirme que tiene las contraseñas necesarias para acceder al dispositivo.  
 
## Administrar BitLocker 

> [!NOTE]
> Esta sección incluye recomendaciones para las organizaciones que han habilitado el cifrado de BitLocker en las unidades de disco duro. Para obtener más información, consulte la [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### Si el cifrado de BitLocker se deshabilita durante la eliminación y sustitución de SSD

Si el dispositivo se puede descifrar antes de la eliminación y sustitución de SSD, siga estos pasos para desactivar BitLocker:

1.  En **configuración**, escriba **BitLocker** y seleccione **Administrar BitLocker**. 
2.  Seleccione **desactivar BitLocker**. 
3.  Apague el dispositivo. 

### Si el cifrado de BitLocker está habilitado durante la eliminación y sustitución de SSD

Si el dispositivo está cifrado antes de la eliminación y sustitución de SSD, siga estos pasos para generar una clave de recuperación de BitLocker y guardarla en almacenamiento USB:

1.  Vaya a **configuración** y escriba **BitLocker**.
2. Seleccione **administrar**  > **clave de recuperación BitLocker generando**BitLocker.
2.  Inserte una unidad USB. 
3.  Guarde la clave de recuperación en el almacenamiento USB.  
4.  Quite la unidad USB.  
5.  Apague el dispositivo. 

## Quitar y reemplazar el SSD 

1.  Quite la SSD con las instrucciones de la [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440). 
2. Coloca el SSD original en un dispositivo nuevo y conecta el nuevo dispositivo a una conexión a Internet por cable.
2.  Encienda el nuevo dispositivo. El dispositivo puede pasar por una actualización de firmware durante el inicio.  
 
## Después de la eliminación y sustitución de SSD

### Administrar SSDs sin cifrar 

Si el SSD sigue sin cifrar durante la transferencia, complete los siguientes pasos: 

1.  Vaya a la contraseña **de opciones de inicio de sesión**  >  **Password** (representada como el icono de llave en el lado izquierdo).  
2.  Escriba la contraseña e inicie sesión pendiente de la autenticación en dos fases (si procede).
3.  Una vez que haya iniciado sesión completamente, vaya a **iniciar**  >  **Account**  >  **sesión**de cuenta.  
4.  Vuelva a iniciar sesión con la contraseña y configure Windows Hello y un PIN cuando se le solicite. 
    - Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD y quiere habilitar BitLocker después de la sustitución, **vaya a BitLocker**  >  **Manage**BitLocker  >  **resume BitLocker**.  
6.  Ejecute **SDT** para confirmar la funcionalidad completa del dispositivo.  
7.  Para comprobar la activación de Windows, navegue hasta la activación de la **configuración**  >  **Activation**.  Si hay algún mensaje de error, seleccione **solucionar problemas**. 
8.  Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a cuenta de **archivo**  >  **Account** y compruebe si hay algún mensaje de error.  

### Administrar SSDs cifradas 

> [!NOTE]
> Necesitará un segundo dispositivo para leer la clave de recuperación de BitLocker guardada en la unidad USB. 

Si el SSD seguía cifrado durante la transferencia, completa lo siguiente:

1.  Inserte la unidad USB que contiene la clave de recuperación de BitLocker en el segundo dispositivo. 
2.  Abra el archivo. txt que contiene la clave de recuperación de BitLocker. 
3.  Escriba manualmente la clave de recuperación de BitLocker en el nuevo dispositivo que contiene el SSD original.  
4.  Una vez que haya escrito correctamente la clave de recuperación de BitLocker, vaya a contraseña de **Opciones de inicio de sesión**  >  **Password** (representada por el icono de llave en el lado izquierdo).  
5.  Escribir la contraseña e iniciar sesión, pendiente de la finalización de la autenticación en dos fases (si procede) 
6.  Una vez que haya iniciado sesión completamente, vaya a **iniciar**  >  **Account**  >  **sesión**de cuenta.  
7.  Vuelva a iniciar sesión con la contraseña y configure Windows Hello y agregue un PIN. 
8.  Si el dispositivo se deshabilitó para BitLocker con el fin de facilitar la eliminación y el reemplazo de SSD y quiere habilitar BitLocker después de la sustitución, vaya a **configuración**  >  **BitLocker**  >  **Manage**BitLocker  >  **resume BitLocker**.  
9.  Ejecute **SDT** para confirmar la funcionalidad completa del dispositivo.  
10. Para comprobar la activación de Windows, vaya a activación de **configuración**  >  **Activation**.  Si hay algún mensaje de error, seleccione **solucionar problemas**.
11. Para comprobar la cuenta de Office, abra la **aplicación de Office**, vaya a la cuenta de **archivo**  >  **Account** y compruebe si hay algún mensaje de error.

## Más información 

Para obtener más información, consulta los artículos siguientes:

- [Guía de eliminación de rSSD para Enterprise](https://www.microsoft.com/download/100440)
- [Guía de recuperación de BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

¿Aún necesitas ayuda? Vaya a [Microsoft Community](https://answers.microsoft.com/).
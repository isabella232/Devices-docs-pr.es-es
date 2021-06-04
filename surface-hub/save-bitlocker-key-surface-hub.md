---
title: Guardar la clave de BitLocker (Surface Hub)
description: Cada Microsoft Surface Hub se configura automáticamente con el software de cifrado de unidad de BitLocker. Microsoft recomienda encarecidamente que te asegures de hacer una copia de seguridad de las claves de recuperación de BitLocker.
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, claves de recuperación de Bitlocker
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10836465"
---
# Guardar la clave de BitLocker (Surface Hub)


Cada Microsoft Surface Hub se configura automáticamente con el software de cifrado de unidad de BitLocker. Microsoft recomienda encarecidamente que te asegures de hacer una copia de seguridad de las claves de recuperación de BitLocker.

Hay varias maneras de administrar la clave de BitLocker en Surface Hub.

1.  Si uniste Surface Hub a un dominio, el dispositivo realizará una copia de seguridad de la clave del dominio y la almacenará en el objeto del equipo.

    Si no encuentras la clave de BitLocker después de unir el dispositivo a un dominio, es probable que tu esquema de Active Directory no admita la copia de seguridad de la clave de BitLocker. Si no quieres cambiar el esquema, puedes guardar la clave de BitLocker yendo a Configuración y siguiendo el procedimiento para usar una cuenta de administrador local, lo que se detallará más adelante en esta lista.

2.  Si has unido Surface Hub a Azure Active Directory (Azure AD), la clave de BitLocker se almacenará en la cuenta usada para unir el dispositivo.

3.  Si está usando una cuenta de administrador local para administrar el dispositivo, puede guardarla en la aplicación **configuración** y navegar para **Actualizar &** la &gt; **recuperación**de seguridad. Inserta una unidad USB y selecciona la opción para guardar la clave de BitLocker. La clave se guardará en un archivo de texto en la unidad USB.


##  <a name="related-topics"></a>Temas relacionados

[Administrar Microsoft Surface Hub](manage-surface-hub.md)

[Guía del administrador de Microsoft Surface Hub](surface-hub-administrators-guide.md)

 

 






---
title: Configurar las redes y la calidad del servicio para Microsoft Teams room en Surface Hub
description: En este artículo se explican los requisitos y recomendaciones para las redes y la calidad del servicio para optimizar Salas de Microsoft Teams en Surface Hub.
keywords: Salas de Teams, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "11910013"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>Configurar las redes y la calidad del servicio para Salas de Microsoft Teams en Surface Hub

En este artículo se explica cómo preparar el entorno para optimizar los Salas de Microsoft Teams en Surface Hub.

## <a name="create-and-test-a-device-account"></a>Crear y probar una cuenta de dispositivo

Una cuenta de dispositivo es una cuenta que el Salas de Microsoft Teams usa para tener acceso a las características desde Exchange, como el calendario, y para habilitar Skype Empresarial. [Consulta Crear y probar una cuenta de dispositivo](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>Comprobar la disponibilidad de la red

> [!TIP]
> Se recomienda encarecidamente usar los procedimientos para la configuración de red enumerados [en Microsoft 365 principios de conectividad de red](https://aka.ms/pnc)

Salas de Teams en Surface Hub debe tener acceso a una red que cumpla estos requisitos:

- Acceso a la instancia de Active Directory Azure Active Directory (Azure AD)
- Acceso a un servidor que puede proporcionar una dirección IP mediante DHCP. Salas de Microsoft Teams en Surface Hub no se puede configurar con una dirección IP estática.
- Acceso a los puertos HTTP 80 y 443.
- Puertos TCP y UDP configurados como se describe en Requisitos de puerto y protocolo para Microsoft 365 y Office 365 direcciones URL e [intervalos](/microsoft-365/enterprise/urls-and-ip-address-ranges) de direcciones IP para Microsoft Teams.

> [!IMPORTANT]
> Salas de Microsoft Teams no admite la autenticación de proxy, ya que puede interferir con las operaciones regulares de Teams. Asegúrese de que Surface Hub dispositivos o Microsoft 365 de servicio de Microsoft 365 se han exento de la autenticación de proxy antes de entrar en producción con Salas de Teams en Surface Hub.

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>Implementar calidad de servicio (QoS) en Surface Hub

Calidad de servicio (QoS) es una combinación de tecnologías de red que permite a los administradores optimizar la experiencia de comunicaciones de uso compartido de aplicaciones y audio en tiempo real.
La configuración de QoS para Microsoft Teams en el Surface Hub puede realizarse con el proveedor de administración de dispositivos móviles [(MDM)](manage-settings-with-mdm-for-surface-hub.md) o a través de un paquete [de aprovisionamiento](provisioning-packages-for-surface-hub.md).

Para configurar QoS para Surface Hub con Microsoft Intune:

1. En Intune, [cree una directiva personalizada](/intune/custom-settings-configure).

2. En **Custom OMA-URI Configuración**, seleccione **Agregar**. Para cada configuración que agregue, escribirá un nombre, una descripción (opcional), un tipo de datos, OMA-URI y un valor.

3. Para garantizar una calidad óptima de vídeo y audio en Surface Hub, agrega la siguiente configuración de QoS al dispositivo.

    | Nombre                  | Descripción           | OMA-URI                                                                        | Tipo    | Valor       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **Puertos de audio**       | Rango de puertos de audio      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | Cadena  | 50000-50019 |
    | **DSCP de audio**        | Marcado de puertos de audio   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | Integer | 46          |
    | **Puerto de vídeo**        | Rango de puertos de vídeo      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | Cadena  | 50020-50039 |
    | **DSCP de vídeo**        | Marcado de puertos de vídeo   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | Integer | 34          |
    | **Puerto compartido**      | Intervalo de puertos compartidos    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | Cadena  | 50040-50059 |
    | **Uso compartido de DSCP**      | Marcado de puertos compartidos | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | Integer | 18          |

4. Cuando se haya creado la directiva, impleméntela en Surface Hub.

## <a name="learn-more"></a>Obtén más información

- [Implementar calidad de servicio (QoS) en Microsoft Teams](/microsoftteams/qos-in-teams)

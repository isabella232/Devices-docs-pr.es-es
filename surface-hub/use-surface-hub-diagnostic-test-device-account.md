---
title: Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo
description: Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: Configuración de accesibilidad, aplicación Configuración, Accesibilidad
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 0a9914f5c07a33306cc8a3ef87de85df47a05a20
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911439"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo

## <a name="introduction"></a>Introducción

> [!NOTE]
> La sección "Account Configuración" de la Surface Hub de diagnóstico de hardware no recopila ninguna información. El correo electrónico y la contraseña que se introducen como entrada solo se usan directamente en el entorno y no se recopilan ni transfieren a nadie. La información de inicio de sesión solo persiste hasta que la aplicación se cierra o finaliza la sesión actual en el Surface Hub.

> [!IMPORTANT]
> * Los privilegios de administrador no son necesarios para ejecutar esta aplicación.
> * Los resultados del diagnóstico deben analizarse con el administrador local antes de abrir una llamada de servicio con Microsoft.

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub Diagnóstico de hardware

De forma predeterminada, [la Surface Hub de](https://www.microsoft.com/store/apps/9nblggh51f2g) diagnóstico de hardware no está instalada en versiones anteriores del sistema Surface Hub hardware. La aplicación está disponible de forma gratuita desde el Microsoft Store. Los privilegios de administrador son necesarios para instalar la aplicación.

   ![Captura de pantalla del diagnóstico de hardware.](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>Acerca de la Surface Hub de diagnóstico de hardware

La Surface Hub de diagnóstico de hardware es una herramienta fácil de navegar que permite al usuario probar muchos de los componentes de hardware dentro del Surface Hub dispositivo. Esta herramienta también puede probar y comprobar una cuenta Surface Hub dispositivo. En este artículo se describe cómo usar la prueba account Configuración dentro de la Surface Hub de diagnóstico de hardware.

> [!NOTE]
> La cuenta del dispositivo para el Surface Hub debe crearse antes de realizar cualquier prueba. La guía Surface Hub administrador proporciona instrucciones y scripts de PowerShell para ayudarle a crear cuentas de dispositivos locales, en línea (Office365) o híbridas. Para obtener más información, vaya al tema Crear y probar una cuenta de dispositivo [(Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) de la guía.

### <a name="device-account-testing-process"></a>Proceso de prueba de cuenta de dispositivo

1. Vaya a **Todas las aplicaciones**y, a continuación, busque la Surface Hub de diagnóstico de hardware.

    ![Captura de pantalla de todas las aplicaciones.](images/02-all-apps.png)

1. Cuando se inicia la aplicación, la **página de** bienvenida proporciona una ventana de texto para documentar el motivo por el que está probando el concentrador. Esta nota se puede guardar en USB junto con los resultados de diagnóstico al finalizar las pruebas. Una vez que termine de escribir una nota, seleccione el **botón** Continuar.

    >[!NOTE]
    >Al guardar los resultados de diagnóstico, no cambie la ruta de acceso predeterminada ni seleccione un subdirectorio. Los archivos se pueden copiar más adelante a través de la aplicación Explorador de archivos.

    ![Captura de pantalla de bienvenida.](images/03-welcome.png)

1. La siguiente pantalla le ofrece la opción de probar todos o algunos de los Surface Hub componentes. Para empezar a probar la cuenta del dispositivo, selecciona el icono **Resultados de** la prueba.

    ![Captura de pantalla de Opciones de prueba.](images/04-test-results-1.png)

    ![Captura de pantalla de los resultados de la prueba.](images/05-test-results-2.png)

1. Seleccione **Cuenta Configuración**.  

    ![Captura de pantalla de la cuenta Configuración.](images/06-account-settings.png)

    La pantalla Configuración cuenta se usa para probar la cuenta del dispositivo.

    ![Captura de pantalla de detalles Configuración cuenta.](images/07-account-settings-details.png)

1. Escribe la dirección de correo electrónico de tu cuenta de dispositivo. La contraseña es opcional, pero se recomienda. Seleccione el **botón Probar cuenta** cuando esté listo para continuar.

    ![Captura de pantalla de la cuenta de prueba.](images/08-test-account.png)

1. Una vez finalizadas las pruebas, revise los resultados de las cuatro áreas de prueba. Cada sección se puede expandir o contraer seleccionando el signo Más o Menos junto a cada tema.

    **Red**

    ![Captura de pantalla de Red.](images/09-network.png)

    **Entorno**

    ![Captura de pantalla del entorno.](images/10-environment.png)

    **Certificados**

    ![Captura de pantalla de certificados.](images/11-certificates.png)

    **Modelo de confianza**

    ![Captura de pantalla del modelo de confianza.](images/12-trust-model.png)

## <a name="appendix"></a>Apéndice

### <a name="field-messages-and-resolution"></a>Mensajes de campo y resolución

#### <a name="network"></a>Red

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Conectividad a Internet |El dispositivo tiene conectividad a Internet |El dispositivo no tiene conectividad a Internet |Comprueba la conectividad a Internet, incluida la conexión proxy |
Versión HTTP |1.1 |1.0 |Si se encuentra HTTP 1.0, provocará problemas con WU y Store |
Conectividad directa a Internet |El dispositivo tiene un dispositivo configurado por proxy que no tiene ningún proxy configurado |N/A |Informativo. ¿Está el dispositivo detrás de un proxy? |
Dirección proxy | | |Si está configurado, devuelve la dirección proxy. |
Autenticación de proxy |El proxy no requiere autenticación |Proxy requiere autenticación de proxy |El resultado puede ser un falso positivo si un usuario ya tiene una sesión abierta en Edge y se ha autenticado a través del proxy. |
Tipos de autenticación de proxy | | |Si se usa la autenticación de proxy, devuelve los métodos de autenticación anunciados por el proxy.  |

#### <a name="environment"></a>Entorno

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Dominio SIP | | |Informativo.  |
Skype Entorno |Skype Empresarial Online, Skype Empresarial OnPrem, Skype Empresarial Hybrid |Informativo. |Qué tipo de entorno se detectó. Nota: El híbrido solo se puede detectar si se introduce la contraseña.
LyncDiscover FQDN | | |Informativo. Muestra el resultado dns de LyncDiscover |
LyncDiscover URI | | |Informativo. Muestra la dirección URL usada para realizar una LyncDiscover en el entorno.|
LyncDiscover |Conexión correcta |Error en la conexión |Respuesta del servicio web LyncDiscover. |
Nombre de host del grupo SIP | | |Informativo. Mostrar el nombre del grupo SIP detectado en LyncDiscover |

#### <a name="certificates-in-premises-hybrid-only"></a>Certificados (solo híbridos locales)

Certificado de LyncDiscover

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
LyncDiscover Cert CN | | |Informativo. Muestra el certificado LD Nombre común |
LyncDiscover Cert CA | | |Informativo. Muestra la CA de certificado DE LD |
LyncDiscover Cert Root CA | | |Informativo. Muestra la CA raíz de certificado de LD, si está disponible. |
Estado de confianza ld |El certificado es de confianza. |El certificado no es de confianza, agregue la CA raíz. |Compruebe el certificado en el almacén de certificados local. Devuelve positivo si la máquina confía en el certificado.|[Descargar e implementar Skype Empresarial certificados con PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Elementos admitidos para Surface Hub paquetes de aprovisionamiento](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

Certificación de grupo SIP

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
CERT DE GRUPO SIP | | |(CONTENTS) |
CA de certificado de grupo SIP | | |(CONTENTS) |
Estado de confianza del grupo SIP |El certificado es de confianza. |El certificado no es de confianza, agregue la CA raíz. |Compruebe el certificado en el almacén de certificados local y devuelva un positivo si los dispositivos confían en el certificado. |
CA raíz de certificado de grupo SIP | | |Información. Mostrar la CA raíz de certificado de grupo SIP, si está disponible. |

#### <a name="trust-model-on-premises-hybrid-only"></a>Modelo de confianza (solo híbrido local)

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Estado del modelo de confianza |No se detectó ningún problema del modelo de confianza. |Dominio SIP y dominio de servidor son diferentes, agregue los siguientes dominios. |Compruebe el fqdn ld/ nombre del servidor LD/ nombre del servidor de grupo de servidores para el problema del modelo de confianza. 
Nombres de dominio | | |Devuelve la lista de dominios que se deben agregar para que SFB se conecte. |

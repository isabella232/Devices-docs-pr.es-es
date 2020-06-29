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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834882"
---
# Uso de la herramienta de diagnóstico de hardware de Surface Hub para probar una cuenta del dispositivo

## Introducción

> [!NOTE]
> La sección "configuración de la cuenta" de la herramienta de diagnóstico de hardware de Surface Hub no recopila información. El correo electrónico y la contraseña que se introducen como entrada solo se usan directamente en su entorno y no se recopilan ni se transfieren a nadie. La información de inicio de sesión se conserva solo hasta que se cierra la aplicación o finaliza la sesión actual en Surface Hub.

> [!IMPORTANT]
> * No se necesitan privilegios de administrador para ejecutar esta aplicación.
> * Los resultados del diagnóstico deben comentarse con el administrador local antes de abrir una llamada de servicio con Microsoft.

### Diagnóstico de hardware de Surface Hub

De forma predeterminada, la aplicación de [diagnóstico de hardware de Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g) no está instalada en versiones anteriores del sistema Surface Hub. La aplicación está disponible gratuitamente en Microsoft Store. Se necesitan privilegios de administrador para instalar la aplicación.

   ![Captura de pantalla de diagnóstico de hardware](images/01-diagnostic.png)

## Acerca de la herramienta de diagnóstico de hardware Surface Hub

La herramienta de diagnóstico de hardware de Surface Hub es una herramienta de fácil navegación que permite al usuario probar muchos de los componentes de hardware dentro del dispositivo Surface Hub. Esta herramienta también puede probar y verificar una cuenta de dispositivo de Surface Hub. En este artículo se describe cómo usar la prueba de configuración de la cuenta en la herramienta de diagnóstico de hardware de Surface Hub.

> [!NOTE]
> Debe crearse la cuenta del dispositivo para Surface Hub antes de que se realicen las pruebas. La guía del administrador de Surface Hub proporciona instrucciones y scripts de PowerShell para ayudarle a crear cuentas locales, en línea (Office365) o de dispositivos híbridos. Para obtener más información, vaya al tema [crear y probar una cuenta de dispositivo (Surface hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) en la guía.

### Proceso de prueba de cuenta de dispositivo

1. Vaya a **todas las aplicaciones**y, a continuación, busque la aplicación de diagnóstico de hardware de Surface Hub.

    ![Captura de pantalla de todas las aplicaciones](images/02-all-apps.png)

1. Cuando se inicia la aplicación, la página **principal** proporciona una ventana de texto para documentar el motivo por el que se está probando el concentrador. Esta nota se puede guardar en USB junto con los resultados del diagnóstico al finalizar las pruebas. Cuando termine de escribir una nota, seleccione el botón **continuar** .

    ![Captura de pantalla de bienvenida](images/03-welcome.png)

1. La siguiente pantalla te ofrece la opción de probar todos o algunos de los componentes de Surface Hub. Para empezar a probar la cuenta del dispositivo, seleccione el icono resultados de la **prueba** .

    ![Captura de pantalla de resultados de pruebas](images/04-test-results-1.png)

    ![Captura de pantalla de resultados de pruebas](images/05-test-results-2.png)

1. Seleccione **configuración**de la cuenta.  

    ![Captura de pantalla de configuración de la cuenta](images/06-account-settings.png)

    La pantalla Configuración de la cuenta se usa para probar la cuenta del dispositivo.

    ![Captura de pantalla de detalles de configuración de la cuenta](images/07-account-settings-details.png)

1. Escriba la dirección de correo electrónico de su cuenta del dispositivo. La contraseña es opcional, pero se recomienda. Selecciona el botón **probar cuenta** cuando estés listo para continuar.

    ![Captura de pantalla de la cuenta de prueba](images/08-test-account.png)

1. Una vez finalizada la prueba, revise los resultados de las cuatro áreas de prueba. Cada sección se puede expandir o contraer seleccionando el signo más o el signo menos junto a cada tema.

    **Red**

    ![Captura de pantalla de red](images/09-network.png)

    **Entorno**

    ![Captura de pantalla del entorno](images/10-environment.png)

    **Certificados**

    ![Captura de pantalla de certificados](images/11-certificates.png)

    **Modelo de confianza**

    ![Captura de pantalla de modelo de confianza](images/12-trust-model.png)

## Apéndice

### Mensajes de campo y resolución

#### Red

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Conectividad a Internet |El dispositivo tiene conexión a Internet |El dispositivo no tiene conexión a Internet |Comprueba la conectividad a Internet, incluidas las conexiones proxy |
Versión HTTP |1,1 |1.0 |Si se encuentra HTTP 1,0, se producirá un problema con WU y Store. |
Conexión directa a Internet |El dispositivo tiene un proxy configurado como no tiene un proxy configurado |N/D |Informativo. ¿Está el dispositivo detrás de un proxy? |
Dirección del proxy | | |Si se configura, devuelve la dirección del proxy. |
Autenticación de proxy |El proxy no requiere autenticación |El proxy requiere autenticación proxy |El resultado puede ser un falso positivo si un usuario ya tiene una sesión abierta en Edge y se ha autenticado a través del proxy. |
Tipos de autenticación de proxy | | |Si se usa la autenticación de proxy, devuelva los métodos de autenticación anunciados por el proxy.  |

#### Entorno

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Dominio SIP | | |Informativo.  |
Entorno de Skype |Skype empresarial online, Skype empresarial local, Skype empresarial híbrido |Informativo. |Qué tipo de entorno se ha detectado. Nota: solo se puede detectar una implementación híbrida si se escribe la contraseña.
FQDN de LyncDiscover | | |Informativo. Muestra el resultado DNS de LyncDiscover |
URI de LyncDiscover | | |Informativo. Muestra la dirección URL que se usa para realizar una LyncDiscover en su entorno.|
LyncDiscover |Conexión correcta |Error en la conexión |Respuesta del servicio Web de LyncDiscover. |
Nombre de host del grupo de SIP | | |Informativo. Mostrar el nombre del grupo de SIP descubierto desde LyncDiscover |

#### Certificados (solo implementaciones híbridas locales)

Certificado LyncDiscover

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
LyncDiscover certificado CN | | |Informativo. Muestra el nombre común de certificado LD |
CA de CERT LyncDiscover | | |Informativo. Muestra el LD certificado CA |
CA raíz de CERT de LyncDiscover | | |Informativo. Muestra la entidad emisora de certificados raíz de certificados, si está disponible. |
LD estado de confianza |El certificado es de confianza. |El certificado no es de confianza, agregue la entidad emisora raíz. |Comprobar el certificado en el almacén de certificados local. Devuelve positivo si el equipo confía en el certificado.|[Descargar e implementar certificados de Skype empresarial con PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / [Elementos admitidos para paquetes de aprovisionamiento de Surface Hub](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

Certificación del grupo de SIP

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Certificado CN de grupo SIP | | |CONTENIDOS |
CA de CERT del grupo SIP | | |CONTENIDOS |
Estado de confianza del grupo SIP |El certificado es de confianza. |El certificado no es de confianza, agregue la entidad emisora raíz. |Comprobar el certificado en el almacén de certificados local y devolver un valor positivo si los dispositivos confían en el certificado. |
CA raíz de CERT pool de SIP | | |Informaciones. Mostrar la entidad emisora de certificados raíz del grupo SIP, si está disponible. |

#### Modelo de confianza (solo local híbrido)

Campo |Correcto |Error |Comentario |Referencia
|------|------|------|------|------|
Estado del modelo de confianza |No se detectó ningún problema de modelo de confianza. |El dominio SIP y el dominio del servidor son diferentes agregue los siguientes dominios. |Compruebe el FQDN/LD nombre del servidor/nombre del servidor de grupo para el problema de modelo de confianza. 
Nombre (s) de dominio (s) | | |Devuelva la lista de dominios que se debe agregar para SFB a Connect. |

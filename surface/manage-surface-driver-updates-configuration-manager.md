---
title: Administrar actualizaciones de controladores de Surface en Configuration Manager
description: En este artículo se describen las opciones disponibles para administrar e implementar actualizaciones de firmware y controladores para dispositivos Surface.
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, actualización, dispositivo, administrar, implementar, controlador, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: da90a0481052d06c2108c8fd096d088bfacdcb87
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911005"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>Administrar actualizaciones de controladores de Surface en Configuration Manager

## <a name="summary"></a>Resumen

A partir [de Microsoft System Center Configuration Manager versión 1710,](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)puedes sincronizar e implementar actualizaciones de controladores y firmware de Microsoft Surface directamente a través del cliente de Configuration Manager. El proceso es similar a la implementación de actualizaciones periódicas. Sin embargo, se necesitan algunas configuraciones adicionales para obtener las actualizaciones de controladores de Surface en el catálogo.

## <a name="prerequisites"></a>Requisitos previos

Para administrar las actualizaciones de controladores de Surface, deben cumplirse los siguientes requisitos previos:

- Debe usar Configuration Manager versión 1710 o una versión posterior.
- Todos los puntos de actualización de software (SUP) deben ejecutarse Windows Server 2016 una versión posterior. De lo contrario, Configuration Manager omite esta configuración y los controladores de Surface no se sincronizarán.

> [!NOTE]
> Si tu entorno no cumple los requisitos [](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) previos, consulta los métodos alternativos para implementar actualizaciones de controladores y firmware de Surface en la sección [preguntas más](#frequently-asked-questions-faq) frecuentes.

## <a name="useful-log-files"></a>Archivos de registro útiles

Los siguientes registros son especialmente útiles cuando administras actualizaciones de controladores de Surface.

|Nombre del registro|Descripción|
|---|---|
|WCM.log|Registra detalles sobre la configuración del punto de actualización de software y las conexiones al servidor WSUS para categorías de actualización suscritas, clasificaciones e idiomas.|
|WsyncMgr.log|Registra detalles sobre el proceso de sincronización de actualizaciones de software.|

Estos registros se encuentran en el servidor de sitio que administra el SUP o en el propio SUP si está instalado directamente en un servidor de sitio.
Para obtener una lista completa de los registros de Configuration Manager, vea [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).

## <a name="enabling-surface-driver-updates-management"></a>Habilitar la administración de actualizaciones de controladores de Surface

Para habilitar la administración de actualizaciones de controladores de Surface en Configuration Manager, siga estos pasos:

1. En la consola de Configuration Manager, vaya a **Administration**  >  **Overview**  >  **Site Configuration**  >  **Sites**.
1. Seleccione el sitio que contiene el servidor SUP de nivel superior para su entorno.
1. En la cinta de opciones, seleccione **Configurar componentes del sitio**y, a continuación, seleccione Punto de actualización de **software**. O bien, haga clic con el botón secundario en el sitio y, a continuación, seleccione **Configurar el punto**de actualización de software de componentes del  >  **sitio**.
1. En la **pestaña Clasificaciones,** active la casilla Incluir controladores de Microsoft Surface y actualizaciones de **firmware.**

   ![Propiedades del componente de punto de actualización de software.](images/manage-surface-driver-updates-1.png)

1. Cuando se le pida el siguiente mensaje de advertencia, seleccione **Aceptar**.

   ![Configuration Manager.](images/manage-surface-driver-updates-2.png)

1. En la pestaña Productos, seleccione los productos que desea actualizar y, a continuación, seleccione **Aceptar**.

   La mayoría de los controladores pertenecen a los siguientes grupos de productos:

   - Windows 10 y versiones posteriores
   - Windows 10 y versiones posteriores actualizar & controladores de mantenimiento
   - Windows 10 Controladores de actualización de aniversario y mantenimiento posteriores
   - Windows 10 Actualización de aniversario y actualizaciones posteriores & controladores de mantenimiento
   - Windows 10 Creators Update y controladores de mantenimiento posteriores
   - Windows 10 Creators Update y actualizaciones posteriores & controladores de mantenimiento
   - Windows 10 Fall Creators Update y controladores de mantenimiento posteriores
   - Windows 10 Fall Creators Update y versiones posteriores & controladores de mantenimiento
   - Windows 10 Controladores de mantenimiento S y posteriores
   - Windows 10 Controladores de mantenimiento S versión 1709 y posteriores para pruebas
   - Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing

   > [!NOTE]
   > La mayoría de los controladores de Surface pertenecen a varios Windows 10 de productos. Es posible que no tenga que seleccionar todos los productos que se enumeran aquí. Para ayudar a reducir el número de productos que rellenan el Catálogo de actualizaciones, se recomienda seleccionar solo los productos que el entorno necesita para la sincronización.

## <a name="verifying-the-configuration"></a>Comprobación de la configuración

Para comprobar que el SUP está configurado correctamente, siga estos pasos:

1. Abra WsyncMgr.log y, a continuación, busque la siguiente entrada:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Si alguna de las siguientes entradas se registra en WsyncMgr.log, vuelva a comprobar el paso 4 de la sección anterior:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Abra WCM.log y, a continuación, busque una entrada similar a la siguiente:

   ![Configuración de WCM.log.](images/manage-surface-driver-updates-3.png)

   Esta entrada es un elemento XML que enumera todos los grupos de productos y la clasificación que el servidor SUP sincroniza actualmente. Por ejemplo, es posible que vea una entrada similar a la siguiente:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Si no encuentra los productos que seleccionó en el paso 6 de la sección anterior, compruebe si la configuración de SUP está guardada.

   También puedes esperar hasta que finalice la siguiente sincronización y, a continuación, comprobar si las actualizaciones de controladores y firmware de Surface aparecen en Actualizaciones de software en la consola de Configuration Manager. Por ejemplo, la consola puede mostrar la siguiente información.

   ![Todos los resultados de búsqueda de actualizaciones de software.](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>Sincronización manual

Si no desea esperar hasta la siguiente sincronización, siga estos pasos para iniciar una sincronización:

1. En la consola de Configuration Manager, vaya **a Software Library**  >  **Overview**  >  **Software Updates**All Software  >  **Updates**.
1. En la cinta de opciones, seleccione **Sincronizar actualizaciones de software**. O bien, haga clic con el botón secundario **en Todas las actualizaciones de software**y, a continuación, seleccione Sincronizar actualización de **software**.
1. Para supervisar el progreso de la sincronización, busque las siguientes entradas en WsyncMgr.log:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <a name="deploying-surface-firmware-and-driver-updates"></a>Implementación de actualizaciones de controladores y firmware de Surface

Puedes implementar las actualizaciones de controladores y firmware de Surface de la misma manera que implementas otras actualizaciones.

Para obtener más información acerca de la [implementación, vea System Center 2012 Configuration Manager–Part7: Software Updates (Deploy).](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)

## <a name="frequently-asked-questions-faq"></a>Preguntas frecuentes (FAQ)

**Después de seguir los pasos de este artículo, los controladores de Surface aún no están sincronizados. ¿Por qué?**

Si sincronizas desde un servidor Windows Server Update Services (WSUS) ascendente, en lugar de Microsoft Update, asegúrate de que el servidor WSUS ascendente esté configurado para admitir y sincronizar las actualizaciones de controladores de Surface. Todos los servidores descendentes están limitados a las actualizaciones que están presentes en la base de datos del servidor WSUS ascendente.

Hay más de 68 000 actualizaciones que se clasifican como controladores en WSUS. Para evitar que los controladores que no están relacionados con Surface se sincronicen con Configuration Manager, Microsoft filtra la sincronización de controladores en una lista de permitidos. Después de publicar e incorporar la nueva lista de permitidos en Configuration Manager, los nuevos controladores se agregan a la consola después de la siguiente sincronización. Microsoft pretende que los controladores de Surface se agregan a la lista de permitidos cada mes en alineación con las versiones de actualización mensuales para que estén disponibles para la sincronización con Configuration Manager.

Si el entorno de Configuration Manager está sin conexión, se importa una nueva lista de permitidos cada vez que importe actualizaciones de [mantenimiento](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) a Configuration Manager. También tendrá que importar un nuevo catálogo [WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contenga los controladores antes de que se muestren las actualizaciones en la consola de Configuration Manager. Dado que un entorno WSUS independiente contiene más controladores que un SUP de Configuration Manager, te recomendamos que establezcas un entorno de Configuration Manager que tenga funcionalidades en línea y que lo configures para sincronizar los controladores de Surface. Esto proporciona una exportación de WSUS más pequeña que se asemeja mucho al entorno sin conexión.

Si el entorno de Configuration Manager está en línea y puede detectar actualizaciones nuevas, recibirá actualizaciones de la lista automáticamente. Si no ve los controladores esperados, revise los archivos WCM.log y WsyncMgr.log para ver si hay algún error de sincronización.

**Mi entorno de Configuration Manager está sin conexión. ¿Puedo importar manualmente controladores de Surface a WSUS?**

No. Incluso si la actualización se importa a WSUS, la actualización no se importará en la consola de Configuration Manager para su implementación si no aparece en la lista de permitidos. Debe usar la Herramienta [de conexión de servicio para](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) importar actualizaciones de mantenimiento a Configuration Manager para actualizar la lista de permitidos.

**¿Qué métodos alternativos tengo para implementar actualizaciones de controladores y firmware de Surface?**

Para obtener información sobre cómo implementar actualizaciones de controladores y firmware de Surface a través de canales alternativos, consulta Administrar actualizaciones de [controladores y firmware de Surface.](manage-surface-driver-and-firmware-updates.md) Si quieres descargar el archivo .msi o .exe y, a continuación, implementar a través de los canales de implementación de software tradicionales, consulta [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## <a name="additional-information"></a>Información adicional

Para obtener más información acerca de las actualizaciones de controladores y firmware de Surface, consulta los artículos siguientes:

- [Administrar las actualizaciones de controladores y firmware de Surface](manage-surface-driver-and-firmware-updates.md)
- [Consideraciones para Surface y System Center Configuration Manager](considerations-for-surface-and-system-center-configuration-manager.md)

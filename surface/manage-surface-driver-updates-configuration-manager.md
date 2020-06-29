---
title: Administrar actualizaciones de controlador de superficie en Configuration Manager
description: En este artículo, se describen las opciones disponibles para administrar e implementar actualizaciones de firmware y controladores para dispositivos Surface.
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
ms.openlocfilehash: 1a9c8c64bd524de58696c73a28795b69cc70a7b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2020
ms.locfileid: "10835866"
---
# Administrar actualizaciones de controlador de superficie en Configuration Manager

## Resumen

A partir de [Microsoft System Center Configuration Manager versión 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), puede sincronizar e implementar actualizaciones de controladores y firmware de Microsoft Surface directamente a través del cliente de Configuration Manager. El proceso es similar al de implementar actualizaciones regulares. Sin embargo, para obtener las actualizaciones de los drivers de Surface en tu catálogo, necesitarás otras configuraciones adicionales.

## Requisitos previos

Para administrar las actualizaciones de los controladores de Surface, se deben cumplir los siguientes requisitos previos:

- Debe usar Configuration Manager versión 1710 o una versión posterior.
- Todos los puntos de actualización de software (SUPs) deben ejecutar Windows Server 2016 o una versión posterior. De lo contrario, el administrador de configuración ignora esta configuración y los controladores de superficie no se sincronizarán.

> [!NOTE]
> Si su entorno no cumple con los requisitos previos, consulte los [métodos alternativos](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) para implementar el controlador de superficie y las actualizaciones de firmware en la sección [preguntas más frecuentes](#frequently-asked-questions-faq) .

## Archivos de registro útiles

Los siguientes registros son especialmente útiles cuando se administran las actualizaciones de los controladores de Surface.

|Nombre de registro|Descripción|
|---|---|
|WCM. log|Registra detalles sobre la configuración del punto de actualización de software y las conexiones con el servidor WSUS para las categorías, clasificaciones e idiomas de las actualizaciones suscritas.|
|WsyncMgr. log|Registra detalles sobre el proceso de sincronización de las actualizaciones de software.|

Estos registros se encuentran en el servidor del sitio que administra el SUP o en el SUP si se instala directamente en un servidor de sitio.
Para obtener una lista completa de los registros de Configuration Manager, consulte [archivos de registro en System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).

## Habilitar la administración de actualizaciones del controlador de Surface

Para habilitar la administración de las actualizaciones del controlador de Surface en Configuration Manager, siga estos pasos:

1. En la consola del administrador de configuración, **Administration**vaya a la  >  **información general**de administración sitios de  >  **configuración del sitio**  >  **Sites**.
1. Seleccione el sitio que contiene el servidor SUP de nivel superior de su entorno.
1. En la cinta de opciones, seleccione **Configurar componentes del sitio**y, a continuación, seleccione **punto de actualización de software**. O bien, haga clic con el botón secundario en el sitio y seleccione **Configurar componentes de sitio**  >  **punto de actualización de software**.
1. En la pestaña **clasificaciones** , active la casilla **incluir actualizaciones de firmware y controladores de Surface de Microsoft** .

   ![Propiedades de componente de punto de actualización de software](images/manage-surface-driver-updates-1.png)

1. Cuando se le solicite en el siguiente mensaje de advertencia, seleccione **Aceptar**.

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. En la pestaña productos, seleccione los productos que desea actualizar y, a continuación, seleccione **Aceptar**.

   La mayoría de los drivers pertenecen a los siguientes grupos de productos:

   - Controladores de la versión de Windows 10 y versiones posteriores
   - Windows 10 y actualización posterior & controladores de servicio
   - Actualización de aniversario de Windows 10 y drivers de mantenimiento posterior
   - Actualización de aniversario de Windows 10 y actualización posterior & controladores de servicio
   - Windows 10 Creators Update y versiones posteriores de servicios de mantenimiento
   - Windows 10 Creators Update y posterior actualiza & controladores de servicio
   - Controladores de mantenimiento de Windows 10 Fall Creators Update y posteriores
   - Windows 10 Fall Creators Update y actualización posterior & drivers de mantenimiento
   - Controladores de mantenimiento de Windows 10 S y versiones posteriores
   - Windows 10 S versión 1709 y posteriores que atienden los drivers para pruebas
   - Windows 10 S versión 1709 y posteriores actualizar & de mantenimiento de controladores para pruebas

   > [!NOTE]
   > La mayoría de los drivers de Surface pertenecen a varios grupos de producto de Windows 10. Es posible que no tenga que seleccionar todos los productos que se muestran aquí. Para ayudar a reducir el número de productos que rellenan el catálogo de actualizaciones, le recomendamos que seleccione solo los productos que necesita su entorno para la sincronización.

## Comprobar la configuración

Para comprobar que el SUP está configurado correctamente, siga estos pasos:

1. Abra WsyncMgr. log y busque la siguiente entrada:

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   Si se ha registrado una de las siguientes entradas en WsyncMgr. log, volver a comprobar el paso 4 de la sección anterior:

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. Abra WCM. log y busque una entrada similar a la siguiente:

   ![Configuración de WCM. log](images/manage-surface-driver-updates-3.png)

   Esta entrada es un elemento XML en el que se muestra una lista de todos los grupos de productos y la clasificación sincronizada actualmente por el servidor SUP. Por ejemplo, es posible que vea una entrada similar a la siguiente:

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   Si no encuentra los productos que seleccionó en el paso 6 de la sección anterior, verifique si la configuración de SUP está guardada.

   También puede esperar hasta que finalice la sincronización siguiente y, después, comprobar si las actualizaciones del controlador de superficie y del firmware se enumeran en actualizaciones de software en la consola de Configuration Manager. Por ejemplo, la consola podría mostrar la siguiente información:

   ![Todos los resultados de búsqueda de actualizaciones de software](images/manage-surface-driver-updates-4.png)

## Sincronización manual

Si no desea esperar hasta la siguiente sincronización, siga estos pasos para iniciar una sincronización:

1. En la consola del administrador de configuración, vaya al software de Descripción general de la **biblioteca de software**para  >  **Overview**  >  **Actualizar**  >  **todas las actualizaciones de software**.
1. En la cinta de opciones, seleccione **sincronizar actualizaciones de software**. O bien, haga clic con el botón secundario en **todas las actualizaciones de software**y seleccione **sincronizar actualización de software**.
1. Busque las siguientes entradas en WsyncMgr. log para supervisar el progreso de la sincronización:

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

## Implementación de actualizaciones de controladores y firmware de superficie

Puede implementar el firmware de superficie y las actualizaciones de drivers de la misma manera en que implementa otras actualizaciones.

Para obtener más información sobre la implementación, consulte [System Center 2012 Configuration Manager-Part7: actualizaciones de software (implementación)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).

## Preguntas frecuentes (FAQ)

**Después de seguir los pasos descritos en este artículo, los drivers de Surface aún no se sincronizan. ¿Por qué?**

Si sincroniza desde un servidor Windows Server Update Services (WSUS) que precede en la cadena, en lugar de Microsoft Update, asegúrese de que el servidor WSUS que precede en la cadena está configurado para admitir y sincronizar las actualizaciones del controlador de la superficie. Todos los servidores descendentes se limitan a las actualizaciones que están presentes en la base de datos del servidor WSUS que precede en la cadena.

Hay más de 68.000 actualizaciones que se clasifican como controladores en WSUS. Para evitar que los controladores no relacionados con la superficie se sincronicen con Configuration Manager, Microsoft filtra la sincronización de controlador contra una lista de permitidos. Después de publicar e incorporar la nueva lista de permitidos en Configuration Manager, los nuevos drivers se agregarán a la consola después de la siguiente sincronización. Microsoft tiene como objetivo obtener los impulsores de superficie agregados a la lista de permitidos cada mes, en línea, con el martes de parches para que estén disponibles para la sincronización con Configuration Manager.

Si su entorno de Configuration Manager está desconectado, se importará una nueva lista de permitidos cada vez que importe [actualizaciones de servicio](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) a Configuration Manager. También tendrá que importar un [nuevo catálogo de WSUS](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) que contenga los drivers antes de que se muestren las actualizaciones en la consola de Configuration Manager. Como un entorno WSUS independiente contiene más drivers que un SUP de Configuration Manager, le recomendamos que establezca un entorno de Configuration Manager que tenga capacidades en línea y que lo configure para sincronizar los impulsores de la superficie. Esto proporciona una exportación de WSUS más pequeña, muy similar al entorno sin conexión.

Si su entorno de Configuration Manager está en línea y puede detectar nuevas actualizaciones, recibirá actualizaciones en la lista automáticamente. Si no ve los drivers esperados, revise el archivo WCM. log y WsyncMgr. log en busca de errores de sincronización.

**Mi entorno de Configuration Manager está desconectado, ¿puedo importar manualmente drivers de Surface en WSUS?**

No. Incluso si la actualización se importa a WSUS, la actualización no se importará a la consola de Configuration Manager para su implementación si no aparece en la lista de permitidos. Debe usar la [herramienta de conexión de servicio](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) para importar las actualizaciones de servicio a Configuration Manager para actualizar la lista de permitidos.

**¿Qué métodos alternativos tengo para implementar actualizaciones de drivers y firmware de Surface?**

Para obtener información sobre cómo implementar actualizaciones de drivers y firmware de Surface a través de canales alternativos, consulte [Manage Surface Driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates). Si desea descargar el archivo. msi o. exe y, a continuación, implementar a través de los canales de implementación de software tradicionales, consulte [mantener actualizado el firmware de la superficie con Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).

## Información adicional

Para obtener más información sobre el controlador de superficie y las actualizaciones de firmware, consulte los artículos siguientes:

- [Descargar el firmware y los controladores más recientes para dispositivos Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)
- [Administrar las actualizaciones de controladores y firmware de Surface](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)
- [Consideraciones para Surface y System Center Configuration Manager](https://docs.microsoft.com/surface/considerations-for-surface-and-system-center-configuration-manager)

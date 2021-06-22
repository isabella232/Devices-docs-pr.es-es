---
title: Garantía y servicio de autoservicio de Surface
description: Microsoft 365 Es posible que los clientes empresariales puedan usar el nodo beta De garantía y servicio de Autoservicio de Surface en el Centro de administración de Microsoft para crear y administrar pedidos de servicio.
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh
manager: laurawi
audience: itpro
ms.openlocfilehash: a6021a58c85ac6ee4c039959dcde9bab632ea1bb
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614151"
---
# <a name="surface-self-serve-warranty-and-service"></a>Garantía y servicio de autoservicio de Surface

Microsoft 365 Es posible que los clientes empresariales puedan usar el nodo Garantía y servicio de autoservicio de Surface en el Centro de Administración de Microsoft 365 para crear y administrar pedidos de servicio. Esta nueva característica, disponible como un programa beta, permite a los administradores globales designar permisos a personas dentro de su empresa responsables de admitir reclamaciones de garantía y servicio, entre las que se incluyen:

- Upload números de serie para los dispositivos que requieren servicio.
- Agregue varias direcciones de envío.
- Cree un único pedido de servicio para uno o varios dispositivos y cubiertas de tipos.
- Consulte Estado del pedido de servicio en tiempo real.
- Enviar y recibir envíos anticipados Exchange envíos masivos si los dispositivos están cubiertos por una garantía extendida o Exchange avanzada se incluyeron como parte de la compra del dispositivo.

## <a name="join-beta-program"></a>Unirse al programa beta

Póngase en contacto con el Administrador de cuentas de éxito del cliente de Microsoft o con el Administrador de éxito del cliente para obtener más información sobre la experiencia y cómo participar en el programa beta.

## <a name="role-based-permissions"></a>Permisos basados en roles

La garantía y el servicio de Surface Self-Serve permite a un administrador global de Microsoft 365 conceder diferentes permisos para crear y administrar pedidos de servicio mediante la asignación de roles a los usuarios.

Cuando se agrega Microsoft 365 inquilino al programa beta, se conceden permisos adicionales a los siguientes roles de administrador:

| Rol                  | Permisos                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Administrador global          | Ver solicitudes de reparación<br>Crear/administrar solicitudes de reparación<br>Agregar/Editar/Eliminar envío a direcciones<br>Crear/administrar usuarios y sus roles |
| Administrador de soporte técnico de servicio | Ver solicitudes de reparación<br>Crear/administrar solicitudes de reparación                                                                               |
| Administrador de facturación         | Ver solicitudes de reparación<br>Crear/administrar solicitudes de reparación<br>Agregar/Editar/Eliminar envío a direcciones(es)                                        |

Para obtener más información acerca de los usuarios y los permisos, vea [Microsoft Admin Center Overview](/microsoft-365/admin/admin-overview/about-the-admin-center).

## <a name="create-and-manage-a-service-order"></a>Crear y administrar un pedido de servicio

1. Vaya al Centro de Administración de Microsoft 365 en [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e inicie sesión con los permisos de administrador adecuados. Para obtener más información, [vea Quién tiene permisos de administrador en mi empresa.](/microsoft-365/business-video/admin-center-overview#who-has-admin-permissions-in-my-business)
2. Ve a **Compatibilidad con las**  >  **reparaciones de dispositivos Surface** y selecciona Crear solicitud de **reparación.** (Si no ve esta opción de reparación, no tiene permiso para acceder a esta página).

    > [!div class="mx-imgBorder"]
    > ![Iniciar solicitud de reparación de autoservicio](images/self-serve-fig1.png)

3. Puede crear una solicitud de reparación para uno o varios dispositivos. Seleccione **Enviar 1 dispositivo** a la vez **o** Enviar varios dispositivos para usar un archivo .csv para cargar varios números de serie y seleccione **Siguiente**.

    > [!NOTE]
    > **Para varios dispositivos:**
    >
    > - En la página Centro de administración, descargue la plantilla CSV de ejemplo, agregue la información necesaria y guárdela en la unidad local.
    > - Seleccione **Upload csv para**las entradas masivas, seleccione el archivo .csv guardado en la unidad local y seleccione **Abrir.**
    > - Se cargarán los números de serie del dispositivo. Seleccione **Siguiente** para continuar con la creación de la reparación.

4. En **Enviar reemplazo a**, seleccione una dirección de envío. O bien,  **seleccione Agregar nueva dirección**.

    > [!NOTE]
    >
    > - Los permisos permiten a determinados administradores agregar nuevos envíos a las direcciones. Si tiene permisos, > puede agregar nuevas direcciones. Escribe la información necesaria y, a continuación,  **selecciona Guardar**.
    > - El formulario valida automáticamente la información de direcciones y es posible que se corrija para realizar cambios si el sistema postal local no reconoce la dirección. La dirección de correo electrónico se usa para enviar notificaciones y comunicaciones para la solicitud de reparación.

    > [!div class="mx-imgBorder"]
    > ![
      Agregar nueva dirección
    ](images/self-serve-fig2a.png)

5. Agrega el dispositivo especificando el número de serie del dispositivo en el bloque de texto. Para obtener más información, consulta [Números de serie del dispositivo](https://support.microsoft.com/help/4036293/surface-find-the-serial-number-on-surface). Si el número de serie es válido, aparecerá una imagen y la información del producto, incluida la fecha de garantía y el número de modelo. Seleccione **Agregar dispositivo si** la información es correcta.

    > [!div class="mx-imgBorder"]
    > ![Agregar dispositivos](images/self-serve-fig2.png)

6. Repita los pasos del 1 al 2 para agregar varios dispositivos (hasta 20 en total) a la solicitud.
7. En el menú desplegable, seleccione el tipo de problema que mejor describe el problema y seleccione **Siguiente.**

    > [!div class="mx-imgBorder"]
    > ![Seleccionar categoría de problema](images/self-serve-fig3.png)

8. Revise su pedido. Si alguna información es incorrecta, elija **Atrás para** corregir errores.
9. Acepte los términos de las condiciones.
10. Si el resumen de la solicitud es correcto, **seleccione Enviar la solicitud**.

    > [!div class="mx-imgBorder"]
    > ![Enviar solicitud de reparación de autoservicio](images/self-serve-fig4.png)

Cuando se muestra la página principal, puede ver la solicitud de servicio en la lista de resumen y recibir un correo electrónico de confirmación.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="why-am-i-getting-error-code-400-generic-client-service-error-401-unauthorized-service-error-or-error-403-forbidden-service-error"></a>¿Por qué obtengo el código de error 400 "Error de servicio de cliente genérico", 401 "Error de servicio no autorizado" o error 403 "Error de servicio prohibido"?

Puede haber un problema con la cuenta Microsoft 365 o el usuario no tiene permisos para acceder al contenido. Para obtener ayuda, Microsoft 365 a su administrador global.

### <a name="when-i-enter-my-shipping-address-and-i-get-an-error-message-that-no-shipping-offers-are-available"></a>¿Al especificar mi dirección de envío y recibir un mensaje de error que indica que no hay ofertas de envío disponibles?

La versión beta Self-Serve y de servicio de Surface tiene una disponibilidad limitada en este momento. Las ofertas solo estarán disponibles si la dirección se encuentra en uno de los siguientes países:

Austria, Bahrein, Bélgica, Bulgaria, Croacia, Chipre, República Checa, Dinamarca, Estonia, Finlandia, Francia, Alemania, Grecia, Hungría, Irlanda, Italia, Kuwait, Letonia, Lituania, Luxemburgo, Malta, Países Bajos, Omán, Polonia, Portugal, Rumania, Eslovaquia, Eslovenia, Sudáfrica, España, Suecia y el Reino Unido (excluyendo Irlanda del Norte).

### <a name="where-can-i-see-orders-that-i-have-placed-through-the-microsoft-365-portal"></a>¿Dónde puedo ver los pedidos que he realizado a través Microsoft 365 portal?

Vaya a [Centro de administración de Microsoft 365: solicitudes de servicio](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs) e inicie sesión con sus Microsoft 365 de usuario.

Los pedidos creados a través del servicio de soporte al cliente de Microsoft no estarán visibles en el módulo Self-Serve garantía y administración de servicios.

### <a name="why-am-i-unable-to-add-edit-or-delete-a-shipping-address"></a>¿Por qué no puedo agregar, editar o eliminar una dirección de envío?

La capacidad de agregar, editar o eliminar una dirección de envío solo la puede hacer su administrador global o de facturación Microsoft 365. Para obtener ayuda, puede comunicarse con ellos.  

### <a name="how-can-i-contact-microsoft-support-for-the-surface-self-serve-warranty-and-service-beta"></a>¿Cómo puedo ponerse en contacto con el soporte técnico de Microsoft para la versión beta Self-Serve garantía y servicio de Surface?

Puedes ponerse en contacto con el soporte técnico directamente a través del módulo de soporte técnico de Surface en el Centro de administración de Microsoft.

1. Inicie sesión en el Centro de administración de Microsoft con sus Microsoft 365 credenciales.
2. Selecciona **Admitir**  >  **reparaciones de dispositivos Surface > ¿Necesitas ayuda?** y describe el problema.
3. Si los resultados no ayudan, seleccione **Póngase en**contacto con el soporte técnico y escriba una descripción del problema. Confirme su número de contacto y dirección de correo electrónico, seleccione el método de contacto que prefiera y, a continuación, seleccione **Póngase en contacto conmigo**.

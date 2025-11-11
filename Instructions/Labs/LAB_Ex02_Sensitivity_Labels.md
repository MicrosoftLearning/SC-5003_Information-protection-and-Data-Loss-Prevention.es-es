---
lab:
  task: Create and publish a sensitivity label
  exercise: Exercise 2 - Create and publish a sensitivity label
---

# Tareas de aptitudes

La tarea consiste en crear y publicar etiquetas de confidencialidad dentro de la organización que clasifiquen y protejan los datos confidenciales según su nivel de confidencialidad y los controles de acceso necesarios.

**Tareas:**

1. Habilitación de la compatibilidad con etiquetas de confidencialidad  
1. Crear un grupo de etiquetas  
1. Crear una etiqueta secundaria  
1. Publicar etiquetas  
1. Configurar el etiquetado automático  

## Tarea 1: Habilitación de la compatibilidad con las etiquetas de confidencialidad para archivos en SharePoint y OneDrive

En esta tarea, habilitarás la coautoría para etiquetas de confidencialidad, que también permite etiquetas de confidencialidad para archivos en SharePoint y OneDrive.

1. Abre **Microsoft Edge** y ve a `https://purview.microsoft.com`.

1. En el panel de navegación izquierdo, selecciona **Configuración** > **Information Protection**.

1. En **Configuración de Information Protection**, asegúrate de que estás en la pestaña **Coautoría de archivos con etiquetas de confidencialidad**.

1. Activa la casilla **Activar la coautoría de archivos con etiquetas de confidencialidad**.

1. Selecciona **Aplicar** en la parte inferior de la pantalla.

Has habilitado correctamente la compatibilidad con las etiquetas de confidencialidad para archivos de SharePoint y OneDrive.

<!--

## Task 2 – Create sensitivity labels

In this task, your HR department has requested a sensitivity label to apply to HR employee documents. You'll create a sensitivity label for internal documents and a sublabel for the HR department.

1. Open **Microsoft Edge** and navigate to **`https://purview.microsoft.com`**. Log into Microsoft Purview as the user you selected as the **Compliance Administrator**.

1. In the Microsoft Purview portal, select **Solutions** from the left sidebar, then select **Information Protection**.

1. On the **Microsoft Information Protection** page, on the left sidebar, select **Sensitivity labels**.

1. On the **Sensitivity labels** page select **+ Create a label**.

1. The **New sensitivity label** configuration will start. On the **Provide basic details for this label**, enter:

    - **Name**: `Internal`
    - **Display name**: `Internal`
    - **Description for users**: `Internal sensitivity label.`
    - **Description for admins**: `Internal sensitivity label for Contoso.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files** and **Emails**. If the checkbox for **Meetings** is selected, make sure it's deselected.

   > [!NOTE]
   > When **Meetings** is selected, you can't create a sublabel for the sensitivity label.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select **Next**.

1. On the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

1. On the **Sensitivity labels** page, find the newly created **Internal** sensitivity label. Select the vertical ellipsis (**...**) next to it, then select **+ Create sublabel** from the dropdown menu.

    ![Screenshot showing the Action menu to create a sublabel for a sensitivity label.](../Media/create-sublabel-button.png)

1. The **New sensitivity label** wizard will start. On the **Provide basic details for this label** page enter:

   - **Name**: `Employee data (HR)`
   - **Display name**: `Employee data (HR)`
   - **Description for users**: `This HR label is the default label for all specified documents in the HR Department.`
   - **Description for admins**: `This label was created with input from the Head of HR. Contact the HR department for any changes to the label settings.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files**, **Emails**, and **Meetings**.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select the **Control access** option, then select **Next**.

1. On the **Access control** page, select **Configure access control settings**.

1. Configure the encryption settings with these options:

   - **Assign permissions now or let users decide?**: Assign permissions now
   - **User access to content expires**: Never
   - **Allow offline access**: Only for a number of days
   - **Users have offline access to the content for this many days**: 15
   - Select the **Assign permissions** link. On the **Assign permissions** flyout panel, select the **+ Add any authenticated users**, then select **Save** to apply this setting.

1. On the **Access control** page, select **Next**.

1. On the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Don't create a policy yet**, then select **Done**.

You have successfully created a sensitivity label for your organizations internal policies and a sensitivity sublabel for the Human Resources (HR) department.

## Task 3 – Publish sensitivity labels

You will now publish the Internal and HR sensitivity label so that the published sensitivity labels will be available for the HR users to apply to their HR documents.

1. In **Microsoft Edge**, the Microsoft Purview portal tab should still be open. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. On the **Sensitivity labels** page select **Publish labels**.

1. The publish sensitivity labels configuration will start.

1. On the **Choose sensitivity labels to publish** page, select the **Choose sensitivity labels to publish** link.

1. On the **Sensitivity labels to publish** flyout panel, select the **Internal** and **Internal/Employee Data (HR)** checkboxes, then select **Add** at the bottom of the flyout panel.

1. Back on the **Choose sensitivity labels to publish** page, select **Next**.

1. On the **Assign admin units** page, select **Next**

1. On the **Publish to users and groups** page, select **Next**.

1. On the **Policy settings** page, select **Next**.

1. On the **Default settings for documents** page, select **Next**.

1. On the **Default settings for emails** page, select **Next**.

1. On the **Default settings for meetings and calendar events** page, select **Next**.

1. On the **Default settings for Fabric and Power BI content** page, select **Next**.

1. On the **Name your policy** page, enter:

   - **Name**: `Internal HR employee data`
   - **Enter a description for your sensitivity label policy**: `This HR label is to be applied to internal HR employee data.`

1. Select **Next**.

1. On the **Review and finish** page, select **Submit**.

1. On the **New policy created**, select **Done** to finish publishing your label policy.

You have successfully published the Internal and HR sensitivity labels. Note that it can take up to 24 hours for changes to replicate to all users and services.

## Task 4 – Create a client-side auto labeling policy

In this task, you'll create a client-side auto-labeling policy. Client-side auto-labels apply automatically to files and emails based on their content, ensuring that sensitive information is classified and protected before it leaves the user's device.

1. You should still be on the **Sensitivity labels** page in the Microsoft Purview portal. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. On the **Sensitivity labels** page, find the newly created **Internal** sensitivity label. Select the vertical ellipsis (**...**) next to it, then select **+ Create sublabel** from the dropdown menu.

1. The **New sensitivity label** configuration will start. On the **Provide basic details for this label** page, enter:

   - **Name**: `Confidential Research Data`
   - **Display name**: `Confidential Research Data`
   - **Description for users**: `This document or email contains sensitive research or development data that is proprietary to the organization.`
   - **Description for admins**: `This label is auto-applied to documents and emails containing information related to research, prototypes, or internal projects.`

1. Select **Next**.

1. On the **Define the scope for this label** page, select **Items**, then select **Files**, **Emails**, and **Meetings**.

1. Select **Next**.

1. On the **Choose protection settings for labeled items** page, select **Apply content marking**, then select **Next**.

1. Select **Next**.

1. On the **Content marking** page, select the toggle to enable content marking.

1. If the checkbox for **Add a footer** is selected, deselect it, and select the checkbox for **Add a watermark**, then select **Customize text**.

1. In the **Customize watermark text** flyout pane, enter `Confidential - R&D Data` as **Watermark text**. Increase the **Font size** to `40`, then select **Save** at the bottom of the panel.

1. Back on the **Content marking** page, if other content marking options are enabled, disable them to ensure **Add a watermark** is the only option enabled.

1. Select **Next**.

1. On the **Auto-labeling for files and emails** page, set the **Auto-labeling for files and emails** to enabled.

1. In the **Detect content that matches these conditions** section, select **+ Add condition** > **Content contains**.

1. In **Content contains** section select the **Add** > **Trainable classifiers**.

1. In the **Trainable classifiers** flyout panel, add these trainable classifiers:

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

1. Select **Add** at the bottom of the panel to add these trainable classifiers.

1. Back on the **Auto-labeling for files and emails** page, select **Next**.

1. On the **Define protection settings for groups and sites** page, select **Next**.

1. On the **Auto-labeling for schematized data assets (preview)** page, select **Next**.

1. On the **Review your settings and finish** page, select **Create label**.

1. On the **Your sensitivity label was created** page, select **Publish label to users' apps**, then select **Done**.

1. On the **Publish label** flyout panel, select **Create new label policy**.

1. On the **Choose sensitivity labels to publish** page, select the **Choose sensitivity labels to publish** link.

1. Select the parent **Internal** label and the **Confidential Research Data** label that was just created, then select **Add**.

1. Back on the **Choose sensitivity labels to publish** page, select **Next**.

1. On the **Assign admin units** page, select **Next**.

1. On the **Publish to users and groups** page, select **Next**.

1. On the **Policy settings** page, select the checkbox for **Users must provide a justification to remove a label or lower its classification**, then select **Next**.

1. On the **Default settings for documents** page, select **Next** until you reach the **Name your policy** page.

1. On the **Name your policy** page, enter:

   - **Name**: `R&D Confidential Data Policy`
   - **Enter a description for your sensitivity label policy**: `Automatically applies labels to source code, project documents, and development files to protect sensitive R&D data.`

1. Select **Next**.

1. On the **Review and finish** page, select **Submit**.

1. On the **New policy created** page, select **Done**.

You have successfully created a client-side auto-labeling policy that will automatically apply the **Confidential Research Data** label to files and emails containing research and development data. It might take up to 24 hours for the policy to take full effect.

## Task 5 – Create a service-side auto labeling policy

In this task, you'll create a service-side auto-labeling policy. Service-side auto-labels are applied by cloud services like SharePoint, Exchange, and OneDrive after content is uploaded or received, ensuring that sensitive data is protected even if users don't manually classify it.

1. You should still be on the **Sensitivity labels** page in the Microsoft Purview portal. If not, navigate to **`https://purview.microsoft.com`** > **Solutions** > **Information Protection** > **Sensitivity labels**.

1. Expand the **Internal** label, then select the `Confidential Research Data` sublabel you created in a previous task.

1. In the **Confidential Research Data** flyout panel, you'll see the properties for the auto-label you created in a previous task. In this panel, select **Create auto-labeling policy**.

    ![Screenshot showing the option to create an auto-labeling policy.](../Media/create-auto-labeling-policy.png)

1. On the **Name your policy** page, enter:

   - **Name**: `R&D Confidential Data Container Policy`
   - **Enter a description for your sensitivity label policy**: `Automatically applies the Confidential Research Data label to content in SharePoint, Exchange, and OneDrive.`

1. Select **Next**.

1. On the **Assign admin units** page, select **Next**.

1. On the **Choose locations where you want to apply the label** page, leave **Exchange email**, **SharePoint sites**, and **OneDrive accounts** selected, then select **Next**.

1. On the **Set up common or advanced rules** page, leave **Common rules** selected, then select **Next**.

1. On the **Define rules for content in all locations** page, edit the **Confidential Research Data rule**.

    ![Screenshot where to edit the rule for a service-side auto-labeling policy.](../Media/auto-apply-labels-edit-rule.png)

1. In the **New rule** flyout panel, under **Conditions** > **Content contains** select the dropdown for **Add**, then select **Trainable classifiers**.

1. In the **Trainable classifiers** flyout panel, add these trainable classifiers:

   - `Source code`
   - `Project documents`
   - `Software Product Development Files`

   This ensures consistent protection between client-side and service-side labels.

1. Select **Add** at the bottom of the panel to add these trainable classifiers.

1. Back on the **Define rules for content in all locations** page, select **Next**.

1. On the **Choose a label to auto-apply**, leave the **Internal/Confidential Research Data** chosen, then select **Next**.

1. On the **Decide if you want to test out the policy now or later** page, select **Run policy in simulation mode**, and select the checkbox for **Automatically turn on policy if not modified after 7 days in simulation**, then select **Next**.

1. On the **Review and finish** page, select **Create policy**.

1. On the **Your auto-labeling policy was created** page, select **Done**.

You have successfully created a service-side auto-labeling policy that will automatically apply the **Confidential Research Data** label to content stored or shared in SharePoint, Exchange, and OneDrive. It might take up to 24 hours for the policy to take effect.

-->
## Tarea 2: Crear un grupo de etiquetas

En esta tarea, creará un grupo de etiquetas para organizar las etiquetas de confidencialidad internas. Los grupos de etiquetas actúan como contenedores para etiquetas relacionadas, como clasificaciones de unidades de negocio o departamentos.

1. Todavía debe iniciar sesión en Microsoft Purview portal como Administrador de cumplimiento.

1. En **Microsoft Edge**, ve a `https://purview.microsoft.com`.

1. En el Portal de Microsoft Purview, selecciona **Soluciones** en la barra lateral izquierda y, después, selecciona **Information Protection**.

1. En la página **Microsoft Information Protection**, en la barra lateral izquierda, y selecciona **Tipos de información confidencial**.

1. En la página **Etiquetas de confidencialidad**, seleccione **+Crear** > **Grupo de etiquetas**.

1. Se iniciará la configuración de **Nuevo grupo de etiquetas**. En **Proporcionar detalles básicos para este grupo de etiquetas**, escriba:

    - **Nombre**: `Internal`
    - **Nombre para mostrar**: `Internal`
    - **Descripción para los usuarios**: `Internal sensitivity label.`
    - **Descripción para los administradores**: `Internal sensitivity label group for Contoso.`

1. Seleccione **Siguiente**.

1. En la página **Revisar la configuración y finalizar**, seleccione **Crear grupo de etiquetas**.

1. En la página **Su grupo de etiquetas se creó correctamente**, seleccione **No crear una etiqueta aún** y, a continuación, seleccione **Listo**.

Ha creado un grupo de etiquetas para su uso interno. Este grupo le ayuda a administrar etiquetas relacionadas para departamentos o categorías de datos específicos.

## Tarea 3: Crear una etiqueta secundaria

Ahora que ha creado un grupo de etiquetas, agregará una etiqueta secundaria para el contenido relacionado con RR HH. Esta etiqueta aplica cifrado y marcas de contenido para proteger los datos de RR. HH. frente al acceso no autorizado.

1. En la página **Etiquetas de confidencialidad**, busque el grupo de etiquetas de confidencialidad **Interno**. Seleccione los puntos suspensivos verticales (**...**) situados junto a él y, después, seleccione **+Crear etiqueta en grupo** en el menú desplegable.

    ![Recorte de pantalla que muestra el menú Acción para crear una etiqueta en el grupo para una etiqueta de confidencialidad.](../Media/create-label-in-group.png)

1. Se iniciará el Asistente para **Nueva etiqueta de confidencialidad**. En la página **Proporcionar detalles básicos de esta etiqueta**, escribe:

   - **Nombre**: `Employee data (HR)`
   - **Nombre para mostrar**: `Employee data (HR)`
   - **Descripción para los usuarios**: `This HR label is the default label for all specified documents in the HR Department.`
   - **Descripción para los administradores**: `This label is created in consultation with Ms. Jones (Head of the HR department). Contact her if you need to change the label settings.`

1. Seleccione **Siguiente**.

1. En la página **Definir el ámbito de esta etiqueta**, selecciona **Archivos** y **Correos electrónicos**. Si la casilla **Reuniones** está activada, asegúrate de desactivarla.

1. Seleccione **Siguiente**.

1. En la página **Elegir la configuración de protección para los elementos etiquetados**, selecciona la opción **Control de acceso** y **Aplicar marcas de contenido** y, después, selecciona **Siguiente**.

1. En la página **Control de acceso**, selecciona **Configurar configuración de control de acceso**.

1. Configura la configuración de cifrado con estas opciones:

   - **¿Asignar ya permisos o permitir que los usuarios decidan?**: Asignar permisos ahora
   - **Acceso del usuario al contenido expira**: Nunca.
   - **Permitir acceso sin conexión**: Solo durante un número de días
   - **Los usuarios tienen acceso sin conexión al contenido durante estos días**: 15
   - Selecciona el vínculo **Asignar permisos**. En el panel flotante **Asignar permisos**, seleccione **+ Agregar usuarios autenticados** y, a continuación, seleccione **Guardar** para aplicar esta configuración.

1. En la página **Control de acceso**, selecciona **Siguiente**.

1. En la página **Marcado de contenido**, selecciona el control de alternancia para habilitar el **Marcado de contenido**.

1. Para cada uno de los siguientes tipos de marcado, activa la casilla y, después, selecciona el icono de edición para escribir el texto:

   |Tipo de marcado|Texto|
   |:---|:---|
   |Agregar una marca de agua|`INTERNAL USE ONLY`|
   |Agregar un encabezado|`Internal Document`|
   |Agregar un pie de página|`Contoso Confidential`|

1. Seleccione **Siguiente**.

1. En la página **Etiquetado automático de archivos y correos electrónicos**, selecciona **Siguiente**.

1. En la página **Definir la configuración de protección para grupos y sitios**, selecciona **Siguiente**.

1. En la página **Revisar la configuración y finalizar**, selecciona **Crear etiqueta**.

1. En la página **Se creó la etiqueta de confidencialidad**, selecciona **No crear una directiva aún** y, a continuación, selecciona **Listo**.

Ha creado una etiqueta secundaria dentro del grupo de etiquetas Interno. La etiqueta aplica cifrado y marcas de contenido a los documentos de RR. HH., lo que facilita la identificación y protección de los datos confidenciales mediante la directiva.

## Tarea 4: Publicar etiquetas

A continuación, publicará la etiqueta de RR. HH. del grupo de etiquetas Interno para que los usuarios del departamento de RR. HH. puedan aplicarla a sus documentos.

1. Todavía debe iniciar sesión en Microsoft Purview portal como Administrador de cumplimiento.

1. En **Microsoft Edge**, debe estar abierta la pestaña del Portal de Microsoft Purview. Si no es así, ve a **`https://purview.microsoft.com`** > **Soluciones** > **Information Protection** > **Etiquetas de confidencialidad**.

1. En la página **Etiquetas de confidencialidad**, selecciona **Publicar etiquetas**.

1. Se iniciará la configuración de publicar etiquetas de confidencialidad.

1. En la página **Elegir etiquetas de confidencialidad para publicar**, selecciona el vínculo **Elegir etiquetas de confidencialidad para publicar**.

1. En el panel flotante **Etiquetas de confidencialidad para publicar**, active la  casilla **Datos internos o de empleados (RR. HH)** y, a continuación, seleccione **Agregar** en la parte inferior de la página flotante.

1. Vuelve a la página **Elegir etiquetas de confidencialidad para publicar** y selecciona **Siguiente**.

1. En la página **Asignar unidades de administración**, selecciona **Siguiente**

1. En la página **Publicar en usuarios y grupos**, selecciona **Siguiente**.

1. En la página **Configuración de directivas** selecciona **Siguiente**.

1. En **Configuración predeterminada de documentos**, selecciona **Siguiente**.

1. En **Configuración predeterminada para correos electrónicos**, selecciona **Siguiente**.

1. En **Configuración predeterminada para reuniones y eventos de calendario**, selecciona **Siguiente**.

1. En la página **Configuración predeterminada del contenido de Fabric y Power BI**, selecciona **Siguiente**.

1. En la página **Asignar nombre a la directiva** escribe:

   - **Nombre**: `Internal HR employee data`

   - **Escribir una descripción para la directiva de etiqueta de confidencialidad**: `This HR label is to be applied to internal HR employee data.`

1. Selecciona **Siguiente**.

1. En la página **Revisar y finalizar**, selecciona **Enviar**.

1. En **Nueva directiva creada**, selecciona **Listo** para finalizar la publicación de la directiva de etiquetas.

Ha publicado el grupo de etiquetas Interno y su etiqueta de RR. HH. para que los usuarios puedan aplicarla a los documentos de RR. HH. La directiva puede tardar hasta 24 horas en propagarse entre los servicios.

## Tarea 5: Configurar el etiquetado automático

Ahora creará una etiqueta secundaria para los datos financieros y la configurará para que se aplique automáticamente al contenido que contiene identificadores financieros, como tarjetas de crédito o números de ruta bancaria.

1. Todavía debe iniciar sesión en Microsoft Purview portal como Administrador de cumplimiento.

1. En **Microsoft Edge**, vaya a `https://purview.microsoft.com` e inicie sesión en Microsoft Purview portal como Administrador de cumplimiento.

1. En el portal de Microsoft Purview, seleccione **Soluciones** > **Information Protection** > **Etiquetas de confidencialidad**.

1. En la página **Etiquetas de confidencialidad**, busca la etiqueta de confidencialidad **interna**. Seleccione los puntos suspensivos verticales (**...**) y seleccione **+Crear etiqueta en grupo** en el menú desplegable.

1. En la página **Proporcionar detalles básicos de esta etiqueta**, escribe:

   |Detalles|Texto|
   |---|---|
   |**Nombre**|`Financial Data`|
   |**Nombre para mostrar**|`Financial Data`|
   |**Descripción para los usuarios**|`This content contains financial data that must be labeled and protected.`|
   |**Descripción para los administradores**|`This label is used for content that includes sensitive financial identifiers.`|

1. Seleccione **Siguiente**.

1. En la página **Definir el ámbito de esta etiqueta**, selecciona **Archivos** y **Correos electrónicos**. Si la casilla **Reuniones** está activada, asegúrate de desactivarla.

1. Seleccione **Siguiente**.

1. En la página **Elegir la configuración de protección para los elementos etiquetados**, selecciona **Siguiente**.

1. En la página **Etiquetado automático de archivos y correos electrónicos**, activa **Etiquetado automático para archivos y correos electrónicos**.

1. En la sección **Detectar contenido que coincida con estas condiciones**, selecciona **+ Agregar condición** > **Contenido incluye**.

1. En la sección **El contenido contiene**, seleccione **Agregar** > **Tipos de información confidencial**.

1. En la página flotante **Tipos de información confidencial**, busca y selecciona estos tipos de información confidencial:

   - `Credit Card Number`
   - `ABA Routing Number`
   - `SWIFT Code`

1. Seleccione **Agregar**.

1. Vuelve a la página **Etiquetado automático de archivos y correos electrónicos** y selecciona **Siguiente**.

1. En la página **Definir la configuración de protección para grupos y sitios**, selecciona **Siguiente**.

1. En la página **Revisar la configuración y finalizar**, selecciona **Crear etiqueta**.

1. En la página **Se creó la etiqueta de confidencialidad**, selecciona **Aplicar automáticamente la etiqueta al contenido confidencial** y, después, selecciona **Listo**.

1. En la página flotante **Crear directiva de etiquetado automático**, selecciona **Revisar directiva**.

1. En la página **Nombre de la directiva de etiquetado automático**, deja el valor predeterminado y selecciona **Siguiente**.

1. En la página **Elegir una etiqueta para aplicar automáticamente**, revisa para asegurarte de que está seleccionada la etiqueta _Datos internos o financieros_ y, después, selecciona **Siguiente**.

1. En la página **Asignar unidades de administración**, selecciona **Siguiente**.

1. En la página **Elegir ubicaciones en las que deseas aplicar la etiqueta**, selecciona las opciones para:

   - Correo electrónico de Exchange
   - Sitios de SharePoint
   - Cuentas de OneDrive

1. Seleccione **Siguiente**.

1. En la página **Configurar reglas comunes o avanzadas**, deja activado el valor predeterminado **Reglas comunes** y selecciona **Siguiente**.

1. En la página **Definir reglas para contenido en todas las ubicaciones**, expande las reglas de _Reglas de datos financieros_ para asegurarte de que se definen las reglas esperadas y selecciona **Siguiente**.

1. En la página **Configuración para correos electrónicos**, selecciona **Siguiente**.

1. En la página **Decidir si deseas probar la directiva ahora o más adelante**, selecciona **Ejecutar directiva en modo de simulación** y activa la casilla **Activar automáticamente la directiva si no se modifica después de 7 días en la simulación**.

1. Seleccione **Siguiente**.

1. En la página **Revisar y finalizar**, selecciona **Crear directiva**.

1. En la página **Se creó la directiva de etiquetado automático**, selecciona **Listo**.

Ha organizado etiquetas en un grupo, las ha publicado para los usuarios y ha habilitado el etiquetado automático para que el contenido confidencial esté protegido sin depender de los usuarios.

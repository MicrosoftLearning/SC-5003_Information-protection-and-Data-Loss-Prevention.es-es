---
lab:
  task: Create a data loss prevention (DLP) policy
  exercise: Exercise 4 - Create a data loss prevention (DLP) policy
---

# Tareas de aptitudes

La tarea consiste en desarrollar y aplicar una directiva personalizada de prevención de pérdida de datos (DLP) adaptada para proteger los datos confidenciales del cliente de su organización, al tiempo que garantiza el cumplimiento de las normativas de protección de datos.

- **Crear una directiva DLP personalizada** en modo de prueba para supervisar los datos sin aplicación.
- **Definir una regla DLP avanzada** dirigida a información confidencial específica.
- **Activar la directiva DLP** para aplicar las protecciones y el cumplimiento activamente.

**Objetivo**: Desarrolle e implemente una directiva personalizada de prevención de pérdida de datos (DLP) para proteger los datos confidenciales del cliente y garantizar el cumplimiento normativo. Comenzará creando una directiva DLP en modo de prueba para la supervisión inicial, procederá a diseñar una regla avanzada dirigida a tipos específicos de información confidencial y, por último, activará la directiva para aplicar la protección de datos en las comunicaciones por correo electrónico, SharePoint, OneDrive y Teams.

## Tarea 1: Crear una directiva de prevención de pérdida de datos (DLP) personalizada

1. Vaya al Portal de cumplimiento de Microsoft Purview.
1. Expanda **Prevención de pérdida de datos** y, a continuación, seleccione **Directivas**.
1. En la página **Directivas**, seleccione **+ Crear directiva**.
1. En el asistente para directivas DLP, en **Iniciar con una plantilla o crear una directiva personalizada**, seleccione:
   - Categorías: **Custom** (personalizada)
   - Normativas: **Directiva personalizada**
1. Seleccione **Siguiente**.
1. En la página **Introducir el nombre de la directiva DLP** escriba:
   - **Nombre**: `Customer interaction protection policy`
   - **Descripción**: `This DLP policy protects customer data integrity and confidentiality in the Customer Service department by preventing unauthorized access and disclosure.`
1. Seleccione **Siguiente** hasta llegar a la página **Elegir dónde aplicar la directiva**.
1. En la página **Elegir dónde aplicar la directiva**, seleccione solo:
   - **Correo electrónico de Exchange**
   - **Sitios de SharePoint**
   - **Cuentas de OneDrive**
   - **Chat y mensajes de canales de Teams**
1. Seleccione **Siguiente**.
1. En la página **Definir la configuración de directiva**, seleccione **Crear o personalizar reglas DLP avanzadas** y, a continuación, seleccione **Siguiente**.
1. En **Personalizar reglas avanzadas de DLP**, seleccione **+ Crear regla**.
1. En la página **Crear regla**:
   - En el campo **Nombre** escriba `Customer data`.
   - En **Condiciones**, seleccione **+ Agregar condición** > **El contenido incluye**.
   - En **El contenido incluye**, seleccione **Agregar** > **Tipos de información confidencial**.
   - En la página **Clasificadores entrenables** de la derecha, seleccione los clasificadores para `Customer Complaints` y `Customer Files` y, a continuación, seleccione **Agregar** en la parte inferior de la página para agregar estos clasificadores entrenados previamente.
   > [!tip] Use la barra de búsqueda para encontrar fácilmente clasificadores que se pueden entrenar.
   - De nuevo en la página **Crear regla** en **El contenido contiene** seleccione **+ Agregar condición** > **El contenido se comparte desde Microsoft365**.
   - En **El contenido se comparte desde Microsoft365**, seleccione **con personas de fuera de mi organización** en la lista desplegable.
   - En **Acciones**, seleccione **+ Agregar una acción** > **Restringir o cifrar el contenido en ubicaciones de Microsoft 365**.
   - En **Restringir o cifrar el contenido en ubicaciones de Microsoft 365**, asegúrese de que está seleccionado el botón de radio **Bloquear solo a personas de fuera de la organización**.
   - En **Notificaciones de usuario**, cambie la casilla de notificaciones a **Activado** y, a continuación, active la casilla **Notificar a los usuarios del servicio Office 365 con una sugerencia de directiva**.
   - En **Invalidaciones de usuario** active la casilla **Permitir invalidaciones de los servicios de Microsoft 365**
   - En **Informes de incidentes**, establezca **Use este nivel de gravedad en alertas de administrador e informes:** en **Medio**.
   - En la parte inferior de **Crear regla** seleccione **Guardar**.
1. De nuevo en la página **Personalizar reglas DLP avanzadas**, seleccione **Siguiente**.
1. En la **página Modo de directiva**, seleccione **Ejecutar la directiva en modo de prueba** y asegúrese de que la opción **Mostrar sugerencias de directiva en modo de simulación** y, a continuación, seleccione **Siguiente**.
1. En la página **Revisar y finalizar**, seleccione **Enviar**.
1. En la página **Crear directiva nueva**, seleccione **Listo**.

## Tarea 2: Modificar una directiva DLP

1. En la página **Directivas**, seleccione la casilla situada a la izquierda de **Directiva de protección de la interacción del cliente** recién creada y, a continuación, seleccione **Editar directiva** en la parte superior de la página.
1. Una vez en el asistente para la creación de directivas DLP, seleccione **Siguiente** hasta llegar a la página **Modo de directiva** y, a continuación, seleccione **Activar la directiva inmediatamente** para aplicar la directiva DLP.
1. Seleccione **Siguiente** para revisar la directiva DLP y, después, seleccione **Enviar** una vez que haya revisado los cambios.
1. En la página **Directiva actualizada**, seleccione **Listo**.

Ahora ha creado correctamente una directiva DLP para proteger los datos confidenciales del cliente.

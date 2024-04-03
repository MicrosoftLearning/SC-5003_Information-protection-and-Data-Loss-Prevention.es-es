---
lab:
  task: Create and publish a sensitivity label
  exercise: Exercise 2 - Create and publish a sensitivity label
---

# Tareas de aptitudes

La tarea consiste en crear y publicar etiquetas de confidencialidad dentro de la organización, que clasifica y protege los datos confidenciales según su nivel de confidencialidad y los controles de acceso necesarios.

- **Crear una etiqueta de confidencialidad** para clasificar datos.
- **Crear una subetiqueta** bajo la etiqueta primaria para agrupar datos.
- **Crear una directiva de etiqueta** para establecer reglas e instrucciones para administrar etiquetas de confidencialidad dentro de la organización.

**Objetivo**: Crear y publicar etiquetas de confidencialidad para mejorar la protección de datos del departamento de RR. HH. La tarea consiste en configurar una etiqueta primaria denominada _Internos_, con una subetiqueta denominada _Datos de los empleados (RR. HH.)_.

## Tarea 1: crear una etiqueta de confidencialidad

1. Vaya al Portal de cumplimiento de Microsoft Purview.
1. Expanda **Information Protection** y, después, seleccione **Etiquetas**.
1. En **Etiquetas**, seleccione **+ Crear una etiqueta**.
1. En **Proporcione los detalles básicos de esta etiqueta**, escriba la siguiente información:

    - **Nombre**: `Internal`
    - **Nombre para mostrar**: `Internal`
    - **Descripción para los usuarios**: `Internal sensitivity label.`
    - **Descripción para los administradores**: `Internal sensitivity label for Contoso.`

1. Seleccione **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta**, seleccione **Elementos**, seleccione **Archivos** y **Correos electrónicos** y, a continuación, seleccione **Siguiente**.
1. En la página **Elija la configuración de protección para los tipos de elementos seleccionados**, seleccione **Siguiente**.
1. Seleccione **Siguiente**, acepte los valores predeterminados hasta que llegue a la página **Revisar la configuración y finalizar** y, a continuación, seleccione **Crear etiqueta**.
1. En la página **Se creó la etiqueta de confidencialidad**, seleccione **No crear una directiva aún** y, a continuación, seleccione **Listo**.

## Tarea 2: crear una etiqueta de subetiqueta

1. En la página Information Protection, resalte (sin seleccionar) la etiqueta **Internos** recién creada y seleccione la vertical **...** ![imagen del menú de puntos verticales](../Media/SensitivityLabelDotMenu.png)
1. Seleccione **+ Crear subetiqueta** en el menú.
1. En **Proporcione los detalles básicos de esta etiqueta**, escriba la siguiente información:

   - **Nombre**: `Employee data (HR)`
   - **Nombre para mostrar**: `Employee data (HR)`
   - **Descripción para los usuarios**: `This label is the default label for all documents in the HR Department.`
   - **Descripción para los administradores**: `This label is created in consultation with the Director of HR.`
1. Seleccione **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta**, seleccione **Elementos**, seleccione **Archivos** y **Correos electrónicos** y, a continuación, seleccione **Siguiente**.
1. En **Elija la configuración de protección para los tipos de elementos que seleccionó**, active la casilla **Control del acceso** y, a continuación, seleccione **Siguiente**.
1. En la página **Control de acceso**:
   - Asegúrese de que esté seleccionado el botón de radio **Establecer la configuración del control de acceso**.
   - En **¿Asignar ya permisos o permitir que los usuarios decidan?** seleccione **Asignar permisos ahora**.
   - En **El acceso del usuario al contenido expira** seleccione **Nunca**.
   - En **Permitir acceso sin conexión**, seleccione **Solo durante un número de días**.
   - En el campo **Los usuarios tienen acceso sin conexión al contenido durante estos días**, escriba 14.
   - En **Asignar permisos a usuarios y grupos específicos**, seleccione el botón **Asignar permisos**.
1. En la página **Asignar permisos**, seleccione **+ Agregar cualquier usuario autenticado** y, a continuación, seleccione **Guardar**.
1. De nuevo en la página **Control de acceso**, seleccione **Siguiente**.
1. Seleccione **Siguiente**, acepte los valores predeterminados hasta que llegue a la página **Revisar la configuración y finalizar** y seleccione **Crear etiqueta**.
1. En la página **Se creó la etiqueta de confidencialidad**, seleccione **No crear una directiva aún** y, a continuación, seleccione **Listo**.

## Tarea 3: publicar una etiqueta de confidencialidad

1. En la página **Etiquetas**, active las casillas situadas junto a la recién creada **Internos** y la subetiqueta **Datos de los empleados (RR. HH.)**.
1. En la página **Elegir etiquetas de confidencialidad para publicar**, asegúrese de que las etiquetas Internos y Datos de los empleados (RR. HH.) se muestren en **Etiquetas de confidencialidad para publicar** y, a continuación, seleccione **Siguiente**.
1. Seleccione **Siguiente** hasta que llegue a la página **Configuración de directiva**.
1. En la página **Configuración de directiva**, active la casilla **Los usuarios deben proporcionar una justificación para quitar una etiqueta o reducir su clasificación**.
1. Seleccione **Siguiente** hasta que llegue a la página **Nombrar directiva**
1. En la página **Nombrar directiva**, escriba la información siguiente:

   - **Nombre**: `Internal HR employee data`
   - **Escriba una descripción para la directiva de etiqueta de confidencialidad**: `This HR label is to be applied to internal HR employee data.`

1. Seleccione **Siguiente**.
1. En la página **Revisar y finalizar**, seleccione **Enviar**.
1. En la página **Nueva directiva creada**, seleccione **Listo**.

Ya creó correctamente una etiqueta de confidencialidad para clasificar los datos de los empleados para el departamento de RR. HH.

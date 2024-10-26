---
lab:
  task: Create a custom sensitive information type
  exercise: Exercise 1 - Create a custom sensitive information type
---

# Tarea de aptitudes

La tarea consiste en crear y publicar etiquetas de confidencialidad dentro de la organización, que clasifica y protege los datos confidenciales según su nivel de confidencialidad y los controles de acceso necesarios.

**Tarea:**

- Creación de tipos de información confidencial personalizados

## Tarea: Creación de tipos de información confidencial personalizados

En esta tarea, crearás un nuevo tipo de información confidencial personalizada que reconoce el patrón de identificadores de empleado cerca de las palabras clave "Employee" y "ID".

1. En **Microsoft Edge**, ve a **`https://purview.microsoft.com`** e inicia sesión en el Portal de Microsoft Purview como el usuario que estableciste como **Administrador de cumplimiento** en una tarea anterior.

1. En la barra lateral izquierda, selecciona **Soluciones** y, después, selecciona **Information Protection**.

1. En la barra lateral izquierda, expande **Clasificadores** y, después, selecciona **Tipos de información confidencial**.

1. En la página **Tipos de información confidencial**, selecciona **+ Crear tipo de información confidencial** para iniciar la configuración del tipo de información confidencial.

1. En la página **Nombre de tipo de información confidencial**, escribe:

    - **Nombre**: `Contoso Employee IDs`
    - **Descripción**: `Pattern for Contoso employee IDs.`

1. Selecciona **Siguiente**.

1. En la página **Definir patrones para este tipo de información confidencial**, selecciona **Crear patrón**.

1. En el panel de control flotante **Nuevo patrón**, selecciona **+ Agregar elemento principal** > **Expresión regular**.

1. En el panel de control flotante **+ Agregar una expresión regular** a la derecha, escribe:

    - **Id.**: `Contoso IDs`
    - **Expresión regular**: `[A-Z]{3}[0-9]{6}`
    - Selecciona el botón de radio de *Coincidencia de cadena*

1. Selecciona **Listo** en la parte inferior del panel de control flotante.

1. De nuevo en el panel de control flotante **Nuevo patrón**, en **Elementos auxiliares**, selecciona el menú desplegable **+ Agregar elementos auxiliares o grupo de elementos** y selecciona **Lista de palabras clave**.

1. En el panel de control flotante **Agregar una lista de palabras clave** a la derecha, escribe:

    - **Id.**: `Employee ID keywords`
    - **No distinguir entre mayúsculas y minúsculas:**

       ```text
       Employee
       ID
       ```

    - Selección del botón de radio para *Coincidencia de palaras*

1. Selecciona **Listo** en la parte inferior del panel de control flotante.

1. De nuevo en el panel de control flotante **Nuevo patrón** en **Proximidad de caracteres**, reduce el valor **Detectar elementos principales Y auxiliares** a `100` caracteres.

1. Selecciona el botón **Crear** en la parte inferior del panel de control flotante.

1. De nuevo en la página **Definir patrones para este tipo de información confidencial**, selecciona **Siguiente**.

1. En la página **Elegir el nivel de confianza recomendado para mostrar en las directivas de cumplimiento**, usa el valor predeterminado y selecciona **Siguiente**.

1. En la página **Revisar configuración y finalizar**, revisa la configuración y selecciona **Crear**. Cuando se haya creado correctamente, selecciona **Listo**.

Has creado correctamente un nuevo tipo de información confidencial para identificar identificadores de empleado en el patrón de tres caracteres en mayúsculas, seis números y las palabras clave "Employee" o "ID" dentro de un intervalo de 100 caracteres.

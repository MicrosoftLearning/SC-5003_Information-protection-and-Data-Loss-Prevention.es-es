---
lab:
  task: Create and assign an auto-labeling policy
  exercise: Exercise 3 - Create and assign an auto-labeling policy
---

# Tareas de aptitudes

La tarea consiste en crear y publicar etiquetas de confidencialidad dentro de la organización, que clasifica y protege los datos confidenciales según su nivel de confidencialidad y los controles de acceso necesarios.

- **Crear una etiqueta de confidencialidad** para clasificar datos.
- **Configurar la etiqueta para el etiquetado automático** de archivos y correos electrónicos.
- **Configurar una directiva de etiquetado automático** para clasificar automáticamente los datos en SharePoint y OneDrive.
- **Publicar la directiva de etiquetado automático** para implementar la etiqueta en toda la organización, automatizando la clasificación para mejorar la seguridad y el cumplimiento.

**Objetivo**: Cree y publique una directiva de etiquetado automático para el departamento de Finanzas. La tarea consiste en configurar una etiqueta de confidencialidad que aplique automáticamente etiquetas a los archivos y correos electrónicos en función de los datos financieros. También debe crear una directiva de etiquetado automático que aplique automáticamente esas etiquetas al contenido en SharePoint y OneDrive.

## Tarea 1: Cree una etiqueta de confidencialidad

1. Vaya al Portal de cumplimiento de Microsoft Purview.
1. Expanda **Information Protection** y, después, seleccione **Etiquetas**.
1. En **Etiquetas**, seleccione **+ Crear una etiqueta**.
1. En **Proporcione los detalles básicos de esta etiqueta**, escriba la siguiente información:

    - **Nombre**: `Protected Financial Records`
    - **Nombre para mostrar**: `Protected Financial Records`
    - **Descripción para los usuarios**: `Use for documents with sensitive financial data.`
    - **Descripción para los administradores**: `Applies encryption and access controls to financial documents.`

1. Seleccione **Siguiente**.
1. En la página **Definir el ámbito de esta etiqueta**, seleccione **Elementos**, seleccione **Archivos** y **Correos electrónicos** y, a continuación, seleccione **Siguiente**.
1. En la página **Elija la configuración de protección para los tipos de elementos seleccionados**, seleccione **Siguiente**.
1. En el **Etiquetado automático de archivos y correos electrónicos**:
   - Establezca el botón de alternancia para habilitar el **Etiquetado automático de archivos y correos electrónicos**
   - En **Detectar contenido que coincida con estas condiciones**, seleccione **+ Agregar condición** > **El contenido incluye**.
   - En **El contenido incluye**, seleccione **Agregar** > **Tipos de información confidencial**.
   - En la página **Tipos de información confidencial**, busque y agregue el tipo de información confidencial para `Credit Card Number`, `U.S. Bank Account Number` y `ABA Routing Number`. **Agregar** para agregar los tres tipos de información confidencial y, después, seleccione **Guardar**.
   - En **Cuando el contenido coincida con estas condiciones**, seleccione **Aplicar automáticamente la etiqueta**.
   - Deje en blanco el mensaje opcional **Mostrar este mensaje a los usuarios cuando se aplique la etiqueta**.
1. Seleccione **Siguiente**, acepte los valores predeterminados hasta que llegue a la página **Revisar la configuración y finalizar** y seleccione **Crear etiqueta**.
1. En la página **Se creó la etiqueta de confidencialidad**, seleccione **No crear una directiva aún** y, a continuación, seleccione **Listo**.

## Tarea 2: Cree una directiva de etiquetado automático

1. En la página **Etiquetas**, active la casilla situada junto a la etiqueta **Registros financieros protegidos** recién creado y seleccione **Crear directiva de etiquetado automático**.
1. En la página **Nombrar directiva de etiquetado automático**, escriba la información siguiente:

   - **Nombre**: `Finance Auto-Label Policy`
   - **Escriba una descripción para la directiva de etiqueta de confidencialidad**: `Automates the labeling of financial documents.`
1. Seleccione **Siguiente** hasta llegar a la página **Definir reglas para el contenido de todas las ubicaciones**.
1. En **Definir reglas para el contenido de todas las ubicaciones**, seleccione **Nueva regla**.
1. En la página **Nueva regla**:
   - Escriba `Financial data` como el **Nombre**.
   - En **Condiciones**, seleccione **+ Agregar condición** > **El contenido incluye**.
   - En **El contenido incluye**, seleccione **Agregar** > **Tipo de información confidencial**.
   - En la página **Tipos de información confidencial**, busque y agregue el tipo de información confidencial para `Credit Card Number`, `U.S. Bank Account Number` y `ABA Routing Number`. **Agregar** para agregar los tres tipos de información confidencial y, después, seleccione **Guardar**.
1. Seleccione **Siguiente** hasta llegar a la página **Decidir si desea probar la directiva ahora o después**.
1. En la página **Decidir si desea probar la directiva ahora o después**, seleccione **Ejecutar directiva en modo de simulación** y, después, seleccione **Siguiente**.
1. En la página **Revisar y finalizar**, seleccione **Crear directiva**.
1. En la página **Se creó la directiva de etiquetado automático**, seleccione **Listo**.

Acaba de crear correctamente una etiqueta de confidencialidad para clasificar los datos financieros para el departamento de Finanzas.

---
lab:
  task: Create a custom sensitive information type
  exercise: Exercise 1 - Create a custom sensitive information type
---

## Inquilinos de WWL: términos de uso

Si se le proporciona un inquilino porque está realizando un curso dirigido por un instructor, tenga en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

# Tareas de aptitudes

La tarea consiste en crear un tipo de información confidencial (SIT) personalizado que cumpla los criterios necesarios:

- **Patrón regex personalizado para el identificador de empleado**: Incluya un patrón regex que identifique la configuración del identificador de empleado único de la organización, que consta de 9 caracteres: 3 dígitos, un guion, seguido de 5 letras (por ejemplo, 123-abcde).
- **Lista de palabras clave asociada a identificadores de empleado**: Incorpore una lista de palabras clave que normalmente están asociadas a identificadores de empleado para mejorar la precisión de la detección.

## Tarea 1: Cree un tipo de información confidencial

1. Vaya al Portal de cumplimiento de Microsoft Purview.
1. Expanda **Clasificación de datos** y seleccione **Clasificadores**.
1. Seleccione **Tipos de información confidencial** y, después, seleccione **+ Crear tipo de información confidencial**.
1. En la página **Nombrar el tipo de información confidencial**, asigne al tipo de información confidencial un **Nombre** y una **Descripción** significativos y, a continuación, seleccione **Siguiente**.
1. En la página **Definir patrones para este tipo de información confidencial**, seleccione **Crear patrón**.
1. En la página **Nuevo patrón**, seleccione **+ Agregar elemento principal** > **Expresión regular**.
1. En la **página Agregar una expresión regular**, asigne a la expresión regular un nombre descriptivo para **Id.** y escriba `\d{3}-[a-zA-Z]{5}` en el campo **Expresión regular** para admitir el requisito de la organización. Seleccione **Listo** una vez completado.
1. De nuevo en la página **Nuevo patrón**, en **Elementos auxiliares**, seleccione **+ Agregar elementos auxiliares o grupo de elementos** > **Lista de palabras clave**.
1. En la página **Agregar una lista de palabras clave**, asigne un **id.** significativo a la lista de palabras clave. En **Grupo de palabras clave n.º 1**, en **No distingue mayúsculas de minúsculas**, escriba:
   - `Employee ID`
   - `Staff number`
   - `Work ID`
1. Seleccione **Listo** una vez completado.
1. De nuevo en la página **Nuevo patrón**, seleccione **Crear**.
1. Seleccione **Siguiente** en la página **Definir patrones para este tipo de información confidencial**.
1. En la página **Elegir el nivel de confianza recomendado para mostrar en las directivas de cumplimiento**, deje la selección predeterminada y, a continuación, seleccione **Siguiente**.
1. Revise la configuración y seleccione **Crear**.
1. En la página **Se ha creado el tipo de información confidencial**, seleccione **Listo**.

Ahora ha creado correctamente un tipo de información confidencial (SIT) personalizado para mejorar la seguridad y la administración de los números de identificación de empleado únicos de su empresa.

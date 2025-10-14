---
lab:
  task: Create a data loss prevention (DLP) policy
  exercise: Exercise 3 - Create a data loss prevention (DLP) policy
---

# Tareas de aptitudes

**Tareas:**

1. Creación de una directiva DLP en modo de simulación
1. Modificación de una directiva DLP
1. Creación de una directiva DLP en PowerShell
1. Activación de una directiva en modo de simulación

## Tarea 1: Creación de una directiva DLP en modo de simulación

En este ejercicio, crearás una directiva de prevención de pérdida de datos (DLP) para proteger la información confidencial de ser compartida por los usuarios. La directiva DLP que crees informará a los usuarios si quieren compartir contenido que contenga información de tarjeta de crédito y les permitirá proporcionar una justificación para enviar esta información. La directiva se implementará en modo de simulación porque aún no deseas que la acción de bloqueo afecte a los usuarios.

1. En **Microsoft Edge**, ve a **`https://purview.microsoft.com`** e inicia sesión en el Portal de Microsoft Purview como el usuario que seleccionaste para tener derechos de **administrador de cumplimiento**.

1. Selecciona **Soluciones** en la barra lateral izquierda y, después, selecciona **Prevención de pérdida de datos**.

1. En la barra lateral izquierda, selecciona **Directivas**.

1. En la página **Directivas**, selecciona **+ Crear directiva** para iniciar la configuración para crear una nueva directiva de prevención de pérdida de datos.

1. En la página **Iniciar con una plantilla o crear una directiva personalizada**, selecciona **Personalizado** como categoría y, después, selecciona **Directiva personalizada** en **Reglamentos**.

1. Selecciona **Siguiente**.

1. En la página **Introducir el nombre de la directiva DLP** escribe:

   - **Nombre**: `Credit Card DLP Policy`
   - **Descripción**: `Protect credit card numbers from being shared`

1. Selecciona **Siguiente**.

1. En la página **Asignar unidades de administración**, selecciona **Siguiente**.

1. En la página **Elegir ubicaciones para aplicar la directiva**, habilita la ubicación solo para **Mensajes de chat y canal de Teams**. Si se seleccionan otras ubicaciones, anula la selección.

1. Selecciona **Siguiente**.

1. En la página **Definir la configuración de directiva**, selecciona **Crear o personalizar reglas DLP avanzadas** y, a continuación, selecciona **Siguiente**.

1. En **Personalizar reglas avanzadas de DLP**, selecciona **+ Crear regla**.

1. En la página de control flotante **Crear regla**, escribe `Credit card information` como nombre en el campo **Nombre**.

1. En **Condiciones**, selecciona **+ Agregar condición** y, después, selecciona **Contenido incluye**.

1. En la área nueva **Contenido incluye**, selecciona **Agregar** y, después, selecciona **Tipos de información confidencial**.

1. En la página **Tipos de información confidencial**, selecciona **Número de tarjeta de crédito** y, después, selecciona **Agregar**.

1. Selecciona **+ Agregar condición** y, después, selecciona **Contenido se comparte en Microsoft 365**.

1. En la nueva sección **Contenido se comparte desde Microsoft 365**, selecciona la opción **solo con personas dentro de mi organización**.

1. En **Acciones**, selecciona **+ Agregar una acción** y, después, selecciona **Restringir el acceso o cifrar el contenido en ubicaciones de Microsoft 365**.

1. En la nueva área **Restringir el acceso o cifrar el contenido en ubicaciones de Microsoft 365**, selecciona **Bloquear a todos.**

1. En **Notificaciones de usuario**, **activa** la opción **Usar notificaciones para informar a los usuarios y ayudar a educarlos sobre el uso adecuado de la información confidencial.** A continuación, activa la casilla **Notificar a los usuarios en el servicio de Office 365 con una sugerencia de directiva**.

1. En **Invalidaciones de usuario**, activa la casilla **Permitir que los usuarios invaliden restricciones de directivas de Fabric (incluido Power BI), Exchange, SharePoint, OneDrive y Teams.**

1. Activa la casilla **Requerir una justificación comercial para invalidar**.

1. En **Informes de incidentes**, en el elemento desplegable **Usar este nivel de gravedad en alertas de administrador e informes**, selecciona **Bajo**.

1. En la parte inferior del panel de control flotante **Crear regla**, selecciona **Guardar**.

1. Vuelve a la página **Personalizar reglas DLP avanzadas** y selecciona **Siguiente**.

1. En la página **Modo de directiva**, selecciona **Ejecutar la directiva en modo de simulación** y activa la casilla **Mostrar sugerencias de directiva mientras se está en modo de simulación**.

1. Selecciona **Siguiente**.

1. En la página **Revisar y finalizar**, revisa la configuración y selecciona **Enviar**.

1. En la página **Nueva directiva creada**, selecciona **Listo**.

Ahora has creado una directiva DLP que busca números de tarjeta de crédito en chats y canales de Microsoft Teams, lo que permite a los usuarios proporcionar una justificación comercial para invalidar la directiva.

## Tarea 2: Modificación de una directiva DLP

En esta tarea, modificarás la directiva DLP existente creada en la tarea anterior para que también examine los correos electrónicos para obtener información de la tarjeta de crédito. Esta modificación garantiza que los datos confidenciales están protegidos en más canales de comunicación.

1. Todavía debes iniciar sesión en Microsoft 365 como el usuario que seleccionaste para ser el **administrador de cumplimiento**.

1. Deberías encontrarte en la página **Directivas** de Microsoft Purview. Si no es así, abra **Microsoft Edge** y ve a `https://purview.microsoft.com`. Selecciona **Soluciones** > **Prevención de pérdida de datos** > **Directivas**.

1. En la página **Directivas**, activa la casilla de la **Directiva DLP de tarjeta de crédito** creada recientemente y, después, selecciona **Editar directiva** para abrir la configuración de la directiva.

1. En la página **Asignar nombre a la directiva DLP**, selecciona **Siguiente**.

1. En la página **Asignar unidades de administración**, selecciona **Siguiente**.

1. En la página **Elegir ubicaciones para aplicar la directiva**, activa la casilla **Correo electrónico de Exchange** para agregar esta ubicación a la directiva DLP.

1. Selecciona **Siguiente** hasta llegar a la página **Revisar y finalizar**.

1. Selecciona **Enviar** en la página **Revisar y finalizar** para aplicar el cambio realizado en la directiva.

1. Una vez actualizada la directiva, selecciona **Listo** en la página **Directiva actualizada**.

Has modificado correctamente la directiva DLP para incluir el examen de correo electrónico, lo que mejora la protección de la información confidencial.

## Tarea 3: Creación de una directiva DLP en PowerShell

En esta tarea, usarás PowerShell para crear una directiva DLP para proteger los identificadores de empleado de Contoso y evitar que se compartan a través de Exchange. Esta directiva notificará a los usuarios que intentan compartir esta información confidencial y bloquearán el correo electrónico si contiene identificadores de empleado.

1. En el escritorio, abre una ventana de PowerShell con privilegios elevados haciendo clic con el botón derecho en el botón Windows de la barra de tareas y selecciona **Terminal (Administrador)**.

1. Ejecuta el cmdlet **Install Module** en la ventana de terminal para instalar la versión más reciente del módulo **PowerShell de Exchange Online**:

    ```powershell
    Install-Module ExchangeOnlineManagement
    ```

1. Confirma el cuadro de diálogo de seguridad de repositorio no de confianza con **Y** para Sí y presiona **Entrar**.  Este proceso puede tardar un tiempo en finalizar.

1. Ejecuta el cmdlet **Connect-IPPSSession** para conectarte a Security & Compliance PowerShell:

   ```powershell
   Connect-IPPSSession
   ```

1. Inicia sesión como el usuario que seleccionaste como **administrador de cumplimiento** en la ventana emergente **Iniciar sesión en su cuenta**.

1. Ejecuta el cmdlet **New-DlpCompliancePolicy** para crear una directiva DLP que examine todos los buzones de Exchange:

   ```powershell
   New-DlpCompliancePolicy -Name "EmployeeID DLP Policy" -Comment "This policy blocks sharing of Employee IDs" -ExchangeLocation All
   ```

1. Ejecuta el cmdlet **New-DlpComplianceRule** para agregar una regla DLP a la directiva DLP que creaste en el paso anterior:

   ```powershell
   New-DlpComplianceRule -Name "EmployeeID DLP rule" -Policy "EmployeeID DLP Policy" -BlockAccess $true -ContentContainsSensitiveInformation @{Name="Contoso Employee IDs"}
   ```

1. Ejecuta el cmdlet **Get-DLPComplianceRule** para revisar la **Regla DLP employeeID**:

   ```powershell
   Get-DLPComplianceRule -Identity "EmployeeID DLP rule"
   ```

Has creado correctamente una directiva DLP mediante PowerShell que examina los identificadores de empleado de Contoso en Exchange.

## Tarea 4: Activación de una directiva en modo de simulación

En esta tarea, activarás la **directiva DLP de tarjeta de crédito** que creaste en modo de simulación para que aplique sus acciones de protección.

1. Todavía debes iniciar sesión en Microsoft 365 como el usuario que seleccionaste como **administrador de cumplimiento**.

1. En **Microsoft Edge**, ve a Directivas DLP; para ello, ve a `https://purview.microsoft.com` > **Soluciones** > **Prevención de pérdida de datos** y selecciona **Directivas** en la barra lateral izquierda.

1. En la página **Directivas**, activa la casilla **Directiva DLP de tarjeta de crédito** y selecciona **Editar directiva** para abrir la configuración de la directiva.

1. Selecciona **Siguiente** hasta llegar a la página **Modo de directiva** y, después, selecciona **Activar la directiva inmediatamente**.

1. En **Revisar y finalizar**, selecciona **Enviar**.

1. En la página **Directiva actualizada**, selecciona **Listo**.

Has activado correctamente la directiva DLP, asegurándote de que los intentos de compartir la información de la tarjeta de crédito están bloqueados y requieren una justificación comercial.

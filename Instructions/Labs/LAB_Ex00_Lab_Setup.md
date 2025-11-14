---
lab:
  task: Prepare your environment for administration
  exercise: Exercise 0 - Prepare your environment for administration
---

## Inquilinos de WWL: términos de uso

Si se te proporciona un inquilino porque estás realizando un curso dirigido por un instructor, ten en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no es apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

# Configuración del laboratorio: Preparación del entorno para la administración

En este laboratorio, configurarás y prepararás el entorno para las tareas de administración. Activarás las características necesarias, configurarás los permisos administrativos y garantizarás la configuración adecuada de los elementos clave.

**Tareas:**

- Habilitación de la auditoría en el Portal de Microsoft Purview
- Asignarás roles de cumplimiento
- Explorarás el portal de cumplimiento de Microsoft Purview

## Tarea: Habilitación de la auditoría en el Portal de Microsoft Purview

En esta tarea, habilitarás la auditoría en el Portal de Microsoft Purview para supervisar las actividades del portal.

1. Inicie sesión en la máquina virtual Client 1 (SC-401-CL1) con la cuenta**Administrador**.

1. Abre Microsoft Edge.

1. En**Microsoft Edge**, vaya a`https://purview.microsoft.com` e inicie sesión como**Administrador MOD**,`admin@WWLxZZZZZZ.onmicrosoft.com` (donde ZZZZZZ es el prefijo de inquilino único proporcionado por el proveedor de hospedaje del laboratorio). La contraseña de administrador te la debería haber proporcionado tu proveedor de servicios de hospedaje de laboratorio.

1. En Microsoft Edge, ve al Portal de Microsoft Purview,`https://purview.microsoft.com`, e inicia sesión.

1. Aparecerá un mensaje sobre el nuevo Portal de Microsoft Purview en la pantalla. Selecciona**Comenzar** para acceder al nuevo portal.

    ![Captura de pantalla que muestra la pantalla de bienvenida al nuevo Microsoft Purview portal.](../Media/welcome-purview-portal.png)

1. Selecciona**Soluciones** en la barra lateral izquierda y, después, selecciona**Auditar**.

1. En la página**Buscar**, selecciona la barra**Iniciar grabación de usuarios y actividad de administrador** para habilitar el registro de auditoría.

    ![Captura de pantalla que muestra el botón Iniciar grabación de usuarios y actividad de administrador.](../Media/enable-audit-button.png)

1. Una vez que selecciones esta opción, la barra azul debe desaparecer de esta página.

    >[!Note] **Nota: Si el botón Auditar no habilita el registro**
    >
    >En algunos inquilinos, es posible al seleccionar**Iniciar grabación de la actividad del usuario y el administrador** no se active Auditar.  
    >
    >Si esto sucede, puede habilitar Auditar mediante PowerShell en su lugar:
    >
    >1. Abra una ventana de terminal con privilegios elevados; para ello, haga clic con el botón derecho en el botón Windows y seleccione**Terminal (Administrador)**.  
    >
    >1. Instale el módulo**Exchange Online PowerShell** más reciente:
    >
    >     ```powershell
    >     Install-Module ExchangeOnlineManagement
    >     ```
    >
    >     Para confirmar las indicaciones, escriba**Y** para Sí y presione**Entrar**.
    >
    >1. Ejecute el siguiente comando para cambiar la directiva de ejecución:
    >
    >     ```powershell
    >     Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    >     ```
    >
    >1. Cierre la ventana de terminal con privilegios elevados y abra una sesión normal de PowerShell.
    >
    >1. Conéctese a Exchange Online:
    >
    >     ```powershell
    >     Connect-ExchangeOnline
    >     ```
    >
    >    Inicie sesión como`admin@WWLxZZZZZZ.onmicrosoft.com`, (donde ZZZZZZ es el prefijo de inquilino único proporcionado por el proveedor de hospedaje del laboratorio). La contraseña de administrador te la debería haber proporcionado tu proveedor de servicios de hospedaje de laboratorio.
    >
    >1. Compruebe si Auditar está habilitado:
    >
    >     ```powershell
    >     Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    >     ```
    >
    >    Si devuelve**_False_**, habilite Auditar:
    >
    >     ```powershell
    >     Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    >     ```
    >
    >1. Compruebe que ahora está habilitado:
    >
    >     ```powershell
    >     Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    >     ```
    >
    >    El comando debe devolver**_True_** una vez que Auditar esté activo.

Has habilitado correctamente la auditoría en Microsoft 365.

## Tarea: Asignación de roles de cumplimiento

En esta tarea, asignarás el**Administrador de cumplimiento** al usuario que usarás para estos ejercicios de laboratorio.

1. Abre**Microsoft Edge** y ve al Centro de administración de Microsoft 365,`https://admin.microsoft.com`. Deberás iniciar sesión como usuario que tenga derechos de**administrador global**.

1. Expande**Usuarios** en la barra lateral izquierda y selecciona**Usuarios activos**.

1. Selecciona o crea un usuario para continuar con estos ejercicios de laboratorio.

   Si decides usar un usuario existente, selecciona un usuario con derechos mínimos para el privilegio de acceso mínimo.

   1. Si creas un nuevo usuario, asigna al usuario una licencia adecuada para estos ejercicios de laboratorio. El usuario debe tener una licencia de Microsoft 365 E5 o un complemento compatible para estos ejercicios. Asigna al usuario el rol**Administrador de cumplimiento** en la configuración opcional del nuevo usuario configurado y finaliza la creación del nuevo usuario.

   1. Si modificas el acceso de un usuario existente, selecciona el usuario y, después, selecciona**Administrar roles**. Asigna al usuario el rol**Administrador de cumplimiento** y guarda los cambios.

1. Cierra la sesión de la cuenta con el acceso de administrador global seleccionando su icono de usuario en la parte superior derecha y selecciona**Cerrar sesión**.

   Ejemplo:

   ![Captura de pantalla que muestra la ruta de navegación para cerrar la sesión de la cuenta de administrador de MOD.](../Media/sign-out.png)

Has asignado correctamente a un usuario el rol**Administrador de cumplimiento**, que es necesario para realizar los distintos ejercicios de este laboratorio.

## Tarea: Exploración del Portal de Microsoft Purview

En esta tarea, iniciarás sesión como el usuario al que previamente concediste el rol**Administrador de cumplimiento** para explorar el Portal de Microsoft Purview. Este rol se denominará**administrador de cumplimiento** en los siguientes laboratorios y ejercicios.

1. En**Microsoft Edge**, ve a**`https://purview.microsoft.com`**.

1. Cuando se muestre la ventana**Elegir una cuenta**, selecciona**Usar otra cuenta**.

1. Cuando se muestre la ventana**Iniciar sesión**, inicia sesión como el usuario que seleccionaste anteriormente como**administrador de cumplimiento**.

1. Familiarízate con el nuevo Portal de Microsoft Purview. Cuando hayas terminado, deja abierta la ventana del explorador.

Has cambiado correctamente a la cuenta del**administrador de cumplimiento** y ya estás listo para iniciar el laboratorio.

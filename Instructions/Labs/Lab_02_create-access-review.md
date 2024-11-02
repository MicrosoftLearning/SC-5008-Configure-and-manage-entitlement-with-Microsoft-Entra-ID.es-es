---
lab:
  title: 'Laboratorio 2: Creación y administración de una revisión de acceso'
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Laboratorio 2: Creación y administración de una revisión de acceso

## Escenario del laboratorio

Las revisiones de acceso garantizan que solo las personas adecuadas tienen acceso a los recursos y la información. Una revisión de acceso se puede configurar para una vez o períodos recurrentes, y permite que los revisores aprueben o denieguen el acceso en función de factores como el rol de usuario, el último inicio de sesión o el nivel de riesgo. Los resultados de estas revisiones se pueden usar para actualizar los derechos de acceso de los usuarios, a fin de asegurar que se alinean con las directivas de la compañía y los requisitos de cumplimiento. En esta compañía, usan una revisión de acceso cuando un empleado cambia de rol dentro de la misma. Por ejemplo, si un empleado pasa de un rol de ventas a un rol de marketing, es posible que ya no necesite acceso a determinadas bases de datos o aplicaciones de ventas. Una revisión de acceso ayudaría a identificar los permisos innecesarios y permitiría a la empresa revocarlos, lo que reduce el riesgo de pérdidas de datos o accesos no autorizados.

#### Tiempo estimado: 15 minutos

### Ejercicio 1: Confirma que no tenemos usuarios que acceden a LinkedIn que no deberían usar este recurso.

#### Tarea 1: Creación de una revisión de acceso - Tipo de revisión

1. Inicia sesión en [https://entra.microsoft.com](https://entra.microsoft.com) con una cuenta de administrador global.

1. Abre el menú **Identidad** y después selecciona **Identity Governance**.

1. En el menú de la izquierda, selecciona **Revisiones de acceso**.

1. En el menú superior, selecciona **+ Nueva revisión de acceso**.

1. En el panel Nueva revisión de acceso, selecciona el elemento **Aplicaciones** en la lista desplegable "Selección de los elementos que se deben revisar".

1. Usa **+ Seleccionar aplicaciones** para elegir **LinkedIn** en la lista.

1. En **Ámbito**, selecciona **Todos los usuarios**.

1. Selecciona el botón **Siguiente: Revisiones** en la parte inferior de la pantalla.

#### Tarea 2: Creación de una revisión de acceso - Revisiones

1. Marca temporalmente la casilla **Revisión de varias fases**.

 **Nota:** Aquí es donde puedes elegir tener varias capas en la revisión de acceso.  Usa esta opción para recursos muy importantes, de modo que la revisión de una sola persona no agregue ni quite el acceso de los usuarios a un recurso crítico.  No vamos a compilar ni probar varias fases, pero el proceso es muy similar.

1. Desmarca la casilla **Revisión de varias fases**.

1. Rellena la página Revisión con los siguientes valores:

| Nombre de campo | Valor |
| :--- | :--- |
| Selección de los revisores | Usuarios o grupos seleccionados: Adele Vance |
| Duración (en días) | 5 |
| Periodicidad de la revisión | Mensualmente |
| Fecha de inicio | Fecha de hoy |
| Final | Finalizar después de un número de repeticiones |
| Apariciones | 3 |
| | |

1. Selecciona la opción **Siguiente: Configuración**.

#### Tarea 3: Creación de una revisión de acceso - Configuración

1. Deja la opción **Aplicar automáticamente los resultados a los recursos** sin marcar.

 **Nota:** Queremos asegurarnos de que validamos los resultados una vez completada la revisión.

1. Elige la opción **Quitar acceso** para **Si el revisor no responde**.

 **Nota:** Puedes usar esta configuración para controlar el nivel de seguridad.  Si ninguna revisión responde en una posición de seguridad menos segura, puedes proceder con Aprobar acceso.  En una posición de seguridad muy segura, puedes usar la opción Quitar acceso.  Al implementar tus propias soluciones, elige lo que sea mejor para tu compañía.

1. En **Al final de la revisión, enviar una notificación a**, selecciona la cuenta de administrador que usas para este laboratorio.

1. Deja los valores predeterminados en **Habilitar asistentes de decisiones de revisión**.

1. Establece el **Contenido adicional para el correo electrónico del revisor** y escribe el valor `Please complete your Access Review as soon as you can.`

1. Selecciona **Siguiente: Revisar + crear **.

1. Escribe los valores siguientes en el nombre y la descripción:

| Nombre de campo | Valor |
| :--- | :--- |
| Nombre de la revisión | `Check LinkedIn` |
| Descripción | `In this access review, we check to see if the right people have access to LinkedIn.` |
| | | 

1. Seleccione **Crear**.

#### Tarea 4: Inicio de sesión como Adele para ejecutar la revisión de acceso

1. Cierra el explorador, si lo tienes abierto.

1. Abre el explorador y conéctate a `https://outlook.office.com/`.

1. Se te pedirá que cambies la contraseña una vez que inicies sesión como Adele.

1. Inicia sesión como Adele Vance en función de tu inquilino.

 **Nota**: Deberías tener un correo electrónico de **Microsoft Security** con el asunto **Acción requerida: Revisa el acceso a LinkedIn...**. Este correo electrónico puede tardar hasta 10 minutos en llegar.

1. Selecciona el botón **Iniciar revisión >**.

 ![Captura de pantalla de la página de revisión de acceso que obtiene AdeleV al iniciar el vínculo en el correo electrónico.  Ten en cuenta que se recomienda quitar a Christopher Green.](./Media/access-review-page.png)

1. Coloca una marca de verificación en el círculo junto a **Christopher Green**.

1. Selecciona la opción **Denegar** en el menú superior.

1. Escribe un motivo para denegar el acceso al recurso. Ejemplo: `The sales campaign is over and Christopher does not need access any more`.

1. Selecciona el botón **Enviar** para enviar la recomendación.

#### Tarea 5: Confirmación de los resultados de la revisión de acceso

1. Cierra el explorador, si lo tienes abierto.

1. Abre el explorador y conéctate a `https://Entra.Microsoft.com/`.

1. Inicia sesión en Microsoft Entra con la cuenta de administrador.

1. En el menú de la izquierda, abre **Gobernanza de identidades**.

1. Selecciona **Revisiones de acceso**.

1. Selecciona la revisión **Comprobar LinkedIn** que compilamos anteriormente en el laboratorio.

1. Revisa la respuesta de AdeleV.

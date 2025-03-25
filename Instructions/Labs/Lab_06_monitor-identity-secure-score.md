---
lab:
  title: 'Laboratorio 6: Supervisión y administración de la posición de seguridad con la puntuación de seguridad de la identidad'
  module: 'Module : Deploying access using Microsoft Entra entitlement management'
---

# Laboratorio 6: Supervisión y administración de la posición de seguridad con la puntuación de seguridad de la identidad

## Escenario del laboratorio

Microsoft Entra Identity Protection proporciona detección y corrección automatizadas a riesgos basados en identidades y facilita datos en el portal para investigar posibles riesgos. Microsoft Entra Identity Protection también proporciona una puntuación de seguridad de identidad para supervisar y mejorar la posición de seguridad de la identidad.  De la misma manera que Microsoft Defender XDR y Microsoft Defender for Cloud, la puntuación de seguridad de identidad proporciona acciones de mejora y recomendaciones que pueden mejorar la posición general de seguridad para la identidad en Microsoft Entra ID.  Este laboratorio explorará esta funcionalidad. 

#### Tiempo estimado: 15 minutos

### Ejercicio 1: Uso de la puntuación de seguridad de identidad para supervisar y administrar la posición de seguridad de identidad

#### Tarea 1: Revisión de la puntuación de seguridad de identidad y acciones de mejora

1. Inicia sesión en  [https://entra.microsoft.com](https://entra.microsoft.com) como Administrador global.

2. Abre el menú **Protección** y selecciona **Puntuación de seguridad de la identidad**

**NOTA**: esto te llevará al panel Puntuación de seguridad de la identidad.

3. Desplázate hacia abajo para ver las **Acciones de mejora**.

4. A diferencia de las acciones de mejora de Microsoft Defender for Cloud y Microsoft Defender XDR, estas acciones de mejora son específicas de la identidad.  Esto proporciona una lista más enfocada en las posibles acciones de la administración de la posición de seguridad.  Las acciones de mejora iniciadas desde esta lista también proporcionarán un impacto en la posición de seguridad general del inquilino. 

#### Tarea 2: Ejecución de una acción de mejora

1. Para mejorar una área de la posición de seguridad de identidad, selecciona **Habilitar directivas de riesgo de inicio de sesión de protección de identidades de Microsoft Entra ID**.

3. En el menú de la izquierda, abre **Protección de identidades | Directiva de riesgo de inicio de sesión**.

4. Selecciona **Todos los usuarios** en **Asignaciones**.

5. Selecciona **Medio y superior** en **Riesgo de inicio de sesión**.

6. Selecciona **Permitir** - **Requerir autenticación multifactor** en **Controles**.

7. Cambia la **Aplicación de directiva** a **Habilitado** (si aún no lo has hecho) y selecciona **Guardar**.

8. Has creado una directiva de riesgo de inicio de sesión que ahora debe aumentar tu puntuación de seguridad de identidad.  Esto tardará hasta 24 horas en afectar a la puntuación de seguridad de la identidad.

9. Revisa otras acciones de mejora y los pasos para crearlas y habilitarlas.

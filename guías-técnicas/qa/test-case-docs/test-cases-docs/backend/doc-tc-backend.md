# Documentación de Test Cases - Backend

Esta guía está enfocada en documentar correctamente **Test Cases orientados al módulo Backend**, considerando lógica de servidor, validaciones, endpoints y buenas prácticas específicas. Está alineada con la estructura utilizada por el equipo QA y la plantilla oficial de backend.

---

## Índice

- [Estructura específica de un Test Case en Backend](#estructura-específica-de-un-test-case-en-backend)
- [Tipos de Test Cases](#tipos-de-test-cases)
- [Ejemplos](#ejemplos)
- [Buenas prácticas](#buenas-prácticas)
- [Notas adicionales](#notas-adicionales)
- [Referencias](#referencias)

---

## Estructura específica de un Test Case en Backend

| Campo                | Descripción                                                                 |
|---------------------|------------------------------------------------------------------------------|
| **ID**              | Formato: `TC-BE-[MODULO]-[NUM]` (ej: `TC-BE-AUTH-001`).                      |
| **Título**          | Breve descripción de lo que se está validando.                               |
| **Precondiciones**  | Datos previos, headers, tokens, configuración de entorno.                   |
| **Datos de Prueba** | Payload, parámetros de consulta o cuerpo de la solicitud.                   |
| **Pasos**           | 1. Endpoint utilizado <br> 2. Tipo de método (GET, POST, PUT, DELETE) <br> 3. Autenticación (si aplica) <br> 4. Headers utilizados <br> 5. Descripción del proceso. |
| **Resultado Esperado** | Status esperado (ej: 200 OK), estructura de respuesta, mensaje.          |
| **Resultado Actual**   | Respuesta real obtenida del servidor.                                     |
| **Estado**          | ✅ Passed / ❌ Failed                                                         |
| **Notas adicionales** | Capturas de Postman, curl, links a colecciones o logs.                    |

---

## Tipos de Test Cases

- **Happy Path:** Validación correcta de un endpoint con datos válidos.
- **Negative Case:** Validación de errores con datos incompletos o incorrectos.
- **Edge Case:** Casos extremos (valores nulos, rangos máximos, inputs inusuales).

---

## Ejemplos

### Caso Positivo: Creación de usuario válido

| Campo               | Descripción                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **ID**             | TC-BE-USER-001                                                               |
| **Título**         | Validar creación de usuario con datos válidos                                |
| **Precondiciones** | Tener acceso a Postman o herramienta API y token de autenticación            |
| **Datos de prueba**| Payload: <br> `{ "name": "Melany", "email": "mel@example.com", "password": "ValidPass123" }` |
| **Pasos**          | 1. Enviar solicitud `POST` a `/api/users` <br> 2. Incluir token en headers <br> 3. Enviar body con el payload definido |
| **Resultado Esperado** | Status `201 Created` <br> Respuesta: `{ "message": "Usuario creado correctamente" }` |
| **Resultado Actual**   | Status `201 Created` <br> Respuesta coincide con lo esperado              |
| **Estado**         | ✅ Passed                                                                     |

---

### Caso Negativo: Email ya registrado

| Campo               | Descripción                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **ID**             | TC-BE-USER-002                                                               |
| **Título**         | Validar error al registrar email duplicado                                  |
| **Precondiciones** | Usuario ya existe con ese email                                              |
| **Datos de prueba**| Payload: <br> `{ "name": "Ana", "email": "mel@example.com", "password": "AnotherPass123" }` |
| **Pasos**          | 1. Enviar solicitud `POST` a `/api/users` con el mismo email que ya existe  |
| **Resultado Esperado** | Status `409 Conflict` <br> Mensaje: `"El email ya está registrado"`       |
| **Resultado Actual**   | Status `409 Conflict` <br> Se muestra mensaje de error                    |
| **Estado**         | ✅ Passed                                                                     |

---
## Ejemplos en archivos .md:
Cada uno de los ejemplos siguientes corresponen a un tipo de caso específicado dentro del documento, teniendo en cuenta la plantilla referencial y las buenas prácticas.

- [`TestCaseBackend`](../backend/TestCaseBackend.md)
- [`TestCaseBackend2`](../backend/TestCaseBackend2.md)  
- [`TestCaseBackend3`](../backend/TestCaseBackend3.md)  
---

## Buenas prácticas

✔ Seguir el formato de ID `TC-BE-[MODULO]-[NUM]`.  
✔ Utilizar herramientas como Postman, Insomnia o Swagger.  
✔ Documentar claramente headers, tokens y payloads.  
✔ Usar JSON para datos de entrada y salida.  
✔ Registrar respuestas exactas y comparar con lo esperado.  
✔ Adjuntar logs, errores o mensajes del servidor cuando sea necesario.

---

## Notas adicionales

- Los Test Cases de backend deben permitir su ejecución paso a paso mediante herramientas de prueba.  
- Es recomendable mantener una colección organizada en Postman.  
- Cuando se usen entornos (staging, testing, prod), especificarlo.

---

## Plantilla Referencial

La estructura y convenciones presentadas en esta guía están basadas en el siguiente formato estandarizado para pruebas de Backend:

[`TestCaseBackend`](../test-case.md)  
> Esta plantilla fue construida como ejemplo base para estructurar correctamente los Test Cases orientados al backend, enfocados en la validación de endpoints, payloads, respuestas JSON, códigos de estado y flujo de autenticación. Incluye campos obligatorios como: ID, precondiciones, datos de prueba, pasos, resultado esperado, resultado actual, estado y notas adicionales.
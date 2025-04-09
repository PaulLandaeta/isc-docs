# Documentación de Test Cases - Frontend

Esta guía está enfocada en documentar correctamente **Test Cases orientados al módulo Frontend**, considerando interacciones visuales, flujos del usuario y buenas prácticas de pruebas en UI. Está alineada con la plantilla oficial utilizada por el equipo.

---

## Índice

- [Estructura específica de un Test Case en Frontend](#estructura-específica-de-un-test-case-en-frontend)
- [Tipos de Test Cases](#tipos-de-test-cases)
- [Ejemplos](#ejemplos)
- [Buenas prácticas](#buenas-prácticas)
- [Notas adicionales](#notas-adicionales)
- [Referencias](#referencias)

---

## Estructura específica de un Test Case en Frontend

Los Test Cases para frontend deben contener:

| Campo                | Descripción                                                                 |
|---------------------|------------------------------------------------------------------------------|
| **ID**              | Debe seguir el formato `TC-FE-[MODULO]-[NUMERO]` (ej: `TC-FE-AUTH-001`).     |
| **Título**          | Descripción breve y clara del objetivo de la prueba.                         |
| **Precondiciones**  | Usuario logueado, datos previos, permisos, etc.                              |
| **Datos de Prueba** | Inputs visibles como texto, checkbox, selección de ítems, etc.               |
| **Pasos**           | Instrucciones detalladas paso a paso sobre la interacción visual.            |
| **Resultado Esperado** | Qué debería ocurrir si el sistema funciona correctamente.               |
| **Resultado Actual**   | Resultado que realmente se obtuvo al ejecutar la prueba.                 |
| **Estado**          | ✅ Passed / ❌ Failed                                                         |
| **Notas adicionales** | Capturas, comentarios, links de error, etc.                              |

---

## Tipos de Test Cases

- **Happy Path:** El flujo correcto que el usuario sigue normalmente.
- **Negative Case:** Prueba con datos incorrectos para validar restricciones.
- **Edge Case:** Condiciones límite (campos vacíos, longitudes máximas, etc.).

---

## Ejemplos

### Caso Positivo: Inicio de sesión exitoso

| Campo               | Descripción                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **ID**             | TC-FE-AUTH-001                                                               |
| **Título**         | Verificar inicio de sesión exitoso con credenciales válidas                 |
| **Precondiciones** | Estar en la pantalla de Login                                                |
| **Datos de prueba**| Email: `melany@example.com` <br> Contraseña: `ValidPass123`                  |
| **Pasos**          | 1. Ingresar email <br> 2. Ingresar contraseña <br> 3. Clic en botón "Login"   |
| **Resultado Esperado** | Redirección al dashboard y mensaje de bienvenida                      |
| **Resultado Actual**   | Redirección exitosa                                                      |
| **Estado**         | ✅ Passed                                                                     |

---

### Caso Negativo: Campo de contraseña vacío

| Campo               | Descripción                                                                 |
|--------------------|------------------------------------------------------------------------------|
| **ID**             | TC-FE-AUTH-002                                                               |
| **Título**         | Validar que se muestre error si la contraseña está vacía                    |
| **Precondiciones** | Estar en la pantalla de Login                                                |
| **Datos de prueba**| Email: `melany@example.com` <br> Contraseña: ` ` (vacío)                     |
| **Pasos**          | 1. Ingresar email <br> 2. Dejar vacío contraseña <br> 3. Clic en "Login"      |
| **Resultado Esperado** | Mostrar mensaje: "La contraseña es obligatoria"                       |
| **Resultado Actual**   | Se muestra mensaje de error                                              |
| **Estado**         | ✅ Passed                                                                     |

---
## Ejemplos en archivos .md:
Cada uno de los ejemplos siguientes corresponen a un tipo de caso específicado dentro del documento, teniendo en cuenta la plantilla referencial y las buenas prácticas.

- [`TestCaseFrontend`](../frontend/TestCaseFrontend.md)
- [`TestCaseFrontend2`](../frontend/TestCaseFrontend2.md)  
- [`TestCaseFrontend3`](../frontend/TestCaseFrontend3.md)  

---

## Buenas prácticas

✔ Utiliza IDs consistentes por módulo: `TC-FE-[MODULO]-[NUM]`.  
✔ Describe paso a paso con precisión.  
✔ Incluye capturas si hay errores visuales.  
✔ Evita pasos genéricos como “hacer clic en el botón”.  
✔ Indica con claridad los resultados esperados y actuales.  
✔ Documenta variantes positivas, negativas y casos límite.  
✔ Los datos deben estar bien definidos (inputs, valores esperados, etc.).

---

## Notas adicionales

- Los Test Cases deben permitir replicar la prueba por cualquier persona.  
- Detallar siempre los flujos visuales con precisión.  
- Asegúrate de que cada Test Case esté alineado con la plantilla `TestCaseFrontend.docx`.  
- Los casos pueden cubrir funcionalidades como login, formularios, navegación, validaciones visuales, botones, etc.

---

## Plantilla Referencial

La estructura y convenciones presentadas en esta guía están basadas en el documento:

[`TestCase.md`](../test-case.md)  
> Esta plantilla fue utilizada como ejemplo para estructurar correctamente los Test Cases de frontend enfocados en flujos visuales y de usuario. Incluye campos obligatorios como: ID, precondiciones, pasos, datos de prueba, resultado esperado, resultado actual y estado.

---
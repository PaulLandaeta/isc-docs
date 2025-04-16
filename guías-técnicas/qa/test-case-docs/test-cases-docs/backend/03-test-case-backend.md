# Backend Test Case Example 3

**Project Name:** Sistema de Gestor de Cursos  
**Project Version:** 2.1.0  
**Test Case ID:** TC-BE-COURSE-001  
**Developer’s Name:** Esteban Méndez  
**Test Case Author’s Name:** Valeria QA  
**Reviewed By:** Adrián QA Lead  

---

## Test Case Specifics

**Test Title:** Validación de eliminación de curso vía API  

**Test Description:** Verificar que un curso pueda ser eliminado exitosamente desde el endpoint `/api/courses/{id}`.

---

### Test Accounts / Login

- **Username:** `admincourse@example.com`  
- **Password:** `AdminDelete321`

---

### Pre-requisite(s)

- Curso previamente creado con ID conocido  
- Token JWT válido con permisos de administrador  
- Base de datos con datos precargados

---

### Steps to Reproduce

1. Autenticarse con usuario administrador.  
2. Enviar solicitud DELETE al endpoint `/api/courses/99`

## Procedimiento del Test

| Paso | Acción                          | Resultado Esperado                           | Resultado Actual                               | ✅/❌ |
|------|----------------------------------|-----------------------------------------------|------------------------------------------------|--------|
| 1    | Enviar solicitud DELETE          | Status 200 y mensaje "Curso eliminado"        | Status 200 recibido                            | ✅     |
| 2    | Verificar en base de datos       | El curso con ID 99 ya no debe existir         | Curso no encontrado                            | ✅     |
| 3    | Intentar acceder al curso eliminado | Status 404 "Curso no disponible"           | Error 404 obtenido                             | ✅     |
| 4    | Intentar eliminar con ID inexistente | Status 404 "Curso no encontrado"          | Error 404 correcto                             | ✅     |
| 5    | Intentar sin token de autenticación | Error 401 no autorizado                     | Acceso denegado por falta de token             | ✅     |

---

## Resultado del Test

**Estado General:** ✅ **Pass**

---

## Notas Adicionales

- El servicio funciona correctamente, pero se recomienda incluir confirmación visual antes del DELETE desde el frontend.

---

## Multimedia

- Captura adjunta de respuesta DELETE exitosa (opcional)

---

## Información del Tester

- **Nombre del Tester:** Valeria QA  
- **Fecha de la Prueba:** 28/03/2025 – 20:15  
- **Sistema Operativo:** Ubuntu 22.04  
- **Herramienta de Pruebas:** Postman
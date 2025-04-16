# Backend Test Case Example

**Project Name:** Sistema de Gestión de Usuarios  
**Project Version:** 1.0.0  
**Test Case ID:** TC-BE-USERS-001  
**Developer’s Name:** Juan Pérez  
**Test Case Author’s Name:** Lucia QA  
**Reviewed By:** Adrián QA Lead  

---

## Test Case Specifics

**Test Title:** Validación de creación de usuario con roles múltiples  

**Test Description:** Verificar que un usuario con múltiples roles pueda ser creado correctamente a través del endpoint `/api/users`.

---

### Test Accounts / Login

- **Username:** `admin@example.com`  
- **Password:** `SecurePass123`

---

### Pre-requisite(s)

- Acceso a herramienta de pruebas (Postman o similar)  
- Backend ejecutándose en entorno de pruebas  
- Token de autenticación válido

---

### Steps to Reproduce

1. Autenticarse con credenciales válidas.  
2. Enviar solicitud POST a `/api/users` con el siguiente payload:
```json
{
  "name": "María Test",
  "email": "maria@example.com",
  "roles": ["editor", "viewer"]
}
```
## Procedimiento del Test

| Paso | Acción                                     | Resultado Esperado                              | Resultado Actual                                   | ✅/❌ |
|------|--------------------------------------------|--------------------------------------------------|----------------------------------------------------|------|
| 1    | Enviar solicitud POST al endpoint `/api/users` | Endpoint responde con status 201              | Respuesta con status 201 y JSON                    | ✅    |
| 2    | Incluir token en los headers               | Token es aceptado y válido                      | Token validado correctamente                       | ✅    |
| 3    | Enviar payload con múltiples roles         | Usuario creado con los roles especificados      | Usuario creado pero solo con un rol                | ❌    |
| 4    | Verificar en base de datos                 | Usuario aparece con todos los roles asignados   | Solo un rol registrado                             | ❌    |
| 5    | Probar con roles inválidos                 | Se retorna error 400 con mensaje claro          | Error 400 con validación correcta                  | ✅    |

---
---

## Resultado del Test

**Estado General:** ❌ **Fail**

---

## Notas Adicionales

- La lógica del backend no asigna múltiples roles correctamente.  
- Se requiere revisión del servicio de creación de usuarios.

---

## Multimedia

- Captura de pantalla adjunta o link a drive (opcional)

---

## Información del Tester

- **Nombre del Tester:** Lucia QA  
- **Fecha de la Prueba:** 27/03/2025 – 21:30  
- **Sistema Operativo:** Windows 11  
- **Herramienta de Pruebas:** Postman  
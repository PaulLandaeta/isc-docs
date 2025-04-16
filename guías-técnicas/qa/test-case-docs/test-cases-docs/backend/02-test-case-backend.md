# Backend Test Case Example 2

**Project Name:** Sistema de Gestión de Usuarios  
**Project Version:** 1.0.0  
**Test Case ID:** TC-BE-USERS-002  
**Developer’s Name:** Carla Ruiz  
**Test Case Author’s Name:** Martín QA  
**Reviewed By:** Adrián QA Lead  

---

## Test Case Specifics

**Test Title:** Validación de actualización de contraseña mediante API  

**Test Description:** Verificar que un usuario pueda actualizar su contraseña correctamente a través del endpoint `/api/users/update-password`.

---

### Test Accounts / Login

- **Username:** `carla@example.com`  
- **Password:** `OldPass456`

---

### Pre-requisite(s)

- Token de autenticación válido  
- Backend levantado en entorno de QA  
- Usuario existente registrado en la base de datos

---

### Steps to Reproduce

1. Autenticarse con credenciales válidas.  
2. Enviar solicitud PUT al endpoint `/api/users/update-password` con el siguiente payload:

```json
{
  "oldPassword": "OldPass456",
  "newPassword": "NewSecure789"
}
```

## Procedimiento del Test

| Paso | Acción                                       | Resultado Esperado                                | Resultado Actual                                     | ✅/❌ |
|------|-----------------------------------------------|----------------------------------------------------|------------------------------------------------------|--------|
| 1    | Enviar solicitud PUT al endpoint `/api/users/update-password` | Status 200 y mensaje de éxito                  | Status 200 y mensaje recibido                        | ✅     |
| 2    | Validar token                                 | Token aceptado y válido                           | Token validado correctamente                         | ✅     |
| 3    | Enviar contraseña antigua incorrecta         | Se retorna error 403 con mensaje de "contraseña incorrecta" | Status 403 con mensaje correcto            | ✅     |
| 4    | Verificar login con nueva contraseña         | Login exitoso con `NewSecure789`                   | Acceso exitoso con nueva contraseña                 | ✅     |
| 5    | Verificar login con contraseña antigua        | Acceso denegado                                    | Acceso fallido como esperado                         | ✅     |

---

## Resultado del Test

**Estado General:** ✅ **Pass**

---

## Notas Adicionales

- La funcionalidad responde correctamente a distintos escenarios.  
- Se recomienda agregar validaciones adicionales al formato de nueva contraseña.

---

## Multimedia

- Captura de pantalla adjunta o link a Postman Collection

---

## Información del Tester

- **Nombre del Tester:** Martín QA  
- **Fecha de la Prueba:** 28/03/2025 – 16:45  
- **Sistema Operativo:** Windows 10  
- **Herramienta de Pruebas:** Postman  

---
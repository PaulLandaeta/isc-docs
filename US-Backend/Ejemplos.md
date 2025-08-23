
# Ejemplos de Guía de User Stories de Backend 

# 📝 User Story: Asignar rol a un usuario

## Descripción  
**Como** sistema de gestión de usuarios,  
**Necesito** asignar un rol específico a un usuario existente,  
**Para** controlar el acceso a funcionalidades según sus permisos asociados.

## ✅ Criterios de Aceptación  
1. **Dado que** un usuario ha sido creado antes,  
   **Cuando** se le asigna un rol que tiene que ser válido mediante el endpoint,  
   **Entonces** el sistema debe registrar la relación en la tabla `user_roles`.

2. **Dado que** se intenta asignar un rol inexistente o el usuario no existe,  
   **Cuando** se envía la solicitud,  
   **Entonces** el sistema debe responder con un error 400 indicando datos inválidos.

##  Especificaciones Técnicas  
- **🔗 Endpoint:** `POST /api/user_roles`  
- **📄 Formato de request:**  
```json
{
  "user_id": 12,
  "role_id": 3
}  
```
## Formato de respuesta esperada:
```json
{
  "status": "success",
  "data": {
    "user_id": 12,
    "role_id": 3
  }
}
```

## Manejo de errores:
- 400 → El user_id o role_id no existen en la base de datos.

- 401 → Usuario no autenticado o sin permisos para esta acción.

- 500 → Error interno al registrar el rol del usuario.



---

# 📝 User Story: Obtener permisos completos de un usuario

## Descripción  
**Como** sistema de autenticación y autorización,  
**Necesito** recuperar todos los permisos asociados a un usuario,  
**Para** validar qué funcionalidades puede acceder en la plataforma.

## ✅ Criterios de Aceptación  
1. **Dado que** un usuario está autenticado,  
   **Cuando** solicita sus permisos mediante el endpoint,  
   **Entonces** el sistema debe devolver la lista completa de permisos que le corresponden por cada rol asignado.

2. **Dado que** un usuario no tiene roles asignados,  
   **Cuando** solicita sus permisos,  
   **Entonces** el sistema debe retornar una lista vacía sin errores.

##  Especificaciones Técnicas  
- **🔗 Endpoint:** `GET /api/users/{user_id}/permissions`  
- **📄 Formato de request:** *(No requiere body, sólo el parámetro en la URL)*

## Formato de respuesta esperada:
```json
{
  "status": "success",
  "data": [
    {
      "permission_id": 1,
      "name": "create_user",
      "category": "Usuarios"
    },
    {
      "permission_id": 4,
      "name": "view_reports",
      "category": "Reportes"
    }
  ]
}
```

## Manejo de errores:
- 400 → ID de usuario inválido o malformado.

- 404 → Usuario no encontrado.

-  500 → Error interno al recuperar permisos.



# 📝 User Story: Crear usuario con asignación de roles

## Descripción  
**Como** sistema de administración,  
**Necesito** registrar un nuevo usuario con uno o más roles desde el inicio,  
**Para** que pueda autenticarse y tener acceso a funcionalidades desde su primer login.

## ✅ Criterios de Aceptación  
1. **Dado que** un administrador proporciona los datos completos del nuevo usuario y sus roles,  
   **Cuando** se hace una solicitud al endpoint de creación,  
   **Entonces** el sistema debe guardar el usuario y vincularlo a los roles indicados.

2. **Dado que** se proporciona un rol inexistente,  
   **Cuando** se intenta registrar al usuario,  
   **Entonces** el sistema debe rechazar la operación y no guardar ningún dato (transacción revertida).

## Especificaciones Técnicas  
- **🔗 Endpoint:** `POST /api/users`  
- **📄 Formato de request:**  
```json
{
  "username": "dany",
  "name": "Daniel",
  "lastname": "Tribeño",
  "mothername": "Lurdes",
  "password": "root1234",
  "email": "danitribeño@gmail.com",
  "phone": "75775482",
  "roles": [2, 4]
}
```

## Formato de respuesta esperada:
```json
{
  "status": "success",
  "data": {
    "user_id": 21,
    "username": "dany",
    "roles_assigned": [2, 4]
  }
}
```
## Consideraciones Técnicas

- El endpoint debe usar una **transacción** para asegurar que si la inserción de `user_profile` o cualquiera de los registros en `user_roles` falla, se haga **rollback**.
- Las contraseñas deben almacenarse de forma segura.
- Validar previamente que los `role_id` proporcionados existan en la base de datos antes de insertarlos.

## ❌ Manejo de errores

- **400** → Falta algún campo obligatorio o el campo `roles` no es un array válido.
- **409** → El `username` o `email` ya existen en el sistema.
- **404** → Uno de los roles especificados no existe.
- **500** → Error interno en la base de datos o al intentar crear el usuario.


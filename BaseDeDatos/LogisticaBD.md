# Documentación de Base de Datos

## Objetivo

El propósito de este documento es explicar de forma clara cómo está organizada la base de datos del proyecto. Esta base de datos almacena información sobre usuarios, roles, permisos, etc., y cómo todo esto se relaciona. Esta guía ayudará a los desarrolladores, testers y analistas funcionales a comprender cómo funciona y cómo se conecta todo.

## 2. Conceptos Básicos

- **Clave primaria (PK)**: Es un campo que identifica de forma única cada fila de una tabla. Ejemplo: el número de carnet de una persona.
- **Clave foránea (FK)**: Es un campo que se conecta con la clave primaria de otra tabla. **Sirve para enlazar información entre dos tablas diferentes**.


## Tablas de la base de datos relevantes

### 1. `user_profile` – Usuarios del sistema
-** ¿Qué guarda esta tabla?**: Aquí se almacenan los datos de cada persona que usa el sistema.
-** Ejemplo de datos que contiene**: nombre, apellido, correo electrónico, contraseña, número de teléfono, código de usuario, etc.
- **Para qué sirve**: Es la base para identificar a los usuarios. También se guarda qué rol principal tiene cada usuario.
- **Ejemplo**: Pedro Pérez es profesor. Su información personal y su rol principal (profesor) están aquí.


| Campo       | Tipo de Dato | Restricciones                    | Descripción                                               |
|-------------|--------------|----------------------------------|-----------------------------------------------------------|
| id          | int          | PK, NOT NULL, UNIQUE            | Identificador único del perfil de usuario.                |
| username    | varchar      | NOT NULL, UNIQUE                | Nombre de usuario utilizado para iniciar sesión.          |
| name        | varchar      | NOT NULL                        | Nombre del usuario.                                       |
| lastname    | varchar      | NOT NULL                        | Apellido del usuario.                                     |
| mothername  | varchar      |                                  | Segundo apellido o nombre de la madre.                    |
| password    | varchar      | NOT NULL                        | Contraseña encriptada.                                    |
| email       | varchar      | NOT NULL, UNIQUE                | Correo electrónico del usuario.                           |
| phone       | varchar      |                                  | Teléfono del usuario.                                     |
| role_id     | int          | FK → `roles.id`                 | Rol asignado al usuario.                                  |
| created_at  | datetime     | DEFAULT CURRENT_TIMESTAMP       | Fecha de creación del perfil.                             |
| updated_at  | datetime     | ON UPDATE CURRENT_TIMESTAMP     | Fecha de última actualización.                            |
| code        | varchar      | UNIQUE                          | Código único adicional para identificación o validación.  |


**Relaciones**:

- FK hacia `roles` (`role_id`)
- Uno a Uno con `professors` y `students` (relación polimórfica basada en `id`)
- Uno a Muchos con `user_roles` (usuario puede tener múltiples roles adicionales)

### 2. `roles` – Tipos de usuario
- **¿Qué guarda esta tabla?**: Define los tipos de usuarios que existen.
- ** Ejemplo de datos que contiene**: administrador, profesor, estudiante, etc.
- **Para qué sirve**: Permite clasificar a los usuarios y determinar qué pueden hacer dentro del sistema.
- **Ejemplo**: El rol “administrador” permite acceder a todo, mientras que el rol “estudiante” tiene acceso limitado.


| Campo | Tipo de Dato | Restricciones    | Descripción                         |
|-------|--------------|------------------|-------------------------------------|
| id    | int          | PK, NOT NULL     | Identificador del rol.              |
| name  | varchar      | NOT NULL, UNIQUE | Nombre del rol (e.g. Admin, Alumno) |

**Relaciones**:

- Uno a Muchos con `user_profile`
- Muchos a Muchos con `permissions` mediante `role_permissions`
- Muchos a Muchos con `user_profile` mediante `user_roles`

### 3. `user_roles` – Roles adicionales de cada usuario

**Propósito**: Relación muchos a muchos entre usuarios y roles adicionales.

- ** ¿Qué guarda esta tabla?**: Las relaciones entre los usuarios y todos los roles que pueden tener.
- **Para qué sirve**: Un usuario puede tener varios roles. Esta tabla lo permite.
- **Ejemplo**: Un usuario puede ser tanto “profesor” como “coordinador académico”. Esta tabla guarda eso.


| Campo    | Tipo de Dato | Restricciones        | Descripción     |
|----------|--------------|----------------------|-----------------|
| user_id  | int          | FK → `user_profile`  | ID del usuario. |
| role_id  | int          | FK → `roles`         | ID del rol.     |

**Relaciones**:

- Muchos a Muchos entre `user_profile` y `roles`

### 4. `professors` – Detalles de los profesores
**Propósito**: Contiene datos específicos para usuarios que son profesores.

- **¿Qué guarda esta tabla?**: Información específica de los usuarios que son profesores.
- **Ejemplo de datos que contiene**: título profesional, departamento al que pertenece, especialidad.
- **Para qué sirve**: Separa los datos generales (que están en `user_profile`) de los datos propios de los profesores.
- **Ejemplo **: Un usuario que es profesor de Matemáticas tendrá aquí su especialidad y su departamento.

| Campo      | Tipo de Dato | Restricciones               | Descripción                      |
|------------|--------------|-----------------------------|----------------------------------|
| id         | int          | PK, FK → `user_profile.id`  | ID del profesor.                 |
| degree     | varchar      |                             | Título profesional del profesor. |
| department | varchar      |                             | Departamento al que pertenece.   |
| specialty  | varchar      |                             | Especialidad académica.          |

**Relaciones**:

- Uno a Uno con `user_profile` (por `id`)

### 5. `students` – Detalles de los estudiantes

**Propósito**: Contiene información adicional para usuarios estudiantes.

- ** ¿Qué guarda esta tabla?**: Información específica de los usuarios que son estudiantes.
- ** Ejemplo de datos que contiene**: si el estudiante tiene beca o no.
-**Para qué sirve**: Igual que con los profesores, aquí se guarda lo que solo aplica a los estudiantes.
- **Ejemplo**: Un estudiante puede tener un campo marcado como “Sí” en beca.

| Campo          | Tipo de Dato | Restricciones              | Descripción                          |
|----------------|--------------|----------------------------|--------------------------------------|
| id             | int          | PK, FK → `user_profile.id` | ID del estudiante.                   |
| is_scholarship | boolean      | DEFAULT FALSE              | Indica si el estudiante tiene beca.  |

**Relaciones**:

- Uno a Uno con `user_profile` (por `id`)

### 6. `permissions` – Acciones que se pueden hacer

**Propósito**: Define los permisos individuales del sistema.

- ** ¿Qué guarda esta tabla?**: Las acciones o funciones que existen en el sistema.
-** Ejemplo de datos que contiene**: “crear usuario”, “editar perfil”, “ver reportes”, etc.
- **Para qué sirve**: Controla qué acciones están permitidas. Los roles se asocian a estas acciones.
-**Ejemplo**: Un permiso podría ser “Eliminar estudiante”.


| Campo        | Tipo de Dato | Restricciones                     | Descripción                         |
|--------------|--------------|-----------------------------------|-------------------------------------|
| id           | int          | PK                                | Identificador del permiso.          |
| name         | varchar      | NOT NULL                          | Nombre del permiso.                 |
| category_id  | int          | FK → `permission_categories.id`   | Categoría a la que pertenece.       |

**Relaciones**:

- Muchos a Muchos con `roles` mediante `role_permissions`
- Muchos a Uno con `permission_categories`

### 7. `role_permissions` – Qué permisos tiene cada rol
**Propósito**: Agrupa permisos por categoría funcional.
|
-** ¿Qué guarda esta tabla?**: La relación entre los roles y los permisos.
-**Para qué sirve**: Define qué puede hacer cada rol en el sistema.
-**Ejemplo**: El rol “Administrador” tiene todos los permisos; el rol “Estudiante” solo tiene algunos.

| Campo | Tipo de Dato | Restricciones | Descripción                    |
|-------|--------------|----------------|--------------------------------|
| id    | int          | PK             | Identificador de la categoría. |
| name  | varchar      | NOT NULL       | Nombre de la categoría.        |


### 8. `permission_categories` – Categorías de permisos

**Propósito**: Relación muchos a muchos entre roles y permisos.

- ** ¿Qué guarda esta tabla?**: Grupos que organizan los permisos por temas o módulos.
- ** Ejemplo de datos que contiene**: “Gestión de usuarios”, “Reportes”, “Módulo académico”.
- **Para qué sirve**: Ayuda a organizar los permisos para que sea más fácil encontrarlos o asignarlos.
- **Ejemplo**: Todos los permisos relacionados con usuarios estarán en la categoría “Gestión de usuarios”.


| Campo         | Tipo de Dato | Restricciones           | Descripción     |
|---------------|--------------|-------------------------|-----------------|
| role_id       | int          | FK → `roles.id`         | ID del rol.     |
| permission_id | int          | FK → `permissions.id`   | ID del permiso. |

**Relaciones**:

- Muchos a Muchos entre `roles` y `permissions`

## Tablas de la base de datos no relevantes

### 9. `knex_migrations` – Control de migraciones

**Propósito**: Registro de migraciones ejecutadas por Knex.js.

- ** ¿Qué guarda esta tabla?**: Información sobre los cambios que se han hecho en la base de datos mediante migraciones.
- ** Ejemplo de datos que contiene**: qué cambio se aplicó, en qué orden, y en qué momento.
-**Para qué sirve**: Es usada por el sistema de desarrollo (Knex.js) para saber qué migraciones ya se ejecutaron y cuáles no.
-**Ejemplo**: Si el equipo de desarrollo agrega una nueva tabla al sistema, se registra aquí para que no se vuelva a aplicar el mismo cambio.

| Campo          | Tipo de Dato | Restricciones | Descripción                    |
|----------------|--------------|----------------|--------------------------------|
| id             | int          | PK             | Identificador de la migración. |
| name           | varchar      | NOT NULL       | Nombre de la migración.        |
| batch          | int          |                | Número de lote de ejecución.   |
| migration_time | datetime     |                | Fecha y hora de ejecución.     |


### 10. `knex_migrations_lock` – Control de acceso a migraciones

**Propósito**: Controla el bloqueo de migraciones concurrentes.

- **¿Qué guarda esta tabla?**: Un pequeño indicador (un “candado”) que dice si alguien está actualmente ejecutando cambios en la base de datos.
- ** Ejemplo de datos que contiene**: un valor de true o false en `is_locked`.
- **Para qué sirve**: Evita que dos personas o procesos modifiquen la estructura de la base de datos al mismo tiempo, lo que podría causar errores.
- **Ejemplo**: Si alguien está aplicando una migración y otro intenta hacerlo al mismo tiempo, este “candado” impide conflictos.


| Campo     | Tipo de Dato | Restricciones | Descripción                          |
|-----------|--------------|----------------|--------------------------------------|
| index     | int          | PK             | Índice único.                        |
| is_locked | boolean      |                | Indica si hay una migración en curso.|

## Relaciones entre las Tablas

### 1. `user_profile` ↔️ `roles`
- **Relación**: Muchos a Uno
- **Explicación**: Cada usuario tiene un rol principal (`role_id`), pero un rol puede estar asignado a muchos usuarios.

### 2. `user_profile` ↔️ `user_roles`
- **Relación**: Uno a Muchos 
- **Explicación**: Un usuario puede tener varios roles adicionales. La tabla `user_roles` funciona como tabla intermedia para representar esta relación muchos a muchos.

### 3. `roles` ↔️ `user_roles`
- **Relación**: Uno a Muchos
- **Explicación**: Un rol puede estar asignado a múltiples usuarios. Esta relación forma parte de la relación muchos a muchos entre usuarios y roles.

### 4. `roles` ↔️ `role_permissions`
- **Relación**: Uno a Muchos 
- **Explicación**: Un rol puede tener muchos permisos asignados. La tabla `role_permissions` actúa como tabla intermedia.

### 5. `permissions` ↔️ `role_permissions`
- **Relación**: Uno a Muchos
- **Explicación**: Un permiso puede ser asignado a múltiples roles. Esta relación completa la relación muchos a muchos entre roles y permisos.


### 6. `permissions` ↔️ `permission_categories`
- **Relación**: Muchos a Uno 
- **Explicación**: Cada permiso pertenece a una categoría. Una categoría agrupa múltiples permisos.

### 7. `user_profile` ↔️ `professors`
- **Relación**: Uno a Uno 
- **Explicación**: Si un usuario es profesor, tendrá una entrada en `professors` que amplía su información (título, departamento, especialidad).

### 8. `user_profile` ↔️ `students`
- **Relación**: Uno a Uno )
- **Explicación**: Si un usuario es estudiante, tendrá una entrada en `students` que extiende su información (beca, etc.).

## Identificadores entre Tablas

### 1. `user_profile`
- **PK**: `id`
- **FK**: `role_id` → apunta a `roles.id`
- **Relación**: Un usuario tiene un rol principal.

### 2. `roles`
- **PK**: `id`
- **FKs relacionadas**:
  - `user_profile.role_id`
  - `user_roles.role_id`
  - `role_permissions.role_id`
- **Relación**: Un rol puede estar asignado a muchos usuarios y tener muchos permisos.

### 3. `user_roles`
- **PK**: `id`
- **FKs**:
  - `user_id` → `user_profile.id`
  - `role_id` → `roles.id`
- **Relación**: Permite que un usuario tenga varios roles.

### 4. `professors`
- **PK**: `id`
- **FK**: `user_id` → `user_profile.id`
- **Relación**: Un profesor es un usuario con información adicional.

### 5. `students`
- **PK**: `id`
- **FK**: `user_id` → `user_profile.id`
- **Relación**: Un estudiante es un usuario con información específica.

### 6. `permissions`
- **PK**: `id`
- **FK**: `category_id` → `permission_categories.id`
- **Relación**: Un permiso pertenece a una categoría.

### 7. `permission_categories`
- **PK**: `id`
- **Relación**: Una categoría puede tener muchos permisos.

### 8. `role_permissions`
- **PK**: `id`
- **FKs**:
  - `role_id` → `roles.id`
  - `permission_id` → `permissions.id`
- **Relación**: Conecta los permisos con los roles.

### 9. `knex_migrations`
- **PK**: `id`
- **Relación**: (No tiene relaciones con otras tablas)


### 10. `knex_migrations_lock`
- **PK**: `index`
- **Relación**: (No tiene relaciones con otras tablas)


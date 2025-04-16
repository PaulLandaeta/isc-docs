# Guía de Buenas Prácticas en el Uso de Postman para Endpoints

## Objetivo

Establecer una guía clara y estructurada para el uso de Postman que asegure entornos, colecciones y endpoints bien configurados y documentados. 

### 1. Documentación de cada petición

Se tiene que poner información útil y concisa en la descripción de cada request:

- Objetivo de la petición
- Parámetros requeridos
- Códigos de respuesta esperados
- Ejemplos de request y response

✅ Ejemplo de descripción:
```markdown
Crea un nuevo usuario/ Create new user
```

**Body:**
```json
{
  "name": "Paul Landaeta",
  "email": "paulandaeta.com",
  "password": "******"
}
```

**Respuestas:**
```json
201: Usuario creado
400: Datos inválidos
```

##  2. Buenas Prácticas en Entornos Colaborativos

### Nomenclatura de Colecciones, Carpetas y Endpoints

### 🔹 Colecciones
**Formato :** `[Proyecto/Servicio] - [Ambiente]`

**Ejemplos:**
- `UserService - Development`
- `EcommerceAPI - Staging`

Esto para identificar para qué servicio o entorno es cada colección.

![Ejemplo Colecciones Postman](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*1bgVYhct_8SHYpqdgfQgow.png)
![Ejemplo Colecciones Postman](https://miro.medium.com/v2/resize:fit:640/format:webp/1*-4ZesYorPmsn64ZsDyMbgw.png)

### 🔹 Carpetas
Incluir una breve descripción que explique qué funcionalidades.
Organizar por **módulos funcionales** o **recursos REST**.

**Formato :** `[Recurso] [Operación Opcional]`

**Ejemplos:**
- `Auth`
- `Products - CRUD`
- `Orders - Checkout Flow`

![Ejemplo Carpetas Postman](https://cdn.hashnode.com/res/hashnode/image/upload/v1628329082904/XCzGVQvvl.png?auto=compress,format&format=webp)

### 🔹 Endpoints
Cada request debe contener:

- Descripción funcional de lo que hace.
- Parámetros esperados en query, path o body.

Usar **verbos HTTP** y una **descripción corta**.

**Formato :** `[VERBO] - [Acción o Recurso]`

**Ejemplos:**
- `GET - List all users`
- `POST - Create new product`
- `DELETE - Remove user by ID`

![Petición documentada en Postman](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*mlvSDliq0ZigIrmqFgwBNA.png)

![Variables de entorno en Postman](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*Z-yeHVi8b5MoxmY1EQ6BJw.png)

**Ejemplo de buena descripción:**

Este endpoint permite crear un nuevo usuario en la base de datos. 
Requiere un token de autorización válido.

  **Parámetros:**
  - name (string, requerido)
  - email (string, requerido)
  - password (string, requerido)

  **Respuestas:**
  - 201: Usuario creado exitosamente.
  - 400: Datos inválidos.
  - 401: Token no válido o ausente.

**Ejemplo de servidor**
- ![Servidor funcionado](https://www.analyticslane.com/storage/2022/10/postman-get-1536x1213.png.webp)

## 2. Estructura de carpetas
Organizar las carpetas por:

- **Módulo funcional** (Auth, Users, Products)
- **Flujo de negocio** (Login Flow, Checkout Flow)
- **Recurso REST** (Orders, Payments)

✅ Ejemplo:

📁 Auth  
└── POST - Login

📁 Users  
├── GET - List users  
└── POST - Create user

📁 Orders - Checkout  
└── POST - Place order




## 4. Uso correcto de variables

- Reutilización de valores comunes
- Seguridad (ocultar tokens y claves)
- Flexibilidad entre entornos

🔹 **Variables de entorno**: `{{baseUrl}}`, `{{authToken}}`

🔹 **Variables locales**: Útiles para datos generados dinámicamente

🔹 **Evitar variables globales sensibles**

 Separar entornos (`Dev`, `Test`, `Prod`) y mantenerlos documentados.

## 5. Versionado de colecciones

El versionado evita pérdida de trabajo y permite mantener trazabilidad.

- Usar sufijos en el nombre: `UserAPI v1`, `Payments v2.1`
- Documentar cambios relevantes en la descripción de la colección
- Usar control de versiones (si se sincroniza con repositorio Git)

 Ejemplo de nombres:
- `Ecommerce API v1.0`
- `Ecommerce API v1.1 - With Discounts`

## 6. Referencias

- [Postman: Colecciones, Environments y Documentación (Medium)](https://medium.com/zurvin/postman-colecciones-environments-y-documentaci%C3%B3n-a86ac96c78bb)
- [Integración y APIs (EGA Futura)](https://discover.egafutura.com/tag/integracion-y-apis/)
- [Postman Gestión de APIs (EGA Futura)](https://franciscougalde.com/postman-gestiona-tu-apis-facilmente)
- [Creación de rutas Postman](https://www.analyticslane.com/2022/11/02/creacion-de-rutas-para-consultar-y-agregar-los-registros-4a-parte-de-creacion-de-una-api-rest-con-express-y-typescript/)

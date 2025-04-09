# 📄 Informe: Estructura del Proyecto Backend en Node.js con Arquitectura en Capas

---

## 🧠 Introducción a Node.js

**Node.js** es un entorno de ejecución de JavaScript del lado del servidor, de código abierto y multiplataforma. Fue creado en 2009 por Ryan Dahl y está construido sobre el motor **V8 de Chrome**, lo que lo convierte en una herramienta potente para desarrollar aplicaciones backend eficientes con JavaScript.

> “Node.js is an open-source and cross-platform JavaScript runtime environment.” – nodejs.dev

### 🌐 Diferencias entre el entorno del navegador y Node.js

| Característica                | Navegador                 | Node.js                       |
|------------------------------|---------------------------|-------------------------------|
| DOM                          | Acceso completo           | No tiene acceso               |
| Acceso a sistema de archivos | No disponible             | Disponible                    |
| Objeto global                | `window`                  | `global`                      |
| Control de versiones         | No control                | Control total                 |
| Carga de módulos             | `import` (limitado)       | `require` y `import` (total) |

### 🧑‍💻 ¿Por qué aprender Node.js?

- Permite trabajar con JavaScript en **frontend y backend**.
- Utilizado por grandes empresas como Netflix, PayPal y LinkedIn.
- Amplia comunidad y documentación.
- Compatible con herramientas modernas (NPM, Express, etc.).
- Basado en el rápido motor V8 de Google.

---

## 🚀 Cómo iniciar un proyecto Node.js

1. **Instala Node.js** desde [nodejs.org](https://nodejs.org/)
2. Verifica con:

```bash
node --version


## 🏗️ Estructura del Proyecto Backend con Arquitectura en Capas

backend/
├── config/
│   └── database.js
├── controllers/
│   └── user.controller.js
├── services/
│   └── user.service.js
├── models/
│   └── user.model.js
├── routes/
│   └── user.routes.js
├── middlewares/
│   └── auth.middleware.js
├── utils/
│   └── jwt.helper.js
├── app.js
├── server.js
├── .env
├── package.json
└── README.md

```

## 🧱 Explicación de las Capas en la Arquitectura del Proyecto

La arquitectura por capas divide el backend en módulos bien definidos, donde cada capa tiene una única responsabilidad. Esta separación favorece el mantenimiento, escalabilidad, reutilización de código y pruebas independientes.


### 1. 📁 `controllers/` – Controladores

Los **controladores** se encargan de recibir las peticiones HTTP desde el cliente (por ejemplo, un frontend o una herramienta como Postman), y delegar el trabajo a la capa de servicios.

Son responsables de:

- Validar las entradas básicas.
- Invocar los servicios correspondientes.
- Devolver respuestas HTTP al cliente (res.status().json()).

#### 🧩 Ejemplo: `controllers/user.controller.js`

```js
const userService = require('../services/user.service');

exports.getAllUsers = async (req, res) => {
  try {
    const users = await userService.getAllUsers();
    res.status(200).json(users);
  } catch (error) {
    res.status(500).json({ message: 'Error fetching users' });
  }
};

```

### 2. 📁 `services/` – Servicios

Los **servicios** contienen la lógica del negocio. Esta capa procesa los datos, aplica reglas, verifica condiciones y se comunica con la capa de persistencia (modelos).

#### Responsabilidades:

- Aplicar reglas de negocio.
- Coordinar acciones entre varias entidades.
- Preparar datos antes de ir a la base de datos o antes de enviarlos al controlador.

#### ❎ Ejemplo: `services/user.service.js`

```js
const User = require('../models/user.model');

exports.getAllUsers = async () => {
  return await User.find();
}; 

```


### 3. 📁 `models/` – Modelos

Aquí se define el **esquema de datos** y se maneja la interacción con la base de datos. En proyectos con MongoDB se utiliza Mongoose; con SQL se puede usar Sequelize, TypeORM, etc.

#### Responsabilidades:

- Definir la forma de los datos.
- Ejecutar operaciones CRUD directamente con la base de datos.

#### ❎ Ejemplo: `models/user.model.js`

```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: String,
  email: String
});

module.exports = mongoose.model('User', userSchema); 

```


### 4. 📁 `routes/` – Rutas

Las **rutas** son el punto de entrada a la API. Asignan las URLs a los métodos del controlador correspondientes.

#### Responsabilidades:

- Definir rutas (endpoints) de la API.
- Asociar cada ruta a su controlador.

#### ❎ Ejemplo: `routes/user.routes.js`

```js
const express = require('express');
const router = express.Router();
const userController = require('../controllers/user.controller');

router.get('/', userController.getAllUsers);

module.exports = router; 

```

### 5. 📁 `config/` – Configuración

Contiene archivos que configuran recursos externos, como la base de datos o variables de entorno.

#### ❎ Ejemplo: `config/database.js`

```js
const mongoose = require('mongoose');

mongoose.connect(process.env.MONGO_URI)
  .then(() => console.log('Connected to DB'))
  .catch(err => console.error('DB Connection Error:', err)); 
  
  ```


### 6. 📁 `middlewares/` – Middleware

Funciones que se ejecutan antes de llegar a los controladores. Útiles para autenticación, validación, logging, etc.

#### ❎ Ejemplo: `middlewares/auth.middleware.js`

```js
module.exports = (req, res, next) => {
  const token = req.headers.authorization;

  if (!token) {
    return res.status(401).json({ message: 'Unauthorized' });
  }

  // Si pasa la validación:
  next();
}; 

```

### 7. 📁 `utils/` – Utilidades

Funciones auxiliares como generadores de tokens, formateadores, validadores, etc.

#### ❎ Ejemplo: `utils/jwt.helper.js`

```js
const jwt = require('jsonwebtoken');

exports.generateToken = (payload) => {
  return jwt.sign(payload, process.env.JWT_SECRET, { expiresIn: '1d' });
}; 

```

## 🔁 Flujo de Comunicación entre Capas

En una arquitectura backend por capas, la comunicación sigue una jerarquía descendente, donde cada capa solo interactúa directamente con la capa que tiene inmediatamente por debajo.

Esto asegura una separación clara de responsabilidades (SoC - Separation of Concerns) y facilita el mantenimiento y escalabilidad del sistema.

### 📥 Flujo típico de una solicitud:

```plaintext
Cliente → Ruta → Controlador → Servicio → Modelo → Base de Datos
             ↑        ↑           ↑         ↑
        Respuesta ← Lógica ← Reglas ← Consulta

```

### 🔄 Descripción del flujo

**Cliente** (Frontend o herramienta como Postman):  
Envía una solicitud HTTP (`GET`, `POST`, `PUT`, `DELETE`) a una ruta de la API.

**Rutas (`routes/`):**  
Define el endpoint al que llega la solicitud y lo asocia con un controlador específico.

**Controladores (`controllers/`):**  
Reciben la solicitud, extraen datos y llaman al servicio correspondiente.

**Servicios (`services/`):**  
Aplican la lógica de negocio, validan reglas y se comunican con los modelos si es necesario.

**Modelos (`models/`):**  
Ejecutan operaciones de persistencia con la base de datos (consultas, inserciones, actualizaciones, eliminaciones).

**Base de Datos:**  
Retorna los datos al modelo, que lo devuelve al servicio, luego al controlador, y finalmente al cliente.

---

### ✅ Buenas prácticas

- **Nunca saltes capas**. Por ejemplo, los controladores **no deberían comunicarse directamente con los modelos**.
- **Mantén cada capa enfocada en una única responsabilidad.**
- **Evita lógica de negocio en los controladores o modelos.**

### Representación esquematica

[ Cliente ]
     |
     v
[ Rutas (routes) ]
     |
     v
[ Controladores (controllers) ]
     |
     v
[ Servicios (services) ]
     |
     v
[ Modelos (models) ]
     |
     v
[ Base de Datos ]


## 🧩 Conclusión

La implementación de un proyecto **backend utilizando Node.js** bajo una **arquitectura en capas** proporciona una base sólida para el desarrollo de aplicaciones web robustas, organizadas y escalables. Este enfoque permite separar claramente las responsabilidades de cada parte del sistema, lo que facilita su mantenimiento, evolución y prueba a lo largo del tiempo.

A lo largo de este documento se ha explorado:

- Qué es Node.js y por qué resulta una tecnología adecuada para el desarrollo del lado del servidor.
- Las diferencias fundamentales entre el entorno de ejecución del navegador y el de Node.js.
- La estructura de carpetas recomendada para un backend modular y limpio, incluyendo las capas de rutas, controladores, servicios, modelos, configuración, middlewares y utilidades.
- El flujo de comunicación entre capas, asegurando una interacción ordenada y desacoplada entre los distintos componentes del sistema.
- Ejemplos prácticos para cada capa, ilustrando su función específica dentro del proyecto.
- Buenas prácticas para evitar errores comunes y mantener un código limpio y escalable.
- La posibilidad de incorporar programación reactiva como una extensión moderna para manejar flujos de datos asíncronos y eventos.

El uso de esta arquitectura permite a los equipos de desarrollo trabajar de forma más eficiente, estandarizada y profesional. Cada capa está diseñada para cumplir con una única responsabilidad, lo que contribuye a reducir errores, mejorar la colaboración entre desarrolladores y facilitar futuras mejoras en el sistema.

📌 **Recomendación:** Para desarrolladores que inician en el backend o buscan aplicar estándares profesionales en sus aplicaciones, esta arquitectura representa una guía práctica y efectiva para construir software de calidad.

---
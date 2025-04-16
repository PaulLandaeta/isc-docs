# 🔹 1. Estándares de nomenclatura

Definir convenciones de nombres ayuda a mantener un código claro y fácil de entender.

## 📌 Nombres de archivos de prueba

### ✅ Formato recomendado:

| Herramienta           | Formato de nombre de archivo   |
|-----------------------|--------------------------------|
| Jest (unit/integration) | `nombreModulo.test.js`       |
| Cypress (E2E)         | `nombreEscenario.cy.js`       |
| Supertest (API)       | `nombreRecurso.test.js`       |

### ✅ Ejemplos correctos:

- Prueba unitaria de un controlador: **`userController.test.js`**
- Prueba de API con Supertest: **`auth.test.js`**
- Prueba E2E con Cypress: **`login.cy.js`**

### ❌ Evitar nombres genéricos como:

- `test1.js`
- `prueba.js`
- `misc.test.js`

# 🔹 2. Esructura recomendada

## 📌 Estructura de carpetas recomendada

```Play_text
/project-root
│── /src
│   ├── /controllers
│   ├── /services
│   ├── /models
│── /tests
│   ├── /unit          # Pruebas unitarias (Jest)
│   ├── /integration   # Pruebas de integración (Jest + Supertest)
│   ├── /e2e           # Pruebas End-to-End (Cypress)
│── cypress/           # Configuración específica de Cypress
│── jest.config.js
│── cypress.config.js
│── package.json

```

## ✅ Reglas clave:

- Separar pruebas **unitarias**, de **integración** y **E2E** en carpetas distintas.
- Colocar las pruebas en la **misma estructura** que el código fuente.  
  **Ejemplo:**  
  Si `userController.js` está en `/src/controllers`, su prueba debe estar en:  
  /tests/unit/controllers/userController.test.js
-Para pruebas de API con **Supertest**, usar `/tests/integration` o `/tests/api`.

# 🔹 3. Estructura del código dentro de cada prueba

## ✅ Formato recomendado:
```javascript
describe("Nombre del módulo o funcionalidad", () => {
  beforeAll(() => { /* Preparación global */ });
  beforeEach(() => { /* Preparación antes de cada test */ });

  test("Debe hacer X correctamente", () => {
    // Arrange (Preparación)
    // Act (Ejecución)
    // Assert (Verificación)
  });

  afterEach(() => { /* Limpieza después de cada test */ });
  afterAll(() => { /* Limpieza global */ });
});
```

## ✅ Ejemplo en Jest (Unit Test)
```javascript
describe("User Service", () => {
  test("Debe retornar un usuario por ID", async () => {
    const user = await getUserById(1);
    expect(user).toHaveProperty("id", 1);
  });
});

```
## ✅ Ejemplo en Cypress (E2E)
```javascript
describe("Prueba de login", () => {
  it("Debe iniciar sesión con credenciales correctas", () => {
    cy.visit("/login");
    cy.get("#email").type("test@example.com");
    cy.get("#password").type("123456");
    cy.get("#submit").click();
    cy.url().should("include", "/dashboard");
  });
});

```
## ✅ Ejemplo en Supertest (API Test)
```javascript
const request = require("supertest");
const app = require("../src/app");

describe("Auth API", () => {
  test("Debe registrar un usuario", async () => {
    const res = await request(app).post("/api/register").send({
      email: "test@example.com",
      password: "123456",
    });

    expect(res.statusCode).toBe(201);
    expect(res.body).toHaveProperty("token");
  });
});

```
# 🔹 4. Convenciones para nombres de pruebas

## 📌 Nombres descriptivos en pruebas

Las pruebas deben ser **claras y descriptivas**, respondiendo a **qué se espera que haga la función**.

### ✅ Ejemplo de nombres correctos:

✔ `"Debe registrar un usuario correctamente"`  
✔ `"Debe retornar error si la contraseña es inválida"`  
✔ `"Debe mostrar el dashboard después del login"`  

### ❌ Evitar nombres vagos como:

🚫 `"Prueba 1"`  
🚫 `"Funciona?"`  
🚫 `"Login ok"`  

# Cómo Reutilizar Código en Pruebas Automatizadas para Mayor Mantenibilidad

## 📌 Estrategia y Descripción

| Estrategia               | Descripción                                                |
|--------------------------|------------------------------------------------------------|
| **Helpers y utilidades**  | Funciones reutilizables para evitar código repetitivo.     |
| **Fixtures**              | Archivos JSON con datos de prueba predefinidos.            |
| **Hooks (before/after)**  | Configuración y limpieza automática en pruebas.            |
| **Page Object Model (POM)** | Separación de lógica de UI en pruebas de Cypress.          |
| **Factories**             | Generación de datos dinámicos en pruebas con Faker.js.     |

# 🔹 1. Uso de Helpers y Utilidades Comunes

Los **helpers** son funciones reutilizables para operaciones repetitivas, como la creación de datos de prueba o validaciones.

## ✅ Ejemplo de Helper en Jest (para pruebas unitarias e integración)
```javascript
// tests/utils/testHelpers.js
const generateUser = () => ({
  name: "John Doe",
  email: `test${Date.now()}@example.com`,
  password: "123456",
});

module.exports = { generateUser };

```
```javascript
// tests/unit/userService.test.js
const { generateUser } = require("../utils/testHelpers");
const { createUser } = require("../../src/services/userService");

describe("User Service", () => {
  test("Debe crear un usuario correctamente", async () => {
    const user = await createUser(generateUser());
    expect(user).toHaveProperty("id");
  });
});

```
## ✅ Ejemplo de Helper en Cypress
```javascript
// cypress/support/commands.js
Cypress.Commands.add("login", (email, password) => {
  cy.visit("/login");
  cy.get("#email").type(email);
  cy.get("#password").type(password);
  cy.get("#submit").click();
  cy.url().should("include", "/dashboard");
});

```
```javascript
// cypress/integration/auth.cy.js
describe("Autenticación", () => {
  it("Debe iniciar sesión correctamente", () => {
    cy.login("test@example.com", "123456");
  });
});

```
## ✅ Ejemplo de Helper en Supertest (para pruebas de API)
```javascript
// tests/utils/apiHelpers.js
const request = require("supertest");
const app = require("../../src/app");

const registerUser = async (userData) => {
  return request(app).post("/api/register").send(userData);
};

module.exports = { registerUser };

```
```javascript
// tests/integration/auth.test.js
const { registerUser } = require("../utils/apiHelpers");

describe("Registro de usuario", () => {
  test("Debe registrar un usuario con éxito", async () => {
    const res = await registerUser({
      email: "newuser@example.com",
      password: "123456",
    });

    expect(res.statusCode).toBe(201);
    expect(res.body).toHaveProperty("token");
  });
});
```
# 🔹 2. Uso de Fixtures para Datos de Prueba

Los fixtures son archivos JSON o JS con datos de prueba predefinidos para simular respuestas del backend o crear usuarios de prueba.

## ✅ Ejemplo en Jest y Supertest (Fixture JSON)
```javascript
// tests/fixtures/users.json
[
  { "name": "John Doe", "email": "john@example.com", "password": "123456" }
]
```
```javascript
// tests/integration/user.test.js
const users = require("../fixtures/users.json");

describe("Usuarios", () => {
  test("Debe crear un usuario desde fixture", async () => {
    const res = await request(app).post("/api/register").send(users[0]);
    expect(res.statusCode).toBe(201);
  });
});
```
## ✅ Ejemplo en Cypress (Fixture JSON)
```javascript
// cypress/fixtures/user.json
{
  "email": "test@example.com",
  "password": "123456"
}

```
```javascript
// cypress/integration/login.cy.js
describe("Login", () => {
  it("Debe iniciar sesión con usuario de fixture", function () {
    cy.fixture("user").then((user) => {
      cy.login(user.email, user.password);
    });
  });
});

```

# 🔹  3. Uso de Hooks para Preparación y Limpieza

Los hooks (beforeAll, beforeEach, afterEach, afterAll) permiten configurar y limpiar pruebas automáticamente.

## ✅ Ejemplo en Jest 
```javascript
beforeAll(async () => {
  await connectToDatabase();
});

afterAll(async () => {
  await disconnectFromDatabase();
});

```
## ✅ Ejemplo en Cypress 
```javascript
beforeEach(() => {
  cy.visit("/");
});

```
## ✅ Ejemplo en Supertest
```javascript
afterEach(async () => {
  await clearTestDatabase();
});

```
# 🔹  4. Creación de POM (Page Object Model) en Cypress

En pruebas E2E con Cypress, el Page Object Model (POM) ayuda a organizar código de pruebas separando lógica de UI.

## ✅Ejemplo de POM en Cypress
```javascript
// cypress/pages/LoginPage.js
class LoginPage {
  visit() {
    cy.visit("/login");
  }

  fillEmail(email) {
    cy.get("#email").type(email);
  }

  fillPassword(password) {
    cy.get("#password").type(password);
  }

  submit() {
    cy.get("#submit").click();
  }
}

export default new LoginPage();

```
```javascript
// cypress/integration/login.cy.js
import LoginPage from "../pages/LoginPage";

describe("Login", () => {
  it("Debe iniciar sesión correctamente", () => {
    LoginPage.visit();
    LoginPage.fillEmail("test@example.com");
    LoginPage.fillPassword("123456");
    LoginPage.submit();
    cy.url().should("include", "/dashboard");
  });
});

```

# 🔹   5. Uso de Factories para Generar Datos Dinámicos

Las factories permiten crear datos dinámicos en pruebas para evitar valores estáticos.

## ✅ Ejemplo en Jest con Faker.js

```javascript
// tests/factories/userFactory.js
const { faker } = require("@faker-js/faker");

const createUser = () => ({
  name: faker.person.fullName(),
  email: faker.internet.email(),
  password: faker.internet.password(),
});

module.exports = { createUser };
```
```javascript
// tests/unit/user.test.js
const { createUser } = require("../factories/userFactory");

describe("Usuarios", () => {
  test("Debe registrar un usuario con datos dinámicos", async () => {
    const newUser = createUser();
    const res = await request(app).post("/api/register").send(newUser);
    expect(res.statusCode).toBe(201);
  });
});
```
## ✅ Ejemplo en Cypress con Faker.js
```javascript
// cypress/integration/signup.cy.js
import { faker } from "@faker-js/faker";

describe("Registro", () => {
  it("Debe registrar un usuario con datos aleatorios", () => {
    cy.visit("/signup");
    cy.get("#name").type(faker.person.fullName());
    cy.get("#email").type(faker.internet.email());
    cy.get("#password").type("123456");
    cy.get("#submit").click();
    cy.url().should("include", "/dashboard");
  });
});
```
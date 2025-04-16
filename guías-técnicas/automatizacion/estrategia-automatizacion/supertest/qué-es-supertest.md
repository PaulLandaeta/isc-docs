# ¿Qué es Supertest?

Supertest es una librería para probar APIs en Node.js. Se utiliza junto con Jest u otros frameworks de pruebas para realizar pruebas de integración en aplicaciones backend. Entre sus beneficios destacan:

- Facilita el envío de solicitudes HTTP y la validación de respuestas.
- Se integra con Express y otros frameworks.
- Compatible con pruebas asíncronas utilizando promesas o `async/await`.
- Supertest se usa junto con Jest para probar APIs REST.

## Estructura recomendada
```Play_text
/tests
│── /api
│   ├── auth.test.js
│   ├── user.test.js
│── supertest.config.js
```

# Buenas prácticas

## ✅  Configurar una instancia de Supertest:
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
## ✅ Usar beforeAll y afterAll para preparar y limpiar datos de prueba.:
```javascript
beforeAll(async () => {
  // Conectar a la base de datos de pruebas
});

afterAll(async () => {
  // Cerrar la conexión
});

```
## ✅ Ejecutar pruebas en paralelo con Jest:
- npx jest --runInBand

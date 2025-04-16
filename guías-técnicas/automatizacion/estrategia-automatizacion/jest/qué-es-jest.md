# ¿Qué es Jest?

Jest es un framework de pruebas para JavaScript desarrollado por Facebook. Es ampliamente utilizado para pruebas unitarias y de integración en aplicaciones basadas en Node.js y React. Sus principales características incluyen:

- Ejecución rápida de pruebas con aislamiento de módulos.
- Soporte nativo para mocks y spies.
- Cobertura de código integrada.

## Estructura recomendada
```Play_text
/project-root
│── /src
│   ├── /controllers
│   │   ├── userController.js
│   │   ├── productController.js
│   ├── /services
│   ├── /models
│── /tests
│   ├── /unit
│   │   ├── userController.test.js
│   │   ├── productController.test.js
│   ├── /integration
│   │   ├── database.test.js
│── jest.config.js
│── package.json
```

# Buenas prácticas

## ✅ Organizar pruebas en carpetas:

- /unit → Pruebas de funciones individuales (controladores, servicios, modelos).
- /integration → Pruebas que validan la interacción entre módulos o con la base de datos.


## ✅ Usar `beforeEach` y `afterEach` para preparar y limpiar datos.
## ✅ Mocking de dependencias:

Usa `jest.mock()` para simular respuestas sin llamar servicios reales.

### Ejemplo:

```javascript
jest.mock('../services/userService', () => ({
  getUserById: jest.fn().mockResolvedValue({ id: 1, name: "John" }),
}));
```

## ✅ Cobertura de código:

Habilita la cobertura en jest.config.js:


```javascript
module.exports = {
  collectCoverage: true,
  coverageDirectory: "coverage",
};
```


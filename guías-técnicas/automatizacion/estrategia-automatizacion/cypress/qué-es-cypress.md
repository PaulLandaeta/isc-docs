
# ¿Qué es Cypress?

Cypress es una herramienta de pruebas de extremo a extremo (E2E) diseñada para aplicaciones web modernas. Se diferencia de otras herramientas al ejecutarse en el mismo ciclo de eventos del navegador, ofreciendo:

- Depuración en tiempo real con recarga automática.
- API sencilla y fácil de aprender.
- Captura automática de screenshots y videos de pruebas.

## Estructura recomendada
```Play_text
/cypress
│── /e2e
│   ├── login.cy.js
│   ├── signup.cy.js
│── /fixtures
│   ├── users.json
│── /support
│   ├── commands.js
│── cypress.config.js
│── package.json
```

# Buenas prácticas

## ✅ Usar cy.fixture() para manejar datos de prueba:
- En cypress/fixtures/users.json:

```javascript
{
  "validUser": { "email": "test@example.com", "password": "123456" }
}
```
- En la prueba:
```javascript
cy.fixture('users').then((users) => {
  cy.get('input[name="email"]').type(users.validUser.email);
  cy.get('input[name="password"]').type(users.validUser.password);
});
```
## ✅Usar cypress/support/commands.js para comandos reutilizables:
```javascript
Cypress.Commands.add("login", (email, password) => {
  cy.get("input[name='email']").type(email);
  cy.get("input[name='password']").type(password);
  cy.get("button[type='submit']").click();
});
```
## ✅ Ejecutar pruebas en modo headless para CI/CD:
- npx cypress run --browser chrome --headless

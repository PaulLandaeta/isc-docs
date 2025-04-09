# Patrones de Diseño en Automatización

## 1. Page Object Model (POM)

### 1.1 Descripción
El *Page Object Model* (POM) es un patrón de diseño estructural utilizado en pruebas automatizadas que separa la lógica de prueba de la estructura de la página web. Se basa en la creación de clases o módulos que representan páginas o componentes de la aplicación, encapsulando la interacción con los elementos de la interfaz en métodos reutilizables.

### 1.2 Ventajas del POM
- **Desacoplamiento del código de prueba:** Permite modificar la UI sin afectar la lógica de prueba.
- **Reutilización de código:** Facilita el uso de los mismos métodos en diferentes pruebas.
- **Mantenibilidad:** Hace que los cambios en la UI requieran modificaciones solo en un lugar.
- **Legibilidad y organización:** Mejora la claridad del código, separando la lógica de prueba de la interacción con la UI.

### 1.3 Ejemplo de Implementación en Selenium con JavaScript

```javascript
const { By } = require('selenium-webdriver');

class LoginPage {
  constructor(driver) {
    this.driver = driver;
    this.usernameInput = "#username";
    this.passwordInput = "#password";
    this.loginButton = "#login";
  }
  
  async login(username, password) {
    await this.driver.findElement(By.css(this.usernameInput)).sendKeys(username);
    await this.driver.findElement(By.css(this.passwordInput)).sendKeys(password);
    await this.driver.findElement(By.css(this.loginButton)).click();
  }
}

module.exports = LoginPage;
```
### 1.4 Beneficios del POM
- Reduce la redundancia de código.
- Facilita el mantenimiento de pruebas automatizadas.
- Mejora la legibilidad y organización del código.
- Permite reutilizar componentes de la interfaz en múltiples pruebas.
- Hace que las pruebas sean menos propensas a fallar ante cambios menores en la UI.
- Se integra fácilmente con frameworks de prueba como Jest, Mocha y TestNG.


## 2.Screenplay Pattern

### 2.1 Descripción
El Screenplay Pattern es un enfoque modular para automatización de pruebas que modela actores y tareas en lugar de interacciones directas con la UI. En lugar de trabajar con clases de páginas (POM), se utilizan Actores, Tareas e Interacciones, lo que mejora la reutilización del código y la expresividad de las pruebas.

### 2.2 Ventajas
- ✅ Facilita la lectura y mantenimiento de pruebas.
- ✅ Modulariza las interacciones, promoviendo la reutilización.
- ✅ Separa completamente la lógica de prueba de la UI.


### 2.3 Ejemplo de Implementación en Selenium con JavaScript

```javascript
const { By } = require('selenium-webdriver');

class Actor {
  constructor(driver) {
    this.driver = driver;
  }

  async attemptsTo(task) {
    await task.performAs(this);
  }
}

class LoginTask {
  constructor(username, password) {
    this.username = username;
    this.password = password;
  }

  async performAs(actor) {
    await actor.driver.findElement(By.id('username')).sendKeys(this.username);
    await actor.driver.findElement(By.id('password')).sendKeys(this.password);
    await actor.driver.findElement(By.id('login')).click();
  }
}

// Uso del patrón Screenplay
const driver = new (require('selenium-webdriver')).Builder().forBrowser('chrome').build();
const actor = new Actor(driver);
actor.attemptsTo(new LoginTask('usuario', 'contraseña'));

```

## 3. Command Pattern

### 3.1 Descripción
El Command Pattern encapsula solicitudes como objetos, permitiendo que los comandos sean ejecutados, almacenados y deshechos de manera flexible. En automatización de pruebas, se usa para definir acciones reutilizables en la UI sin que la prueba dependa directamente de los detalles de implementación.

### 3.2 Ventajas
- ✅ Desacopla la ejecución de comandos de su implementación.
- ✅ Facilita la reutilización y combinación de acciones.
- ✅ Permite registrar comandos para futuras repeticiones.

### 3.3 Ejemplo de Implementación con JavaScript

```javascript
const { By } = require('selenium-webdriver');

class Command {
  execute() {}
}

class ClickElement extends Command {
  constructor(selector) {
    super();
    this.selector = selector;
  }

  async execute(driver) {
    await driver.findElement(By.css(this.selector)).click();
  }
}

class EnterText extends Command {
  constructor(selector, text) {
    super();
    this.selector = selector;
    this.text = text;
  }

  async execute(driver) {
    await driver.findElement(By.css(this.selector)).sendKeys(this.text);
  }
}

// Uso del patrón Command
const driver = new (require('selenium-webdriver')).Builder().forBrowser('chrome').build();
const loginCommands = [
  new EnterText("#username", "testuser"),
  new EnterText("#password", "testpassword"),
  new ClickElement("#login")
];

(async () => {
  for (let command of loginCommands) {
    await command.execute(driver);
  }
})();
``` 

 
# 🟨 JavaScript Conventions

**Referencia:** [JavaScript Best Practices - Airbnb](https://github.com/airbnb/javascript) 

## Convenciones Generales
JavaScript es un lenguaje dinámico ampliamente utilizado en el desarrollo web. Para mantener un código limpio y legible, se deben seguir estas convenciones de codificación estándar:

- Evitar el uso de `var`; preferir `const` y `let`.
- Seguir la nomenclatura camelCase para variables y funciones.
- Mantener una estructura de código modular.
- Usar comentarios claros y útiles.

## Declaración de Variables
<p style="font-size: 16px;">En JavaScript, las variables deben declararse adecuadamente para evitar errores en tiempo de ejecución.</p>

```javascript
// ❌ Incorrect
var userName = "Lucia";

// ✅ Correct
const userName = "Lucia"; // No cambia
let userAge = 20; // Puede cambiar 
```

### Nombres de Variables
- <p style="font-size: 16px;">Utilizar nombres descriptivos y significativos.</p>
- <p style="font-size: 16px;">Evitar nombres genéricos como `temp`, `data` o `info`.</p>
- <p style="font-size: 16px;">Para constantes globales, usar SCREAMING_SNAKE_CASE.</p>

```javascript
// ❌ Incorrect
let x = 5;
const PI = 3.14; // No cumple con la convención

// ✅ Correct
let userScore = 100;
const MAX_USERS = 50;
```

## Funciones
JavaScript permite definir funciones de múltiples maneras. Se recomienda el uso de funciones **flecha (`=>`)** siempre que sea posible para mantener la sintaxis limpia y evitar problemas con `this`.

```javascript
// ❌ Incorrect (Uso de 'function')
function getUserName() {
  return "Lucia";
}

// ✅ Correct (Uso de funciones flecha)
const getUserName = () => "Lucia";
```

### **Parámetros y Valores por Defecto**
```javascript
// ❌ Incorrect (No se establecen valores por defecto)
function greetUser(name) {
  console.log("Hello, " + name);
}

// ✅ Correct (Valores por defecto en parámetros)
const greetUser = (name = "Guest") => {
  console.log(`Hello, ${name}!`);
}; 
```

## Estructuras de Control
<p style="font-size: 16px;">El uso de `if`, `switch`, y `for` debe ser claro y evitar redundancias.</p>

```javascript
// ❌ Incorrect
if (userRole === "admin") {
  hasAccess = true;
} else {
  hasAccess = false;
}

// ✅ Correct
const hasAccess = userRole === "admin"; 
```

## Manejo de Errores
<p style="font-size: 16px;">Siempre manejar errores con `try/catch` y evitar dependencias en errores silenciosos.</p>

```javascript
// ❌ Incorrect (No maneja errores)
const fetchData = async () => {
  const response = await fetch("https://api.example.com/data");
  return response.json();
};

// ✅ Correct (Manejo de errores)
const fetchData = async () => {
  try {
    const response = await fetch("https://api.example.com/data");
    return await response.json();
  } catch (error) {
    console.error("Error fetching data:", error);
  }
}; 
```

## Clases y Programación Orientada a Objetos (POO)
<p style="font-size: 16px;">JavaScript soporta clases con `class` para definir estructuras de datos más organizadas.</p>

```javascript
// ❌ Incorrect (Definición inconsistente)
function User(name, age) {
  this.name = name;
  this.age = age;
}

// ✅ Correct (Uso de clases y métodos)
class User {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  getDetails() {
    return `${this.name} tiene ${this.age} años`;
  }
}
const user = new User("Lucia", 20); 
```

## Buenas Prácticas Generales

✔ Usar `===` en lugar de `==` para comparaciones estrictas.

✔ Usar `map`, `filter` y `reduce` en lugar de `for` cuando sea posible.

✔ Evitar modificar objetos `prototype` en tiempo de ejecución.

✔ Usar `const` para funciones y objetos inmutables.  

✔ Organizar el código en módulos (`import/export`).

---

## Característica Única: **Prototipos y Herencia**
<p style="font-size: 16px;">JavaScript utiliza prototipos para manejar la herencia y reutilizar métodos entre objetos.</p>

```javascript
// ✅ Correct (Using Prototypal Inheritance)
function Animal(name) {
  this.name = name;
}

Animal.prototype.speak = function () {
  console.log(`${this.name} makes a sound`);
};

const dog = new Animal("Buddy");
dog.speak(); // Output: Buddy makes a sound
```

Siguiendo estas mejores prácticas, el código en JavaScript será más **limpio, mantenible y eficiente**.
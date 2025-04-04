# 🔵 TypeScript Conventions

**Referencia:** [TypeScript Best Practices - Dev.to](https://dev.to/sovannaro/typescript-best-practices-2025-elevate-your-code-quality-1gh3)

## Introducción
TypeScript es un superconjunto de JavaScript que añade tipado estático opcional y características avanzadas para mejorar la seguridad y mantenibilidad del código.

## Declaración de Tipos
<p style="font-size: 16px;">Usar anotaciones de tipo explícitas para evitar errores en tiempo de ejecución.</p>

```typescript
// ❌ Incorrect (No type specified)
let user;
user = "Lucia";

// ✅ Correct (Using explicit types)
let user: string;
user = "Lucia";
```

## Uso de `any` y Alternativas Seguras
Evita el uso de `any` siempre que sea posible y usa tipos específicos.

```typescript
// ❌ Incorrect (Using 'any')
let data: any;
data = 42;

// ✅ Correct (Using specific types)
let data: number;
data = 42;
```

## Interfaces y Tipos
<p style="font-size: 16px;">Las interfaces permiten definir estructuras claras para objetos y clases.</p>

```typescript
// ❌ Incorrect (Using an inline object)
const user = {
  name: "Lucia",
  age: 20,
};

// ✅ Correct (Using an interface)
interface User {
  name: string;
  age: number;
}
const user: User = { name: "Lucia", age: 20 };
```

## Genéricos
<p style="font-size: 16px;">Los genéricos permiten definir estructuras reutilizables sin perder tipado.</p>

```typescript
// ❌ Incorrect (Using 'any')
function getValue(value: any): any {
  return value;
}

// ✅ Correct (Using generics)
function getValue<T>(value: T): T {
  return value;
}
```

## Manejo de Errores
TypeScript recomienda el uso de `try/catch` con tipos específicos.

```typescript
// ❌ Incorrect (No error type specified)
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.log(error.message);
}

// ✅ Correct (Specifying error type)
try {
  throw new Error("Something went wrong");
} catch (error: unknown) {
  if (error instanceof Error) {
    console.log(error.message);
  }
}
```

## Clases y Programación Orientada a Objetos (POO)
TypeScript mejora la programación orientada a objetos con `private`, `public`, y `readonly`.

```typescript
// ❌ Incorrect (No access modifiers)
class User {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
}

// ✅ Correct (Using private and readonly)
class User {
  private readonly name: string;
  constructor(name: string) {
    this.name = name;
  }
  getName(): string {
    return this.name;
  }
}
```

## Buenas Prácticas Generales
✔ Usar `const` y `let` en lugar de `var`.  
✔ Evitar el uso de `any` a menos que sea estrictamente necesario.  
✔ Usar interfaces y tipos para estructurar datos.  
✔ Prefiere `readonly` cuando un valor no debe cambiar.  
✔ Implementa `strictNullChecks` para evitar errores de valores nulos.  
✔ Usa `async/await` en lugar de promesas encadenadas.  

## Característica Única: **Decoradores en TypeScript**
<p style="font-size: 16px;">TypeScript permite el uso de decoradores para modificar el comportamiento de clases y métodos.</p>

```typescript
// ✅ Correct (Uso de un decorador en TypeScript)
function Logger(target: Function) {
  console.log("Logging class: ", target);
}

@Logger
class User {
  constructor(public name: string) {}
}
```

---

Siguiendo estas convenciones, TypeScript garantizará código más seguro, robusto y escalable. 
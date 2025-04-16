# 🛠️ Helper

## Propósito

La carpeta `helper/` contiene **funciones específicas de apoyo** que encapsulan lógica común que no califica como `utils` genéricos ni como hooks, pero que **sí contribuyen a tareas del dominio** de la aplicación. Son funciones o fragmentos de lógica que ayudan a simplificar procesos dentro del contexto del negocio.

A diferencia de `utils`, los helpers pueden tener mayor relación con la estructura del sistema o incluso contener algunas dependencias más específicas (como manejo de rutas, formatos propios, reglas de validación, etc.).

## Importancia

🔹 Permite reutilizar lógica relacionada al negocio o a la presentación de datos.  
🔹 Reduce duplicación y mejora el orden interno del proyecto.  
🔹 Encapsula comportamientos útiles sin mezclarlos en componentes o hooks.

> Ejemplos comunes: `getInitialsFromName()`, `formatUserRole(role)`, `generateSlugFromTitle(title)`

## Buenas Prácticas

- Agrupar helpers por dominio o módulo si son muchos.  
- Evitar colocar lógica de estado o acceso directo a React.  
- Documentar la funcionalidad brevemente con JSDoc si es compleja.

## Ejemplo de funciones helper

```ts
// ✅ userHelper.ts
export const getInitials = (name: string): string => {
  return name
    .split(" ")
    .map((n) => n[0])
    .join("")
    .toUpperCase();
};

export const formatRole = (role: string): string => {
  switch (role) {
    case "admin": return "Administrator";
    case "user": return "User";
    default: return "Guest";
  }
};
```

```ts
// ❌ Incorrecto - Lógica directamente embebida en componentes
const Welcome = ({ name }) => {
  const initials = name.split(" ").map((n) => n[0]).join("").toUpperCase();
  return <p>Hello, {initials}</p>; // Difícil de mantener o reutilizar
};
```

## Ubicación esperada en el proyecto

```
src/
├── helper/
│   ├── userHelper.ts
│   └── stringHelper.ts
```

## Conclusión

La carpeta `helper/` ayuda a mantener la lógica limpia y modular, facilitando el mantenimiento y mejorando la cohesión interna del código. Es perfecta para comportamientos reutilizables ligados a reglas de negocio o presentación.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)

---

## Característica única

Una característica valiosa de los helpers es su capacidad de **traducir reglas de negocio específicas en funciones reutilizables**, manteniendo los componentes libres de lógica innecesaria. Esto aporta claridad, testabilidad y reusabilidad dentro del dominio de la aplicación.
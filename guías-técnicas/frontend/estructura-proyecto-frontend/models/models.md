# 🧾 Models

## Propósito

La carpeta `models/` contiene las **interfaces y tipos TypeScript** que definen las estructuras de datos utilizadas en toda la aplicación. Aquí se formalizan las formas que deben tener los objetos, respuestas de APIs, parámetros y estructuras de estado.

Esto permite asegurar **tipado estricto, autocompletado inteligente y validación estática** en tiempo de desarrollo.

## Importancia

🔹 Mejora la claridad del código al definir contratos de datos explícitos.  
🔹 Ayuda a prevenir errores comunes en la manipulación de datos.  
🔹 Facilita la documentación implícita del sistema.  
🔹 Potencia herramientas como VS Code y linters con autocompletado y refactorización segura.

> Ejemplo común: `User`, `Product`, `AuthResponse`, `ThemeConfig`, etc.

## Buenas Prácticas

- Nombrar los archivos con el nombre del modelo (por ejemplo: `User.ts`, `Product.ts`).
- Utilizar `interface` cuando se espera extender o implementar en el futuro.
- Usar `type` para uniones o tipos derivados más dinámicos.
- Agrupar los modelos por dominio cuando sea necesario (ej. `models/auth/User.ts`).

## Ejemplo de modelos

```ts
// ✅ User.ts
export interface User {
  id: string;
  name: string;
  email: string;
  role: "admin" | "user";
}

// ✅ AuthResponse.ts
export interface AuthResponse {
  token: string;
  user: User;
}
```

```ts
// ❌ Incorrecto - Uso de tipos implícitos y no centralizados
const user = {
  id: "1",
  name: "Mel",
  email: "mel@example.com",
};
```

## Ubicación esperada en el proyecto

```
src/
├── models/
│   ├── User.ts
│   ├── Product.ts
│   └── AuthResponse.ts
```

## Conclusión

La carpeta `models/` fortalece la calidad del código al proporcionar una base de tipado consistente en todo el proyecto. Su uso correcto mejora la experiencia del desarrollador, facilita la colaboración y reduce errores en tiempo de ejecución.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)

---

## Característica única

`models/` tiene el valor especial de actuar como **documentación viva del sistema**, ya que sus definiciones reflejan fielmente las estructuras que componen la lógica de negocio y la comunicación con servicios externos. Además, pueden compartirse fácilmente con backend u otras apps para garantizar integridad de datos.
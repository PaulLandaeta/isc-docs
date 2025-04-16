# 🧭 Routes

## Propósito

La carpeta `routes/` contiene la definición de todas las rutas de navegación dentro de la aplicación. 

Centralizar las rutas en una carpeta permite controlar de forma clara la estructura de navegación, evitando rutas duplicadas o inconsistentes. Además, mejora la mantenibilidad al tener todas las rutas en un solo lugar.

## Importancia

🔹 Define la arquitectura de navegación del proyecto.  
🔹 Evita la repetición de strings y rutas hardcodeadas.  
🔹 Facilita la implementación de rutas protegidas (con autenticación), redirecciones, layouts por secciones, etc.

> Por ejemplo, rutas como `/login`, `/dashboard`, `/profile`, etc. pueden centralizarse aquí.

## Buenas Prácticas

- Utilizar un archivo `routes.ts` para almacenar todas las rutas como constantes.
- Crear una estructura jerárquica si hay rutas con subrutas.
- Tipar las rutas si es necesario para evitar errores.

## Ejemplo de definición de rutas

```ts
// ✅ routes.ts - Rutas centralizadas
export const ROUTES = {
  HOME: "/",
  LOGIN: "/login",
  DASHBOARD: "/dashboard",
  PROFILE: "/profile",
};
```

```tsx
// ✅ Uso en React Router
import { Route, Routes } from "react-router-dom";
import { ROUTES } from "./routes";

<Routes>
  <Route path={ROUTES.HOME} element={<HomePage />} />
  <Route path={ROUTES.LOGIN} element={<LoginPage />} />
</Routes>
```

```tsx
// ❌ Incorrecto - Strings hardcodeadas y sin organización
<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/login" element={<Login />} />
  <Route path="/dashboard" element={<Dashboard />} />
</Routes>
```

## Ubicación esperada en el proyecto

```
src/
├── routes/
│   └── routes.ts
```

## Conclusión

La carpeta `routes/` mejora la organización de la navegación en el frontend. Al centralizar las rutas, se evita la redundancia y se facilita el mantenimiento de la estructura de la aplicación. Además, permite implementar estrategias como rutas protegidas, lazy loading, y layouts compartidos de forma más controlada.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
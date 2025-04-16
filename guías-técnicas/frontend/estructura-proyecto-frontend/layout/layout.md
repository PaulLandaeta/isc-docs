# 🧩 Layout

## Propósito

La carpeta `layout/` contiene los **componentes estructurales** del proyecto, es decir, aquellos que definen la disposición visual global de la aplicación: encabezados, barras laterales, pies de página, wrappers de rutas, etc.

Estos componentes proporcionan una base reutilizable para que todas las páginas compartan una misma estructura visual y de navegación.

## Importancia

🔹 Mantiene la coherencia visual entre diferentes páginas.  
🔹 Facilita la aplicación de estilos globales y wrappers comunes.  
🔹 Permite separar las responsabilidades de estructura de contenido dinámico.

> Ejemplo: un `MainLayout` que incluye `Navbar`, `Sidebar` y un `Outlet` para el contenido de la ruta.

## Buenas Prácticas

- Crear layouts reutilizables como `AuthLayout`, `DashboardLayout`, etc.  
- Utilizar `<Outlet />` de `react-router-dom` para renderizar contenido dinámico.  
- Usar composition de componentes para mejorar flexibilidad.  
- Mantener los layouts simples, sin lógica de negocio.

## Ejemplo de layout base

```tsx
// ✅ MainLayout.tsx
import { Outlet } from "react-router-dom";
import Navbar from "../components/Navbar";
import Footer from "../components/Footer";

const MainLayout = () => {
  return (
    <div>
      <Navbar />
      <main>
        <Outlet />
      </main>
      <Footer />
    </div>
  );
};

export default MainLayout;
```

```tsx
// ❌ Incorrecto - Layout sin reutilización ni estructura clara
const Layout = ({ children }) => {
  return <div>{children}</div>; // No tiene encabezado, pie ni composición real
};
```

## Ubicación esperada en el proyecto

```
src/
├── layout/
│   ├── MainLayout.tsx
│   ├── AuthLayout.tsx
│   └── DashboardLayout.tsx
```

## Conclusión

La carpeta `layout/` permite construir interfaces consistentes, organizadas y reutilizables. Centralizar la estructura de la aplicación mejora la experiencia del usuario y simplifica el mantenimiento del frontend.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)

---

## Característica única

Una característica especial de `layout/` es que **actúa como puente entre las rutas y la interfaz visual compartida**, permitiendo que múltiples páginas reutilicen la misma estructura sin duplicación de código. Esto es esencial para mantener la coherencia visual y separar correctamente las capas de presentación. 🧱
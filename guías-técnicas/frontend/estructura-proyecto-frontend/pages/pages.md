# 📄 Pages

## Propósito

La carpeta `pages/` contiene las **vistas principales de la aplicación**, es decir, cada página que representa una ruta definida (por ejemplo: `/login`, `/home`, `/profile`, etc.). Estas páginas se encargan de componer la interfaz usando los componentes necesarios y pueden conectarse con la lógica del store, hooks, o servicios.

Organizar las páginas en esta carpeta ayuda a separar claramente las **vistas** del resto de la lógica de negocio o componentes reutilizables.

## Importancia

🔹 Mejora la estructura general de la aplicación al separar rutas y vistas.  
🔹 Facilita la navegación y escalabilidad del proyecto.  
🔹 Ayuda a mantener limpio el código, organizando cada página por responsabilidad.

> Ejemplos comunes: `LoginPage.tsx`, `DashboardPage.tsx`, `UserProfilePage.tsx`

## Buenas Prácticas

- Nombrar cada archivo de página con el sufijo `Page` para diferenciarlas de componentes (`HomePage.tsx`).
- Separar la lógica de UI en componentes reutilizables cuando sea necesario.
- Evitar sobrecargar las páginas con demasiada lógica (delegar a hooks o servicios).
- Crear subcarpetas si una página requiere archivos auxiliares (como estilos o subcomponentes).

## Ejemplo básico de una página

```tsx
// ✅ DashboardPage.tsx
import { useEffect } from "react";
import { useFetch } from "../hooks/useFetch";
import { ROUTES } from "../routes/routes";
import DashboardCard from "../components/DashboardCard";

const DashboardPage = () => {
  const { data, loading } = useFetch("/api/dashboard");

  return (
    <div>
      <h1>Dashboard</h1>
      {loading ? <p>Loading...</p> : <DashboardCard data={data} />}
    </div>
  );
};

export default DashboardPage;
```

```tsx
// ❌ Incorrecto - Lógica mezclada y sin organización
const Dashboard = () => {
  const [info, setInfo] = useState(null);
  useEffect(() => {
    fetch("/api/dashboard")
      .then((res) => res.json())
      .then(setInfo);
  }, []);
  return <div>{JSON.stringify(info)}</div>;
};
```

## Ubicación esperada en el proyecto

```
src/
├── pages/
│   ├── LoginPage.tsx
│   ├── DashboardPage.tsx
│   └── ProfilePage.tsx
```

## Conclusión

La carpeta `pages/` representa las vistas principales de la aplicación y actúa como puente entre la lógica y la interfaz. Mantener esta carpeta bien organizada garantiza una experiencia de desarrollo fluida y mejora la escalabilidad del sistema.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
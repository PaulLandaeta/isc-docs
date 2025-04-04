# ⚡ Hooks

## Propósito

La carpeta `hooks/` contiene **custom hooks** (hooks personalizados) que encapsulan lógica reutilizable que puede ser compartida entre varios componentes.

Los hooks permiten separar la lógica del estado, efectos secundarios, peticiones a APIs y otras funciones del ciclo de vida de los componentes sin necesidad de usar clases. Al centralizar esta lógica en una carpeta específica, se mejora la escalabilidad y mantenibilidad del proyecto.

## Importancia

🔹 Los hooks permiten **reducir la duplicación de código** y mejorar la reutilización.  
🔹 Ayudan a mantener los componentes más limpios y enfocados en la presentación.  
🔹 Son clave en proyectos con lógica compleja (autenticación, manejo de formularios, sincronización con APIs).

> Ejemplos comunes: `useAuth`, `useFetch`, `useForm`, `useTheme`

## Buenas Prácticas

- Los nombres de los hooks deben comenzar con **"use"** obligatoriamente (`useNombre`).
- Mantener los hooks **puros y reutilizables**, sin depender de props ni estados externos.
- Tipar correctamente los estados, retornos y parámetros.
- Colocar cada hook en su propio archivo y usar nombres descriptivos.

## ✨ Ejemplo de hook personalizado

```tsx
// ✅ Correcto - Hook para obtener datos de una API
import { useState, useEffect } from "react";

export function useFetch<T>(url: string) {
  const [data, setData] = useState<T | null>(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(url)
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      });
  }, [url]);

  return { data, loading };
}
```

```tsx
// ❌ Incorrecto - Hook sin nombre adecuado y sin tipado
function fetcher() {
  const [info, setInfo] = useState(null);
  useEffect(() => {
    fetch("/api/data")
      .then(res => res.json())
      .then(setInfo);
  }, []);
  return info;
}
```

## Ubicación esperada en el proyecto

```
src/
├── hooks/
│   ├── useAuth.ts
│   ├── useFetch.ts
```

## Conclusión

La carpeta `hooks/` centraliza la lógica reutilizable y abstrae comportamientos comunes, facilitando el desarrollo limpio y modular. Su correcto uso permite que los componentes sean más simples y enfocados exclusivamente en la presentación visual.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
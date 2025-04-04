# 🔧 Services

## Propósito

La carpeta `services/` centraliza la lógica relacionada con **llamadas a APIs**, **autenticación**, y otras funciones de negocio que se comunican con fuentes de datos externas. 

Separar estos servicios permite desacoplar la lógica de negocio de los componentes, facilitando el mantenimiento, las pruebas y la reutilización del código en diferentes partes de la aplicación.

## Importancia

🔹 Es una carpeta **clave** en cualquier arquitectura bien estructurada.  
🔹 Facilita la implementación de principios como **Single Responsibility** y **Separation of Concerns**.  
🔹 Permite gestionar mejor la configuración global de peticiones (headers, tokens, errores, etc).

> Ejemplos comunes: `auth.ts`, `api.ts`, `userService.ts`

## Buenas Prácticas

- Utilizar librerías como **Axios** para manejar las peticiones HTTP.
- Definir una instancia base de Axios con configuración común (`baseURL`, headers, interceptors).
- Mantener cada servicio en un archivo separado según su propósito.
- Evitar lógica de UI en los servicios.

## Ejemplo de configuración y servicio

```ts
// ✅ api.ts - Instancia base de Axios
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.example.com",
  headers: {
    "Content-Type": "application/json",
  },
});

export default api;
```

```ts
// ✅ auth.ts - Servicio de autenticación
import api from "./api";

export const login = async (email: string, password: string) => {
  const response = await api.post("/login", { email, password });
  return response.data;
};
```

```ts
// ❌ Incorrecto - Lógica mezclada y sin instancias centralizadas
const login = async (email, password) => {
  const response = await fetch("https://api.example.com/login", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ email, password }),
  });
  return await response.json();
};
```

## Ubicación esperada en el proyecto

```
src/
├── services/
│   ├── api.ts
│   ├── auth.ts
│   ├── userService.ts
```

## Conclusión

La carpeta `services/` ayuda a estructurar y centralizar toda la lógica relacionada con la comunicación externa. Su uso correcto mejora la mantenibilidad del proyecto, promueve la reutilización y evita la duplicación de código en los componentes.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
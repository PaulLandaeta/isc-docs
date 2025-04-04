## ⚙️ Configuración

La carpeta `src/config/` es donde se almacenan los archivos de configuración del proyecto, como variables de entorno, rutas de la aplicación y otras configuraciones globales. Esta carpeta es esencial para mantener un código organizado y fácil de mantener.

### Estructura de la Carpeta de Configuración

```
/src/config/
├── env.ts # Variables de entorno
└── routes.ts # Definición de rutas de la app
```

### Buenas Prácticas para Configuración

1. **Separar la configuración del código de negocio**:  
   Mantener los archivos de configuración en una carpeta separada ayuda a evitar el hardcoding y facilita la modificación de valores sin afectar la lógica del negocio.

2. **Centralizar las rutas de la aplicación**:  
   Definir todas las rutas en un solo archivo (por ejemplo, `routes.ts`) evita duplicar código y facilita el mantenimiento.

3. **Usar variables de entorno**:  
   Las variables de entorno deben estar centralizadas en un archivo (por ejemplo, `env.ts`) para facilitar su acceso y modificación.

### Ejemplo de Archivo de Variables de Entorno

```typescript
// src/config/env.ts
export const ENV = {
  API_URL: import.meta.env.VITE_API_URL || "https://api.example.com",
  MODE: import.meta.env.MODE || "development",
  IS_PRODUCTION: import.meta.env.MODE === "production",
};
```
## Ejemplo de Archivo de Rutas

```typescript
// src/config/routes.ts
export const ROUTES = {
  HOME: "/",
  LOGIN: "/login",
  DASHBOARD: "/dashboard",
  PROFILE: "/profile",
  SETTINGS: "/settings",
};
```
## Uso de la configuración en Componentes
Aquí tienes un ejemplo de cómo usar las rutas y variables de entorno en un componente

```typescript
import React from "react";
import { ROUTES } from "../config/routes";
import { ENV } from "../config/env";

const Navbar: React.FC = () => {
  return (
    <nav>
      <ul>
        <li>
          <a href={ROUTES.HOME}>Inicio</a>
        </li>
        <li>
          <a href={ROUTES.LOGIN}>Iniciar Sesión</a>
        </li>
        <li>
          <a href={ROUTES.DASHBOARD}>Dashboard</a>
        </li>
      </ul>
      <p>Modo actual: {ENV.MODE}</p>
    </nav>
  );
};

export default Navbar;
```
## Beneficios de Usar una Carpeta de Configuración
- **Organización:** Mantener todos los archivos de configuración en una sola carpeta facilita su localización y modificación.

- **Evitar hardcoding:** Al centralizar valores como rutas y variables de entorno, se evita repetir código y se facilita el mantenimiento.

- **Facilidad de cambios:** Si necesitas cambiar una ruta o una variable de entorno, solo debes hacerlo en un solo lugar.

- **Escalabilidad:** Una estructura bien organizada de configuración permite que el proyecto crezca sin volverse caótico.

- **Colaboración en equipo:** Una configuración centralizada facilita que todos los miembros del equipo sigan las mismas convenciones.
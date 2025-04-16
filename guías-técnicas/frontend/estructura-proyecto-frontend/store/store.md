# 🏬 Store

## Propósito

La carpeta `store/` centraliza toda la **gestión de estado global** de la aplicación. Aquí se definen los **slices, reducers, acciones y configuración del store**, usualmente utilizando librerías como **Redux Toolkit**, **Zustand**, o **Jotai**.

Esta arquitectura permite compartir estados entre múltiples componentes sin necesidad de prop drilling o estructuras complicadas.

## Importancia

🔹 Permite manejar datos globales como el usuario autenticado, tokens, temas, notificaciones, etc.  
🔹 Evita la duplicación de lógica de estado en múltiples componentes.  
🔹 Mejora la escalabilidad y mantenibilidad en aplicaciones medianas o grandes.

> Ejemplos comunes: `authSlice`, `themeSlice`, `cartSlice`

## Buenas Prácticas

- Usar **Redux Toolkit** para evitar boilerplate innecesario.  
- Tipar correctamente el estado y las acciones.  
- Dividir el estado en **slices** separados por contexto.  
- Mantener los efectos secundarios (como llamadas a API) en `thunks` u otros middleware.

## Ejemplo de implementación con Redux Toolkit

```ts
// ✅ authSlice.ts
import { createSlice, PayloadAction } from "@reduxjs/toolkit";

interface AuthState {
  isAuthenticated: boolean;
  token: string | null;
}

const initialState: AuthState = {
  isAuthenticated: false,
  token: null,
};

const authSlice = createSlice({
  name: "auth",
  initialState,
  reducers: {
    login: (state, action: PayloadAction<string>) => {
      state.isAuthenticated = true;
      state.token = action.payload;
    },
    logout: (state) => {
      state.isAuthenticated = false;
      state.token = null;
    },
  },
});

export const { login, logout } = authSlice.actions;
export default authSlice.reducer;
```

## Ubicación esperada en el proyecto

```
src/
├── store/
│   ├── index.ts        # Configuración del store
│   ├── authSlice.ts    # Estado de autenticación
│   └── themeSlice.ts   # Estado de tema visual
```

## Conclusión

La carpeta `store/` es fundamental para organizar y escalar el estado global de la aplicación. Su uso adecuado evita la complejidad en la gestión de datos compartidos y contribuye a una arquitectura limpia y sostenible.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
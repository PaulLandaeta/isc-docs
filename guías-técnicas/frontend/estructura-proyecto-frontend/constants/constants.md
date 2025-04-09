# 🧱 Constants

## Propósito

La carpeta `constants/` contiene todas las **constantes globales** utilizadas en el proyecto. Estas constantes pueden incluir nombres de acciones, textos estáticos, claves de configuración, colores, mensajes de error, entre otros.

Centralizar estas constantes mejora la mantenibilidad del proyecto y evita la repetición o errores al escribir valores duplicados.

## Importancia

🔹 Evita el uso de "magic strings" o valores repetidos dispersos en el código.  
🔹 Facilita actualizaciones rápidas en un solo lugar.  
🔹 Mejora la legibilidad y organización del código.  

> Ejemplos de constantes comunes: tipos de usuario, estados del sistema, mensajes predefinidos.

## Buenas Prácticas

- Organizar las constantes por tipo o contexto (por ejemplo: `messages.ts`, `roles.ts`, `env.ts`).
- Nombrar las constantes en **SCREAMING_SNAKE_CASE**.
- Exportar cada conjunto de constantes de manera modular.
- Evitar constantes innecesarias o que solo se usan una vez.

## Ejemplo de implementación

```ts
// ✅ messages.ts
export const MESSAGES = {
  ERROR_LOGIN: "Invalid username or password.",
  SUCCESS_LOGOUT: "You have been logged out successfully.",
};
```

```ts
// ✅ roles.ts
export const ROLES = {
  ADMIN: "admin",
  USER: "user",
};
```

```ts
// ❌ Incorrecto - Magic strings en el código
if (user.role === "admin") {
  // ...
}
```

## Ubicación esperada en el proyecto

```
src/
├── constants/
│   ├── messages.ts
│   ├── roles.ts
│   └── env.ts
```

## Conclusión

La carpeta `constants/` es esencial para mantener la coherencia y limpieza del código. Agrupar valores constantes mejora la mantenibilidad del proyecto y reduce la probabilidad de errores humanos durante el desarrollo.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
# 🎨 Theme

## Propósito

La carpeta `theme/` contiene la **configuración visual y estilística global** del proyecto. Aquí se definen temas, paletas de colores, tamaños de fuente, estilos globales y configuración de diseño responsivo.

Centralizar esta información permite mantener coherencia visual en toda la aplicación y facilita actualizaciones rápidas al estilo general.

## Importancia

🔹 Permite personalizar el aspecto de la interfaz de forma controlada.  
🔹 Mejora la escalabilidad visual en proyectos que crecen en complejidad.  
🔹 Facilita el soporte para múltiples temas (como modo oscuro o claro).

> Comúnmente se define un `defaultTheme`, variables de estilo y tipografía en esta carpeta.

## Buenas Prácticas

- Mantener el theme como **objeto exportable** reutilizable en librerías como styled-components, Chakra UI o MUI.  
- Tipar correctamente los objetos del tema.  
- Evitar estilos inline y repetitivos dentro de los componentes.

## Ejemplo básico de configuración de tema

```ts
// ✅ theme.ts
export const theme = {
  colors: {
    primary: "#3498db",
    secondary: "#2ecc71",
    text: "#333",
    background: "#f5f5f5",
  },
  fontSizes: {
    small: "0.8rem",
    medium: "1rem",
    large: "1.5rem",
  },
};
```

```ts
// ✅ Uso del tema (ej. con styled-components)
import styled from "styled-components";

const Title = styled.h1`
  color: ${({ theme }) => theme.colors.primary};
  font-size: ${({ theme }) => theme.fontSizes.large};
`;
```

```ts
// ❌ Incorrecto - Colores hardcodeados
const Title = styled.h1`
  color: #3498db;
  font-size: 1.5rem;
`;
```

## Ubicación esperada en el proyecto

```
src/
├── theme/
│   ├── theme.ts
│   └── colors.ts
```

## Conclusión

La carpeta `theme/` estandariza la identidad visual del proyecto, facilitando un desarrollo consistente, escalable y preparado para soportar diferentes estilos. Centralizar el diseño mejora tanto la experiencia de usuario como la productividad del equipo de desarrollo.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
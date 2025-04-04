# 📁 Components

## Propósito

La carpeta `components/` contiene todos los **componentes reutilizables de la interfaz de usuario (UI)**. Estos componentes encapsulan bloques visuales funcionales del sistema, permitiendo que puedan reutilizarse en múltiples vistas sin necesidad de reescribir código.

En proyectos con **React** y **TypeScript**, separar los componentes en esta carpeta facilita el desarrollo modular, mejora la organización y mantiene el código limpio y escalable. Además, promueve la separación de responsabilidades al mantener la lógica de presentación independiente de la lógica de negocio.

## Importancia

🔹 Esta carpeta es **fundamental** en cualquier proyecto React bien estructurado.
🔹 Permite una mayor reutilización de código.
🔹 Mejora la legibilidad y mantenibilidad del sistema.
🔹 Permite realizar pruebas unitarias de componentes específicos de manera más sencilla.

> Ejemplo de componentes comunes:
> - Botones (`Button.tsx`)
> - Tarjetas (`Card.tsx`)
> - Encabezados o barras de navegación (`Navbar.tsx`)
> - Elementos de formulario (`Input.tsx`, `Checkbox.tsx`)

## Buenas Prácticas

- Cada componente debe estar en su **propio archivo**.
- Usar **nombres descriptivos** y en PascalCase (ej: `UserProfile.tsx`).
- Tipar los `props` utilizando interfaces o types.
- Dividir componentes complejos en subcomponentes más pequeños.
- Mantener la carpeta organizada: se puede usar una estructura en subdirectorios si es necesario.

```bash
src/
└── components/
    ├── Button.tsx
    ├── Card.tsx
    ├── Navbar/
    │   ├── Navbar.tsx
    │   └── Navbar.module.css
```

## Ejemplo de implementación

```tsx
// ✅ Correcto - Componente tipado y claro
interface ButtonProps {
  label: string;
  onClick: () => void;
}

export const Button: React.FC<ButtonProps> = ({ label, onClick }) => {
  return <button onClick={onClick}>{label}</button>;
};
```

```tsx
// ❌ Incorrecto - Sin tipado ni estructura clara
export default function Button(props) {
  return <button>{props.label}</button>;
}
```

## Consejos adicionales

- Utiliza librerías como `classnames` para gestionar múltiples clases CSS.
- Agrega pruebas unitarias con herramientas como `Jest` o `React Testing Library`.
- Documenta los props usando comentarios o herramientas como Storybook.

## Ubicación esperada en el proyecto

```
src/
├── components/
│   ├── Button.tsx
│   ├── Card.tsx
│   └── Navbar/
│       ├── Navbar.tsx
│       └── Navbar.module.css
```

## Conclusión

La carpeta `components/` es un núcleo esencial de la estructura de un proyecto frontend con React. Permite encapsular la UI de manera organizada, reutilizable y mantenible. Una buena arquitectura de componentes no solo acelera el desarrollo, sino que mejora la experiencia del equipo en su conjunto.

Implementar buenas prácticas desde el inicio garantiza un producto escalable, limpio y robusto a largo plazo.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)
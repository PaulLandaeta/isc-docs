# 🧮 Utils

## Propósito

La carpeta `utils/` almacena funciones auxiliares o utilitarias reutilizables que cumplen tareas específicas y repetitivas a lo largo de la aplicación. Estas funciones no dependen del estado de la interfaz y pueden ser usadas en cualquier parte del proyecto.

Organizar estas funciones en `utils/` permite evitar la duplicación de lógica y mantener el código más limpio, modular y DRY (Don't Repeat Yourself).

## Importancia

🔹 Centraliza lógica que no pertenece directamente a un componente o servicio.  
🔹 Aumenta la reusabilidad del código.  
🔹 Mejora el testeo unitario y la mantenibilidad del proyecto.

> Ejemplos típicos: formateadores de fecha, validadores, cálculos matemáticos, generadores de tokens.

## Buenas Prácticas

- Dividir las funciones por tipo (por ejemplo: `dateUtils.ts`, `stringUtils.ts`, `arrayUtils.ts`).
- Nombrar las funciones de forma descriptiva.
- Mantener funciones puras (sin efectos secundarios ni dependencias globales).
- Agregar pruebas unitarias si es posible.

## Ejemplos de funciones en `utils`

```ts
// ✅ dateUtils.ts
export const formatDate = (date: string): string => {
  return new Date(date).toLocaleDateString("en-US");
};

export const getYear = (): number => new Date().getFullYear();
```

```ts
// ✅ stringUtils.ts
export const capitalize = (text: string): string => {
  return text.charAt(0).toUpperCase() + text.slice(1);
};
```

```ts
// ❌ Incorrecto - Funciones dentro de componentes (difíciles de reutilizar)
const formatDate = (date: string) => {
  return new Date(date).toLocaleDateString("en-US");
};
```

## Ubicación esperada en el proyecto

```
src/
├── utils/
│   ├── dateUtils.ts
│   ├── stringUtils.ts
│   └── mathUtils.ts
```

## Conclusión

La carpeta `utils/` es esencial para mantener una base de código limpia y eficiente. Gracias a ella, es posible abstraer lógica repetitiva, fomentar la reutilización y lograr una arquitectura más escalable y probada.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)

---

## Característica única

Una ventaja clave de la carpeta `utils/` es que sus funciones pueden ser **totalmente independientes del contexto de React**, lo que las hace ideales para pruebas unitarias, uso en múltiples proyectos y compartición como bibliotecas utilitarias externas. Son bloques reutilizables que no dependen del entorno donde se usan. 
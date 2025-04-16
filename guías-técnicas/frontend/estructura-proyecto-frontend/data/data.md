# 🗃️ Data

## Propósito

La carpeta `data/` contiene archivos con datos estáticos o precargados que se utilizan en distintas partes del proyecto. Estos datos pueden estar en formato JSON, objetos exportados, listas de constantes, configuraciones locales, etc.

Este enfoque permite **separar la lógica del contenido**, facilitando su reutilización, edición y escalabilidad.

## Importancia

🔹 Centraliza la información estructurada del proyecto.  
🔹 Evita tener datos quemados (hardcodeados) dentro de los componentes.  
🔹 Permite modificar contenido sin alterar la lógica funcional.  
🔹 Útil para prototipos, pruebas o versiones offline.

> Ejemplos comunes: listas de opciones, textos informativos, rutas estáticas, configuraciones visibles, contenido de UI.

## Buenas Prácticas

- Usar nombres descriptivos como `faqData.ts`, `plans.ts`, `featuresList.ts`.  
- Organizar los datos en objetos o arrays bien estructurados.  
- No mezclar datos con lógica de presentación o lógica de negocio.  
- Usar JSON solo si no es necesario procesarlos dentro del proyecto (por ejemplo, al cargarlos dinámicamente).

## Ejemplo de uso de `data/`

```ts
// ✅ featuresList.ts
export const features = [
  {
    title: "Fast Performance",
    description: "Vite enables lightning-fast hot module replacement."
  },
  {
    title: "Typed Safety",
    description: "TypeScript provides confidence and better DX."
  }
];
```

```ts
// ❌ Incorrecto - Datos quemados dentro del componente
const Features = () => (
  <ul>
    <li>Fast Performance - Vite enables lightning-fast hot module replacement.</li>
    <li>Typed Safety - TypeScript provides confidence and better DX.</li>
  </ul>
);
```

## Ubicación esperada en el proyecto

```
src/
├── data/
│   ├── faqData.ts
│   ├── plans.ts
│   └── featuresList.ts
```

## Conclusión

La carpeta `data/` mejora la organización del contenido estático, separándolo de la lógica de presentación. Esto permite reutilización, edición más sencilla y escalabilidad del código fuente, especialmente en proyectos que manejan múltiples bloques de contenido.

---

> Referencia utilizada: [Understanding the Vite Project Structure](https://dev.to/theprinceofprogramming/understanding-the-vite-project-structure-28jp)

---

## Característica única

`data/` permite **aislar contenido editable o estructurado del código funcional**, lo cual es especialmente útil en proyectos que requieren internacionalización, múltiples versiones o separación de responsabilidades entre devs y creadores de contenido. 
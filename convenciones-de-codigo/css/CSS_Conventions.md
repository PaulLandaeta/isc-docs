# 🔵 CSS Conventions

**Referencia:** [CSS Best Practices - Andre de Sousa](https://github.com/andredesousa/css-best-practices)

## Introducción
CSS (Cascading Style Sheets) define la apariencia de los elementos HTML en la web. Aplicar buenas prácticas mejora la mantenibilidad y la coherencia del diseño.

## Organización del Código
<p style="font-size: 16px;">Mantener el código ordenado mejora su legibilidad y mantenimiento.</p>

```css
/* ❌ Incorrect (CSS sin organización) */
h1 {
  color: red;
}
p {
  font-size: 16px;
}

/* ✅ Correct (Usar variables y una estructura clara) */
:root {
  --primary-color: #ff5733;
  --text-size: 16px;
}

h1 {
  color: var(--primary-color);
}
p {
  font-size: var(--text-size);
}
```

## Nomenclatura y Selectores
<p style="font-size: 16px;">Usar convenciones de nombres como BEM (Block Element Modifier) para mayor claridad.</p>

```css
/* ❌ Incorrect (Nombres genéricos) */
.container div {
  color: blue;
}

/* ✅ Correct (Uso de BEM) */
.card__title {
  color: blue;
}
```

## Flexbox y Grid para Diseño Responsivo
Usar `display: flex` y `display: grid` en lugar de `float`.

```css
/* ❌ Incorrect (Uso de float) */
.container {
  float: left;
  width: 50%;
}

/* ✅ Correct (Uso de flexbox) */
.container {
  display: flex;
  justify-content: space-between;
}
```

## Evitar el Uso de `!important`
`!important` debe evitarse siempre que sea posible para mantener la especificidad del CSS.

```css
/* ❌ Incorrect */
h1 {
  color: red !important;
}

/* ✅ Correct */
h1 {
  color: var(--primary-color);
}
```

## Buenas Prácticas Generales

✔ Usar variables CSS (`:root { --color: #333; }`).  
✔ Evitar selectores muy específicos que dificulten la reutilización del código.  
✔ Usar `rem` y `em` en lugar de `px` para tamaños responsivos.  
✔ Mantener una estructura modular en los archivos CSS.  
✔ Aplicar `minify` en archivos CSS en producción.  

## Característica Única: **Dark Mode y Temas**
<p style="font-size: 16px;">Se recomienda implementar variables CSS para un modo oscuro sin reescribir estilos.</p>

```css
/* ✅ Correct (Modo claro y oscuro con variables CSS) */
:root {
  --background-color: white;
  --text-color: black;
}

[data-theme="dark"] {
  --background-color: black;
  --text-color: white;
}

body {
  background-color: var(--background-color);
  color: var(--text-color);
}
```

---

Siguiendo estas mejores prácticas, el código CSS será más **estructurado, reutilizable y escalable**. 
# 🔴 HTML Conventions

**Referencia:** [HTML Best Practices - Kinsta](https://kinsta.com/blog/html-best-practices/)

## Introducción
HTML (HyperText Markup Language) es el lenguaje base para estructurar contenido en la web. Aplicar buenas prácticas garantiza accesibilidad, semántica y optimización para motores de búsqueda.

## Estructura del Documento
<p style="font-size: 16px;">Es importante mantener una estructura clara con etiquetas semánticas.</p>

```html
<!-- ❌ Incorrect -->
<div id="header">
  <h1>Website Title</h1>
</div>

<!-- ✅ Correct -->
<header>
  <h1>Website Title</h1>
</header>
```

## Semántica
<p style="font-size: 16px;">Usar etiquetas semánticas mejora la accesibilidad y el SEO.</p>

```html
<!-- ❌ Incorrect (Using generic divs) -->
<div class="nav">
  <ul>
    <li><a href="#">Home</a></li>
  </ul>
</div>

<!-- ✅ Correct (Using semantic elements) -->
<nav>
  <ul>
    <li><a href="#">Home</a></li>
  </ul>
</nav>
```

## Accesibilidad
<p style="font-size: 16px;">Usar atributos de accesibilidad como `alt` en imágenes y roles en etiquetas.</p>

```html
<!-- ❌ Incorrect -->
<img src="image.jpg">

<!-- ✅ Correct -->
<img src="image.jpg" alt="Description of image">
```

## Formularios y Usabilidad
<p style="font-size: 16px;">Usar etiquetas `<label>` correctamente asociadas a los campos de formulario.</p>

```html
<!-- ❌ Incorrect -->
<input type="text" placeholder="Enter name">

<!-- ✅ Correct -->
<label for="name">Name:</label>
<input type="text" id="name">
```

## Buenas Prácticas Generales
✔ Usar etiquetas semánticas (`<header>`, `<section>`, `<footer>`).  
✔ Incluir atributos `alt` en todas las imágenes.  
✔ Evitar el uso excesivo de `<div>` para estructurar contenido.  
✔ Usar `aria-label` y `role` cuando sea necesario para accesibilidad.  
✔ Mantener un orden lógico en los encabezados (`<h1>` a `<h6>`).  

## Característica Única: **Optimización para SEO**
<p style="font-size: 16px;">El HTML bien estructurado mejora el posicionamiento en motores de búsqueda.</p>

```html
<!-- ✅ Correct (Uso de meta etiquetas SEO) -->
<meta name="description" content="Best HTML practices for modern web development">
<meta name="keywords" content="HTML, best practices, web development">
```

---

Siguiendo estas mejores prácticas, el código HTML será más **estructurado, accesible y optimizado para SEO**. 
# 🖼️ Assets

## Propósito

La carpeta `assets/` está destinada al almacenamiento de **recursos estáticos** utilizados dentro del proyecto, como imágenes, íconos, fuentes, logotipos, archivos SVG, videos o cualquier otro archivo multimedia que forme parte del diseño visual de la aplicación.

Su organización ayuda a mantener estos archivos fuera de la lógica y componentes del frontend, manteniendo una arquitectura más limpia y escalable.

## Importancia

🔹 Centraliza los recursos visuales y estáticos del proyecto.  
🔹 Facilita la reutilización de imágenes e íconos en múltiples vistas.  
🔹 Mejora el orden y separa claramente la UI de los recursos visuales.  
🔹 Permite mantener consistencia de marca y diseño.

> Ejemplos: `logo.svg`, `hero-banner.jpg`, `font-roboto.woff2`, `illustration-empty.png`

## Buenas Prácticas

- Agrupar los recursos en subcarpetas según su tipo (`images/`, `icons/`, `fonts/`).
- Usar nombres descriptivos y en minúscula separados por guiones.
- Optimizar imágenes antes de subirlas (formato, peso y resolución).
- Evitar almacenar archivos innecesarios o duplicados.

## Ejemplo de estructura

```
src/
├── assets/
│   ├── images/
│   │   ├── login-background.jpg
│   │   ├── user-avatar.png
│   ├── icons/
│   │   ├── logo.svg
│   │   ├── close.svg
│   ├── fonts/
│   │   ├── roboto.woff2
```

## Conclusión

La carpeta `assets/` permite organizar los archivos estáticos esenciales para la identidad visual de una aplicación. Separarlos del código asegura una mejor estructura, evita errores y facilita su mantenimiento a largo plazo.

---

> Referencia utilizada: [Best Practices in Vite and React](https://codeparrot.ai/blogs/a-beginners-guide-to-using-vite-react)

---

## Característica única

La carpeta `assets/` brinda la posibilidad de manejar **contenido visual reutilizable** desde un solo lugar, lo que **reduce la redundancia**, mejora la coherencia visual y acelera el desarrollo de interfaces modernas. Además, al estar optimizado, mejora el rendimiento del sitio. 
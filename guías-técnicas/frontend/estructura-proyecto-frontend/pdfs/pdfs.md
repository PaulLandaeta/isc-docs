# 📄 PDFs

## Propósito

La carpeta `pdfs/` se utiliza para almacenar archivos en formato PDF que son requeridos dentro de la aplicación. Estos documentos pueden estar relacionados con manuales, plantillas, contratos, reportes, instructivos, currículums o material descargable ofrecido al usuario final.

Aunque no contienen código, estos archivos pueden ser esenciales para funcionalidades de descarga, vista previa o impresión desde la interfaz del sistema.

## Importancia

🔹 Centraliza documentos que necesitan ser accesibles desde el frontend.  
🔹 Facilita funcionalidades como descarga de archivos, impresión o vista previa.  
🔹 Mejora la organización de contenido estático no multimedia.

> Ejemplos comunes: `user-guide.pdf`, `terms-and-conditions.pdf`, `invoice-template.pdf`

## Buenas Prácticas

- Mantener los nombres descriptivos, en minúscula y separados por guiones.  
- Usar formatos ligeros y optimizados (idealmente < 1MB).  
- Evitar duplicados y mantener solo versiones actualizadas.  
- No colocar documentos personales o sensibles sin control de acceso.

## Ejemplo de uso en un botón de descarga

```tsx
// ✅ Componente con enlace de descarga
<a href="/pdfs/user-guide.pdf" download>
  Download User Guide
</a>
```

```tsx
// ❌ Incorrecto - Cargar archivos PDF directamente desde componentes sin ruta clara
import userGuide from "../../components/user-guide.pdf";
```

## Ubicación esperada en el proyecto

```
src/
├── pdfs/
│   ├── user-guide.pdf
│   ├── report-2024.pdf
│   └── invoice-template.pdf
```

## Conclusión

La carpeta `pdfs/` permite manejar documentos clave del proyecto de manera organizada y centralizada. Es especialmente útil cuando la aplicación necesita distribuir material descargable o visualizar contenido formal en formato PDF.

---

> Referencia utilizada: [Understanding the Vite Project Structure](https://dev.to/theprinceofprogramming/understanding-the-vite-project-structure-28jp)

---

## Característica única

Una característica importante de `pdfs/` es su **rol documental dentro del proyecto**, facilitando la entrega de información impresa o descargable al usuario final sin requerir backends o servicios externos. Esto es clave en apps educativas, institucionales o administrativas. 📎
# Documentación de Bug Reports

Esta guía contiene las buenas prácticas, estructura y ejemplos necesarios para documentar **Bug Reports** de forma clara, precisa y alineada a la plantilla oficial del equipo. La documentación está dividida en **Frontend** y **Backend**, considerando las particularidades de cada área.

---

## Índice

- [Estructura del Bug Report](#estructura-del-bug-report)
- [Buenas Prácticas](#buenas-prácticas)
- [Plantilla Oficial](#plantilla-oficial)
- [Módulos](#módulos)
- [Referencias](#referencias)

---

## Objetivos

- Explicar cómo se estructura correctamente un Bug Report.
- Definir el propósito de cada campo en la plantilla oficial.
- Presentar ejemplos prácticos bien redactados.
- Documentar buenas prácticas para priorización y categorización.
- Brindar una guía útil tanto para frontend como backend.

---

## Estructura del Bug Report

Todo Bug Report debe incluir los siguientes elementos como mínimo:

- **Título del Bug**  
  ➤ Breve, claro y representativo del problema.

- **Descripción**  
  ➤ Explicación clara de lo que sucede, cuándo ocurre y bajo qué condiciones.

- **Pasos para Reproducir**  
  ➤ Instrucciones detalladas para replicar el bug.

- **Resultado Esperado**  
  ➤ Qué se esperaba que sucediera.

- **Resultado Actual**  
  ➤ Qué sucedió realmente.

- **Severidad**  
  ➤ Crítica, Alta, Media o Baja.

- **Prioridad**  
  ➤ Alta, Media o Baja (según impacto y urgencia).

- **Módulo Afectado**  
  ➤ Indicar si el bug corresponde a frontend o backend (o ambos).

- **Evidencia**  
  ➤ Capturas de pantalla, videos o enlaces a reproducción del error.

- **Estado del Bug**  
  ➤ Abierto, En progreso, Corregido, Cerrado, etc.

---

## Buenas Prácticas

✔ Usar títulos breves pero descriptivos.  
✔ Detallar pasos reproducibles, incluso si son simples.  
✔ Evitar lenguaje ambiguo ("a veces falla", "algo no funciona").  
✔ Priorizar correctamente según impacto.  
✔ Usar evidencia visual siempre que sea posible.  
✔ Asegurar que el reporte sea entendible para devs, testers y stakeholders.

---

## Plantilla Oficial

La plantilla oficial se encuentra en la carpeta general y debe utilizarse como base para todo Bug Report.

Archivo: [`Plantilla Bug report.md`](../PlantillaBug.xlsx)

---

## Módulos

La documentación de bugs debe dividirse por módulo según el contexto:

- `frontend/`: Bugs relacionados a la UI o flujos visuales del usuario.
- `backend/`: Bugs asociados a lógica del servidor, API, validaciones, etc.

Cada módulo contiene:

- `README.md` explicativo con buenas prácticas.
- Ejemplos reales llenados con la plantilla.

---
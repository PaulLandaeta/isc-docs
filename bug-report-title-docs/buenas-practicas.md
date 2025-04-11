# Buenas Prácticas para Nombrar Documentos de Bug Reports

Este archivo recoge las principales recomendaciones que deben seguirse al momento de redactar los títulos de los documentos de Bug Reports. Estas buenas prácticas buscan mantener la coherencia, claridad y utilidad de los reportes en todo el flujo de trabajo del equipo.

---

## ✅ Recomendaciones que Sí Debes Seguir

- Usar el formato estándar establecido en el proyecto.
- Especificar siempre el sistema afectado (Frontend, Backend o API).
- Indicar con claridad la prioridad o severidad del bug.
- Describir el comportamiento observado en forma breve y directa.
- Utilizar verbos activos y sustantivos precisos (*fails, missing, not loading, overlaps, etc.*).
- Escribir los títulos en inglés para facilitar la lectura técnica y global del equipo.
- Si aplica, incluir versión de la app, tipo de dispositivo o navegador afectado.

---

## ❌ Prácticas que Debes Evitar

- Títulos genéricos como `error`, `bug`, `problema`, `no funciona`, etc.
- Usar palabras ambiguas como `raro`, `a veces`, `algo pasa`, `no responde bien`.
- Incluir comentarios personales o frases informales.
- Omitir información clave como el módulo, sistema o severidad.
- Colocar detalles excesivos en el nombre del archivo.

---

## Consejos Adicionales

- En herramientas como Jira o GitHub, el título del documento suele coincidir con el título del ticket. Asegúrate de que sea útil para quien lo vea sin abrir el archivo.
- Recomendado usar plantillas o checklists para validar que tu título cumple con todos los puntos del estándar.
- Revisa los títulos anteriores para mantener consistencia léxica (por ejemplo, no usar “Login” en un caso y “Sign in” en otro similar).
- Si el bug está relacionado a varios módulos, priorizar el más afectado.  
Ejemplo: `[Critical] [Frontend] [Login] y [Navbar] se sobreponen en pantallas móviles`
# 🐞 Documentación de Bug Reports - Backend

Esta sección está dedicada a la documentación de errores encontrados en el entorno de **backend**, alineada con la plantilla oficial proporcionada por el equipo de QA.

Cada bug report debe reflejar claramente:
- La acción realizada.
- El resultado esperado y el real.
- Clasificación técnica (frecuencia, prioridad, tipo).
- Pasos detallados para reproducirlo.

---

## Archivos Incluidos

| Archivo                        | Descripción                                                       |
|-------------------------------|-------------------------------------------------------------------|
| `BugBackendEjemplo1.md`       | Bug de creación fallida por error de validación.                |
| `BugBackendEjemplo2.md`       | Error en la actualización de datos por formato incorrecto.       |

---

## Estructura del Bug Report (Backend)

Todo bug debe ser documentado siguiendo esta estructura general:

### Información General
- Reportado por
- Fecha y hora
- Módulo / Servicio afectado
- Versión del sistema

### Detalles del Bug
- Acción realizada
- Mensaje de error (si aplica)
- Resultado esperado
- Resultado real

### Clasificación
- Frecuencia (Cada vez, Ocasional, etc.)
- Prioridad (Alta, Crítica, Media, etc.)
- Tipo de Defecto (Backend)

### Pasos para Reproducir
Listado secuencial de pasos que permitan replicar el error. Incluye herramientas como Postman o capturas de JSON si es necesario.

---

## Buenas Prácticas
- Ser claro y objetivo al describir la acción.
- Incluir datos técnicos si es posible: payloads, endpoints, headers.
- Precisar el error HTTP recibido, si aplica.
- Adjuntar capturas o ejemplos JSON si ayudan a la reproducción.

---

## Plantilla Referencial

Esta documentación se alinea con el archivo:

[`{Plantilla Bug Report}.md`](../PlantillaBug.md)  
> Utilizado como referencia estándar.

---
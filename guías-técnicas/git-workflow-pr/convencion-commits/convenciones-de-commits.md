
## 2. Convenciones de Commits

### 2.1 ¿Qué es un Commit?

Un commit es un registro de los cambios realizados en el código fuente. En un entorno colaborativo, los mensajes de commit deben ser claros, estructurados y seguir convenciones para facilitar la trazabilidad y comprensión del historial del proyecto.

**Buenas prácticas:**
- Realizar commits con frecuencia para que los cambios sean más fáciles de rastrear.
- Asegurar que cada commit represente un único propósito.
- Mantener commits atómicos: cada uno debe representar un cambio completo y funcional.
- Utilizar el tipo de commit adecuado según el cambio realizado.
- Incluir ámbitos para módulos específicos cuando el proyecto lo requiera.
- Preferir varios commits específicos en lugar de uno genérico que mezcle cambios diversos.


#### Tipos comunes de commits

- `feat`: nueva funcionalidad.
- `fix`: corrección de errores.
- `docs`: cambios en la documentación.
- `style`: cambios de formato que no afectan el funcionamiento.
- `refactor`: reestructuración sin cambios funcionales.
- `test`: adición o modificación de pruebas.
- `chore`: tareas menores como actualización de dependencias o configuraciones.


#### Reglas de estilo

- Iniciar la descripción con un verbo en imperativo ("feat", "fix").
- Evitar el uso de punto final.
- Limitar la línea de descripción a un máximo de 50 caracteres.
- Utilizar el cuerpo para explicar detalles técnicos, si es necesario.
- Agregar la sección `BREAKING CHANGE` en caso de cambios que rompan la compatibilidad.



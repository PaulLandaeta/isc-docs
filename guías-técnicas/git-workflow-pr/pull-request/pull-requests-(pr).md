## 1. Pull Requests (PR)

### 1.1 ¿Qué es un Pull Request?

Un Pull Request (PR) es una solicitud formal mediante la cual un desarrollador pide que los cambios realizados en una rama sean revisados antes de integrarse a una rama principal del repositorio, como `main` o `develop`. Este proceso permite al equipo colaborar, detectar errores y discutir implementaciones antes de fusionar el código en el entorno principal.

**Buenas prácticas:**
- Verificar que la rama contenga solo los cambios relacionados con una tarea específica.
- Mantener la rama actualizada con la rama base para evitar conflictos.
- Probar y revisar el código localmente antes de abrir el PR.

### 1.2 Buenas prácticas para Pull Requests

- **Evitar commits directos a main**: Las modificaciones deben realizarse en ramas independientes.
- **Utilizar nombres descriptivos para las ramas**: Por ejemplo, `usuario/agregar-login` o `feature/login-page`.
- **Realizar PR pequeños**: Cambios reducidos facilitan la revisión y aprobación.
- **Escribir descripciones claras**: Indicar qué se cambió, por qué y cómo probarlo.
- **Incluir capturas de pantalla o gifs**: Especialmente en PRs que afectan la interfaz visual.
- **Referenciar issues o tareas relacionadas**: Vincular el PR con su origen para proporcionar contexto.

**Buenas prácticas adicionales:**
- Dividir funcionalidades grandes en varios PRs pequeños.
- Etiquetar al revisor adecuado según el módulo afectado.
- Utilizar comentarios en el código para resaltar decisiones relevantes o solicitar revisiones específicas.

### 1.3 Recomendaciones adicionales

- Emplear plantillas de Pull Request para unificar criterios de revisión.
- Asegurarse de que el PR supere todas las pruebas automatizadas.

**Buenas prácticas:**
- Automatizar las revisiones utilizando linters y pruebas de integración continua.
- Mantener un historial de PRs para documentar decisiones técnicas.

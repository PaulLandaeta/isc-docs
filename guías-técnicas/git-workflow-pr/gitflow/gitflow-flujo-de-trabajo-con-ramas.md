
## 3. Gitflow: Flujo de trabajo con ramas

### 3.1 ¿Qué es Gitflow?

Gitflow es un modelo de ramificación que estandariza la gestión de versiones, funcionalidades y correcciones en un proyecto. Este modelo es especialmente útil en equipos que liberan versiones de manera regular y requieren mantener una estructura organizada.

**Buenas prácticas:**
- Adoptar Gitflow en proyectos con múltiples desarrolladores y ciclos de versión definidos.
- Evitar que las ramas se extiendan demasiado sin integrarse con `develop`, para reducir conflictos.

### 3.2 Tipos de ramas en Gitflow

- **main**: rama principal que contiene las versiones estables en producción.
- **develop**: rama de integración para cambios en desarrollo.
- **feature/**: ramas dedicadas a nuevas funcionalidades.
- **release/**: ramas para la preparación de lanzamientos.
- **hotfix/**: ramas para solucionar errores críticos en producción.

**Buenas prácticas:**
- Nombrar las ramas de forma descriptiva, por ejemplo: `feature/login-module`, `hotfix/crash-login`.
- Eliminar las ramas una vez que se han fusionado.
- No mezclar funcionalidades en ramas de corrección o lanzamiento.

### 3.3 Flujo de trabajo

1. Crear la rama `develop` a partir de `main`.
2. Desde `develop`, crear ramas `feature/nombre` para cada nueva funcionalidad.
3. Al finalizar el desarrollo, fusionar `feature` en `develop`.
4. Crear ramas `release/nombre` desde `develop` para preparar versiones.
5. Fusionar `release` en `main` y `develop`, y eliminar la rama.
6. En caso de errores urgentes, crear ramas `hotfix` desde `main` y fusionarlas en `main` y `develop` una vez resueltas.

**Buenas prácticas:**
- Automatizar los procesos de merge mediante pipelines de integración continua.
- Documentar los cambios incluidos en cada fusión.
- Verificar que `main` y `develop` se mantengan actualizadas.

### 3.4 Ventajas y desventajas

**Ventajas:**
- Proporciona claridad en el flujo de trabajo.
- Permite separar el desarrollo de la producción.
- Compatible con revisión de código y entornos CI/CD.

**Desventajas:**
- Puede resultar complejo para proyectos de menor escala.
- La gestión de muchas ramas incrementa la necesidad de operaciones de merge.
---

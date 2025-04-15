# Guía Estándar para la Redacción de User Stories en Backend

## 1. Objetivo

Estandarizar la redacción de User Stories para el desarrollo backend, para que describan de forma clara y técnica la lógica de negocio, las integraciones con otros servicios, el manejo de datos y errores, y que estén alineadas con los criterios de aceptación del equipo de desarrollo.

Esta guía busca facilitar la comprensión del alcance y mejorar la planificación y desarrollo técnico dentro de entornos ágiles como Scrum o Kanban.

---

## 2. Revisión del Formato Actual

- ✅ **Fortalezas:**
  - Algunas historias usan un formato orientado al propósito.
  - Inclusión básica de criterios de aceptación.

- ⚠ **Áreas de Mejora:**
  - Historias poco específicas o con títulos genéricos como "Crear autenticación".
  - Poca claridad sobre los sistemas involucrados y el objetivo técnico.
  - Falta de referencias técnicas (API, endpoints, estructuras de datos, reglas de negocio).

---

## 3. Diferencias entre User Stories de Frontend y Backend

| Aspecto                  | Frontend                                          | Backend                                                 |
|--------------------------|---------------------------------------------------|----------------------------------------------------------|
| Rol principal            | Usuario/interfaz                                 | Sistema/servicio interno                                |
| Enfoque                  | Experiencia visual/interacción                   | Lógica de negocio, procesamiento y persistencia de datos |
| Ejemplos técnicos        | Compatibilidad con navegadores, diseño responsivo| API REST, validación de datos, integraciones externas    |
| Valor entregado          | Facilidad de uso, accesibilidad                  | Eficiencia, seguridad, escalabilidad                     |

---

## 4. Elementos Clave de una User Story de Backend

Una buena historia de backend debe incluir:

- ✅ **Actor del sistema o servicio** (quién ejecuta la acción).
- ✅ **Acción o funcionalidad técnica requerida**.
- ✅ **Propósito o beneficio del proceso**.
- ✅ **Lógica de negocio involucrada** (reglas, condiciones, flujos alternos).
- ✅ **Impacto en base de datos** (lectura, creación, actualización, eliminación).
- ✅ **Integraciones** con otros servicios internos o externos (APIs, colas, eventos).
- ✅ **Manejo de errores** y mensajes esperados ante fallos.
- ✅ **Requerimientos técnicos adicionales** (autenticación, logs, métricas, rendimiento).

---

## 5. Plantilla Estandarizada

### Formato de la User Story

```text
Como [servicio/sistema interno], necesito [acción técnica a realizar] para [objetivo o beneficio técnico]. 
```

### ✅ Criterios de Aceptación

Usar formato **Given - When - Then**:

Dado/Given [contexto del sistema], Cuando/When [se produce una acción o evento], Entonces/Then [resultado esperado del sistema o API].


### Especificaciones Técnicas

- API endpoint involucrado (método, URL, parámetros)
- Formato de datos esperado (JSON, XML, etc.)
- Estructura de respuesta esperada (status codes, payload)
- Errores manejados (con código HTTP y descripción)
- Logs relevantes
- Validaciones obligatorias
- Esquema de base de datos afectado (tablas/colecciones)
- Seguridad: autenticación, autorización, expiración de tokens

---

## 6. Ejemplos Prácticos

### ✅ Ejemplo Bien Estructurado

**User Story:**

Como servicio de autenticación, necesito generar y validar tokens JWT para que los usuarios puedan autenticarse de manera segura.

**Criterios de Aceptación:**

- Dado que un usuario proporciona credenciales válidas,  
  Cuando realiza una solicitud POST al endpoint `/auth/token`,  
  Entonces el sistema debe generar un token JWT firmado con clave secreta.

- Dado que el token fue generado correctamente,  
  Cuando se incluye en la cabecera de una solicitud,  
  Entonces el sistema debe validar su integridad, firma y expiración.

**Especificaciones Técnicas:**

- Endpoint: `POST /auth/token`
- Formato del token: JWT (HS256)
- Tiempo de expiración configurable en archivo `.env`
- Código de error 401 si el token es inválido o caducado

---

### ❌ Ejemplo Mal Estructurado

**User Story:**

Crear autenticación con tokens.

**Problemas:**

- No identifica quién lo necesita (servicio/sistema).
- No describe el objetivo de la funcionalidad.
- No detalla la lógica, criterios de validación ni errores.
- Falta información técnica relevante.

---

## 7. Proceso de Socialización y Validación

- Se recopilará retroalimentación para adaptar la plantilla a distintos tipos de servicios (REST, event-driven).
- Se planifica una prueba piloto con historias reales del backlog para validar su aplicabilidad y claridad.
- Ajustes finales se incorporarán previo a su adopción formal.

---

## 8. Referencias

- [Scrum Guide](https://scrumguides.org)
- [Atlassian: How to write user stories](https://www.atlassian.com/agile/project-management/user-stories)
- [Agile Alliance – User Stories](https://www.agilealliance.org/agile101/user-stories/)
- [Auth0: Introduction to JWT](https://auth0.com/docs/secure/tokens/json-web-tokens)
- [12 Factor App - Backing Services](https://12factor.net/backing-services)
- [REST API Design Best Practices](https://restfulapi.net/)

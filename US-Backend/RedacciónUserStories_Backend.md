# Guía Estándar para la Redacción de User Stories en Backend

## 1. Objetivo

Estandarizar la redacción de User Stories para el desarrollo backend, para que describan de forma clara y técnica la lógica de negocio, las integraciones con otros servicios, el manejo de datos y errores, y que estén alineadas con los criterios de aceptación del equipo de desarrollo.

## 2. Revisión del Formato Actual

- *Fortalezas:*
  - Algunas historias usan un formato orientado al propósito.
  - Inclusión básica de criterios de aceptación.

- *Áreas de Mejora:*
  - Historias poco específicas o con títulos genéricos como "Crear autenticación".
  - Poca claridad sobre los sistemas involucrados y el objetivo técnico.
  - Falta de referencias técnicas (API, endpoints, estructuras de datos, reglas de negocio).


## 3. Diferencias entre User Stories de Frontend y Backend

| Aspecto                  | Frontend                                          | Backend                                                 |
|--------------------------|---------------------------------------------------|----------------------------------------------------------|
| Rol principal            | Usuario/interfaz                                 | Sistema/servicio interno                                |
| Enfoque                  | Experiencia visual/interacción                   | Lógica de negocio, procesamiento y persistencia de datos |
| Ejemplos técnicos        | Compatibilidad con navegadores, diseño responsivo| API REST, validación de datos, integraciones externas    |
| Valor entregado          | Facilidad de uso, accesibilidad                  | Eficiencia, seguridad, escalabilidad                     |


## 4. Elementos Clave de una User Story de Backend

Una buena historia de backend debe incluir:

- *Actor del sistema o servicio* (quién ejecuta la acción).
- *Acción o funcionalidad técnica requerida*.
- *Propósito o beneficio del proceso*.
- *Lógica de negocio involucrada* (reglas, condiciones, flujos alternos).
- *Impacto en base de datos* (lectura, creación, actualización, eliminación).
- *Integraciones* con otros servicios internos o externos (APIs, colas, eventos).
- *Manejo de errores* y mensajes esperados ante fallos.
- *Requerimientos técnicos adicionales* (autenticación, logs, métricas, rendimiento).


## 5. Plantilla Estandarizada

# User Story: [Título descriptivo]

##  Descripción
*Como* [servicio o sistema interno],  
*Necesito* [acción técnica],  
*Para* [objetivo técnico o beneficio].


## Criterios de Aceptación  
1. *Dado que* [contexto o precondición],  
   *Cuando* [acción o evento],  
   *Entonces* [resultado esperado].  

2. *Dado que* [contexto o precondición],  
   *Cuando* [acción o evento],  
   *Entonces* [resultado esperado].


## Especificaciones Técnicas  

- *Endpoint:* METHOD /ruta/del/endpoint  
- *Formato de request:*  
  ```json
  {
    "ejemploCampo": "valor"
  }
  ```
  

  ## Formato de respuesta esperada:
  ```json
  {
  "status": "success",
  "data": { "ejemploCampo": "valor" }
  }
  ```

  

## Manejo de errores:
- 400 → [Descripción del error por datos inválidos]

- 401 → [Descripción del error por auth]

- 500 → [Descripción del error interno]

## 6. Objetivos y métricas
| Objetivo                          | Métrica de Cumplimiento                                |
|----------------------------------|----------------------------------------------------------|
| Funcionalidad cumple su propósito | Pasa pruebas esperadas                                |
| Manejo correcto de errores        | Devuelve códigos HTTP correctos                       |
| Documentación clara y detallada   | Se especifican endpoints, payloads y respuestas       |
| Integración sin problemas         | Interoperabilidad validada con otros servicios        |
| Seguridad aplicada correctamente  | Tokens, roles y permisos controlados                  |

## Integraciones / Dependencias

- *Servicio/API externa involucrada:*  
  Especificar nombre y función del servicio o API externa

- *Colas, eventos o mensajes relacionados:*  
  Mencionar colas de mensajes, eventos de sistema o suscriptores involucrados

- *Tablas o colecciones afectadas:*  
  Indicar nombres de tablas o colecciones de base de datos que se impactan

### Especificaciones Técnicas
[Son los detalles técnicos que explican cómo debe funcionar la historia de usuario “por detrás” (en el servidor, base de datos, APIs, lógica de negocio). Como los endpoints que se crean o modifican, validaciones necesarias, estructuras de datos, integraciones y reglas que aseguran que el sistema trabaje correctamente.]

[Se aclara que no existe una regla para las especificaciones técnicas, estos son especificaciones de ejemplo dependiendo de la tarea que se requiera]

- API endpoint involucrado (método, URL, parámetros)
- Formato de datos esperado (JSON, XML, etc.)
- Estructura de respuesta esperada (status codes, payload)
- Errores manejados (con código HTTP y descripción)
- Logs relevantes
- Validaciones obligatorias
- Esquema de base de datos afectado (tablas/colecciones)
- Seguridad: autenticación, autorización, expiración de tokens


## 7. Ejemplos Prácticos

### Ejemplo Bien Estructurado

*User Story:*

Como servicio de autenticación, necesito generar y validar tokens JWT para que los usuarios puedan autenticarse de manera segura.

*Criterios de Aceptación:*

- Dado que un usuario proporciona credenciales válidas,  
  Cuando realiza una solicitud POST al endpoint /auth/token,  
  Entonces el sistema debe generar un token JWT firmado con clave secreta.

- Dado que el token fue generado correctamente,  
  Cuando se incluye en la cabecera de una solicitud,  
  Entonces el sistema debe validar su integridad, firma y expiración.

*Especificaciones Técnicas:*

- Endpoint: POST /auth/token
- Formato del token: JWT (HS256)
- Tiempo de expiración configurable en archivo .env
- Código de error 401 si el token es inválido o caducado

### Ejemplo Mal Estructurado

*User Story:*

Crear autenticación con tokens.

*Problemas:*

- No identifica quién lo necesita (servicio/sistema).
- No describe el objetivo de la funcionalidad.
- No detalla la lógica, criterios de validación ni errores.
- Falta información técnica relevante.


## 8. Referencias

- [Scrum Guide](https://scrumguides.org)
- [Atlassian: How to write user stories](https://www.atlassian.com/agile/project-management/user-stories)
- [Agile Alliance – User Stories](https://www.agilealliance.org/agile101/user-stories/)
- [Auth0: Introduction to JWT](https://auth0.com/docs/secure/tokens/json-web-tokens)
- [12 Factor App - Backing Services](https://12factor.net/backing-services)
- [REST API Design Best Practices](https://restfulapi.net/)

# 🐞 Bug Report - Fallo en creación de usuario por error de validación

## Información General

| Campo               | Detalle                                      |
|---------------------|----------------------------------------------|
| **Reportado por**   | QA Loren                                    |
| **Fecha y Hora**    | 06/28/2024 - 14:15                           |
| **Área del Problema** | API de Usuarios - Endpoint `/api/users`     |
| **Título del Problema** | La creación de usuario falla cuando se envían campos vacíos |
| **Archivos Adjuntos** | Request body, Response JSON, Logs           |
| **Reproducibilidad** | Siempre                                      |
| **Hora de Ocurrencia** | 06/28/2024 - 14:15                          |
| **URL Exacta**       | `https://api.example.com/api/users`         |
| **Versión de la API** | 2.3.0                                       |

---

## Detalles del Bug

| Acción Realizada | Mensaje de Error |
|------------------|------------------|
| Se intentó crear un usuario con un payload donde el campo `email` está vacío. | "El campo email es requerido" |

| Resultado Esperado | Resultado Real |
|--------------------|----------------|
| El sistema debe devolver un mensaje de validación clara y evitar la creación. | Se devuelve un error genérico sin detalles de validación. |

---

## Clasificación

| Frecuencia    | Prioridad | Tipo de Defecto |
|---------------|-----------|-----------------|
| ☑️ Cada vez   | ☑️ Crítico | ☑️ Backend       |

---

## Pasos para Replicar el Bug

1. Autenticarse con una cuenta admin válida.
2. Realizar un `POST` al endpoint `/api/users`.
3. Enviar el siguiente payload con el campo `email` vacío:

```json
{
  "name": "Prueba Backend",
  "email": "loren@prueba.com",
  "password": "ValidPass123"
}
```
## Observar la respuesta del sistema.

## Multimedia

Adjuntar captura del request y response desde Postman (opcional).

---

## Información del Tester

- **Nombre:** QA Loren
- **Fecha:** 28/03/2025 – 14:45  
- **Sistema Operativo:** Windows 11  
- **Herramienta de Pruebas:** Postman  
# 🐞 Bug Report - Error en la actualización de datos por formato incorrecto

## Información General

| Campo                | Detalle                                                  |
|----------------------|----------------------------------------------------------|
| **Reportado por**    | QA Carlos                                                |
| **Fecha y Hora**     | 28/03/2025 – 14:45                                       |
| **Área del Problema**| API de Usuarios - Endpoint `/api/users/:id`             |
| **Título del Problema** | Error al intentar actualizar un usuario con un campo numérico mal formateado |
| **Archivos Adjuntos**| Payload de request, capturas del error                   |
| **Reproducibilidad** | Siempre                                                  |
| **Hora de Ocurrencia** | 28/03/2025 – 14:45                                     |
| **URL Exacta**       | `https://api.example.com/api/users/15`                  |
| **Versión de la API**| 2.3.1                                                    |

---

## Detalles del Bug

| Acción Realizada                                                                 | Mensaje de Error                     |
|----------------------------------------------------------------------------------|--------------------------------------|
| Se intentó actualizar un usuario con un campo `age` como string (`"twenty"`)    | "Formato inválido para el campo age" |

| Resultado Esperado                                                               | Resultado Real                                   |
|----------------------------------------------------------------------------------|--------------------------------------------------|
| El sistema debería validar el campo y retornar un error 400 con mensaje claro.  | El sistema lanza un error 500 sin explicación.   |

---

## Clasificación

| Frecuencia     | Prioridad | Tipo de Defecto |
|----------------|-----------|-----------------|
| ☑️ Cada vez    | ☑️ Medio  | ☑️ Backend       |

---

## Pasos para Replicar el Bug

1. Autenticarse como admin en el entorno de pruebas.
2. Realizar una solicitud `PUT` al endpoint `/api/users/15`.
3. Enviar el siguiente payload malformado:

```json
{
  "name": "Carlos QA",
  "email": "carlosqa@example.com",
  "age": "twenty"
}
```

## Observar la respuesta del sistema.

---

## Multimedia

Adjuntar captura de Postman con el request y response (opcional).

---

## Información del Tester

- **Nombre:** Carlos QA  
- **Fecha:** 28/03/2025 – 14:45  
- **Sistema Operativo:** Windows 11  
- **Herramienta de Pruebas:** Postman  
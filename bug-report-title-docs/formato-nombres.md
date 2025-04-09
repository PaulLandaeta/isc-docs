# Formato Estándar para Nombres de Documentos de Bug Reports

Este archivo define el formato oficial que debe seguirse para nombrar los documentos de Bug Reports dentro del equipo. La estructura propuesta busca garantizar uniformidad y claridad, facilitando la identificación rápida del problema documentado.

---

## Formato Recomendado

[Prioridad] [Sistema] [Módulo] Descripción clara del error


### Componentes del Formato:

| Elemento        | Descripción                                                                  |
|------------------|-----------------------------------------------------------------------------|
| `[Prioridad]`    | Nivel de severidad del bug: `[Critical]`, `[High]`, `[Medium]`, `[Low]`     |
| `[Sistema]`      | Sistema afectado: `[Frontend]`, `[Backend]`, `[API]`                        |
| `[Módulo]`       | Área funcional afectada: `[Login]`, `[Checkout]`, `[Perfil]`, etc.          |
| `Descripción`    | Explicación corta y precisa del comportamiento erróneo                      |

---

## Ejemplos Correctos 

### 🔹 Frontend

| Severidad  | Sistema   | Módulo     | Descripción                                                 |
|------------|-----------|------------|-------------------------------------------------------------|
| Critical   | Frontend  | Login      | El formulario no se muestra en Safari                       |
| High       | Frontend  | Checkout   | Botón de pago desactivado en iPhone                         |
| Medium     | Frontend  | Dashboard  | Los gráficos se superponen en la ventana                    |

---

### 🔹 Backend

| Severidad  | Sistema   | Módulo     | Descripción                                                       |
|------------|-----------|------------|-------------------------------------------------------------------|
| Critical   | Backend   | Auth       | La validación del token falla después de iniciar sesión           |
| High       | Backend   | Orders     | Error 500 en la solicitud de pago                                 |
| Low        | Backend   | Reports    | Retraso de respuesta de API > 10s en v1.3.2                       |


## ❌ Ejemplos Incorrectos

| Nombre Incorrecto   | Problema                                                        |
|---------------------|-----------------------------------------------------------------|
| `error checkout`    | Sin prioridad, sistema ni descripción útil                      |
| `fix bug`           | Demasiado genérico                                              |
| `problema en login` | No indica sistema ni severidad                                  |
| `ticket error 500`  | Falta contexto y no comunica el módulo afectado                 |
| `Login falla`       | Incompleto y sin estructura                                     |

---

## Casos Especiales

| Tipo de caso             | Ejemplo correcto                                                              |
|--------------------------|-------------------------------------------------------------------------------|
| Bug en varios sistemas   | `[Critical] [Frontend/Backend] [Profile] Data mismatch when editing info`     |
| Afecta versión específica| `[High] [Backend] [API-Payments] Null error on v2.1.1 only`                   |
| Errores intermitentes    | `[Medium] [Frontend] [Login] Random redirect to 404 after submit`             |
| Problemas visuales       | `[Low] [Frontend] [Dashboard] Chart titles clipped in Firefox`                |

---

## Recomendaciones Generales

- Mantener los nombres entre 50 y 100 caracteres.
- Evitar el uso de términos vagos como “bug”, “error”, “falla” sin más detalles.
- Asegurarse de que el nombre sea comprensible sin abrir el documento.
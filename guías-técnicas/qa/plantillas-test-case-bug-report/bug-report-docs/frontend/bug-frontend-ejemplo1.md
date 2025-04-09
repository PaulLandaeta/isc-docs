## 🐞 Bug Report - Validación de campo obligatorio en formulario

### Información General

| Campo                    | Detalle                                                                 |
|--------------------------|-------------------------------------------------------------------------|
| **Reportado por**        | Fernando QA                                                               |
| **Fecha y Hora**         | 06/27/2024 - 11:00 PM                                                   |
| **Área del Problema**    | Gestión de Problemas                                                    |
| **Título del Problema**  | No se muestra mensaje de error al dejar campo obligatorio vacío         |
| **Archivos Adjuntos**    | Validación, Formulario, UX                                              |
| **Reproducibilidad**     | Siempre                                                                 |
| **Hora de Ocurrencia**   | 06/27/2024 - 11:00 PM                                                   |
| **URL Exacta**           | https://ejemplo.com/app/#/create-problem                                |
| **Versión de Compilación** | 1.0.0                                                                 |

---

### Detalles del Bug

| Acción Realizada                                                                                         | Mensaje de Error                        |
|----------------------------------------------------------------------------------------------------------|-----------------------------------------|
| El usuario intenta enviar el formulario sin llenar el campo "Título".                                    | No aparece ningún mensaje de error.     |

| Resultado Esperado                                                            | Resultado Real                                          |
|-------------------------------------------------------------------------------|---------------------------------------------------------|
| Debería mostrarse un mensaje claro: “El título es obligatorio.”              | El formulario se reinicia sin mostrar ninguna advertencia. |

---

### Clasificación

| Frecuencia     | Prioridad | Tipo de Defecto |
|----------------|-----------|-----------------|
| ☑️ Cada vez     | ☑️ Crítico | ☑️ Frontend      |

---

### Pasos para Replicar el Bug

1. Iniciar sesión en la plataforma.  
2. Ir al formulario de creación de problemas.  
3. Dejar vacío el campo "Título".  
4. Hacer clic en el botón "Crear Problema".  
5. Verificar si aparece mensaje de error (no aparece).  
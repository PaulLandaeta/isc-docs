## 🐞 Bug Report - Botón “Crear Problema” no responde tras validación

### Información General

| Campo                    | Detalle                                                                                     |
|--------------------------|---------------------------------------------------------------------------------------------|
| **Reportado por**        | Lucia QA                                                                                   |
| **Fecha y Hora**         | 06/27/2024 - 11:45 PM                                                                       |
| **Área del Problema**    | Gestión de Problemas                                                                        |
| **Título del Problema**  | El botón “Crear Problema” no funciona después de que se muestra un mensaje de error por campos vacíos |
| **Archivos Adjuntos**    | Formulario, Validaciones, Navegación                                                       |
| **Reproducibilidad**     | Siempre                                                                                     |
| **Hora de Ocurrencia**   | 06/27/2024 - 11:45 PM                                                                       |
| **URL Exacta**           | https://ejemplo.com/app/#/create-problem                                                    |
| **Versión de Compilación** | 1.0.0                                                                                     |

---

### Detalles del Bug

| Acción Realizada                                                                                                                                     | Mensaje de Error                                     |
|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| El usuario intenta crear un problema sin llenar campos requeridos, se muestra el mensaje de error correctamente, pero al llenarlos después y hacer clic en “Crear Problema”, el botón no responde. | No se muestra mensaje nuevo, el botón queda sin funcionalidad. |

| Resultado Esperado                                                                                                 | Resultado Real                                       |
|--------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| El botón “Crear Problema” debería funcionar una vez que los campos estén completos.                              | El botón permanece inactivo incluso con campos válidos. |

---

### Clasificación

| Frecuencia     | Prioridad | Tipo de Defecto |
|----------------|-----------|-----------------|
| ☑️ Cada vez     | ☑️ Alto    | ☑️ Frontend      |

---

### Pasos para Replicar el Bug

1. Iniciar sesión como usuario válido.  
2. Ir al formulario para crear un nuevo problema.  
3. Dejar campos requeridos vacíos y hacer clic en "Crear Problema".  
4. Observar el mensaje de error.  
5. Llenar los campos requeridos y hacer clic nuevamente.  
6. Observar que el botón no responde.
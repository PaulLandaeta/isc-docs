# Bug Report 

## Información General

| Campo                   | Detalle                                                        |
|-------------------------|----------------------------------------------------------------|
| **Reportado por**       | Julian Rojas                                               |
| **Fecha y Hora**        | 06/27/2024 - 11:00 PM                                          |
| **Área del Problema**   | Gestión de Becas                                               |
| **Título del Problema** | Los subtítulos al entrar a un problema no desaparecen cuando no tienen nada de contenido dentro |
| **Archivos Adjuntos**   | Entrada, Salida, Restricciones, Explicación                   |
| **Reproducibilidad**    | Siempre                                                        |
| **Hora de Ocurrencia**  | 06/27/2024 - 11:00 PM                                          |
| **URL Exacta**          | https://upb-forces-qa.vercel.app/#/                            |
| **Versión de Compilación** | 1.0.0                                                      |

---

## Detalles del Bug

| Acción Realizada | Mensaje de Error                  |
|------------------|-----------------------------------|
| Se verificó que los subtítulos como “Entrada”, “Salida”, etc., no aparecen en caso de no tener nada dentro de su body al crear el problema. | No aparece ningún mensaje de error. |

| Resultado Esperado | Resultado Real |
|--------------------|----------------|
| Según las instrucciones de la tarea, al no tener nada dentro de su body, los subtítulos no deberían mostrarse. | Los subtítulos aparecen en los detalles del problema incluso al estar vacíos en sus bodies. |

---

## Clasificación

| Frecuencia    | Prioridad | Tipo de Defecto |
|---------------|-----------|-----------------|
| ☑️ Cada vez   | ☑️ Crítico | ☑️ Frontend     |

---

## Pasos para Replicar el Bug

1. Logearse en la página.
2. Crear un problema con los elementos Entrada, Salida y Restricciones vacíos.
3. Guardar el problema.
4. Ir al detalle desde la sección "Problemas".
5. Observar que se muestran los subtítulos aunque estén vacíos.

---

## Multimedia

Adjuntar capturas o grabación del comportamiento si es necesario.

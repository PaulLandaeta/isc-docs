# Sistema de Gamificación: Monedas y Diamantes

## Introducción
Este documento describe el sistema de gamificación basado en **monedas** y **diamantes**, incluyendo las formas de ganar y gastar puntos.

## Conversión de Story Points a Diamantes y Monedas
Las **Story Points** son una unidad de medida utilizada en metodologías ágiles para estimar el esfuerzo relativo necesario para completar una tarea o funcionalidad.  

Cada **Story Point** equivale a una cantidad específica de diamantes y monedas según la siguiente tabla:

| Story Points | Diamantes | Monedas |
|-------------|----------|---------|
| 1           | 1        | 15      |
| 3           | 2        | 30      |
| 5           | 3        | 50      |
| 8           | 5        | 100     |

### Bonificaciones
- **Por finalización rápida**: Si un estudiante termina la tarea en la mitad del tiempo, gana **+15 monedas** adicionales.

### Penalizaciones
- Si el estudiante **no participa en reuniones** organizadas por el equipo, perderá **-1 diamante** y **-10 monedas**.
- Si el estudiante **rechaza una tarea sin razón válida**, perderá **-2 diamantes** y **-20 monedas**.
- Si el estudiante entrega una tarea con un **retraso de 1 día**, se obtiene la mitad de las monedas y diamantes.
- Si el estudiante **no entrega una tarea después del día de retraso permitido**, no ganará monedas ni diamantes y perderá **20 monedas**.  
- Si el estudiante no tiene monedas, recibirá un **llamado de atención**.
- Tras **tres llamados de atención**, el estudiante pierde la materia.

---

## Recompensas por Resolución de Bugs
Un **bug** es un error o defecto en un programa de computadora que produce un resultado inesperado.  
Los estudiantes que resuelvan **bugs** ganan diamantes y monedas dependiendo de la gravedad del problema:

| Tipo de Bug | Diamantes | Monedas |
|------------|----------|---------|
| Menor (error visual, ajuste simple) | 1 | 10 |
| Medio (error funcional que afecta pero no bloquea) | 3 | 30 |
| Crítico (error que bloquea completamente el sistema) | 5 | 50 |

Las soluciones presentadas por los estudiantes serán evaluadas por el **QA** (*Quality Assurance*), quien se encargará de aceptar o rechazar el arreglo.

### Penalizaciones por Bugs
- Si un bug arreglado sigue fallando o es rechazado por QA, el estudiante pierde **-5 monedas**.
- Si un estudiante no logra reproducir un bug, el **QA pierde -5 monedas**.

---

## Ganancias de QA
Los QA reciben diamantes y monedas por su trabajo en pruebas:

| Acción | Diamantes | Monedas |
|--------|----------|---------|
| Crear un test case nuevo | 1 | 10 |
| Ejecutar un test case existente | 1 | 10 |
| Encontrar un fallo en una prueba | 3 | 30 |

### Bonificaciones y penalizaciones
- Si un test case detecta un **bug crítico**, el QA obtiene un **bono de +1 diamante**.
- Si un test case es **rechazado por ser mal diseñado**, el QA pierde **-5 monedas**.

---

## Recompensas y Penalizaciones para Líderes
Los líderes de equipo ganan puntos según su desempeño:

| Tarea del Líder | Diamantes | Monedas |
|----------------|----------|---------|
| Organizar y liderar reuniones | 1 | 10 |
| Distribuir tareas equitativamente | 1 | 10 |
| Resolver conflictos dentro del equipo | 3 | 30 |
| Mentoría efectiva (ayuda en debugging o dudas) | 2 | 20 |
| Entrega de reportes a tiempo | 2 | 15 |
| Completar todas las tareas del sprint | 4 | 50 |
| Facilitar una presentación del equipo | 2 | 20 |
| Recibir feedback positivo (de la mitad del equipo) | 2 | 20 |

### Bonificaciones
- Si el equipo de un líder tiene un desempeño excelente en **dos sprints seguidos**, el líder gana **5 diamantes de bonificación** (para repartir entre los miembros del equipo).

### Penalizaciones
- **Recibir evaluación negativa (por estudiante)**: **-1 diamante** y **-20 monedas**.
- **Asignar tareas de manera injusta (según feedback del equipo)**: **-2 diamantes** y **-20 monedas**.
- **Faltar a reuniones importantes sin aviso**: **-1 diamante** y **-10 monedas**.
- **Recibir 3 quejas formales**: **-4 diamantes** y **-50 monedas**.
- **Acumular 5 faltas graves**: Se **remueve del cargo**.

---

## Uso de Monedas
Las monedas pueden gastarse en diferentes beneficios:

| Beneficio | Costo (Monedas) | Descripción |
|-----------|----------------|-------------|
| Extender el plazo de una tarea 1 día | 20  | Agrega 24 horas adicionales para entregar una tarea. |
| Rehacer una actividad mal calificada | 30  | Permite volver a presentar una actividad sin penalización. |
| Obtener una pista de la tarea | 10  | Recibe una pista para resolver una tarea difícil. |
| Cambiar de equipo | 50  | Permite moverse a otro equipo de trabajo. |
| Cambiar de rol | 200  | Cambia a otro rol dentro del equipo. |
| Saltarse una tarea (US 1 a 3) | 100  | Permite omitir la entrega de una tarea con baja puntuación en Story Points. |
| Saltarse una tarea (US 5 a 8) | 200  | Permite omitir la entrega de una tarea con alta puntuación en Story Points. |
| Comprar 1 diamante | 150  | Convierte monedas en un diamante (máximo 3 por estudiante). |
| Mentoría con el líder | 20  | 15 minutos de mentoría especial sobre una tarea. |
| Mentoría con el docente | 40  | 15 minutos de mentoría con el profesor. |
| Duplicar diamantes ganados en una tarea | 200  | Duplica los diamantes obtenidos. |
| Evitar penalización por entrega tardía | 80  | No recibe penalización si entrega tarde. |
| Revisión extra de código | 20  | Revisión detallada con feedback del líder. |

---

## Conclusión
Este sistema fomenta la colaboración, el esfuerzo y el aprendizaje en equipo.  
Planifica bien tu estrategia, gana diamantes y monedas, y utilízalos sabiamente para mejorar tu desempeño.  

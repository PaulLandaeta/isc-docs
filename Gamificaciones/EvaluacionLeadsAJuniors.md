# 📘 Sistema de Puntos para Story Points (SP)

Este documento forma parte del sistema de gamificación del equipo y tiene como objetivo estandarizar la conversión de **Story Points (SP)** en **monedas** y **diamantes**, según los valores interpolados entre 0.5 y 8 SP. Además, se incluye una guía sobre cómo utilizar el archivo Excel adjunto para el seguimiento de desempeño por sprint.

---

## 🎯 Objetivo

Como líder, quiero comprender el puntaje apropiado que debo asignar a mi equipo para ser justo con los puntajes.

Permitir una asignación justa y transparente de puntos a los integrantes del equipo, basada en los esfuerzos reflejados por los Story Points.

---
## 🔢 Conversión de SP a Monedas y Diamantes (Interpolada)

A partir de la tabla base definida en el sistema oficial de gamificación, se generó una interpolación entre los siguientes valores:

| Story Points | Diamantes | Monedas |
|--------------|-----------|---------|
| 1            | 1         | 15      |
| 3            | 2         | 30      |
| 5            | 3         | 50      |
| 8            | 5         | 100     |

La interpolación lineal permite calcular valores intermedios desde **0.5 hasta 8 SP**.

---

## 📥 Descarga del archivo Excel

Puedes descargar el archivo Excel que contiene:
- Las fórmulas automáticas para calcular monedas y diamantes según los SP asignados.
- Columnas individuales para cada miembro junior.
- Organización por sprint.
- Suma total de puntos obtenidos por persona en cada sprint.

👉 [📊 Descargar Excel de Puntajes](./EvaluacionLeadsAJuniors.xlsx)

---

## 📊 Archivo: `GamificacionesPuntajesEquipo.xlsx`

Este archivo contiene:

### 1. **Hoja: `Tabla SP → Recompensas`**
Contiene la tabla interpolada desde **0.5 hasta 10 Story Points** (SP), donde cada SP otorga una cantidad proporcional de diamantes y monedas.

| Story Points | Diamantes | Monedas |
|--------------|-----------|---------|
| 0.5          | 0.75       | 7.5     |
| 1.0          | 1.0       | 15.0    |
| 1.5          | 1.25      | 18,75    |
| ...          | ...       | ...     |
| 8.0         | 5     | 100  |

> ⚠️ Los valores han sido **interpolados linealmente** entre los valores base definidos en el sistema de gamificación.

### 2. **Hoja: `Plantilla Sprint`**
Plantilla en blanco para registrar los datos de cada sprint:

- `Nombre del Junior`: nombre del integrante del equipo.
- `Story Points`: total de puntos asignados en el sprint.
- `Diamantes`: calculados según la tabla.
- `Monedas`: calculadas según la tabla.
- `Bonos/Penalizaciones`: campo libre para sumar o restar según desempeño.
- `Total Diamantes`: suma de diamantes con bonificaciones/penalizaciones.
- `Total Monedas`: suma de monedas con bonificaciones/penalizaciones.

---

## ✅ Cómo usar este archivo

1. Consulta la hoja `Tabla SP → Recompensas` para ver cuántas monedas y diamantes equivalen a cierto número de SP.
2. Llena la hoja `Plantilla Sprint` al terminar cada sprint.
3. Aplica bonificaciones o penalizaciones según lo documentado en el sistema de gamificación.
4. Usa los totales para premiar o dar seguimiento al rendimiento de cada miembro del equipo.

---
## 👍 Siguiente paso

Una vez revisado este documento, puedes abrir el archivo Excel y comenzar a registrar los Story Points de cada tarea asignada durante los sprints.

---

## 📎 Recomendaciones adicionales
- Actualiza el archivo tras cada sprint.
- Guarda respaldos por sprint en subcarpetas como `/sprint-1`, `/sprint-2`, etc.
- Puedes agregar hojas nuevas para hacer seguimiento por trimestre o ciclo académico.




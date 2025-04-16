# Ejemplos de Comentarios en Pull Requests

A continuación se presentan ejemplos reales o simulados de comentarios buenos y malos durante la revisión de PRs.

---

## ✅ Correct Comment Examples

| Type                     | Comment                                                                                          |
|--------------------------|--------------------------------------------------------------------------------------------------|
| Clear suggestion         | “Consider renaming this variable to `userData` to better reflect its contents.”                |
| Constructive question    | “Why did you choose a `forEach` here instead of `map`?”                                        |
| Praise + improvement     | “Great structure here! Just wondering if extracting this into a helper function would help?”   |
| Clarity request          | “Could you add a comment here explaining why this check is needed?”                            |
| Backed-up proposal       | “We could use `.trim()` here to avoid potential whitespace issues.”                            |

---

## ❌ Incorrect Comment Examples

| Comment                          | Problem                                                                 |
|----------------------------------|-------------------------------------------------------------------------|
| “This code is wrong.”            | Vague, provides no solution or reasoning.                              |
| “Did you even test this?”        | Aggressive tone, feels personal.                                       |
| “Don’t do it like this.”         | Lacks context and explanation.                                         |
| “Terrible variable name.”        | Judgmental, no constructive alternative offered.                       |
| “Fix this.”                      | Doesn’t specify what’s wrong or how to improve it.                     |

---


## Ejemplo real del equipo – PR #178

> PR: `docs(#178): bug report titles naming documentation`  
> Comentario realizado por el revisor:

> “La documentación cubre aspectos clave como la claridad, la consistencia y el formato estándar, lo cual permite identificar rápidamente el problema sin necesidad de revisar el documento completo.”

**Análisis**:  
Este comentario es un excelente ejemplo de revisión constructiva. Comienza validando el trabajo hecho.  
Sigue todos los principios de una buena revisión: respeto, claridad, propuesta y apertura al diálogo.

---

## Pro Tip

Un buen comentario es:

✔️ Claro  
✔️ Amable  
✔️ Justificado  
✔️ Orientado a mejorar  
✔️ Específico
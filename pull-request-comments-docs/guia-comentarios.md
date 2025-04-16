# Guía de Buenas Prácticas para Comentar Pull Requests (PR)

Esta guía establece recomendaciones clave para escribir comentarios efectivos, respetuosos y útiles durante la revisión de Pull Requests (PR) en proyectos colaborativos.

---

## ✅ Qué Hacer

| Práctica recomendada                            | Ejemplo                                                                 |
|-------------------------------------------------|-------------------------------------------------------------------------|
| Haz preguntas en lugar de afirmaciones duras | ¿Crees que podríamos usar un `switch` aquí en lugar de tantos `if`?    |
| Justifica tus sugerencias                    | Podríamos usar `const` aquí ya que la variable no cambia su valor.     |
| Pide claridad si algo no se entiende         | ¿Podrías explicar por qué se eligió esta estructura?                   |
| Sé específico y directo                      | Este `console.log` parece innecesario, ¿puede eliminarse?              |
| Comenta solo lo relevante                    | Esta línea está duplicada con la de la línea 24.                       |
| Mantén un tono respetuoso y constructivo     | Gran trabajo aquí. Solo una sugerencia para mejorar la legibilidad.   |

---

## ❌ Qué Evitar

| Mala práctica                         | Por qué evitarlo                                                        |
|--------------------------------------|-------------------------------------------------------------------------|
| ❌ Críticas vagas                     | "Esto está mal" → No aporta valor ni guía al autor del PR.              |
| ❌ Comentarios sarcásticos o pasivo-agresivos | Afecta la moral del equipo y genera incomodidad.               |
| ❌ Repetir lo mismo sin contexto      | Repetir "esto no me gusta" sin explicar por qué no ayuda a mejorar.    |
| ❌ Ignorar las convenciones del equipo| Puede generar inconsistencias o retrabajo innecesario.                  |
| ❌ Comentarios personales             | Enfocarse en el código, no en la persona.                              |

---

## Frases Útiles para Comentar PRs

- “Buen trabajo aquí, ¿te parece si simplificamos esta parte?”
- “¿Podrías agregar un comentario para aclarar esta lógica?”
- “¿Hay una razón por la cual usamos `var` en lugar de `let`?”
- “¿Podríamos dividir este bloque en una función para mejorar la legibilidad?”
- “Sugiero renombrar esta variable para que refleje mejor su propósito.”

---

## Tip 

Cuando sugieras un cambio, incluye el **por qué** y si es posible, una **alternativa**.  
Esto convierte un comentario en una oportunidad de aprendizaje mutuo.

---

> Esta guía promueve una revisión efectiva y colaborativa. Todos los comentarios deben buscar mejorar el código y fortalecer el equipo.
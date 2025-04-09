# Guía para la Redacción de Títulos de Historias de Usuario (User Stories)

Este documento establece un conjunto de normas y buenas prácticas para redactar títulos de User Stories en proyectos de desarrollo ágil. Su objetivo es garantizar que los títulos reflejen claramente el propósito de cada historia, manteniendo la uniformidad, claridad y trazabilidad dentro del backlog del equipo.

---

## Objetivo

Estandarizar la estructura, redacción y estilo de los títulos de las User Stories para que:

- Sean comprensibles por todos los miembros del equipo.
- Reflejen de manera clara la intención funcional.
- Permitan identificar el módulo o área afectada.
- Faciliten el seguimiento en herramientas de gestión como Jira, Trello o Azure DevOps.

---

## Formato Estándar

**Estructura recomendada:**
[Module] Expected user/system action

### Componentes

| Elemento            | Descripción                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `[Module]`          | Área o funcionalidad del sistema que se ve afectada.                        |
| `Action`            | Qué debe poder hacer el usuario o sistema.                                 |

✅ El título debe centrarse en **lo que se espera lograr**.  
❌ No debe incluir tecnicismos, errores vagos, ni tareas internas como "crear función".

---

## ✅ Ejemplos Correctos 

| Correct Title Example                                      | Justificación                                               |
|------------------------------------------------------------|-------------------------------------------------------------|
| `[Checkout] Allow users to pay using PayPal`               | Módulo + acción clara con objetivo funcional.               |
| `[Authentication] Reset password via email`                | Preciso, sin redundancias.                                  |
| `[Dashboard] Display monthly sales chart`                  | Indica qué se muestra y dónde.                              |
| `[Profile] Let users update their personal information`    | Se enfoca en la experiencia del usuario.                    |

---

## ❌ Ejemplos Incorrectos 

| Incorrect Title                     | Why It's Incorrect                                           |
|-------------------------------------|---------------------------------------------------------------|
| `Fix login issue`                   | No se indica la causa, módulo o intención.                    |
| `Update stuff`                      | Vago y sin contexto técnico o funcional.                      |
| `User Profile 2.0`                  | No expresa ninguna acción esperada.                          |
| `Error 404 when clicking something` | Parece un bug, no una historia de usuario.                   |

---

## Recomendaciones de Redacción

- Utilizar verbos de acción: *allow, enable, display, validate, notify...*
- Ser concisos: menos de 15 palabras idealmente.
- Evitar detalles técnicos que no aporten claridad.
- Indicar el **resultado esperado** y no el proceso técnico.
- Asegurar que el título **por sí solo** dé una idea clara del objetivo.

---

## Casos Especiales

### 🔸 Historias técnicas:
Cuando una US tiene un objetivo técnico, el título debe seguir siendo entendible:

[Backend] Optimize image upload process

### 🔸 Historias condicionales:
Para flujos alternos o errores controlados:

[Payments] Notify user if credit card is declined

---

## Referencias Utilizadas

- [Guía de User Stories - Atlassian](https://www.atlassian.com/agile/project-management/user-stories)  
  Explica estructura, redacción y uso en gestión ágil.

- [Mountain Goat Software – User Stories](https://www.mountaingoatsoftware.com/agile/user-stories)  
  Fuente clásica sobre historias de usuario según prácticas ágiles.

- [Agile Alliance - User Stories](https://www.agilealliance.org/glossary/user-stories)  
  Definición estándar de historias de usuario en contexto ágil.

En caso de que el enlace no redirija directamente al fragmento consultado, se recomienda usar el buscador del sitio con términos como:  
**"User Story format"**, **"how to write user stories"**, **"agile story titles"**.

---

## Notas Finales

- Este estándar aplica tanto a historias de frontend como de backend.
- Forma parte del esfuerzo por unificar la documentación técnica en el equipo.
- Esta guía debe aplicarse en combinación con la estructura de redacción del cuerpo y los criterios de aceptación de cada User Story.
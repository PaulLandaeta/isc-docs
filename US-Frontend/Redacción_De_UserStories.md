# Guía Estándar para la Redacción de User Stories en Frontend

## 1. Objetivo

Establecer una la redacción de User Stories enfocadas en el desarrollo de interfaces y experiencia de usuario, asegurando claridad, coherencia y alineación con las mejores prácticas ágiles (Scrum, Kanban, XP).

---

## 2. Revisión del Formato Actual

- ✅ Fortalezas:
  - Uso básico del formato "Como [rol], quiero [acción], para [beneficio]".
  - Inclusión de criterios de aceptación.

- ⚠ Inconsistencias:
  - Algunas historias no especificaban el comportamiento esperado.
  - Pocas referencias a usabilidad o accesibilidad.
  - Ausencia de detalles técnicos como compatibilidad con navegadores o dispositivos.
---

## 3. Buenas Prácticas en Metodologías Ágiles
Frameworks ágiles:

- **Scrum**: Foco en historias centradas en el valor para el usuario.
- **Kanban**: Claridad en los criterios de aceptación y condiciones de entrega.
- **Extreme Programming (XP)**: Detalles sobre la interacción del usuario y pruebas funcionales.

---

## 4. Elementos Clave en User Stories de Frontend

Una User Story de Frontend bien definida debe incluir:

- **Rol del usuario** (persona que interactúa con la interfaz).
- **Acción o funcionalidad esperada**.
- **Valor o beneficio esperado**.
- **Comportamiento del sistema** ante la interacción.
- **Accesibilidad y usabilidad**.
- **Requisitos de diseño** (Tipografías, paleta de colores, componentes UI).
- **Restricciones técnicas** (dispositivos, navegadores, frameworks).

---

## 5. Plantilla Estandarizada

### Formato de la User Story

```text
Como [rol del usuario], quiero [acción o funcionalidad], para [beneficio o valor].
```
### ✅ Criterios de Aceptación

Usar el formato **Given - When - Then**:
```text
Dado/Given [contexto inicial o estado del sistema], Cuando/When [acción que realiza el usuario], Entonces/Then [resultado esperado del sistema].
```

### 🧩 Especificaciones Adicionales

- Navegadores compatibles (ej. Chrome, Firefox, Safari)
- Dispositivos soportados (Mobile, Tablet, Desktop)
- Framework o librería frontend utilizada (React, Angular, etc.)
- Estándares de accesibilidad (WCAG 2.1, ARIA)

---

## 6. Ejemplos

### ✅ Ejemplo Bien Estructurado

**User Story:**
Como usuario registrado, quiero poder editar mi perfil desde el menú principal, para mantener mi información actualizada.


**Criterios de Aceptación:**

- Dado que estoy autenticado y en la página principal,  
  Cuando hago clic en "Mi Perfil",  
  Entonces debo ser redirigido a un formulario editable con mis datos actuales.

- Dado que he editado los datos correctamente,  
  Cuando presiono "Guardar",  
  Entonces el sistema debe mostrar un mensaje de confirmación y actualizar la información.

**Especificaciones:**

- Compatible con Chrome, Firefox y Safari.
- Soporte para pantallas de 360px en adelante.
- El formulario debe cumplir con estándares WCAG AA.

---

### ❌ Ejemplo Mal Estructurado

**User Story:**


**Problemas:**

- No indica quién necesita la funcionalidad.
- No se expresa el valor que aporta.
- No hay contexto ni criterios medibles.
- No especifica comportamientos esperados.

---

## 7. Acciones planificadas para la validación de la plantilla 

- Validación pendiente con equipo de Frontend y Product Owners.
- Se planifica realizar pruebas con historias reales del backlog 
- Feedback recopilado será incorporado para asegurar claridad.

---
## 8. Referencias

- [Scrum Guide ](https://scrumguides.org)
- [Atlassian: How to write user stories](https://www.atlassian.com/agile/project-management/user-stories)
- [Agile Alliance – User Stories](https://www.agilealliance.org/agile101/user-stories/)
---

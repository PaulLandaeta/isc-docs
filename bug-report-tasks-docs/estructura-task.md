# Estructura Estándar para una Task de Bug Report

Esta estructura debe seguirse al momento de registrar un bug como Task en el sistema de gestión (como Taiga, Jira, Trello, etc.), con el fin de asegurar trazabilidad, claridad y reproducibilidad del error.

---

## Campos obligatorios

### Título descriptivo y preciso
- Especificar el tipo de error, módulo afectado y sistema.
- Usar el formato definido en la guía de nombres de bug reports.

**Ejemplo**:  
`[High] [Frontend] [Checkout] Payment button not responding on Chrome`

---

### Descripción del error
- Describir claramente el comportamiento observado.
- Indicar si el error es constante o intermitente.
- Evitar términos vagos como “no funciona”.

---

### Pasos para reproducir el bug
- Enumerar paso por paso lo necesario para llegar al error.
- Ser lo más específico posible.

**Ejemplo**:
1. Iniciar sesión como usuario cliente.
2. Navegar al módulo de Checkout.
3. Seleccionar método de pago y hacer clic en “Pagar”.
4. El botón no responde ni muestra feedback visual.

---

### Resultado esperado vs resultado actual
- Qué debería ocurrir vs. qué ocurre realmente.

**Ejemplo**:  
- ✅ **Esperado**: Al hacer clic en “Pagar”, se procesa el pago y se muestra una pantalla de confirmación.  
- ❌ **Actual**: No ocurre ninguna acción al presionar el botón.

---

### Contexto del entorno de pruebas
- Navegador, dispositivo, sistema operativo, fecha, versión del sistema.

**Ejemplo**:
- Chrome v124.0, Windows 10, resolución 1366x768, Sprint 17 (deploy del 12/04/2025).

---

### Evidencia visual
- Capturas de pantalla, video o grabación de pantalla (Loom, XRecorder, etc.).
- Adjuntar archivos si es posible o incluir links.

---

### Logs / Mensajes de consola (si aplica)
- Copiar el error desde la consola si es visible.
- Adjuntar fragmentos JSON, tracebacks u otros detalles técnicos útiles.

---

### Enlace al Bug Report original (opcional)
- Si el bug ya fue documentado por otro canal (formulario, planilla, etc.), incluir el link directo para referencia.

---

> ⚠️ Las tasks sin esta información corren el riesgo de ser rechazadas o quedar en revisión indefinida.
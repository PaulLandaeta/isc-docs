# Plantilla Ejemplo para Registrar una Task de Bug Report

Se recomienda copiar y pegar esta plantilla al crear una Task en el sistema de gestión (Taiga, Jira, etc.), reemplazando el contenido entre paréntesis.
Durante la revisión de tareas anteriores, se identificaron errores comunes como descripciones vagas, ausencia de pasos reproducibles o títulos genéricos, lo cual motivó la creación de esta guía.

---

## Título

`[Severidad] [Sistema] [Módulo] Descripción breve del error`

**Ejemplo**:  
`[High] [Frontend] [Login] Button freezes after clicking 'Submit' on mobile`

---

## Descripción del error

(Describe el comportamiento observado del sistema. Indica si el error es constante o intermitente.)

**Ejemplo**:  
Después de rellenar el formulario de acceso y hacer clic en «Enviar», la página se bloquea y no se muestra ninguna respuesta. El problema se produce sistemáticamente en los navegadores móviles.

---

## Pasos para reproducirlo

1. Vaya a la página de inicio de sesión.
2. Introducir credenciales válidas.
3. Haga clic en el botón «Enviar».
4. Observe la congelación y la falta de respuesta.

---

## Resultado esperado vs actual

- **Esperado**: El usuario es redirigido al panel de control tras iniciar sesión correctamente.
- **Actual**: El botón se congela y no ocurre nada.

---

## Entorno de pruebas

- Browser: Safari 16.2
- OS: iOS 17.3.1
- Device: iPhone 13 mini
- App version: v2.5.3 (deploy 11/04/2025)

---

## Evidencia

(Screenshot o link a Loom, XRecorder u otra grabación)  
Ejemplo: https://loom.com/share/bug-login-submit-freeze

---

## Logs / Consola

Uncaught TypeError: Cannot read properties of undefined (reading 'token') at submitLogin (login.js:48)

---

## Enlace al Bug Report (opcional)

(Si ya se documentó en otra herramienta o Excel, incluir aquí el enlace)  
Ejemplo: https://drive.google.com/bug-report-login-v253
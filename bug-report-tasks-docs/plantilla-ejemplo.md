# Plantilla Ejemplo para Registrar una Task de Bug Report

Se recomienda copiar y pegar esta plantilla al crear una Task en el sistema de gestión (Taiga, Jira, etc.), reemplazando el contenido entre paréntesis.  
Durante la revisión de tareas anteriores, se identificaron errores comunes como descripciones vagas, ausencia de pasos reproducibles o títulos genéricos, lo cual motivó la creación de esta guía.

---

## TÍTULO

`[Severidad] [Sistema] [Módulo] Descripción breve del error`

**Ejemplo**:  
`[High] [Frontend] [Login] Button freezes after clicking 'Submit' on mobile`

---

## DESCRIPCIÓN DEL ERROR

(Describe el comportamiento observado del sistema. Indica si el error es constante o intermitente.)

**Ejemplo**:  
Después de rellenar el formulario de acceso y hacer clic en «Enviar», la página se bloquea y no se muestra ninguna respuesta. El problema se produce sistemáticamente en los navegadores móviles.

---

## PASOS PARA REPRODUCIRLO

1. Vaya a la página de inicio de sesión.
2. Introducir credenciales válidas.
3. Haga clic en el botón «Enviar».
4. Observe la congelación y la falta de respuesta.

---

## RESULTADO ESPERADO VS ACTUAL

- **Esperado**: El usuario es redirigido al panel de control tras iniciar sesión correctamente.
- **Actual**: El botón se congela y no ocurre nada.

---

## ENTORNO DE PRUEBAS

- Browser: Safari 16.2  
- OS: iOS 17.3.1  
- Device: iPhone 13 mini  
- App version: v2.5.3 (deploy 11/04/2025)

---

## EVIDENCIA

(Screenshot o link a Loom, XRecorder u otra grabación)  
Ejemplo: https://loom.com/share/bug-login-submit-freeze

---

## LOGS / CONSOLA

`Uncaught TypeError: Cannot read properties of undefined (reading 'token') at submitLogin (login.js:48)`

---

## ENLACE AL BUG REPORT (opcional)

(Si ya se documentó en otra herramienta o Excel, incluir aquí el enlace)  
Ejemplo: https://drive.google.com/bug-report-login-v253

---

## EJEMPLO COMPLETO SIMULADO (LOGIN)

Este ejemplo representa cómo se debería documentar un bug real:

---

### Título  
`[High] [Frontend] [Login] Login fails with correct credentials`

### Descripción  
Cuando el usuario intenta iniciar sesión con credenciales correctas, el sistema muestra un mensaje de error de “contraseña incorrecta” aunque los datos sean válidos. El error ocurre siempre en dispositivos móviles.

### Pasos para reproducir  
1. Ir a la pantalla de inicio de sesión  
2. Ingresar el email `user@test.com` y contraseña correcta  
3. Presionar “Iniciar Sesión”  
4. Aparece mensaje de error: “Invalid password”

### Resultado esperado vs actual  
- **Esperado**: Usuario accede al dashboard correctamente  
- **Actual**: Se muestra error de contraseña y no se accede

### Entorno de pruebas  
- Browser: Chrome 123  
- OS: Android 13  
- Device: Pixel 6  
- App version: v2.5.3 (deploy 13/04/2025)

### Evidencia  
Captura adjunta + grabación Loom: `https://loom.com/share/login-error-test`

### Logs / Consola  
`401 Unauthorized: Token rejected for user ID 101`

### Enlace al Bug Report (opcional)  
_No documentado previamente_
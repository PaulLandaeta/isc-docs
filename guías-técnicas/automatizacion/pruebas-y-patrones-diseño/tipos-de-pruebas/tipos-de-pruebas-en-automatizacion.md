# Tipos de Pruebas en Automatización

## 1. Smoke Test

### 1.1 Definición
Un *Smoke Test* es un conjunto básico de pruebas que se ejecutan para verificar que las funcionalidades principales de una aplicación funcionan correctamente antes de proceder con pruebas más exhaustivas. Su objetivo es determinar si una nueva compilación del software es estable y puede someterse a pruebas más rigurosas.

### 1.2 Aplicación
- Se ejecuta en cada nueva compilación del software.
- Ayuda a detectar fallos críticos en una etapa temprana del desarrollo.
- Se compone de casos de prueba que validan funciones esenciales sin probar en profundidad.
- Se puede automatizar utilizando herramientas como Selenium, Cypress o JUnit.
- Usualmente forma parte de un proceso de integración continua para validar builds de software.

## 2. Regression Test

### 2.1 Definición
Un *Regression Test* (prueba de regresión) se encarga de garantizar que los cambios recientes en el código no hayan introducido defectos en las funcionalidades previamente implementadas y verificadas. Se basa en la ejecución repetida de pruebas para confirmar que el software sigue funcionando como se espera después de actualizaciones o correcciones de errores.

### 2.2 Importancia
- Asegura la estabilidad del software después de modificaciones.
- Se ejecuta periódicamente o automáticamente en pipelines de CI/CD.
- Puede incluir pruebas unitarias, de integración y funcionales.
- Se pueden utilizar herramientas como Selenium WebDriver, TestNG, Jest y Mocha para su automatización.
- Facilita la detección temprana de errores en funciones ya existentes sin afectar la experiencia del usuario.

## 3. Pruebas End-to-End (E2E)

### 3.1 Definición
Las pruebas *End-to-End* verifican el funcionamiento de toda la aplicación de extremo a extremo, asegurando que todos los módulos interactúan correctamente. Evalúan flujos de usuario completos, desde la interfaz hasta la base de datos y sistemas externos, garantizando que cada componente funcione como un todo integrado.

### 3.2 Implementación
1. Identificar los flujos críticos del usuario.
2. Automatizar las interacciones con la interfaz.
3. Ejecutar pruebas en entornos de preproducción.
4. Validar la salida esperada en cada paso del flujo.
5. Se pueden implementar con herramientas como Cypress, Playwright, Selenium y WebDriverIO.
6. Ayudan a detectar fallos en la integración entre diferentes sistemas o servicios.

---


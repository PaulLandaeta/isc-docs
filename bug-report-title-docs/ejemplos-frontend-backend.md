# Ejemplos de Títulos de Bug Reports para Frontend y Backend

A continuación se presentan ejemplos prácticos de títulos bien y mal redactados para documentos de Bug Reports, divididos según el sistema afectado. 

---

## 🔹 Ejemplos Correctos – Frontend

| Severidad  | Sistema   | Módulo     | Título                                                                 |
|------------|-----------|------------|------------------------------------------------------------------------|
| Critical   | Frontend  | Login      | Form does not render on Safari                                         |
| High       | Frontend  | Checkout   | Payment button disabled on mobile devices                              |
| Medium     | Frontend  | Dashboard  | Charts misaligned on window resize                                     |
| Low        | Frontend  | Navbar     | Icons misaligned on iPhone SE                                          |
| High       | Frontend  | Modal      | Close button not clickable after opening twice                         |
| Medium     | Frontend  | Search     | Autocomplete suggestions not showing                                   |
| Low        | Frontend  | Tooltip    | Text overflow in small resolution                                      |

> Estos títulos indican claramente el módulo, el sistema, la severidad y el comportamiento observado.

## 🔹 Ejemplos Correctos – Backend

| Severidad  | Sistema   | Módulo        | Título                                                                      |
|------------|-----------|---------------|-----------------------------------------------------------------------------|
| Critical   | Backend   | Auth          | Token validation fails for expired sessions                                 |
| High       | Backend   | Orders        | API returns 500 error for invalid payment method                            |
| Medium     | Backend   | Reports       | Delay in response time over 10s                                             |
| Low        | Backend   | Notifications | Email retry mechanism fails silently                                        |
| High       | Backend   | Payments      | Incorrect currency conversion for USD                                       |
| Medium     | Backend   | Users         | Duplicate user ID creation in edge case                                     |
| Low        | Backend   | Logs          | Debug logs appear in production environment  

> En estos casos, se detallan errores específicos en la lógica o respuestas del servidor.

## ❌ Ejemplos Incorrectos – Ambos sistemas

| Título Incorrecto      | Problema                                                           |
|------------------------|--------------------------------------------------------------------|
| `Error en el login`    | Está en español, sin estructura ni información clara.              |
| `Bug checkout`         | No tiene contexto ni severidad.                                    |
| `No se muestra`        | Frase ambigua, sin indicar el módulo afectado.                     |
| `Problema con API`     | Genérico, no describe el tipo de problema ni el comportamiento.    |
| `Fix backend`          | Vago, sin detalles ni formato estándar.                            |
| `Se rompe al darle click`     | Sin sistema, módulo ni lenguaje estándar.                   |
| `pantalla se queda blanca`    | No está en inglés, y no hay descripción técnica.            |

---

> Estos ejemplos sirven como guía directa para la redacción de nuevos títulos de Bug Reports, y deben utilizarse como referencia en la validación de futuras entregas.
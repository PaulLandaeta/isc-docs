# Test Case - Validación de mensaje de error en campo obligatorio

**Nombre del Proyecto:** Plataforma Educativa - Módulo Problemas  
**Versión del Proyecto:** 1.0.0  
**ID del Test Case:** TC-FE-PROB-002  
**Nombre del Desarrollador:** QA Dev  
**Autor del Test Case:** Belen QA  
**Revisado por:** QA Lead Adrián  

---

## Detalles del Test

**Título del Test:** Validación de mensaje de error en campo obligatorio  

**Descripción del Test:**  
Verificar que el sistema muestre un mensaje de error al dejar vacío un campo obligatorio en el formulario de creación de problemas.

---

## Datos de Autenticación

- **Usuario:** qa_front@example.com  
- **Contraseña:** TestFrontend456  

---

## Precondiciones

- Acceso a la plataforma con credenciales válidas  
- Conexión estable a internet  
- Navegador compatible y actualizado  

---

## Pasos para Reproducir

1. Iniciar sesión en la plataforma  
2. Acceder al formulario de creación de problemas  
3. Dejar vacío el campo 'Título' y hacer clic en 'Guardar'  
4. Corregir el campo vacío y enviar de nuevo  

---

## Procedimiento del Test

| Paso | Acción                                                  | Resultado Esperado                                    | Resultado Actual                                     | Estado |
|------|----------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------|--------|
| 1    | Iniciar sesión en la plataforma                          | Usuario autenticado correctamente                      | Usuario autenticado correctamente                    | ✅     |
| 2    | Acceder al formulario de creación de problemas           | Formulario visible correctamente                       | Formulario visible correctamente                     | ✅     |
| 3    | Dejar vacío el campo 'Título' y hacer clic en 'Guardar'  | Mensaje de error visible: "El título es obligatorio"   | Mensaje mostrado correctamente                       | ✅     |
| 4    | Corregir y enviar de nuevo                               | Formulario se envía correctamente                      | Formulario enviado sin errores                       | ✅     |

---

## Resultado del Test

**Estado General:** ✅ Aprobado  

---

## Notas Adicionales

- La validación funciona correctamente al detectar campos vacíos.  
- Se recomienda aplicar estilos más visibles para mejorar la experiencia del usuario.

---

## Multimedia

- Adjuntar captura de pantalla o enlace a video

---

## Información del Tester

- **Nombre:** Belen QA  
- **Fecha:** 28/03/2025 - 10:30  
- **Sistema Operativo:** Windows 11  
- **Navegador:** Mozilla Firefox 123.0  
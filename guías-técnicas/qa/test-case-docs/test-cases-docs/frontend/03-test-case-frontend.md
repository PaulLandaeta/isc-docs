# Test Case - Verificación de navegación entre tabs del editor

**Nombre del Proyecto:** Plataforma Educativa - Módulo Problemas  
**Versión del Proyecto:** 1.0.0  
**ID del Test Case:** TC-FE-PROB-003  
**Nombre del Desarrollador:** QA Dev  
**Autor del Test Case:** Brandon QA  
**Revisado por:** QA Lead Adrián  

---

## Detalles del Test

**Título del Test:** Verificación de navegación entre tabs del editor  

**Descripción del Test:**  
Asegurar que los tabs (Descripción, Entrada, Salida) cambian de vista correctamente al ser seleccionados.

---

## Datos de Autenticación

- **Usuario:** frontend_tester@example.com  
- **Contraseña:** ValidFrontTest789  

---

## Precondiciones

- Acceso a la plataforma con credenciales válidas  
- Conexión estable a internet  
- Navegador compatible y actualizado  

---

## Pasos para Reproducir

1. Iniciar sesión con cuenta válida  
2. Ir al editor de problemas  
3. Hacer clic en el tab 'Entrada'  
4. Hacer clic en el tab 'Salida'  

---

## Procedimiento del Test

| Paso | Acción                                  | Resultado Esperado                           | Resultado Actual                              | Estado |
|------|------------------------------------------|-----------------------------------------------|------------------------------------------------|--------|
| 1    | Iniciar sesión con cuenta válida         | Usuario autenticado correctamente             | Usuario autenticado correctamente             | ✅     |
| 2    | Ir al editor de problemas                | Editor se carga con los tabs visibles         | Editor cargado correctamente                  | ✅     |
| 3    | Hacer clic en el tab 'Entrada'           | Se muestra contenido del tab 'Entrada'        | Contenido cargado sin problemas               | ✅     |
| 4    | Hacer clic en el tab 'Salida'            | Se muestra contenido del tab 'Salida'         | Contenido no cambió de tab                    | ❌     |

---

## Resultado del Test

**Estado General:** ❌ Fallido  

---

## Notas Adicionales

- Existe un bug que impide el cambio de tab a 'Salida'.  
- Revisar el evento `onClick` del componente de tabs.

---

## Multimedia

- Adjuntar captura de pantalla o enlace a video

---

## Información del Tester

- **Nombre:** Brandon QA  
- **Fecha:** 28/03/2025 - 11:00  
- **Sistema Operativo:** Windows 11  
- **Navegador:** Google Chrome 122.0  
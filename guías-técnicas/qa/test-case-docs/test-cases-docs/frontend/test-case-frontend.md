# Test Case - Creación de Problema sin Subtítulos Vacíos

**Nombre del Proyecto:** Plataforma Educativa - Módulo Problemas  
**Versión del Proyecto:** 1.0.0  
**ID del Test Case:** TC-FE-PROB-001  
**Nombre del Desarrollador:** Carla Dev  
**Autor del Test Case:** QA Ron  
**Revisado por:** QA Lead Adrián  

---

## Detalles del Test

**Título del Test:** Validación de subtítulos vacíos al crear un problema.  

**Descripción del Test:**  
Verificar que, al crear un problema, no se muestren subtítulos como "Entrada" y "Salida" si no se ha ingresado contenido en dichas secciones.

---

## Datos de Autenticación

- **Usuario:** testuser@example.com  
- **Contraseña:** UserTest123  

---

## Precondiciones

- Tener acceso a la plataforma con un rol autorizado.  
- Contar con conexión estable a internet.  
- Navegador actualizado (Google Chrome, Firefox o similar).  

---

## Pasos para Reproducir

1. Iniciar sesión en la plataforma.  
2. Navegar a la sección de "Problemas".  
3. Crear un nuevo problema sin ingresar texto en los campos de "Entrada" y "Salida".  
4. Guardar el problema y acceder al detalle del mismo.  

---

## Procedimiento del Test

| Paso | Acción                                                      | Resultado Esperado                                      | Resultado Actual                                     | Estado |
|------|-------------------------------------------------------------|----------------------------------------------------------|------------------------------------------------------|--------|
| 1    | Iniciar sesión en la plataforma                             | Usuario autenticado correctamente                        | Usuario autenticado correctamente                    | ✅     |
| 2    | Acceder al módulo de problemas                              | Se muestra la sección con lista de problemas             | Se muestra correctamente                             | ✅     |
| 3    | Crear problema sin llenar "Entrada" ni "Salida"             | El problema se guarda sin mostrar esos subtítulos vacíos | Subtítulos visibles aunque no tienen contenido       | ❌     |
| 4    | Visualizar el detalle del problema creado                   | Subtítulos "Entrada" y "Salida" no deberían mostrarse    | Subtítulos aparecen sin contenido                    | ❌     |

---

## Resultado del Test

**Estado General:** ❌ Fallido  

---

## Notas Adicionales

- La lógica de renderizado de subtítulos no verifica si hay contenido antes de mostrarlos.  
- Posible mejora: aplicar condicional para no renderizar subtítulos vacíos.  

---

## Multimedia

Adjuntar captura de pantalla o enlace a video (drive, loom, etc).

---

## Información del Tester

- **Nombre:** Ron QA  
- **Fecha:** 27/03/2025 - 22:00  
- **Sistema Operativo:** Windows 11  
- **Navegador:** Google Chrome 122.0  

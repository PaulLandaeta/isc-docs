# 🧪 Documentación de Test Cases

Este módulo recopila las convenciones, estructuras y buenas prácticas para redactar **Test Cases** de manera clara y efectiva. La guía está alineada con la plantilla proporcionada por el equipo, y considera tanto el enfoque de **Frontend** como el de **Backend**, ya que existen diferencias clave en su forma de documentar.

---

## Índice

- [Estructura de un Test Case](./estructura/README.md)
- [Ejemplos de Test Cases](./ejemplos/README.md)
- [Criterios de Aceptación](./criterios/README.md)
- [Plantilla Oficial](./plantilla/README.md)

---

## Objetivos

- Documentar la estructura y propósito de un Test Case.
- Incluir ejemplos prácticos bien redactados.
- Definir criterios de aceptación claros y medibles.
- Alinear la documentación con la plantilla oficial del equipo.

---

## Plantillas Oficiales

En la carpeta `plantillas` se incluyen los documentos base utilizados por el equipo:

- `TestCaseFrontend.docx`: Plantilla referencial para pruebas de UI.
- `TestCaseBackend.docx`: Plantilla referencial para pruebas de API u operaciones internas.

Estas plantillas deben acompañar a la documentación para facilitar su comprensión y aplicación.

---

## Módulos

- **Frontend:** Contiene Test Cases orientados a interfaces gráficas. Los pasos deben ser extremadamente detallados (e.g., hacer clic en botones, ingresar texto, seleccionar opciones).
- **Backend:** Incluye Test Cases orientados a validaciones de lógica del servidor o endpoints. Suele incluir capturas de Postman, payloads, respuestas esperadas, códigos de estado, etc.

---

## Herramientas y formato

| Elemento clave         | Descripción                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Plantilla Base**     | Se utiliza el archivo `plantilla-test-case.docx` como estructura principal. |
| **Formato**            | Markdown (`.md`) para documentación técnica.                                |
| **Organización**       | Por módulo (`frontend` y `backend`), cada uno con su propio README.         |

---

## Estructura de un Test Case

Todo Test Case debe contener como mínimo los siguientes campos:

- **ID del Test Case**  
  ➤ Un identificador único, siguiendo convenciones específicas por módulo.

- **Título**  
  ➤ Descripción breve y clara del objetivo de la prueba.

- **Precondiciones**  
  ➤ Requisitos previos (usuarios, datos, entorno, permisos, etc.).

- **Datos de Prueba**  
  ➤ Inputs a utilizar en la prueba (pueden incluir cuentas, credenciales, etc.).

- **Pasos**  
  ➤ Instrucciones detalladas paso a paso que permitan replicar la prueba.

- **Resultado Esperado**  
  ➤ Comportamiento esperado del sistema al seguir los pasos.

- **Resultado Actual**  
  ➤ Comportamiento real observado al ejecutar la prueba.

- **Estado**  
  ➤ Resultado de la prueba (✅ Passed / ❌ Failed).

- **Notas adicionales** (opcional)  
  ➤ Comentarios, capturas, videos o enlaces útiles.

---

## Tipos de Test Cases

| Tipo             | Descripción                                                                 |
|------------------|------------------------------------------------------------------------------|
| **Happy Path**   | Flujo correcto donde todo se ejecuta sin errores.                           |
| **Negative Case**| Pruebas con datos erróneos o condiciones inválidas para validar el sistema. |
| **Edge Case**    | Casos límite o extremos no habituales.                                      |

---

## Buenas Prácticas

✔ Usar títulos descriptivos y precisos.  
✔ Ser detallado en los pasos para permitir la reproducción exacta.  
✔ Evitar lenguaje ambiguo como “hacer clic por ahí” o “llenar con algo”.  
✔ Usar identificadores únicos para los Test Cases.  
✔ Documentar errores comunes y variantes (positivas y negativas).  
✔ Agrupar los Test Cases según funcionalidades o módulos.

---

## Notas Finales

- Todos los Test Cases deben organizarse según su tipo (frontend o backend).  
- Cualquier nuevo ejemplo debe agregarse en su carpeta correspondiente.  
- La plantilla oficial debe estar siempre disponible en este repositorio.  
- Este README puede ser actualizado a medida que se mejoren las prácticas de documentación.

---

## Referencias

- Plantilla oficial: [`Test Case`](./test-case.md)
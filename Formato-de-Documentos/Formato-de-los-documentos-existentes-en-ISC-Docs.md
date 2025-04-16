# 📄 Formato de los documentos existentes en ISC-Docs  

Este documento centralizado contiene toda la documentación estandarizada del proyecto con el fin de revisar, corregir y unificar el formato, estructura y nomenclatura de todos los archivos de documentación, garantizando coherencia y cumplimiento con los estándares del equipo.

## 📜 Reglas Globales para Todos los Documentos  

### 🗂️ Jerarquía de encabezados  

- (#) Título principal

- (##) Subtítulo

- (###) Subsección

### 🏷️ Emojis estandarizados por tipo de sección  

- (📌) Introducción
- (🔧) Configuración
- (⚠️) Manejo de Errores
- (🎯) Conclusión
- (🔗) Referencias

### 💻 Bloques de código

Antes de cada bloque, añadir una descripción breve

- 📌 **Introducción**: Descripción del propósito del documento.

- 🔧 **Configuración**: Contexto sobre qué se configura y por qué.

- ⚠️ **Manejo de Errores**: Breve explicación de cómo abordar fallos.

- 🛠️ **[Nombre de Herramienta/Proceso]**: Qué es y cuándo usarlo.

- 🔍 **Monitoreo (o Verificación)**: Qué se monitorea y con qué herramientas.

- 🎯 **Conclusión (o Puntos Clave)**: Resumen + lista de 3-5 puntos clave.

- 🔗 **Referencias (o Recursos Adicionales)**: Lista de enlaces relevantes.

---

## 📂 Estandarización del Inventario de Documentación ISC-Docs  

Para que se respeto un mismo formato en todos los archivos, se sugiere realizar cambios en los nombres de las carpetas y de sus respectivos archivos de documentación técnica; es así que se puede obtener un listado estandarizado. Con los cambios aplicados la estructura se debería ver así:

- **DevOps**

  - Despliegue-del-Servidor.md

  - Documentacion-de-Monitoreo-y-Logs.md

  - Guia-de-Setup.md

- **Documentacion-de-Grupos-de-Equipo**

  - Definicion-de-Asignacion-de-Grupos-y-Roles.md

  - Formato-de-Registro-de-Equipos.md

  - Normas-de-Trabajo-en-Equipos.md

- **Estrategia-de-Automatizacion**

  - Estandares-y-Buenas-Practicas.md

- **Estructura-Backend**

  - Estructura-Backend.md

- **Gamificaciones**

  - Manejo-de-Puntos.md

  - Tareas-por-Rol.md

  - Tipos-de-Rol.md

- **Pruebas-y-Patrones**

  - Patrones-de-Diseno-en-Automatizacion.md

  - Tipos-de-Pruebas-en-Automatizacion.md

- **Bug-Report-Docs**

  - Documentacion-de-Bug-Reports.md
  
- **Estructura-Proyecto-Frontend**

  - Introduccion.md

  - Configuracion.md

  - PDFs.md

  - Estructura-del-Proyecto-Frontend.md

- **Gitflow-PRs**

  - Introduccion.md Pull-Request.md

  - Gitflow.md

  - Convenciones-de-Commit.md

- **Test-Cases-Docs-Backend-y-Frontend**
  - Documentacion-de-Test-Cases-Backend.md

  - Documentacion-de-Test-Cases-Frontend.md

Para esta ocasión, los documentos están sin tíldes para prevenir algunos errores de compilación y reconocimiento de caracteres ajenos (distintos) a los establecidos en los lenguajes de programación populares, que generalmente están desarrollados en inglés.

---

## 🔍 Corrección y Estandarización de Documentos  

Proceso de revisión y unificación de formatos, nombres y estructuras para garantizar consistencia en la documentación del repositorio.

- **DevOps**

  - **Despliegue-del-Servidor.md**

    - **Emojis Repetidos o Inconsistentes**
      - 🛠️ Configuración de Servidores → 🔧 Configuración de Servidores.

      - 🛠️ Manejo de Errores → ⚠️ Manejo de Errores.

    - **Textos Introductorios Faltantes**

      - 📊 Flujo de Despliegue desde CI/CD hasta Producción (Falta descripción del diagrama de flujo).

      - 🛠️ Configuración de Servidores para Staging y Producción (Falta contexto sobre criterios de configuración).

      - 🔄 Configuración de Jenkins o GitHub Actions (Falta explicación del propósito de los pipelines).

      - 📜 Comandos para Iniciar y Verificar el Despliegue (Falta indicar cuándo/usar estos comandos).

      - 🔍 Ejemplos de Logs de Despliegue (Falta explicar qué información buscar en logs).

      - 🛠️ Manejo de Errores y Rollback (Falta contexto sobre protocolo de errores).

      - 📊 Monitoreo Post-Despliegue (Falta indicar objetivos del monitoreo).

    - **Bloques Faltantes**

      - No existe sección 🔗 Referencias

    - **Conclusión**
      - El texto para concluir es denso; se sugiere evitar redundancias y ser más puntual.

    - **Mayor Limpieza en el Documento**

      - Sobran espacios después de texto.

      - Faltan lineas para diferenciar bloques o segmentos.

      - Bloques de código sin contexto (lenguaje utilizado).

      - Eliminar los ':' de los subtitulos y en vez añadir un breve texto debajo (**opcional**).

  - **Documentacion-de-Monitoreo-y-Logs.md**

    - **Emojis Inconsistentes**

      - 🛠️ Herramientas de Monitoreo → 🔧 Herramientas de Monitoreo

      - 🛠️ Buenas prácticas → 📌 Buenas prácticas

    - **Textos Introductorios Faltantes**

      - Estructura de un Log (Falta explicar por qué estandarizar formatos).

      - ¿Cómo se monitorea con Logs? (Falta contexto sobre objetivos del monitoreo).

    - **Consistencia en Títulos**

      - Reemplazar títulos de pregunta con afirmaciones claras y concisa.

        - ¿Qué es un Log? → Definición de un Log.

        - ¿Cómo se monitorea con Logs? → Monitoreo de un Log.

    - **Conclusión poco Accionable**

      - Las conclusiones podrían ser más extensas y explícitas.

    - **Mayor Limpieza en el Documento**

      - Sobran espacios después de texto.

      - Faltan lineas para diferenciar bloques o segmentos.

      - Bloques de código sin contexto (lenguaje utilizado).

      - Los Emojis deberían ir delante del texto del título/subtítulo.

  - **Guia-de-Setup.md**

    - **Referencias**

      - Falta enlace a GitHub Flow (para metodología de ramas).

      - Falta enlace a GitLab CI/CD Docs (como alternativa a GitHub Actions).

      - Falta enlace a Jenkins Pipeline Syntax.

    - **Consistencia en Títulos**

      - Reemplazar títulos de pregunta con afirmaciones claras y concisa.

        - ❓ ¿Qué es CI (Integración Continua)? → 🔄 Integración Continua (CI).

        - ❓ ¿Qué es CD (Despliegue Continuo)? → 🚀 Despliegue Continuo (CD).

    - **Mayor Limpieza en el Documento**

      - Bloques de código sin contexto (lenguaje utilizado).

- **Documentacion-de-Grupos-de-Equipo**

  - **Definicion-de-Asignacion-de-Grupos-y-Roles.md**

    - **Falta de texto introductorio**

      - 📊 Equipos gestión 2025 (No explica el propósito de esta sección).

      - 🚀 Descripción de Niveles de Experiencia (Falta contexto sobre cómo se relaciona con la gamificación).

    - **Bloques Faltantes**

      - No existe sección 🔗 Referencias

    - **Inconsistencias en emojis de títulos**

      - 📖 Descripción → 📌 Descripción

      - 📊 Equipos gestión 2025 → 👥 Equipos gestión 2025

    - **Mayor Limpieza en el Documento**

      - Faltan/Sobran lineas para diferenciar bloques o segmentos.

      - Línea --- sobrante al final

      - No se requiere el uso de (**) para un subtítulo

  - **Formato-de-Registro-de-Equipos.md**

    - **Problemas de Estructura y Jerarquía**

      - (###) 📌 Datos del Equipo → (##) 📌 Datos del Equipo

      - (###) 📄 Ejemplo de Registro → (##) 📄 Ejemplo de Registro

    - **Falta de Texto Introductorio**

      - 📌 Datos del Equipo (No explica el propósito de esta sección).

      - 📄 Ejemplo de Registro (No explica qué representa el ejemplo).

    - **Bloques Faltantes**

      - No se requiere la sección 🔗 Referencias

      - No se requiere la sección 🎯 Conclusiones

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - La línea divisoria (|---|) no coincide con el ancho del texto.

      - Línea --- sobrante al final.

      - Eliminar los ':' de los subtitulos y en vez añadir un breve texto debajo (**opcional**).

  - **Normas-de-Trabajo-en-Equipos.md**

    - **Problemas de Estructura y Jerarquía**

      - Subtítulos mal nivelados → ### 📖 Descripción debería ser ## 📖 Descripción (nivel ## en lugar de ###).

      - Inconsistencia en niveles → ## 📌 Normas Generales vs ### 🛠️ DevOps (roles deberían estar al mismo nivel jerárquico que normas generales).

    - **Falta de Texto Introductorio en Secciones**

      - 🏗️ Normas por Roles (Falta una breve descripción que explique el propósito de esta división por roles).

      - 🔄 Normas Generales entre Equipos (No explica cómo se relaciona con las normas internas de equipo).

    - **Mayor Limpieza en el Documento**

      - Faltan/Sobran lineas para diferenciar bloques o segmentos.

      - Falta línea en blanco después de --- (antes de ## 📌 Normas Generales).

    - **Bloques Faltantes**
      - No existe sección 🔗 Referencias

- **Estrategia-de-Automatizacion**

  - **Estandares-y-Buenas-Practicas.md**

    - **Título del Documento Faltante**

      - Añadir un título con su respectiva jerarquía (#)

    - **Problemas de Estructura y Jerarquía**

      - (#) 🔹 1. Estándares de nomenclatura → (##) 🔹 1. Estándares de nomenclatura

      - (#) 🔹 2. Esructura recomendada → (##) 🔹 1. Estándares de nomenclatura

      - Existe error de jerarquía en todo el documento.

    - **Emojis Repetidos o Inconsistentes**

      - Repetición de emojis (🔹, ✅)

    - **Bloques de Código**

      - Falta descripción previa en algunos bloques.

    - **Mayor Limpieza en el Documento**

      - Faltan lineas para diferenciar bloques o segmentos.

      - Eliminar los ':' de los subtitulos y en vez añadir un breve texto debajo (**opcional**).

      - Falta línea en blanco después de --- en algunas secciones.

      - Errores tipográficos.

- **Estructura-Backend**

  - **Estructura-Backend.md**

    - **Títulos sin emojis**:

      - Representación esquematica → Falta emoji (ej: 📊).

    - **Bloques de Código**

      - Falta descripción previa en algunos bloques.

    - **Bloques Faltantes**

      - Faltan enlaces a Mongoose/Express docs.

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Eliminar los ':' de los subtitulos y en vez añadir un breve texto debajo (**opcional**).

      - Falta línea en blanco después de --- en algunas secciones.

      - Bloques de código sin contexto (lenguaje utilizado).

      - Errores tipográficos.

      - Eliminar numeración en ### 1. 📁 controllers/ → ### 📁 controllers/

- **Gamificaciones**

  - **Manejo-de-Puntos.md**

    - **Emojis Inconsistentes**

      - Introducción → Debería usar 📌.

      - Faltan emojis (ej: 🔄, 🐞) en Conversión de Story Points... y Recompensas por Resolución de Bugs.

    - **Listas con Formato Inconsistente**

      - Algunas usan - **texto** (negritas), otras solo - texto.

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Falta línea en blanco después de --- en algunas secciones.

      - Errores tipográficos.

      - Bloques de texto densos

  - **Tareas-por-Rol.md**

    - **Inconsistencias en el Estilo de Redacción**

      - Mezcla de 2da persona ("Debes documentar endpoints") y 3ra persona ("El Writer garantiza que...").

    - **Títulos sin emojis**

      - Progresión en el Rol de QA → 📈 Progresión en el Rol de QA.

    - **Falta contexto introductorio**

      - Antes de 🎨 Tareas de Frontend, añadir una línea explicando cómo se relacionan estas tareas con la gamificación.

    - **Errores de Formato**

      - Falta línea en blanco después de --- antes de ## 🎨 Tareas de Frontend.

      - Algunas usan - **texto**, otras solo - texto. Estandarizar con negritas para ítems clave.

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Podría ser más profesional: 👶 De Junior a Senior → Nivel Junior → Senior

      - Errores tipográficos/ortográficos.

  - **Tipos-de-Rol.md**

    - **Repetición de Contenido**

      - 👨‍🔬 ¿Qué es un Programador Senior? aparece dos veces (la segunda debería ser Lead).

    - **Problemas de Formato**

      - Algunas viñetas usan - **texto**, otras solo - texto.

      - Falta línea en blanco después de --- antes de ## 🧑‍🎓 ¿Qué es un Programador Junior?.

      - "Writer Junior" vs. "Writer Lead" (falta coherencia en mayúsculas).

    - **Contenido Redundante**

      - Conclusión muy extensa

    - **Mayor Limpieza en el Documento**

      - Sobran espacios después de texto.

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - 🚶 ¿Cómo pasar de Junior a Senior? → 📈 Progresión: Junior → Senior.

      - Mezcla de 3ra persona ("Un Junior debe...") y 2da persona ("Debes mejorar tus habilidades")

      - 🚶 (caminar) no refleja progresión profesional → Usar 📈 o 🚀

- **Pruebas-y-Patrones**

  - **Patrones-de-Diseno-en-Automatizacion.md**

    - **Inconsistencias de Formato**

      - Falta línea en blanco después de 2.Screenplay Pattern y con 3.Command Pattern.

      - Estandarizar con - para listas y reservar ✅ para checklists.

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Redundancia en Contenido**

      - Sección 1.4 "Beneficios del POM" repite información ya cubierta en 1.2 Ventajas del POM. Se puede eliminar la seccion 1.4

    - **Bloques Faltantes**

      - Incluir una conclusión similar a:

        ```markdown
        ## 🎯 Conclusión  
        Estos patrones (POM, Screenplay, Command) optimizan la automatización de pruebas mediante:  
        - **Modularidad**: Código reutilizable y mantenible.  
        - **Claridad**: Pruebas legibles y fáciles de depurar.  
        - **Escalabilidad**: Adaptables a cambios en la UI.  
        ```

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Añadir --- entre patrones principales para separar secciones.

      - 1.1 Descripción → 📌 Descripción para seguir estándares de emojis.

  - **Tipos-de-Pruebas-en-Automatizacion.md**

    - **Listas desbalanceadas**

      - En 1.2 Aplicación, hay 5 ítems, pero 4 usan puntos (-) y el 5° es un párrafo.

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Bloques Faltantes**

      - Falta introducción general:

        ```markdown
        # 🧪 Tipos de Pruebas en Automatización  
        
        Este documento clasifica los principales tipos de pruebas automatizadas, su aplicación y herramientas asociadas para garantizar calidad en el software.  
        ```

      - Falta conclusión

        ```markdown
        ## 🎯 Conclusión  
        Estas pruebas (Smoke, Regression, E2E) cubren diferentes niveles de validación:  
        - **Smoke**: Verificación rápida de funcionalidades críticas.  
        - **Regression**: Estabilidad tras cambios en el código.  
        - **E2E**: Validación de flujos completos del usuario.  
        ```

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Añadir --- entre patrones principales para separar secciones.

      - Falta línea en blanco antes de --- al final del documento.

- **Bug-Report-Docs**

  - **Documentacion-de-Bug-Reports.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Sección de Módulos Poco Clara**

      - Agregar estructura de carpetas:

        ```markdown
        📂 bug-reports/  
        ├── 📄 README.md          # Guía general  
        ├── 📂 frontend/          # Bugs de UI  
        │   ├── 📄 README.md      # Buenas prácticas específicas  
        │   └── 📄 ejemplo1.md    # Bug report de ejemplo  
        └── 📂 backend/           # Bugs de API/lógica  
            ├── 📄 README.md  
            └── 📄 ejemplo1.md   
        ```

    - **Mayor Limpieza en el Documento**

      - Falta línea en blanco después de --- antes de ## Objetivos

      - Faltan lineas para diferenciar bloques o segmentos.

- **Estructura-Proyecto-Frontend**

  Como mejora adicional se recomendaría tener una unica carpeta para todos los archivos de documentación en vez de tener una carpeta por archivo.

  - **Introduccion.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - (##) 📜 Introducción → (#) 📜 Introducción ya que es el título

      - Components, Hooks, y Pages podrían agruparse bajo 🗂️ Estructura Principal.

      - Configuración y Utils podrían agruparse bajo ⚙️ Configuración y Utilidades.

      - Falta un breve texto despues de los subtitulos.

    - **Agregar Guía Rápida de Uso**

      - Añadir una sección para nuevos desarrolladores:

        ```markdown
        ## 🚀 Primeros Pasos  
        1. Clonar el repositorio: `git clone [url]`  
        2. Instalar dependencias: `npm install`  
        3. Ejecutar en desarrollo: `npm run dev`   
        ```

    - **Mayor Limpieza en el Documento**

      - Falta línea en blanco después de --- antes de ## Objetivos.

      - Las referencias mencionadas no incluyen enlaces directos.

      - Eliminar los ':' de los subtitulos y en vez añadir un breve texto debajo (**opcional**).

  - **Configuracion.md**

    - **Estructura y Formato**

      - Añadir # 🛠️ Configuración del Proyecto al inicio como titulo o reducir un (#) en la jerarquía.

      - Falta un breve texto despues de los subtitulos.

    - **Emojis Inconsistentes**

      - 🛠️ Estructura... → 📂 Estructura...

    - **Reorganizar secciones**

      - Integrar beneficios con buenas prácticas

    - **Mayor Limpieza en el Documento**

      - Falta línea en blanco antes/después de bloques de código.

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

  - **PDFs.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Mayor Limpieza en el Documento**

      - Bloques de código sin contexto (lenguaje utilizado).

      - Añadir versiones de tecnologías

      - Falta una linea final.

      - Sobra un emoji al final (📎).

  - **Estructura-del-Proyecto-Frontend.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Falta contexto**

      - No explica qué significa "Estado" (¿Completado? ¿En progreso?).

    - **Agregar Guía Rápida de Uso**

      - Añadir una sección para nuevos desarrolladores:

        ```markdown
        ## 🚀 Primeros Pasos  
        1. Clonar el repositorio: `git clone [url]`  
        2. Instalar dependencias: `npm install`  
        3. Ejecutar en desarrollo: `npm run dev`   
        ```

    - **Mayor Limpieza en el Documento**

      - Falta espacio después del emoji en # 🏗️Estructura → Debería ser # 🏗️ Estructura.

      - Línea --- antes de "Referencias" no tiene línea en blanco previa

      - Añadir versiones de tecnologías

- **Gitflow-PRs**

  Como recomendación, se sugiere que los títulos de esta carpeta no tengan un número definido de comienzo, es decir que no estén enumerados en el título.

  - **Introduccion.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.
  
    - **Formato y Estructura**

      - Falta espacio después de - en los enlaces: ❌ -[PullRequest] → ✅ - [PullRequest]  

      - Play_text no es un lenguaje válido → Usar plaintext.

      - La lista de carpetas no coincide con los enlaces del índice.

      - Falta un breve texto despues de los subtitulos.

    - **Falta introducción motivadora:**

      - No explica por qué son importantes los PRs, GitFlow y commits estructurados:

        ```markdown
        Este documento estandariza el flujo de trabajo con Git para garantizar:  
        - ✅ **Trazabilidad**: Commits claros y PRs documentados.  
        - 🤝 **Colaboración**: Revisiones de código efectivas.  
        - 🚀 **CI/CD**: Integración con pipelines de despliegue.    
        ```

    - **Emojis Inconsistentes**

      - Introducción → Debería ser 📌 Introducción para seguir estándares

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Errores tipográficos.

      - Sobran espacios después de texto.

  - **Pull-Request.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - Existe error en la jerarquía ya que el documento comienza directamente con 1. Pull Requests (PR)

      - "Mantener la rama actualizada" aparece en 1.1 y 1.2 y se lo puede consolidar en una sola sección.

      - Falta un breve texto despues de los subtitulos.

    - **Mayor Limpieza en el Documento**

      - Sobran/Faltan lineas para diferenciar bloques o segmentos.

      - Errores tipográficos.

      - Sobran espacios después de texto.

      - Falta línea en blanco después de **Buenas prácticas:** en 1.1.

  - **Gitflow.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - Existe error en la jerarquía ya que el documento comienza directamente con 3. Gitflow: Flujo de trabajo con ramas

      - Las ramas en 3.2 usan - **main**: (negritas), pero otras secciones usan solo -.

      - Falta un breve texto despues de los subtitulos.

    - **Mayor Limpieza en el Documento**

      - Falta línea en blanco después de **Buenas prácticas:** en 3.1

      - Sobra línea en blanco antes de ### 3.2 Tipos de ramas...

  - **Convenciones-de-Commit.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - El documento comienza con 2. Convenciones de Commits → 📝 Convenciones de Commits al inicio

      - Falta un breve texto despues de los subtitulos.

    - **Mayor Limpieza en el Documento**

      - Falta línea en blanco después de **Buenas prácticas:**.

      - Sobra línea en blanco antes de #### Tipos comunes de commits.

- **Test-Cases-Docs-Backend-y-Frontend**

  - **Documentacion-de-Test-Cases-Backend.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - Añadir descripciones breves bajo cada título.

      - Mezcla de ✔ y - en listas.

    - **Mayor Limpieza en el Documento**

      - Faltan lineas para diferenciar bloques o segmentos.

  - **Documentacion-de-Test-Cases-Frontend.md**

    - **Falta de emojis en títulos:**

      - Título/subtítulos no cuentan con emojis.

    - **Formato y Estructura**

      - Añadir descripciones breves bajo cada título

    - **Mayor Limpieza en el Documento**

      - Faltan lineas para diferenciar bloques o segmentos.

## 🎯 Recapitulación  

Estos cambios garantizan:  

- **Consistencia**: Todos los documentos siguen la misma estructura.

- **Profesionalismo**: Presentación estandarizada y formal.  

- **Mantenibilidad**: Facilita actualizaciones y colaboración.

# Documentación del Módulo Docente

## Introducción

Este documento describe detalladamente el funcionamiento del **Módulo Docente** dentro del sistema de gestión académica de ISC. Aquí se explica paso a paso cómo se realiza el proceso de creación, edición, visualización y eliminación de docentes. Además, se documenta la estructura de la interfaz de usuario, validaciones necesarias y comportamiento del sistema ante entradas incorrectas. Todo el contenido sigue el estándar de documentación utilizado en el repositorio `isc-docs`.

---

##  Creación de Docente

### Acceso al módulo

Para comenzar, es necesario iniciar sesión en el sistema. Una vez dentro, desde la pantalla principal, se puede acceder al módulo de gestión de docentes haciendo clic en la opción correspondiente del menú desplegado a la derecha de la pantalla.

![Pantalla principal](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/pantalla-inicial.png)
*Figura 1: Página principal con el menú de opciones al lado derecho.*

---

### Formulario de creación

Al hacer clic en el botón **“Agregar Docente”**, se despliega un formulario que solicita los siguientes datos:

- **Nombre**
- **Apellido**
- **Código**
- **Correo electrónico**
- **Número de celular**
- **Curso asignado** (opcional)

![Formulario de registro](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/datos-docente.png)

*Figura 2: Formulario de registro de docente con campos para nombre, apellido, código, correo y celular.*

Cada campo está debidamente identificado con etiquetas claras y, en algunos casos, marcadores de obligatorio.

---

## Validaciones y Excepciones

### Campos obligatorios

Si el usuario intenta continuar sin completar los campos requeridos, el sistema mostrará un mensaje de advertencia resaltando los campos incompletos.

![Campos obligatorios](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/datos-erroneos-docente.png)

*Figura 3: Mensajes de error en rojo bajo los campos vacíos.*

---

### Validación del número de celular

El campo **número de celular** está sujeto a una validación especial. El sistema espera que este campo cumpla con el siguiente formato:

- Longitud mínima: **8 caracteres numéricos**
- No se permiten letras ni caracteres especiales

![Número inválido](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/numero-invalido.png)

*Figura 4: Campo de número de celular con el mensaje de error al introducir caracteres no válidos.*

---

### Código duplicado o correo inválido

- Si se intenta registrar un docente con un **código que ya existe**, se mostrará un mensaje de advertencia.
- Lo mismo ocurre si se proporciona un **correo electrónico inválido**.

![Correo inválido](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/correo-invalido.png)

*Figura 5: Campo de correo electrónico con el mensaje de error al introducir caracteres no válidos.*

---

## Agregar Docente al Sistema

### Creación exitosa del docente

Una vez que se ingresan todos los datos de forma correcta y se presiona el botón de guardar, el sistema:

1. Valida todos los campos
2. Registra la información del docente
3. Muestra una notificación de éxito

    ![Docente creado](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/docente-creado.png)

    *Figura 6: Notificación de creación exitosa del docente.*

4. Actualiza automáticamente la **tabla de docentes** con el nuevo ingreso

### Error inesperado al crear un docente

En algunos casos, puede aparecer un mensaje genérico de error con el texto **“¡Vaya! Error al crear el docente”**. Este mensaje no especifica la causa del fallo, y suele deberse a errores como:

- Datos inválidos no detectados por el frontend
- Fallas en la validación del backend

    ![Error al crear](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/docente-no-creado.png)

    *Figura 7: Notificación de error en la creación del docente.*

Cuando esto sucede, el usuario puede cerrar el mensaje y revisar los campos nuevamente o intentar enviar el formulario más tarde.

---

## Estructura de la Tabla de Docentes

Después de agregar al docente, este se visualizará en una tabla dinámica ubicada en el módulo. Esta tabla presenta los siguientes campos por cada docente registrado:

- **Código**
- **Nombre**
- **Correo**
- **Celular**
- **Curso**
- **Acciones**

![Tabla de docentes](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/encabezado-de-tabla-docente.png)
*Figura 8: Tabla de docentes con columnas: Código, Nombre, Correo, Celular, Curso y Acciones.*

---

## Acciones Disponibles

Cada docente listado en la tabla tiene una serie de acciones disponibles, identificadas mediante íconos ubicados en la columna de **Acciones**:

- **Editar**: Permite modificar la información del docente. Al hacer clic, se abre una ventana emergente con los campos previamente llenados.
- **Ver perfil**: Muestra todos los datos del docente en una vista completa, útil para consultas detalladas.
- **Eliminar**: Elimina al docente del sistema previa confirmación. Esta acción es irreversible.

![Acciones](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/acciones-docente.png)

*Figura 9: Fila mostrando los íconos de acciones: ver perfil (ojo), editar (lápiz) y eliminar (basurero).*

---

## Interfaz de Usuario

La interfaz de usuario ha sido diseñada para facilitar la gestión docente, y sus elementos clave son:

- **Botón Agregar Docente**: Visible desde el módulo, inicia el flujo de creación.
- **Modal/Formulario emergente**: Permite introducir los datos del docente sin salir de la pantalla principal.
- **Tabla de Docentes**: Se actualiza automáticamente con cada acción (agregado, edición o eliminación).
- **Íconos de acción**:
  - Lápiz para editar
  - Ojo para ver el perfil
  - Basurero para eliminar

![Interfaz completa](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/af4b8680598e344c96b22e6eaf2a5b549eafafac/Documentacion-de-Pagina/Creacion-de-Docente/interfaz-docente.png)
*Figura 10: Vista completa del módulo docente.*

---

## Conclusión

El módulo docente brinda una solución eficiente para la administración de personal académico dentro del sistema ISC. La estructura clara del formulario, las validaciones integradas y la tabla interactiva permiten una gestión precisa, ágil y sin complicaciones. Esta documentación busca facilitar el entendimiento de cada componente y proceso involucrado, alineándose con las buenas prácticas de desarrollo y usabilidad.

---

## Referencias

- Página del sistema web: [isc-system-web-qa.vercel.app](https://isc-system-web-qa.vercel.app/) *(acceso restringido a usuarios autenticados)*

---


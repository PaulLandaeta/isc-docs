# Módulo de Estudiantes 🎓

Este módulo permite la gestión completa de los estudiantes dentro del sistema ISC. A través de esta interfaz, es posible crear, visualizar, editar y eliminar estudiantes registrados. También se contempla la gestión de estudiantes becarios, permitiendo ingresar sus horas becarias correspondientes.

## ✍️ Creación de Estudiante

Para registrar un nuevo estudiante en el sistema, se debe acceder al formulario de creación con el botón `+ AGREGAR ESTUDIANTE`, donde se solicitan los siguientes datos obligatorios:

- **Nombre**
- **Apellido**
- **Código**
- **Correo**
- **Teléfono**

### 🧑‍🎓 Estudiante Becario

En caso de que el estudiante sea becario, el formulario incluye una opción que permite activar el ingreso de **horas becarias**. Al habilitar esta opción, se desplegará un campo adicional donde se deben ingresar las horas asignadas al estudiante.

## ➕ Agregar Estudiante

Una vez llenado el formulario con la información correspondiente, se debe hacer clic en el botón `GUARDAR`. Esta acción guarda los datos ingresados en la base de datos del sistema y actualiza automáticamente la tabla general, mostrando el nuevo estudiante.

## 📊 Tabla de Estudiantes

Los estudiantes registrados se visualizan en una tabla con los siguientes campos:

- **Código**: Número único asignado al estudiante.
- **Nombre**: Nombre completo del estudiante.
- **Correo**: Dirección de correo electrónico del estudiante.
- **Celular**: Número de teléfono del estudiante.
- **Acciones**: Opciones interactivas para gestionar al estudiante.

La tabla permite una visualización clara, paginación y acciones inmediatas para cada registro.

## ⚙️ Acciones en la Tabla

Cada estudiante registrado dispone de tres íconos en la columna de **Acciones**, los cuales permiten gestionar de manera individual su información:

- 👁️ **Ver perfil**: Muestra todos los datos del estudiante en una vista detallada.
- 📝 **Editar**: Permite modificar los datos del estudiante en un formulario prellenado.
- 🗑️ **Eliminar**: Borra al estudiante del sistema previa confirmación por parte del usuario.

---

## 👤 Vista de Perfil del Estudiante

Al hacer clic en el ícono 👁️, se muestra una tarjeta detallada con la información del estudiante, incluyendo:

- 📷 Foto de perfil
- 👤 **Nombre completo**
- 📧 **Correo electrónico**
- 🆔 **Código**
- 📱 **Teléfono** 
- 📅 **Botón**: `AGENDAR UNA REUNIÓN`


---

## 💻 Interfaz de Usuario

La interfaz del módulo está orientada a la facilidad de uso y claridad visual. Los elementos más destacados son:

- 🔵 Un botón azul en la parte superior derecha (`+ AGREGAR ESTUDIANTE`) para acceder al formulario de registro.
- 📋 La tabla central muestra los datos de los estudiantes en formato estructurado, con columnas visibles y ordenadas.
- 🧭 Los íconos de acción están alineados a la derecha de cada fila. Al pasar el cursor sobre ellos, se despliegan tooltips que indican su función:
  - 👁️ **Ojo** para ver perfil.
  - 📝 **Lápiz** para editar.
  - 🗑️ **Basurero** para eliminar.

El diseño sigue la estética institucional de la UPB, asegurando consistencia con el resto del sistema.

---

📍 **URL del módulo**: [https://isc-system-web-qa.vercel.app/students](https://isc-system-web-qa.vercel.app/students)

# 🧾 Documentación del Módulo Estudiante

## 🧠 Introducción

Este documento describe detalladamente el funcionamiento del **Módulo Estudiante** dentro del sistema de gestión académica de ISC. Aquí se explica paso a paso cómo se realiza el proceso de creación, visualización, edición y eliminación de estudiantes. También se abordan validaciones importantes y la experiencia de usuario dentro del sistema. Todo el contenido sigue el estándar de documentación utilizado en el repositorio `isc-docs`.

---

## 🎓 Creación de Estudiante

### 🚪 Acceso al módulo

Para comenzar, es necesario iniciar sesión en el sistema. Una vez dentro, desde la pantalla principal, se puede acceder al módulo de gestión de estudiantes haciendo clic en la opción correspondiente del menú.

![Pantalla principal](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/pantalla-inicial.png)
*Figura 1: Página principal tras el inicio de sesión, con acceso al módulo estudiante.*

---

### ➕ Formulario de creación

Al hacer clic en el botón **“Agregar Estudiante”**, se despliega un formulario que solicita los siguientes datos:

- **Nombre**
- **Apellido**
- **Código**
- **Correo electrónico**
- **Número de celular**
- **Horas becarias** (solo si el estudiante es becario)

![Formulario de registro](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/datos-estudiante.png)
*Figura 2: Formulario de creación de estudiante.*

Si se selecciona la opción **“¿Es Becario?”**, se mostrará un campo adicional para ingresar las horas becarias del estudiante.

![Horas Becarias](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/horas-becarias.png)
*Figura 3: Campo de horas becarias activado al marcar “¿Es Becario?”*

---

## 🧪 Validaciones y Excepciones

### 📛 Campos obligatorios

Si el usuario intenta guardar sin completar los campos requeridos, el sistema mostrará un mensaje de advertencia en cada campo faltante.

![Campos obligatorios](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/datos-erroneos-estudiante.png)
*Figura 4: Advertencia por campos vacíos.*

---

### ⚠️ Validación del número de celular

El campo **número de celular** requiere:

- Mínimo 8 caracteres numéricos
- No se permiten letras ni caracteres especiales

![Número inválido](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/numero-invalido.png)
*Figura 5: Validación fallida por número de celular no válido.*

---

### 🔁 Correo electrónico inválido

Si se introduce un correo con formato inválido, el sistema muestra un mensaje de error en rojo debajo del campo.

![Correo inválido](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/correo-invalido.png)
*Figura 6: Error por correo electrónico inválido.*

---

## 💾 Agregar Estudiante al Sistema

### ✅ Creación exitosa del estudiante

Una vez que se ingresan correctamente todos los datos y se presiona el botón de guardar:

1. Se validan los datos
2. Se guarda la información del estudiante
3. El sistema muestra un mensaje de éxito

    ![Creación exitosa](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/estudiante-creado.png)
    *Figura 7: Notificación de creación exitosa.*

4. Se actualiza automáticamente la **tabla de estudiantes**

### ❌ Error inesperado al crear un estudiante

En algunos casos, puede aparecer un mensaje genérico de error. Este mensaje no especifica la causa del fallo, y suele deberse a errores como:

- Datos inválidos no detectados por el frontend
- Fallas en la validación del backend

    ![Error al crear estudiante](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/estudiante-no-creado.png)
    *Figura 8: Notificación de error en la creación del estudiante.*

Cuando esto sucede, el usuario puede cerrar el mensaje y revisar los campos nuevamente o intentar enviar el formulario más tarde.

---

## 📋 Estructura de la Tabla de Estudiantes

La tabla donde se listan los estudiantes contiene las siguientes columnas:

- **Código**
- **Nombre**
- **Correo**
- **Celular**
- **Acciones**

![Tabla de estudiantes](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/encabezado-de-tabla-estudiante.png)
*Figura 9: Tabla con los estudiantes registrados.*

---

## 🛠️ Acciones Disponibles

Cada estudiante en la tabla tiene asignados íconos que permiten realizar diferentes operaciones:

- ✏️ **Editar**: Permite modificar los datos del estudiante. Al hacer clic, se abre el mismo formulario con los datos precargados.
- 👁️ **Ver perfil**: Abre una vista detallada con toda la información del estudiante.
- 🗑️ **Eliminar**: Elimina al estudiante de la base de datos, previa confirmación del usuario.

![Acciones](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/acciones-estudiante.png)
*Figura 10: Iconos para editar, ver y eliminar estudiante.*

---

## 🖥️ Interfaz de Usuario

La interfaz de usuario permite gestionar estudiantes de manera rápida e intuitiva. Sus principales elementos son:

- **Botón Agregar Estudiante**: Inicia el flujo de creación.
- **Formulario Modal**: Aparece al agregar o editar un estudiante, con validaciones claras.
- **Tabla Dinámica**: Se actualiza automáticamente al realizar cualquier acción.
- **Íconos de Acción**:
  - ✏️ Editar
  - 👁️ Ver perfil
  - 🗑️ Eliminar

![Interfaz completa](https://raw.githubusercontent.com/PaulLandaeta/isc-docs/fix/writer/%23333-Student-Creation/Documentacion-de-Pagina/Creacion-de-Estudiante/interfaz-estudiante.png)
*Figura 11: Vista general del módulo estudiante.*

---

## 🧩 Conclusión

El módulo estudiante facilita la gestión de alumnos dentro del sistema ISC de forma eficiente y clara. Las validaciones ayudan a mantener la calidad de los datos, y la interfaz proporciona una experiencia de usuario fluida. Esta documentación busca dejar constancia precisa del flujo de creación y manejo de estudiantes, cumpliendo con las buenas prácticas establecidas.

---

## 🔗 Referencias

- Página del sistema web: [isc-system-web-qa.vercel.app](https://isc-system-web-qa.vercel.app/) *(acceso restringido a usuarios autenticados)*

---

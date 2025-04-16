# 🤝 Cómo Contribuir al Proyecto (Fork y Pull Request)

Este tutorial te guiará paso a paso para colaborar correctamente con el repositorio haciendo un **fork**, trabajando en una **rama** y enviando un **Pull Request** (PR).

---

## ✅ Requisitos previos

- Tener una cuenta en [GitHub](https://github.com)
- Tener `git` instalado en tu computadora
- Conocimientos básicos de terminal

---

## 🚀 Paso 1: Hacer un Fork del Repositorio

1. Ve al repositorio principal del proyecto.  
   👉 Por ejemplo: `https://github.com/nombre-del-repo`

2. Haz clic en el botón **"Fork"** en la esquina superior derecha.

3. GitHub creará una copia del repositorio en **tu cuenta personal**.

---

## 💻 Paso 2: Clona tu Fork

```bash
git clone https://github.com/TU_USUARIO/nombre-del-repo.git
cd nombre-del-repo
```

> 🔁 Reemplaza `TU_USUARIO` con tu nombre de usuario de GitHub.

---

## 🌱 Paso 3: Crea una nueva rama para trabajar

> No trabajes directamente en la rama `main`.

```bash
git checkout -b nombre-de-tu-rama
```

Ejemplo:

```bash
git checkout -b fix/login-bug
```

---

## ✍️ Paso 4: Realiza tus cambios y haz commit

Haz los cambios necesarios en el código o en la documentación, luego:

```bash
git add .
git commit -m "Fix: corrige bug en formulario de login"
```

---

## 🔄 Paso 5: Sube tus cambios a tu Fork

```bash
git push origin nombre-de-tu-rama
```

---

## 📬 Paso 6: Crea el Pull Request

1. Ve a tu repositorio en GitHub.
2. Haz clic en **"Compare & pull request"**.
3. Asegúrate de que:
   - Estás enviando desde tu rama `nombre-de-tu-rama`.
   - Hacia la rama `main` o `develop` del repositorio original.
4. Escribe una **descripción clara** del cambio que hiciste.
5. Haz clic en **"Create Pull Request"**.

---

## 🔁 Paso 7: Espera la revisión

El equipo revisará tu PR y puede solicitar cambios.  
Si es necesario, haz más commits y push en la misma rama: se actualizará automáticamente el PR.

---

## 🧼 Limpieza (Opcional)

Después de que tu PR sea aceptado, puedes limpiar tu rama local:

```bash
git checkout main
git pull origin main
git branch -d nombre-de-tu-rama
```

---

## 💡 Consejos útiles

- Nombra tus ramas claramente: `feature/registro`, `fix/404-error`, `docs/manual-usuarios`, etc.
- No incluyas muchos cambios no relacionados en un mismo PR.
- Lee los lineamientos de contribución antes de empezar.

---

¡Gracias por contribuir a los proyectos de ISC! 🎉

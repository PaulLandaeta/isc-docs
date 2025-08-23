
# Manual de Proceso de un Pull Request (PR)

Este documento tiene como objetivo describir el proceso paso a paso para contribuir a un repositorio remoto en GitHub mediante la creación de una Pull Request (PR). Se detallan las acciones desde la creación de una rama hasta la fusión (merge) de los cambios al repositorio principal, siguiendo buenas prácticas de colaboración y control de versiones.

## REPOSITORIO BASE

- **Repositorio original:** `isc-docs`
- **Participantes:**  
  - Todos deben realizar un **fork** del repositorio.  
  - Ejemplo de contribuyente: Sebastian `(docs(#235): Documentation-of-the-PR-process`  
- **Formato PR:**  
  - Título: `docs(#Numero): descripción (Formal)`  

---

## 🧭 Pasos del Proceso

### 1. Crear Fork del Repositorio

#### 🔧 Desde la Interfaz Web

1. Ve al repositorio original en GitHub (`isc-docs`).
2. Haz clic en el botón `Fork` ubicado en la parte superior derecha de la página.

![fork1](https://raw.githubusercontent.com/S3bas77/isc-docs/feat/writer/#235-Documentation-of-the-PR-process//gitWorkflow-PRs/Flujo_de_PR/images/fork1.png)

3. Selecciona tu cuenta personal para crear una copia del repositorio en tu espacio.

![fork2](/gitWorkflow-PRs/Flujo_de_PR/images/fork2.png)

#### 💻 Desde la Terminal

```bash
git clone https://github.com/PaulLandaeta/isc-docs.git
cd isc-docs
git remote add upstream https://github.com/PaulLandaeta/isc-docs.git
```

- `git clone`: clona tu *fork* (no el original) en tu máquina local.
- `cd isc-docs`: navega al directorio del proyecto.
- `git remote add upstream`: añade una referencia al repositorio original para poder sincronizar tu fork con los últimos cambios del autor principal.

Actualizar tu fork con la última versión del repositorio base:

```bash
git fetch upstream
git merge upstream/main
```

Esto asegura que estás trabajando sobre la versión más reciente y evita conflictos más adelante.

---

### 2. Crear una Rama Nueva

```bash
git checkout -b feat/writer/#235-Documentation-of-the-Pr-process
```

- Este comando **crea una nueva rama** (con un nombre descriptivo) y cambia automáticamente a ella.
- Las ramas permiten trabajar en funcionalidades específicas sin afectar el código de la rama principal (`main` o `develop`).

📘 **Convención de nombre:**  
`feat/writer/#235-Documentation-of-the-Pr-process`, `fix/navbar`, etc.  
Ver más en [Convenciones de Commits](/gitWorkflow-PRs/ConvecionCommits/Convenciones_de_Commits.md).

---

### 3. Agregar el Contenido

- Abre el proyecto en tu editor de código (como VS Code).
- Realiza las modificaciones necesarias: pueden ser correcciones, nuevas funciones o documentación.
- Guarda los cambios frecuentemente y asegúrate de que el código funcione correctamente si estás trabajando con funcionalidades.

🧪 Si es código funcional, **haz pruebas locales** para validar que no rompes nada.

---

### 4. Realizar un Commit
```bash
git add .
git commit -m "(docs(#235): Documentation-of-the-PR-process)"
```

- `git add .`: agrega todos los archivos modificados al área de preparación.
- `git commit -m`: guarda esos cambios en tu historial local de Git con un mensaje estructurado.

![commit1](/gitWorkflow-PRs/Flujo_de_PR/images/commit1.png)

✍️ El mensaje debe ser claro y cumplir el formato acordado para facilitar la revisión:

- Tipo (`docs`, `feat`, `fix`)
- Número de issue (si aplica): `#235`
- Descripción breve y sin punto final

---

### 5. Enviar los Cambios
```bash
git push origin feat/writer/#235-Documentation-of-the-Pr-process
```
- Este comando sube tu rama con los cambios al repositorio remoto en GitHub.
- `git push`: sube los commits a GitHub.
- `origin`: el repositorio remoto (tu fork).
- `feat/writer/#235-Documentation-of-the-Pr-process`: la rama que has creado.

![push1](/gitWorkflow-PRs/Flujo_de_PR/images/push1.png)

Se utiliza este comando para aislar una nueva funcionalidad y mantener el código organizado.

---

### 6. Crear el Pull Request (PR)
1. Ve a tu repositorio en GitHub.
2. Ir a tu fork en GitHub y hacer click en "Compare & Pull Request".

![pr1](/gitWorkflow-PRs/Flujo_de_PR/images/PR.png)


3. Verifica que:
   - La rama base sea `main` o `develop` (según el flujo de trabajo).
   - La rama de comparación sea tu rama (`feat/...`).

✍️ Escribe un **título claro** y una **descripción detallada**:


📝 **Ejemplo de Título:**  
`(docs(#235): Documentation-of-the-PR-process)`

📝 **Descripción del PR:**  
- ¿Qué se hizo?  
- ¿Por qué se hizo?  
- ¿Cómo probarlo?


![pr2](/gitWorkflow-PRs/Flujo_de_PR/images/pr2.png)

---
### 7. Revisión y Merge del PR

Espera la revisión por parte de otros colaboradores. Ellos pueden:
  - Dejar comentarios
  - Solicitar cambios
  - Aprobar el PR


🔀 Una vez aprobado:

1. Haz clic en `Merge Pull Request` para fusionar los cambios en `main` o `develop`.
2. Asegúrate de que no haya conflictos antes de hacerlo.

Desde la terminal (opcional):

```bash
git checkout develop
git pull origin develop
git merge nombre-de-la-rama
git push origin develop
```

### 8. Limpieza de Ramas

Una vez que tu PR ha sido fusionado, es buena práctica **eliminar la rama** para mantener el repositorio ordenado.

```bash
git branch -d nombre-de-la-rama             # elimina la rama local
git push origin --delete nombre-de-la-rama  # elimina la rama en GitHub
```

---
## ✅ Buenas Prácticas (Resumen)

📌 Según el documento [Pull Requests (PR)](/gitWorkflow-PRs/PullRequest/Pull_Requests_(PR).md):

- Mantener ramas pequeñas y específicas.
- Incluir capturas si afecta la interfaz.
- Referenciar issues relacionados.
- Usar nombres de rama descriptivos.
- Probar el código localmente antes del PR.

---

## 📚 Gitflow y Organización

📘 Según el documento [Gitflow](/gitWorkflow-PRs/GitFlow/Gitflow_Flujo_de_trabajo_con_ramas.md):

- Usar ramas `feature/`, `release/`, `hotfix/` según corresponda.
- Fusionar `feature` → `develop` y luego a `main` si es estable.
- Eliminar ramas luego del merge.

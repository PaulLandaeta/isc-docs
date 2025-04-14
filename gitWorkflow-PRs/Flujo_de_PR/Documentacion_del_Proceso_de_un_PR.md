
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

- Ir al repositorio original.
- Click en `Fork` en la esquina superior derecha.

![fork1](/gitWorkflow-PRs/Flujo_de_PR/images/fork1.png)

- Elegir tu cuenta para crear el fork.

![fork2](/gitWorkflow-PRs/Flujo_de_PR/images/fork2.png)

#### 💻 Desde la Terminal

```bash
git clone https://github.com/PaulLandaeta/isc-docs.git
cd isc-docs
git remote add upstream https://github.com/PaulLandaeta/isc-docs.git
```

- `git clone`: clona el repositorio original a tu máquina local.
- `cd isc-docs`: accede al directorio del repositorio clonado.
- `git remote add upstream`: agrega una referencia al repositorio original (de Paul) para poder sincronizarlo en el futuro.

```bash
git fetch upstream
git merge upstream/main
```

Estas líneas te permitirán mantener actualizado tu fork con los últimos cambios del repositorio principal.

---

### 2. Crear una Rama Nueva

```bash
git checkout -b feat/writer/#235-Documentation-of-the-Pr-process
```

- `git checkout -b` crea una nueva rama llamada `feat/writer/#235-Documentation-of-the-Pr-process` y te cambia automáticamente a esa rama.
- Se utiliza para desarrollar una nueva funcionalidad de forma aislada.

📘 **Convención de nombre:**  
`feat/writer/#235-Documentation-of-the-Pr-process`, `fix/navbar`, etc.  
Ver más en [Convenciones de Commits](/gitWorkflow-PRs/ConvecionCommits/Convenciones_de_Commits.md).

---

### 3. Agregar el Contenido

- Realiza los cambios necesarios en los archivos correspondientes.
- Asegúrate de probar el funcionamiento antes de hacer commit.

---

### 4. Realizar un Commit
```bash
git add .
git commit -m "(docs(#235): Documentation-of-the-PR-process)"
```

- `git add .`: agrega todos los archivos modificados al área de preparación.
- `git commit -m`: registra los cambios con un mensaje estructurado.

![commit1](/gitWorkflow-PRs/Flujo_de_PR/images/commit1.png)

📌 El mensaje debe seguir esta convención:

- Tipo: `docs`, `feat`, `fix`, etc.
- Número de tarea: `(#235)`
- Descripción clara y sin punto final


---

### 5. Enviar los Cambios
```bash
git push origin feat/writer/#235-Documentation-of-the-Pr-process
```

- `git push`: sube los commits a GitHub.
- `origin`: el repositorio remoto (tu fork).
- `feat/writer/#235-Documentation-of-the-Pr-process`: la rama que has creado.

![push](/gitWorkflow-PRs/Flujo_de_PR/images/push1.png)

Se utiliza este comando para aislar una nueva funcionalidad (en este caso, el login del usuario) y mantener el código organizado.

---

### 6. Crear el Pull Request (PR)

- Ir a tu fork en GitHub y hacer click en "Compare & Pull Request".

![pr1](/gitWorkflow-PRs/Flujo_de_PR/images/PR.png)


- Asegúrate de que la rama base sea `main` o `develop`, y la comparada tu rama `feat/`.
- Escribe un título y descripción clara.


📝 **Ejemplo de Título:**  
`(docs(#235): Documentation-of-the-PR-process)`

📝 **Descripción del PR:**  
- ¿Qué se hizo?  
- ¿Por qué se hizo?  
- ¿Cómo probarlo?


![pr2](/gitWorkflow-PRs/Flujo_de_PR/images/pr2.png)

---
### 7. Revisión y Merge del PR

- **✅ Revisión final**

Verifica que todos los cambios estén correctamente revisados y aprobados por al menos un revisor.

- **🔀 Realizar el merge**

Desde la interfaz de GitHub para integrar los cambios en la rama principal (develop o main según el flujo).

```bash
git checkout develop
git pull origin develop
git merge nombre-de-la-rama
git push origin develop
```

- **🧹 Limpieza**

Una vez realizado el merge, elimina la rama si ya no se necesita para mantener el repositorio limpio.

**Eliminar la rama localmente:**
```bash
git branch -d nombre-de-la-rama
```
**Eliminar la rama en el repositorio remoto (GitHub):**
```bash
git push origin --delete nombre-de-la-rama
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
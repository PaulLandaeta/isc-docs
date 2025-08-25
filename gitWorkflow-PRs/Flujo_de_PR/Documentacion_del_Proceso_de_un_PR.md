
# Manual de Proceso: Pull Request en VS Code

## REPOSITORIO BASE

- **Repositorio original:** `isc-docs`
- **Participantes:**  
  - Todos deben realizar un **fork** del repositorio.  
  - Ejemplo de contribuyente: Sebastian `(docs(#233): Evaluation leads Juniors`  
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
-  🔍 Clona el repositorio original (con la dirección del isc-Docs) a tu máquina local.

```bash
git clone https://github.com/PaulLandaeta/isc-docs.git
```
Esto crea una copia exacta del repositorio para que puedas trabajar en él de forma independiente.
- 📂 Accede al directorio del proyecto clonado.
```bash
cd isc-docs
```
Después de clonar, este comando 
te mueve dentro de la carpeta isc-docs donde están todos los archivos 
del repositorio.
- 🔄 Agrega una referencia al repositorio original (de Paul) con el nombre upstream.
```bash
git remote add upstream https://github.com/PaulLandaeta/isc-docs.git
```
Esto es útil para más adelante poder sincronizar tu fork con los cambios del repositorio original, por ejemplo, con:
```bash
git fetch upstream
git merge upstream/main
```


---

### 2. Crear una Rama Nueva
Después de haber realizado tus cambios localmente, debes subirlos a tu repositorio remoto (tu fork en GitHub) para poder abrir un Pull Request.

#### 💻 Desde la Terminal

```bash
git checkout -b feat/login
```
`git checkout -b` crea una nueva rama llamada feat/login y te cambia automáticamente a esa rama.

Se utiliza para aislar una nueva funcionalidad (en este caso, el login del usuario) y mantener el código organizado.

Tip: Siempre trabaja en una rama diferente a main o develop para mantener una buena práctica de flujo de trabajo.

📘 **Convención de nombre:**  
`feat/login`, `fix/navbar`, etc.  
Ver más en el documento de [Convenciones de Commits](/gitWorkflow-PRs/ConvecionCommits/Convenciones_de_Commits.md).

---

### 3. Agregar el Contenido

- Realiza los cambios necesarios en los archivos correspondientes.

---

### 4. Realizar un Commit
Entra a la terminal.

Usar el formato adecuado para los commits:
- Agregar todos los cambios al área de preparación (staging).
```bash
git add .
```
Añade todos los archivos modificados (el . indica "todos los archivos en el directorio actual") al área de preparación, lo cual significa que están listos para ser "commiteados".
- Crear un commit con un mensaje descriptivo
```bash
git commit -m "docs(#233): Evaluation leads Juniors"
```
Registra los cambios añadidos con `git add` como un commit.

El mensaje `docs(#233): Evaluation leads Juniors"` sigue la convención:

- `docs`: tipo de commit (en este caso, cambios documentales)

- `(#233)`: referencia al número de tarea en GitHub

- `Evaluation leads Juniors`: descripción corta, clara y sin punto final


Ver más en [Convenciones de Commits](/gitWorkflow-PRs/ConvecionCommits/Convenciones_de_Commits.md).



---

### 5. Enviar los Cambios
Después de haber realizado tus cambios localmente, debes subirlos a tu repositorio remoto (tu fork en GitHub) para poder abrir un Pull Request.

```bash
git push origin feat/login
```

---

### 6. Crear el Pull Request (PR)

- Ir al repositorio fork en GitHub.
- Verás una opción para abrir un Pull Request.

📸 *[Agregar aquí imagen de commit en VS Code o terminal]*

- Asegúrate de que la rama base sea `main` o `develop` y la comparada sea tu rama `feat/`.

📝 **Formato del PR:**  
**Título:** `docs(#Numero): descripción (Formal)`  
**Descripción:** Qué se hizo, por qué, y cómo probarlo.

📸 *[Agregar imagen creando un PR]*

---

## ✅ Buenas Prácticas (Resumen)

📌 Según el documento [Pull Requests (PR)](/gitWorkflow-PRs/PullRequest/Pull_Requests_(PR).md):

- Mantener ramas pequeñas y específicas
- Incluir capturas si afecta la interfaz
- Referenciar issues relacionados
- Usar nombres de rama descriptivos
- Probar el código localmente antes del PR

---

## 📚 Gitflow y Organización

📘 Según el documento [Gitflow](/gitWorkflow-PRs/GitFlow/Gitflow_Flujo_de_trabajo_con_ramas.md):

- Usar ramas `feature/`, `release/`, `hotfix/` según corresponda
- Fusionar `feature` → `develop` y luego a `main` si es estable
- Eliminar ramas luego del merge

📸 *[Agregar diagrama visual del flujo de Gitflow]*
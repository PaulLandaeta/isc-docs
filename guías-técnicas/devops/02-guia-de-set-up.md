# 📖 Guía de Setup CI/CD

## 📘 Introducción a CI/CD

CI/CD (Integración Continua y Despliegue Continuo) es una metodología que automatiza las fases de desarrollo de software, desde la integración de código hasta su despliegue en producción. Esta práctica surge como una respuesta a los problemas que enfrentan los equipos de desarrollo al integrar cambios frecuentes en el código base y garantizar que estos cambios no introduzcan errores.

---

## 📚 Conceptos clave

### 🔄 ¿Qué es CI (Integración Continua)?

La Integración Continua (CI) es el proceso de automatizar la incorporación de cambios de código en un repositorio central. Cada vez que un desarrollador sube nuevas modificaciones, estas se validan mediante una serie de pruebas automatizadas. Este enfoque permite detectar errores de manera temprana, ya que los cambios se integran con mayor frecuencia en lugar de esperar a que varias funcionalidades estén completas.

En un entorno con CI, el código es construido, probado y validado de forma automatizada, lo que mejora la calidad del software y asegura que cada modificación no rompa funcionalidades existentes. Además, se fomenta un flujo de trabajo más ágil donde los desarrolladores pueden colaborar con mayor eficiencia y confianza.

### 🚀 ¿Qué es CD (Despliegue Continuo)?

El Despliegue Continuo (CD) extiende la Integración Continua al automatizar el proceso de entrega y, en algunos casos, el despliegue a entornos de producción. Una vez que el código ha pasado por las pruebas automatizadas, puede ser liberado de forma rápida y confiable. Esto reduce significativamente el tiempo que tarda una nueva característica o corrección en estar disponible para los usuarios.

En la práctica, el CD asegura que el software siempre esté en un estado que se pueda desplegar. Dependiendo de la estrategia adoptada, este proceso puede implicar Entrega Continua, donde el código está listo para desplegarse manualmente, o Despliegue Automático, donde los cambios se publican directamente en producción.

### ✅ Beneficios de CI/CD

Los beneficios de implementar CI/CD son numerosos.

- Permite detectar errores de forma temprana gracias a la ejecución automática de pruebas en cada cambio de código.

- Se mejora la calidad del software y se reduce el tiempo que los desarrolladores gastan buscando y corrigiendo fallos.

- Se minimizan los errores humanos al automatizar el proceso de `linting`, lo que resulta en lanzamientos más rápidos y fiables.

- Se fomenta la colaboración entre los equipos y se estandariza la forma en la que se entrega el software, facilitando la escalabilidad y el mantenimiento a largo plazo.

### 🔧 ¿Qué es un Pipeline y por qué es importante?

Un pipeline en el contexto de CI/CD es una secuencia automatizada de pasos que transforma el código fuente en un producto final listo para ser desplegado. Cada pipeline está compuesto por múltiples etapas (stages) como la compilación, ejecución de pruebas, validaciones de calidad y finalmente el despliegue.

El propósito principal de un pipeline es automatizar estos procesos para garantizar que cada cambio en el código pase por las mismas verificaciones antes de llegar a producción. Esto ayuda a mantener la calidad del software, reducir errores humanos y acelerar el tiempo de entrega.

La importancia de definir un pipeline radica en varios factores:

- Automatización y verificación consistente.

- Detección temprana de errores.

- Entrega rápida y con menos errores.

- Definir un flujo de trabajo para el equipo de desarrollo.

---

## 📋  Requisitos previos

Antes de empezar, asegúrate de tener lo siguiente:

- Una cuenta en **GitHub** o un servidor con **Jenkins** instalado.
- Un repositorio con tu código fuente.
- Conocimiento básico de **Git**.

## ⚙️ Configuración de CI/CD

### 🐈 Configuración de CI/CD con GitHub Actions

Para comenzar con la configuración se tiene que crear el workflow:

1. Ve a tu repositorio en **GitHub**.
2. Haz clic en la pestaña **Actions**.
3. Selecciona **New workflow** > **Set up a workflow yourself**.
4. Crea un archivo en **`.github/workflows/ci.yml`**.

Posterior a dicha creación, se tiene que definir las etapas del pipeline. Un workflow está dividido en jobs (trabajos) que pueden contener steps (pasos).

#### Ejemplo de configuración

```yaml
name: Node.js CI/CD

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout del código
        uses: actions/checkout@v3

      - name: Instalar dependencias
        run: npm install

      - name: Ejecutar pruebas
        run: npm test

      - name: Desplegar
        if: github.ref == 'refs/heads/main'
        run: ./deploy.sh
```

Guarda el archivo y haz un **commit**.

### 🤵🏻 Configuración de CI/CD con Jenkins

Para comenzar con la configuración, primero se debe instalar Jenkins

1. Descarga Jenkins desde [jenkins.io](https://www.jenkins.io/download/).
2. Sigue las instrucciones de instalación para tu sistema operativo.
3. Accede a la interfaz web en `http://localhost:8080`.

Una vez realizada la instalación, se continúa con la creación de un pipeline:

1. En Jenkins, selecciona **New Item**.
2. Elige **Pipeline** y asigna un nombre.
3. Configura el **Pipeline script**.

#### Ejemplo de configuración (groovy)

Pipeline básico en **Jenkinsfile**:

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh './deploy.sh'
            }
        }
    }
}
```

## ⚙️ Configuración de Staging

Staging es un entorno de preproducción donde se prueban los cambios antes de implementarlos en producción. Este entorno simula las condiciones reales del sistema, permitiendo validar nuevas características y detectar posibles errores sin afectar a los usuarios finales.

Para evitar confusiones, las diferencias clave entre los entornos de Staging y Producción son:

- **Aislamiento de cambios**: En staging, los desarrolladores pueden validar nuevas funciones sin comprometer el entorno de producción.

- **Pruebas exhaustivas**: Se realizan pruebas de rendimiento, integración y seguridad antes de pasar a producción.

- **Simulación de entorno real**: Aunque es similar a producción, staging puede utilizar bases de datos o credenciales simuladas para evitar exponer información sensible.

- **Reducción de riesgos**: Permite detectar errores antes de que lleguen a los usuarios finales, garantizando mayor estabilidad en producción.

### 🐈 Configuración de Staging con GitHub Actions

Para crear un pipeline de Staging con GitHub Actions, se define un nuevo workflow en el directorio .github/workflows/. Este workflow se activará en ramas específicas o al crear pull requests.

#### Ejemplo de configuración de Staging

```groovy
name: Staging CI/CD

on:
  push:
    branches: [staging]

jobs:
  staging:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout del código
        uses: actions/checkout@v3

      - name: Instalar dependencias
        run: npm install

      - name: Ejecutar pruebas
        run: npm test

      - name: Desplegar en Staging
        env:
          STAGING_URL: ${{ secrets.STAGING_URL }}
        run: ./deploy-staging.sh
```

En este ejemplo:

- El pipeline se activa cuando hay un push en la rama staging.

- Se instala el entorno, se ejecutan pruebas y, si todo es correcto, se despliega en el entorno de staging.

- Las credenciales se gestionan con secrets para mayor seguridad.

### 🤵🏻 Configuración de Staging con Jenkins

Para implementar un pipeline de Staging en Jenkins, se crea un Jenkinsfile que define las etapas específicas.

#### Ejemplo de configuración de Staging (groovy)

```groovy
pipeline {
    agent any

    environment {
        STAGING_URL = credentials('staging-url')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'staging'
            }
            steps {
                sh './deploy-staging.sh'
            }
        }
    }
}
```

En este ejemplo:

- Se utiliza la variable de entorno STAGING_URL con las credenciales almacenadas en Jenkins.

- El despliegue solo se ejecuta si la rama es staging.

- Cada etapa (checkout, build, test, deploy) está claramente definida para asegurar un flujo automatizado y repetible.

## ⚙️ Configuración de Producción

Documentar la configuración del pipeline para el entorno de producción es fundamental para asegurar que los despliegues sean seguros, consistentes y automatizados. Esta guía explica cómo crear un pipeline optimizado para producción usando GitHub Actions y Jenkins, junto con las mejores prácticas para minimizar errores.

---

### 🐈 Configuración de Producción con GitHub Actions

1. **Ejecutar el pipeline** solo en ramas de producción (por ejemplo: `main` o `release`).  
2. **Validar el código** con pruebas automatizadas (unitarias, integración, seguridad).  
3. **Desplegar** en el entorno de producción.  
4. **Notificar** el resultado del despliegue.

#### Ejemplo de pipeline de Producción (YAML)

```yaml
name: Production CI/CD

on:
  push:
    branches:
      - main

jobs:
  production:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout del código
        uses: actions/checkout@v3

      - name: Configurar Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 20

      - name: Instalar dependencias
        run: npm install --production

      - name: Ejecutar pruebas
        run: npm test

      - name: Desplegar en Producción
        if: success()
        env:
          PROD_URL: ${{ secrets.PROD_URL }}
          API_KEY: ${{ secrets.API_KEY }}
        run: ./deploy-prod.sh

      - name: Notificar éxito
        if: success()
        run: echo "🚀 Despliegue en producción completado exitosamente."

      - name: Notificar fallo
        if: failure()
        run: echo "❌ El despliegue en producción ha fallado."
```

---

### 🤵🏻 Configuración de Producción con Jenkins

#### Ejemplo de pipeline de Producción (Jenkinsfile)

```groovy
pipeline {
    agent any

    environment {
        PROD_URL = credentials('prod-url')
        API_KEY = credentials('api-key')
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'npm install --production'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                sh './deploy-prod.sh'
            }
        }
    }

    post {
        success {
            echo 'Despliegue exitoso en producción.'
        }
        failure {
            echo 'Error en el despliegue en producción.'
        }
    }
}
```

---

### 🐞 Errores comunes y soluciones en el pipeline de producción

| **Error**                               | **Causa probable**                           | **Solución**                                   |
|-----------------------------------------|----------------------------------------------|-----------------------------------------------|
| ❌ Fallo en la autenticación API        | Secrets mal configurados                     | Verificar las variables de entorno (`secrets`).|
| 📦 Dependencias no instaladas           | Falta `npm install --production`             | Asegúrate de instalar solo las necesarias.    |
| 🔒 Problemas de permisos                | Falta de acceso al entorno de producción     | Revisar permisos del `deploy` y del servidor. |
| ⏳ Timeout en el despliegue              | Script de despliegue ineficiente o colgado   | Optimizar `deploy.sh` y validar conexiones.   |
| 🧬 Pruebas fallidas antes del despliegue | Código roto o dependencias incompatibles     | Ejecutar pruebas localmente antes de hacer push.|

---

### 📉 Mejores prácticas para producción

- **Seguridad primero**: Usa **secrets** para manejar credenciales sensibles.  
- **Validar antes de desplegar**: Ejecuta pruebas exhaustivas (unitarias, integración, e2e).  
- **Reversión automatizada (rollback)**: Prepara scripts para revertir despliegues fallidos.  
- **Notificaciones**: Envía alertas a Slack, Discord o correo electrónico en caso de errores.  
- **Versionado**: Usa etiquetas (`git tag`) para identificar versiones desplegadas.  

## 🔗 Recursos adicionales

- [Documentación oficial de GitHub Actions](https://docs.github.com/en/actions)
- [Guía de inicio de Jenkins](https://www.jenkins.io/doc/)
- [Pipeline Syntax](https://www.jenkins.io/doc/book/pipeline/syntax/)

# 🚀 Guía Completa de Despliegue en Staging y Producción

## 📌 Introducción

Esta guía proporciona una descripción detallada del proceso de despliegue en los entornos de staging y producción. Está diseñada para asegurar que las implementaciones sean consistentes, reproducibles y estén libres de errores.

## 📊 Flujo de Despliegue desde CI/CD hasta Producción

1. **Commit y Push:** El desarrollador realiza cambios en el código y los envía al repositorio (GitHub, GitLab, Bitbucket, etc.).

2. **Integración Continua (CI):**
   - Se ejecutan pruebas automatizadas (unitarias, de integración, E2E).
   - Validación de calidad de código (linting, formateo).

3. **Despliegue en Staging:**
   - Si las pruebas pasan, el código se despliega en el entorno de staging.
   - Se realizan pruebas manuales y automáticas adicionales para validar la integridad del sistema.

4. **Despliegue en Producción:**
   - Una vez aprobado el staging, el código se despliega al entorno de producción.
   - Se ejecutan verificaciones finales (smoke tests, health checks).

## 🛠️ Configuración de Servidores para Staging y Producción

### 1. Especificaciones del Servidor

| Entorno     | Nombre del Servidor        | IP               | 
|-------------|----------------------------|------------------|
| **Staging** | staging.myapp.com          | 192.168.1.10     | 
| **Producción** | production.myapp.com       | 192.168.1.20    

### 2. Variables de Entorno

Asegúrate de definir las variables sensibles en cada entorno:

#### Archivo `.env` para Staging

```
ENVIRONMENT=staging
DB_HOST=staging-db.myapp.com
DB_USER=staging_user
DB_PASSWORD=securepassword
API_KEY=staging-api-key
```

#### Archivo `.env` para Producción

```
ENVIRONMENT=production
DB_HOST=prod-db.myapp.com
DB_USER=prod_user
DB_PASSWORD=securepassword
API_KEY=prod-api-key
```

## 🔄 Configuración de Jenkins o GitHub Actions

Este despliegue está configurado para aplicaciones desarrolladas en Node.js con Express en el backend y React con Vite en el frontend.

### Ejemplo de Pipeline con GitHub Actions (YAML)

Dentro de un archivo similar a `github/workflows/ci-cd.yml` se tiene que ingresar el siguiente código:

```yaml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout código
        uses: actions/checkout@v2

      - name: Configurar Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '20'

      - name: Instalar dependencias
        run: npm install

      - name: Ejecutar pruebas
        run: npm test

      - name: Desplegar en Staging
        if: github.ref == 'refs/heads/main'
        run: |
          ssh user@staging.myapp.com 'bash /deploy.sh'
```
#### 💡 Explicación:

- Activa el pipeline cuando haya un push en `main`.

- Configura Node.js y ejecuta pruebas.

- Si todo va bien, usa `ssh` para conectarse al servidor y ejecutar `/deploy.sh`.

### Ejemplo de Pipeline con Jenkins (Groovy)

Para Jenkins, se tiene que trabajar dentro de un Pipeline Script

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:usuario/repo.git'
            }
        }

        stage('Build & Test') {
            steps {
                sh 'npm install'
                sh 'npm test'
            }
        }

        stage('Deploy to Staging') {
            when {
                branch 'main'
            }
            steps {
                sh 'ssh user@staging.myapp.com "bash /deploy.sh"'
            }
        }
    }
}
```

#### 💡 Explicación:

- Descarga el código (`git`).

- Instala dependencias (`npm install`).

- Ejecuta pruebas (`npm test`).

- Si está en `main`, despliega a staging con `ssh`.

## 📜 Comandos para Iniciar y Verificar el Despliegue

### 1. Despliegue Manual (Terminal)

```bash
ssh user@staging.myapp.com
cd /var/www/myapp
./deploy.sh
```

### 2. Validar el Estado del Servicio

```bash
systemctl status myapp
journalctl -u myapp -f
```

## 🔍 Ejemplos de Logs de Despliegue

### Despliegue Exitoso

```
[INFO] Starting deployment...
[INFO] Pulling latest changes...
[INFO] Running migrations...
[INFO] Restarting service...
[INFO] Deployment successful!
```

### Error en el Despliegue

```
[ERROR] Migration failed: Cannot connect to database.
[ERROR] Deployment aborted!
```

## 🛠️ Manejo de Errores y Rollback

### 1. Identificar el Error

- Revisar los logs con:

```bash
journalctl -u myapp -f
```

### 2. Realizar un Rollback

Si un despliegue falla, vuelve a una versión estable anterior:

```bash
ssh user@staging.myapp.com
cd /var/www/myapp
./rollback.sh
```

### 3. Validar el Rollback

```bash
systemctl status myapp
```

## 📊 Monitoreo Post-Despliegue

Después del despliegue, es importante monitorear el rendimiento y errores:

### 1. Monitoreo de Logs

```bash
tail -f /var/log/myapp.log
```

### 2. Monitoreo de Recursos

```bash
top
df -h
free -m
```

### 3. Herramientas de Monitoreo Recomendadas

- Prometheus + Grafana: Para monitoreo de métricas.

- New Relic / Datadog: Para análisis de rendimiento.

- Sentry: Para monitoreo de errores en aplicaciones web.

Con estas estrategias, se puede asegurar un despliegue seguro y eficiente.

## 📌 Conclusión

Implementar un proceso de despliegue eficiente y seguro es fundamental para garantizar la estabilidad y escalabilidad de una aplicación. A lo largo de esta guía, se ha cubierto cada aspecto clave del despliegue, empezando desde la configuración de los entornos de staging y producción hasta el monitoreo. Para lograr una integración y entrega continua efectiva, es crucial:

- Mantener pipelines de CI/CD bien configurados con GitHub Actions o Jenkins.  
- Asegurar que los servidores estén correctamente configurados y optimizados.  
- Implementar mecanismos de rollback para responder rápidamente a errores en producción.  
- Monitorear activamente la aplicación con herramientas como Prometheus, Grafana o Sentry.  
- Seguir buenas prácticas de despliegue para minimizar el impacto en los usuarios finales.  

El uso de automatización y monitoreo no solo reduce el riesgo de errores humanos, sino que también mejora la eficiencia del equipo de desarrollo y operaciones. Con esta guía, se puede obtener una base sólida para implementar y mejorar continuamente un proceso de despliegue. 
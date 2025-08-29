## Configuración y Cómo Levantar el Proyecto

## 🛠️ Flujo de Desarrollo Recomendado

### 1️ Levantar primero el microfrontend
```bash
cd login-microfrontend
npm install
npm run dev

```

### 2️⃣ Luego levantar la aplicación principal:

``` bash
cd ../mi-microfrontend
npm install
npm start
```
## ⚠️ Notas
- Ambos proyectos usan React 19.1.0 y React Router DOM 7.6.2 para evitar conflictos.

- Si quieres que los cambios en login-microfrontend se reflejen automáticamente en mi-microfrontend, debes mantener ambos servidores corriendo al mismo tiempo.

- Asegúrate de que los puertos no estén ocupados.
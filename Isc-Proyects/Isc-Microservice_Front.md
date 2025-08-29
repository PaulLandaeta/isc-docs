# 📌 Introducción
Este repositorio contiene un sistema de autenticación basado en microfrontends.  
El objetivo principal es mantener el **login desacoplado** de la aplicación principal, permitiendo escalabilidad y modularidad.

---

## 🗂️ Estructura Principal
La arquitectura se divide en dos partes principales:  
- **login-microfrontend** → Microfrontend independiente para autenticación.  
- **App Principal** → Aplicación que consume o integra el microfrontend.  

---

### 📁 login-microfrontend/
Microfrontend independiente para el sistema de autenticación, construido con **Vite + React + TypeScript**.

#### 📂 public/
Contiene los archivos estáticos servidos directamente por el navegador.  
- `fondito.png` → Imagen de fondo  
- `Logo_UPB.jpg` → Logo de la universidad  
- `upblogo.jpeg` → Logo alternativo UPB  
- `vite.svg` → Logo de Vite  

#### 📂 src/
Código fuente del microfrontend.

##### 📁 assets/
Recursos estáticos para uso en la UI.  
- `fotito.png` → Imagen adicional  
- `react.svg` → Logo de React  

##### 📁 components/
Componentes React reutilizables para el login.  
- `Login.tsx` → Componente principal de login  
- `LoginForm.tsx` → Formulario de autenticación  
- `ModelSelector.tsx` → Selector de modelo/auth  
- `SocialLogin.tsx` → Login con redes sociales  

##### 📁 pages/auth/
Páginas relacionadas con autenticación.  
- `ForgotPasswordPage.tsx` → Recuperación de contraseña  
- `ResetPasswordPage.tsx` → Reset de contraseña  

---

### 📁 App Principal (Raíz)
Aplicación que integra o consume el microfrontend de login.

#### 📂 public/
Archivos accesibles públicamente.  
- `favico.ico` → Favicon  
- `index.html` → HTML principal  
- `logo192.png` → Logo de 192px  
- `manifest.json` → Configuración PWA  
- `robots.txt` → Instrucciones para bots  

#### 📂 src/
Código fuente principal de la app.  

##### 📁 assets/
Imágenes y logos usados en la aplicación.  
- `fondito.png`  
- `fotito.jpg/png`  
- `UPB.png`  

##### 📁 components/
Componentes de login social.  
- `SocialLoginCentralizado.tsx`  
- `SocialLoginDerecha.tsx`  
- `SocialLoginIzquierda.tsx`  

##### 📁 styles/
Módulos CSS para estilos modulares.  
- `layoutStyle.module.css` → Estilos de layout  
- `login.module.css` → Estilos de login  

---

## ⚙️ Configuración y Utilidades
Aquí se encuentran los archivos de configuración que permiten compilar, linting y empaquetado.  

- `.gitignore` → Archivos excluidos de Git  
- `eslint.config.js` → Configuración de ESLint  
- `index.html` → Documento HTML raíz  
- `package.json` → Dependencias y scripts  
- `tsconfig.*.json` → Configuración de TypeScript  
- `vite.config.ts` → Configuración de Vite  

---

## 🛠️ Tecnologías Utilizadas
Se emplean diferentes tecnologías para cada módulo.  

**login-microfrontend**  
- React + TypeScript  
- Vite como bundler  
- ESLint para linting  
- CSS Modules  

**App Principal**  
- React (JavaScript)  
- Webpack (inferido por estructura)  
- Jest para testing  

---

## 🔄 Relación entre Módulos
El **login-microfrontend** puede integrarse en la aplicación principal de varias maneras:  
- Importado como paquete  
- Servido como aplicación independiente  
- Usado mediante **Module Federation**  

---

## 📦 Dependencias
Dependencias inferidas según la estructura.  

**Microfrontend:**  
- React, TypeScript, Vite, ESLint  

**App Principal:**  
- React, Webpack, Jest, Testing Libraries  

---



# 🔧Configuración y Cómo Levantar el Proyecto

## Flujo de Desarrollo Recomendado

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



   
# 📂 Estructura del Proyecto Frontend

```bash
└── 📁 fronted
    └── 📁 login-microfrontend
        └── 📁 public 
            └── fondito.png
            └── Logo_UPB.jpg
            └── upblogo.jpeg
            └── vite.svg
        └── 📁 src
            └── 📁 assets
                └── fotito.png
                └── react.svg
            └── 📁 components
                └── Login.tsx
                └── LoginForm.tsx
                └── ModelSelector.tsx
                └── SocialLogin.tsx
            └── 📁 pages
                └── 📁 auth
                    └── ForgotPasswordPage.tsx
                    └── ResetPasswordPage.tsx
            └── App.css
            └── App.tsx
            └── index.css
            └── main.tsx
            └── vite-env.d.ts
        └── .gitignore 
        └── estlint.config.js
        └── index.html
        └── package-lock.json
        └── package.json
        └── tsconfig.app.json
        └── tsconfig.json 
        └── tsconfig.node.json
        └── vite.config.ts
    └── 📁 public
        └── favico.ico
        └── index.html
        └── logo192.png
        └── logo192.png
        └── manifest.json
        └── robots.txt
    └── 📁 src
        └── 📁 assets
            └── fondito.png
            └── fotito.jpg
            └── fotito.png
            └── UPB.png
        └── 📁 components
            └── SocialLoginCentralizado.tsx
            └── SocialLoginDerecha.tsx
            └── SocialLoginIzquierda.tsx
        └── 📁 styles
            └── layoutStyle.module.css
            └── login.module.css
        └── App.jsx
        └── App.test.js
        └── index.js
        └── logo.svg
        └── resportWebVitals.js
        └── setupTest.js
    ├── .gitignore
    ├── App.jsx
    ├── package-lock.json
    ├── package.json
    ├── README.json
    ├── yarn.lock
```
## 🚀 Primeros Pasos  
1. Clonar el repositorio o hacer fork :  `git clone https://github.com/PaulLandaeta/auth-microservice/tree/main`  
2. Entrar en la carpeta de frontend: `cd .\frontend\`  
3. Instalar dependencias: `npm install`  
3. Instalar dependencias: `yarn install`  
4. Ejecutar en desarrollo: `npm run start`



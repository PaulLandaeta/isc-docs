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



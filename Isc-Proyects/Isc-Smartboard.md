## 1. Introducción y Alcance de las Pruebas

### 1.1 Objetivo de la Documentación
Este documento tiene como finalidad detallar la configuración y preparación necesarias para la ejecución de pruebas automatizadas en el proyecto SmartBoard sobre dispositivos Android. El objetivo principal es estandarizar el entorno de trabajo y definir los pasos básicos para que cualquier miembro del equipo pueda:
- Instalar y configurar correctamente las herramientas de automatización.
- Levantar el entorno de pruebas con Appium y un emulador Android.
- Entender la arquitectura de pruebas utilizada.

<img width="417" height="166" alt="Imagen 1" src="https://github.com/user-attachments/assets/1577f2cb-0046-4d60-8994-11cc46d59ad9" />

### 1.2 Tecnologías Utilizadas
- **Android Studio**: IDE principal del proyecto, utilizado para la gestión del código y de los emuladores Android.
- **Java (SDK 11 o superior)**: Lenguaje base del desarrollo y de las pruebas.
- **Gradle**: Sistema de construcción y gestión de dependencias del proyecto.
- **Appium 2.x**: Framework de automatización móvil.
- **Appium Inspector**: Herramienta para inspección de elementos y configuración de Desired Capabilities.
- **Page Object Model (POM)**: Patrón de diseño adoptado en la estructura de las pruebas.

<img width="1036" height="730" alt="Imagen 2" src="https://github.com/user-attachments/assets/a53e85fd-21f0-4720-8a1c-f0c9945759f4" />

### 1.3 Patrón de Diseño (Page Object Model - POM)
El patrón Page Object Model (POM) se implementa para separar la lógica de prueba de la lógica de la interfaz de usuario:
- Cada pantalla de la aplicación cuenta con una clase que representa sus elementos y acciones.
- Los casos de prueba llaman a estas clases para ejecutar escenarios de manera reutilizable.
- Esto mejora la mantenibilidad y facilita la adaptación a cambios en la UI.

<img width="569" height="746" alt="Imagen 3" src="https://github.com/user-attachments/assets/d6f7da01-0818-43f2-bc63-dda3fccaa95f" />

## 2. Preparación y Configuración del Entorno

### 2.1 Requisitos del Sistema
- **Sistema Operativo**: Windows 10/11 (64 bits).
- **Java JDK 11 o superior** (configurado en variables de entorno).
- **Android Studio** con:
  - SDK de Android instalado.
  - AVD Manager con al menos un emulador configurado (ejemplo: Pixel 4 API 30).
- **Node.js 16 o superior** (para instalar Appium).
- **Git** (para clonar el repositorio).

<img width="1036" height="730" alt="Imagen 4" src="https://github.com/user-attachments/assets/19b36d79-e141-41f3-8848-254571c4cfab" />

### 2.2 Configuración del Entorno

#### Instalar Node.js
- Descargar desde nodejs.org e instalar.

#### Instalar Appium y Appium Doctor
Ejecutar en terminal:
```bash
npm install -g appium
npm install -g appium-doctor
appium-doctor --android
```

#### Instalar Driver de Appium para Android
```bash
appium driver install uiautomator2
appium driver list   # Para verificar
```

#### Instalar Appium Inspector
- Descargar desde: Appium Inspector Releases
- Se utiliza para definir y probar Desired Capabilities y explorar elementos de la app en el emulador.

#### Configurar Android Studio
- Abrir Android Studio e instalar el SDK de Android (versión 11 o superior).
- Crear un emulador desde AVD Manager (ejemplo: Pixel 4 API 30).
- Probar la conexión con:
  ```bash
  adb devices
  ```

<img width="414" height="112" alt="Imagen 5" src="https://github.com/user-attachments/assets/bc405edc-c674-47f2-a933-5c71df08876d" />
<img width="630" height="213" alt="Imagen 6" src="https://github.com/user-attachments/assets/cb4ab6a3-8f42-498a-a175-d3871e9580a0" />

#### Variables de entorno
Configurar en el sistema:
- `JAVA_HOME` → ruta al JDK
- `ANDROID_HOME` → ruta al SDK de Android

Agregar al PATH:
- `%ANDROID_HOME%\platform-tools`
- `%ANDROID_HOME%\tools`

#### Verificar Instalación
- Levantar Appium Server:
  ```bash
  appium
  ```
- Iniciar emulador Android desde Android Studio.
- Validar que el dispositivo está disponible:
  ```bash
  adb devices
  ```

### 2.3 Clonación del Proyecto
- Hacer fork del repositorio base: [PaulLandaeta/SmartBoard](https://github.com/PaulLandaeta/SmartBoard)
- Clonar tu fork en la máquina local.
- Abrir el proyecto en Android Studio.
- Sincronizar dependencias con Gradle.

## 3. Ejecución de los Casos de Prueba

### 3.1 Configuración Previa 

#### Creación del Emulador
1. En Android Studio, abrir AVD Manager y seleccionar "Create a new virtual device".
2. Elegir el modelo Pixel 9 Pro XL.
3. Finalizar la configuración.
4. Para equipos con recursos limitados, se recomienda usar un dispositivo Android físico.

#### Generación del APK
1. Abrir el virtual device.
2. Desde la barra superior de Android Studio seleccionar Build > Generate APKs.
3. Esperar a que finalice el proceso.
4. Una vez generado el APK, arrastrarlo al emulador creado para instalarlo.
5. Abrir el APK instalado y dejarlo abierto en el virtual device.

### 3.2 Inicio del Servidor de Appium
1. Descargar Appium Inspector desde: (https://github.com/appium/appium-inspector/releases)
2. Instalar Appium:
   ```bash
   npm install -g appium
   ```
3. Instalar UIAutomator2:
   ```bash
   appium driver install uiautomator2
   ```
4. Inspección de la aplicación:
   - Conectarse al emulador con: `adb -s emulator-5554 shell` (El 5554 puede variar de acuerdo al dispositivo conectado)
   - Obtener información de la ventana activa: `dumpsys window windows | grep -E 'imeLayeringTarget'`

### 3.3 Ejecución desde la Consola
1. Iniciar Appium:
   ```bash
   appium
   ```
2. Verificar dispositivos conectados:
   ```bash
   adb devices
   ```

### 3.4 Ejecución desde el IDE

#### Configuración de Appium Inspector
1. Abrir Appium Inspector y completar los campos con la información obtenida:
   ```json
   {
     "deviceName": "Pixel 9 Pro XL",
     "platformVersion": "16", 
     "appPackage": "edu.upb.lp.genericgame",
     "appActivity": "edu.upb.lp.core.activities.AndroidGameActivity",
     "platformName": "Android", 
     "automationName": "uiautomator2"
   }
   ```
2. Guardar la información.
3. Hacer click en "StartSession" para comenzar a inspeccionar la interfaz de la aplicación
4. Para que se actualice la pantalla necesitara primero cambiar de pantalla en el emulador.
luego actualizar el appiumInspector para poder obtener información del nuevo interfaz.


## 4. Mantenimiento de las Pruebas

### 4.1 Solución de Problemas Comunes

#### Problemas con Gradle
1. Cambio en gradle.properties (Project Properties):
   ```properties
   org.gradle.jvmargs = -Xmx2048M -Dkotlin.daemon.jvm.options\="-Xmx2048M" --add-exports=java.base/sun.nio.ch=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --add-opens=java.base/java.lang.reflect=ALL-UNNAMED --add-opens=java.base/java.io=ALL-UNNAMED --add-exports=jdk.unsupported/sun.misc=ALL-UNNAMED
   android.useAndroidX = true
   android.enableJetifier = false
   ```
   Cambiar `android.enableJetifier` a `false`

2. Configuración en build.gradle (Module :app):
   ```groovy
   compileSdkVersion 34
   namespace 'edu.upb.lp.genericgame'
   
   defaultConfig {
       applicationId "edu.upb.lp.genericgame"
       minSdkVersion 21
       targetSdkVersion 34
       versionCode 1
       versionName "1.0"
       testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
   ```

3. Verificar en local.properties que la dirección del SDK es correcta

#### Estructura de Archivos Esenciales
1. Clase Session.java:
   ```java
    package test.session;
    import io.appium.java_client.android.AndroidDriver;
    import org.openqa.selenium.remote.DesiredCapabilities;
    import io.appium.java_client.AppiumDriver;
    import test.factoryDevices.FactoryDevices;

    import java.net.MalformedURLException;
    import java.net.URL;
    public class Session {
        private static Session session = null;
        private AppiumDriver device;
        private Session() {
            DesiredCapabilities caps = new DesiredCapabilities();
            caps.setCapability("platformName", "Android");
            caps.setCapability("appium:deviceName", "Practica Interna");
            caps.setCapability("appium:platformVersion", "9");
            caps.setCapability("appium:automationName", "uiautomator2");
            caps.setCapability("appium:appPackage", "edu.upb.lp.genericgame");
            caps.setCapability("appium:appActivity", "edu.upb.lp.core.activities.AndroidGameActivity");
            try {
                device = new AppiumDriver(new URL("http://127.0.0.1:4723/"), caps);
            } catch (MalformedURLException e) {
                throw new RuntimeException(e);
            }
        }

        public static Session getInstance() {
            if (session == null) {
                session = new Session();
            }
            return session;
        }

        public void closeApp(){
            device.quit();
            session = null;
        }

        public static void resetInstance() {
            if (session != null) {
                session.device.quit();
                session = null;
            }
        }
        public AppiumDriver getDevice(){
            return  device;
        }
        public void setUp() {}
    }
   ```

2. Clase AppiumControl:
   ```java
   package test.controls;
   
   import org.openqa.selenium.By;
   import org.openqa.selenium.WebElement;
   import test.session.Session;
   
   public class AppiumControl {
       protected By locator;
       protected WebElement control;
   
       public AppiumControl(By locator){
           this.locator = locator;
       }
   
       protected void findControl(){
           control = Session.getInstance().getDevice().findElement(locator);
       }
   
       public void click(){
           findControl();
           control.click();
       }
   
       public String getText(){
           findControl();
           return control.getText();
       }
   
       public boolean isControlDisplayed(){
           try {
               findControl();
               return control.isDisplayed();
           } catch (Exception e){
               return false;
           }
       }
   }
   ```

3. Configuración del Android Driver:
   ```java
   package test.factoryDevices;
   
   import io.appium.java_client.AppiumDriver;
   import io.appium.java_client.android.AndroidDriver;
   import org.openqa.selenium.remote.DesiredCapabilities;
   
   import java.net.MalformedURLException;
   import java.net.URL;
   import java.time.Duration;
   
   public class Android implements IDevice{
   
       @Override
       public AppiumDriver create() {
           DesiredCapabilities capabilities = new DesiredCapabilities();
           capabilities.setCapability("appium:deviceName","Pixel 9 Pro XL");
           capabilities.setCapability("appium:platformVersion","16");
           capabilities.setCapability("appium:appPackage","edu.upb.lp.genericgame");
           capabilities.setCapability("appium:appActivity","edu.upb.lp.core.activities.AndroidGameActivity");
           capabilities.setCapability("platformName","Android");
           capabilities.setCapability("appium:automationName","uiautomator2");
           
           AppiumDriver driver = null;
           try {
               driver = new AndroidDriver(new URL("http://127.0.0.1:4723/"),capabilities);
           } catch (MalformedURLException e) {
               throw new RuntimeException(e);
           }
           driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(30));
           return driver;
       }
   }
   ```
   En la parte de capabilities, colocar las mismas variables que se introdujeron dentro de Appium para levantar el servidor.

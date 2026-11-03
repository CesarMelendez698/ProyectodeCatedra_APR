# FinanzasUDB 🎓💰

**FinanzasUDB** es una aplicación móvil diseñada específicamente para estudiantes de la **Universidad Don Bosco (UDB)**, que integra en una sola plataforma la **gestión financiera universitaria** (control de presupuestos, ingresos, egresos y cuentas) y la **planificación académica** (horario semanal de clases, registro de materias y calendario interactivo de actividades y entregas).

---

## 🚀 Características Principales

### 1. 💳 Gestión de Cuentas y Finanzas
- **Cuentas Base del Sistema:** Viene configurado con *Efectivo*, *Tarjeta* y *Cuenta Bancaria*.
- **Cuentas Dinámicas:** Permite crear cuentas personalizadas con saldos iniciales y colores distintivos.
- **Eliminación Segura:** Permite eliminar cuentas sin romper los saldos históricos ni corromper las transacciones asociadas.
- **Transacciones de Ingresos y Gastos:** Registro detallado con monto, fecha, categoría universitaria/personal, cuenta origen/destino y notas.
- **Dashboard Estadístico:** Gráficas interactivas de distribución de gastos, balance total y resumen de flujo mensual.

### 2. 📅 Horario, Materias y Calendario Académico
El módulo académico está estructurado en 3 secciones independientes:
- **Horario Semanal:** Visualización de clases organizadas por día de la semana (Lunes a Sábado) con hora de inicio, hora de finalización, aula y docente.
- **Materias:** Directorio de materias inscritas en el ciclo.
- **Calendario Interactivo:** Vista mensual para programar eventos en fechas específicas (exámenes, entregas de proyectos, laboratorios, talleres).
- **Tipos de Actividad Personalizables:** Posibilidad de registrar nuevos tipos de actividad con nombres y colores personalizados, además de eliminar los que ya no se necesiten.

### 3. 👤 Perfil Universitario
- **Selector de Campus UDB:** Permite elegir entre:
  - *Campus Antiguo Cuscatlán*
  - *Campus Soyapango*
  - *UDB Virtual*
- Registro de Carrera Universitaria, Ciclo académico actual y datos personales.
- Sincronización en la nube con Firestore y almacenamiento en caché local con AsyncStorage.

### 4. 🔐 Seguridad y Autenticación
- Autenticación con **Firebase Auth** (correo y contraseña).
- Validación de formularios, persistencia de sesión ("Recordar usuario") y opción de recuperación de contraseña.
- Base de datos en la nube con **Cloud Firestore** para sincronización multiplataforma.

---

## 🛠️ Tecnologías y Dependencias

- **Framework Principal:** [React Native](https://reactnative.dev/) (v0.88.1) con [Expo](https://expo.dev/) (SDK ~58.0.22)
- **Lenguaje:** JavaScript (ES6+ / Node.js)
- **Navegación:** [@react-navigation/native](https://reactnavigation.org/) v7 con Stack Navigator y Bottom Tabs
- **Backend & Nube:** [Firebase](https://firebase.google.com/) v13 (Authentication & Cloud Firestore)
- **Almacenamiento Local:** `@react-native-async-storage/async-storage`
- **Componentes Visuales:** `@expo/vector-icons`, `react-native-chart-kit`, `react-native-svg`
- **Selectores de Fecha/Hora:** `@react-native-community/datetimepicker`
- **Compilación en la Nube:** [EAS Build (Expo Application Services)](https://docs.expo.dev/build/introduction/)

---

## 📋 Requisitos Previos

Antes de ejecutar o compilar el proyecto, asegúrate de tener instalado:

1. **Node.js** (versión 18 o superior recomendada): [nodejs.org](https://nodejs.org/)
2. **npm** (incluido con Node.js) o **yarn**
3. **Dispositivo de prueba o Emulador:**
   - Para probar rápidamente en tu teléfono: Descarga la app **Expo Go** desde [Google Play Store](https://play.google.com/store/apps/details?id=host.exp.exponent) o [Apple App Store](https://apps.apple.com/app/expo-go/id982107779).
   - Opcional: Emulador de Android Studio o Simulador de Xcode.

---

## 💻 Ejecución Local con Expo

Sigue estos sencillos pasos para correr la aplicación en modo desarrollo:

### 1. Clonar o abrir el proyecto
Abre una terminal en la carpeta raíz del proyecto:
```bash
cd ProyectodeCatedra_APR
```

### 2. Instalar dependencias
Instala todas las librerías necesarias del proyecto:
```bash
npm install
```

### 3. Iniciar el servidor de Expo
Ejecuta el siguiente comando para iniciar el servidor de desarrollo:
```bash
npx expo start
```
> **Tip:** Si deseas limpiar la caché antes de iniciar, puedes correr:
> ```bash
> npx expo start -c
> ```

### 4. Abrir la aplicación
- **En tu teléfono físico (Recomendado):**
  1. Conecta tu teléfono a la **misma red Wi-Fi** que tu computadora.
  2. Abre la app **Expo Go** en Android o la cámara en iOS.
  3. Escanea el código QR que aparece en la terminal o en la ventana del navegador.
- **En emulador de Android:** Presiona la tecla `a` en la terminal.
- **En simulador de iOS (macOS):** Presiona la tecla `i` en la terminal.
- **En navegador web:** Presiona la tecla `w` en la terminal.

---

## 📦 Generación e Instalación del APK para Android

El proyecto ya cuenta con la configuración de **EAS (Expo Application Services)** lista en el archivo `eas.json` para generar directamente archivos instalables `.apk` de Android (sin necesidad de generar bundles `.aab` de la tienda).

### 1. Descargar APK ya compilado
Puedes descargar e instalar directamente la última versión compilada con el nombre **FinanzasUDB** y el logo oficial desde el siguiente enlace de EAS:

👉 **[Descargar APK de FinanzasUDB en Expo.dev](https://expo.dev/accounts/melendez/projects/FinanzasUDB/builds/97b3cbb3-ce65-47e8-97e1-d41d09603348)**

### 2. Generar un nuevo APK por tu cuenta con EAS

Si realizas cambios en el código y deseas compilar un nuevo APK:

1. **Iniciar sesión en Expo CLI:**
   ```bash
   npx eas-cli login
   ```
2. **Lanzar la compilación en la nube para Android:**
   ```bash
   npx eas-cli build --platform android --profile preview
   ```
3. El proceso de compilación se ejecutará en los servidores de Expo en la nube. Al finalizar, la terminal te proporcionará un enlace directo de descarga y un código QR para bajar el APK directamente a tu teléfono Android.

### 3. Cómo instalar el APK en tu dispositivo Android
1. Abre el enlace de descarga o transfiere el archivo `.apk` a tu teléfono.
2. Al pulsar sobre el archivo descargado, si el sistema te lo solicita, permite la opción **"Instalar aplicaciones de fuentes desconocidas"** para tu navegador o gestor de archivos.
3. Si Google Play Protect muestra una advertencia preventiva, pulsa en **"Más detalles"** y selecciona **"Instalar de todas formas"**.
4. ¡Abre **FinanzasUDB** y comienza a usar la app!

---

## 📂 Estructura del Proyecto

```text
ProyectodeCatedra_APR/
├── assets/                  # Íconos de la app (icon.png, android-icon-foreground.png, favicon)
├── LOGO/                    # Logotipo fuente de FinanzasUDB
├── src/
│   ├── components/          # Componentes reutilizables (botones, modales, tarjetas)
│   ├── context/             # Proveedores de estado global (FinanceContext.js)
│   ├── firebase/            # Configuración e inicialización de Firebase
│   ├── navigation/          # Enrutadores (AppNavigator.js, TabNavigator.js)
│   ├── screens/             # Pantallas de la aplicación
│   │   ├── LoginScreen.js         # Inicio de sesión
│   │   ├── RegisterScreen.js      # Registro de nuevos estudiantes
│   │   ├── ForgotPasswordScreen.js# Recuperación de contraseña
│   │   ├── DashboardScreen.js     # Panel principal y balances
│   │   ├── TransactionsScreen.js  # Gestión de transacciones y cuentas
│   │   ├── ScheduleScreen.js      # Horario semanal, materias y calendario
│   │   └── ProfileScreen.js       # Perfil del estudiante y selector de campus
│   └── utils/               # Utilidades, formateadores y constantes
├── app.json                 # Configuración de Expo (nombre, slug, íconos, paquete)
├── eas.json                 # Configuración de perfiles de compilación EAS (APK)
├── index.js                 # Punto de entrada de la aplicación
├── package.json             # Dependencias y scripts de npm
└── README.md                # Documentación oficial del proyecto
```

---

## 👥 Soporte y Contribución

Desarrollado para el proyecto de cátedra de la **Universidad Don Bosco (UDB)**. Para dudas técnicas o soporte, revisa la documentación oficial de [Expo Docs](https://docs.expo.dev/) o la consola de [Firebase](https://console.firebase.google.com/).


# 🏋️ RepsMaster

App Android hecha en **MIT App Inventor** que **cuenta repeticiones de ejercicios en el gym** usando sensores conectados a un **ESP32**. Los datos se sincronizan en tiempo real con **Firebase Realtime Database**.

## ✨ Funciones
- **Contador de repeticiones:** inicia una serie, define una meta y ve las repeticiones y el tiempo en vivo.
- **Selector de ejercicio:** peso muerto, press de banca, sentadilla, curl de bíceps.
- **Sensores en tiempo real:** estado del ESP32 y lecturas de:
  - **FSR** (sensor de fuerza/presión)
  - **MPU6050** (acelerómetro y giroscopio)
  - **Ultrasónico** (distancia)
  - **Flex sensor** (flexión)
- **Calibración** desde la app con sliders: ángulo mínimo, distancia mínima, sensibilidad del FSR y umbral del flex.
- **Estadísticas:** repeticiones totales, mejor ejercicio, ejercicio más frecuente y tiempo entrenando.

## 🔌 Arquitectura
```
Sensores → ESP32 → Firebase Realtime Database ⇄ App Android (App Inventor)
```
La app lee y escribe en Firebase por su API REST (componente `Web`), y guarda datos locales con `TinyDB`.

## 🚀 Cómo abrirlo
1. Entra a [ai2.appinventor.mit.edu](https://ai2.appinventor.mit.edu).
2. *Projects → Import project (.aia)* y elige `RepsMaster.aia`.
3. Crea tu propio proyecto en Firebase (Realtime Database) y reemplaza en los bloques:
   - `TU-PROYECTO` por el nombre de tu base de datos.
   - `TU_FIREBASE_SECRET` por tu llave.
   > ⚠️ Nunca subas tu llave real a un repositorio público.

## 📁 Estructura
- `RepsMaster.aia`: proyecto listo para importar.
- `src/`: pantallas (`.scm` = diseño, `.bky` = bloques): `Screen1`, `selector`, `contador`, `sensores_tiemporeal`, `estadisticas_hist`.
- `assets/`: fuentes e imágenes.

## 🛠️ Tecnologías
MIT App Inventor · ESP32 · Firebase Realtime Database · sensores FSR, MPU6050, ultrasónico y flex

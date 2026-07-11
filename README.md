# 🚀 ResQRadar: Sistema Avanzado de Búsqueda y Rescate (SAR)

![ResQRadar Banner](https://correangel.github.io/resqradar/img/banner_ai.png)

**ResQRadar** es una plataforma de software y hardware de grado profesional diseñada para **operaciones de protección civil, bomberos y paramédicos**. 

Utiliza la distorsión y el rebote de las ondas de radiofrecuencia (Wi-Fi CSI) para extraer micro-movimientos. Esto permite detectar **latidos cardíacos (BPM)** y **frecuencias respiratorias (RPM)** de víctimas atrapadas bajo escombros, tierra o concreto, sin necesidad de que la víctima lleve dispositivos electrónicos o sensores consigo.

🌐 **Sitio Web y Documentación Oficial:** [https://correangel.github.io/resqradar](https://correangel.github.io/resqradar)

---

## 🛠️ Características Principales

*   **📡 Radar Biométrica (CSI):** Extrae información del estado del canal Wi-Fi, filtrando frecuencias biológicas humanas (0.1 Hz a 0.7 Hz) mediante Transformada de Fourier (FFT) y Filtros Hampel.
*   **📍 Fusión de Sensores (Anti-Falsos Positivos):** Utiliza el acelerómetro, giroscopio y brújula del teléfono para cancelar el movimiento del propio rescatista, garantizando lecturas precisas.
*   **👥 Rastreador Espacial (MultiVictimTracker):** Capacidad de segmentar el espacio para detectar y aislar a múltiples víctimas simultáneamente en un barrido de 360°.
*   **🕸️ Modo Enjambre (Red Mesh P2P):** Conecta a decenas de rescatistas en el área de desastre sin necesidad de internet, usando *Nearby Connections* (Bluetooth LE y Wi-Fi Direct) para compartir telemetría y chat offline.
*   **🆘 Portal Cautivo Web:** Emite una red Wi-Fi de rescate (`ResQRadar-Emergency`). Cuando una víctima se conecta, se despliega automáticamente un sitio web alojado en el celular del rescatista para recibir alertas SOS y triangular su ubicación.
*   **📄 Reportes Tácticos (PDF & KML):** Genera mapas de calor geolocalizados y reportes médicos vitales listos para compartir con el personal de triaje o sistemas de inteligencia artificial GIS.
*   **🌑 Modo OLED Táctico:** Interfaz optimizada en negro puro (True Black) para ahorrar batería en campo, proteger la visión nocturna de los brigadistas y dar alertas visuales e intensas hápticas (sin ruido).

---

## 🏗️ Arquitectura del Sistema

*   **Frontend Mobile:** Desarrollado íntegramente en **Flutter**, asegurando alto rendimiento, animaciones a 60 FPS (como el Sweep Gradient del radar) e internacionalización nativa.
*   **Capa Base y DSP:** Procesamiento de Señales Digitales nativo (Kotlin / Dart) que gestiona el hardware del dispositivo (antena Wi-Fi en modo promiscuo/monitor).
*   **Base de Datos Local:** Uso extensivo de SQLite y Hive para almacenamiento persistente y encriptado offline de coordenadas y signos vitales.

---

## 💻 Instalación y Despliegue

Actualmente, ResQRadar se compila como una aplicación Android (`.apk`).
Para construir el proyecto localmente con Flutter:

```bash
flutter clean
flutter pub get
flutter build apk --release
```
El instalable se generará en `build/app/outputs/flutter-apk/app-release.apk`.

---

## ⚖️ Licencia y Propiedad Intelectual

*   La base de código original de detección Wi-Fi (CSI) que sirvió de inspiración fue desarrollada por **Carlos Mundaray (Solvitco)** bajo **Licencia MIT**.
*   **ResQRadar**, su interfaz gráfica, algoritmos de aislamiento de FFT, Modo Enjambre P2P y Portal Cautivo son propiedad intelectual de **Moovitya C.A. (2026)** y constituyen obras derivadas avanzadas de nivel profesional e industrial.

*Diseñado para salvar vidas. Operación 100% Offline.*

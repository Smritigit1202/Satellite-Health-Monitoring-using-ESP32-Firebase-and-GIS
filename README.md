

# 🌐 Satellite Health Monitoring using ESP32, Firebase, and GIS (Wokwi IoT Project)

project link - https://wokwi.com/projects/437739700820155393
---

## ✅ Aim

To design and simulate a satellite health monitoring system using an ESP32 microcontroller that:

* Detects onboard temperature and voltage,
* Logs real-time data to Firebase,
* Includes location (lat/lon) for GIS integration,
* Visualizes and analyzes satellite health status using geospatial tools.

---

## 🎯 Objectives

* Simulate satellite onboard environment with temperature and voltage sensors.
* Detect conditions like **overheating** or **low battery**.
* Log real-time telemetry to Firebase Realtime Database.
* Attach dynamic **geolocation coordinates** for each entry.
* Enable integration with **GIS platforms** (QGIS / Google Maps).
* Learn IoT + Cloud + GIS pipeline using Wokwi.

---

## 🧰 Materials Required

| Component             | Details                                 |
| --------------------- | --------------------------------------- |
| ESP32 Dev Board       | Simulated in [Wokwi](https://wokwi.com) |
| Temperature Sensor    | e.g., LM35 or analog simulation         |
| Power Supply          | Simulated voltage source                |
| Internet Connectivity | Via ESP32 WiFi                          |
| Firebase Project      | Real-time Database enabled              |
| GIS Tool (Optional)   | QGIS, Google Maps, Leaflet.js           |

---

## 💻 Software and Libraries Required

### 🛠 Platform

* [Wokwi IoT Simulator](https://wokwi.com)
* Firebase Console (Realtime DB)

### 📦 Libraries (`libraries.txt`)

```
adafruit/Adafruit GFX Library@1.11.5
adafruit/Adafruit SSD1306@2.5.9
```

### 🔌 ESP32 Built-in Headers

* `WiFi.h`
* `HTTPClient.h`
* `Wire.h`
* `Adafruit_GFX.h`
* `Adafruit_SSD1306.h`

---

## 📚 Theory

Satellites must monitor their internal environment (e.g., heat, battery status) to stay operational.
By using **IoT principles**, we simulate a satellite’s thermal and power telemetry. With **Firebase**, we store this data remotely.
By tagging each data point with **GPS coordinates**, the data becomes GIS-ready for spatial analysis.

---
## Circuit Diagram

<img width="898" height="431" alt="image" src="https://github.com/user-attachments/assets/ab2e85f3-1554-419b-a9e0-38211e0d5af5" />

---
## Working Video



https://github.com/user-attachments/assets/c991ca47-631a-4ade-a8dd-a6a4119c859f


---

## Plotted points from csv


<img width="959" height="485" alt="image" src="https://github.com/user-attachments/assets/bae6e576-71d4-4eb1-a7b6-252242462819" />


----
---
## ⚙️ Procedure

1. **Simulate Hardware:**

   * Use Wokwi to connect ESP32, temperature sensor, and OLED display.
2. **Code Setup:**

   * Use Arduino `.ino` file to read sensor data, simulate GPS, and send to Firebase.
3. **Firebase Integration:**

   * Set up Firebase Realtime Database and get API key & URL.
   * ESP32 sends JSON with temp, voltage, status, latitude, longitude.
4. **GIS Preparation:**

   * Export data from Firebase (CSV or programmatically).
   * Import into QGIS or Google Maps with location-based layers.
5. **Visualization:**

   * Use GIS tools to visualize data clusters, paths, or heat maps of unhealthy nodes.

---

## 📈 Expected Outcome

* Live streaming of telemetry data to Firebase.
* Each data point includes:

  * `temperature`, `voltage`, `status`
  * `latitude`, `longitude`
* OLED shows live health info.
* GIS-ready data can be plotted easily.

---

## 🎯 Results (Sample Firebase Entry)

```json
{
  "temperature": 42.3,
  "voltage": 3.4,
  "status": "Battery Low",
  "latitude": 28.6139,
  "longitude": 77.2090
}
```

* ✅ Firebase database updates in real-time.
* ✅ Entries can be visualized in QGIS for satellite tracking.

---

## ⚠️ Precautions

* Always check Firebase rules to avoid unauthorized access.
* Keep voltage and temperature thresholds realistic.
* When using actual GPS (not simulation), ensure GPS lock.
* Firebase quota limits apply if logging frequently.


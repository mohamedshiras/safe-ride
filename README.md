# Safe Ride 🚦🛡️

An IoT-based safety application developed with **Flutter** and integrated with an **ESP32** development board.

> **Goal:** Collect real-time data from an ESP32 (sensors / inputs) and show alerts + live status inside the mobile app.

---

## ✨ Features

- 📡 Real-time data sync between ESP32 ↔ mobile app
- 🔔 Safety alerts/notifications (configurable)
- 📍 Live status dashboard (speed/impact/location/etc. — based on your sensors)
- 🧾 Event history logs (optional)
- 🔐 Basic authentication (optional)

---

## 🧩 Tech Stack

- **Flutter / Dart**
- **ESP32**
- Firebase **Realtime Database** *(recommended)* or MQTT/HTTP *(optional)*

---

## 🏗️ High-Level Architecture

1. **ESP32** reads sensor values (e.g., impact, pressure, button press, GPS, etc.)
2. ESP32 sends data to a backend channel (Firebase RTDB / MQTT / REST API)
3. **Flutter app** listens to updates in real-time and renders:
   - current state
   - alerts
   - logs/history

---

## 📦 Project Structure
```txt
safe-ride/
 ├─ lib/            # Flutter app source
 ├─ assets/         # Images/icons
 ├─ pubspec.yaml
 └─ README.md
```

---

## 🚀 Getting Started (Flutter App)

### 1) Clone the repo
```bash
git clone https://github.com/mohamedshiras/safe-ride.git
cd safe-ride
```

### 2) Install dependencies
```bash
flutter pub get
```

### 3) Run the app
```bash
flutter run
```

---

## 🔥 Firebase Setup (Recommended)

If you're using Firebase Realtime Database:

1. Create a Firebase project
2. Enable Realtime Database
3. Add Android/iOS app in Firebase console
4. Download config files:
   - `android/app/google-services.json`
   - `ios/Runner/GoogleService-Info.plist`
5. Make sure your database rules are set correctly for testing (then lock it down later)

### Example RTDB data format
```json
{
  "device": {
    "status": "safe",
    "impact": 0,
    "latitude": 6.9271,
    "longitude": 79.8612,
    "updatedAt": 1700000000
  }
}
```

---

## 🧠 ESP32 Side (Overview)

You can send data using:

- Firebase RTDB library (ESP32)
- REST API requests
- MQTT broker

### Typical sensors you can connect

- IMU (impact detection)
- GPS module
- Pressure/FSR sensor
- Emergency push button

Add your ESP32 firmware code in a separate folder like `esp32/` if you want the full project in one repo.

---

## 🧪 Roadmap (Optional)

- [ ] Push notifications for emergency alerts
- [ ] User profile + emergency contacts
- [ ] Offline caching + sync
- [ ] Export logs (CSV/PDF)
- [ ] Admin dashboard (web)

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first to discuss what you'd like to change.

---

## 📝 License

This project is open-source and licensed under the **Apache License 2.0**.  
See the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

- **GitHub:** [https://github.com/mohamedshiras](https://github.com/mohamedshiras)
- **Portfolio:** [https://mohamedshiras.dev](https://mohamedshiras.dev)

---

*If you tell me **how SafeRide works exactly** (what sensors you're using + whether you use Firebase RTDB or MQTT), I'll tailor the README to match your real flow (and add correct setup steps).*

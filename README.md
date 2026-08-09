# DrinkSync

**Capstone project — Computer Engineering (group)**  
**Authors:** Kareem Kholaif ([@kholaif](https://github.com/kholaif)), [Karim Smires](https://github.com/ks1686), and collaborators

DrinkSync is an Android hydration tracker paired with a Bluetooth-connected load-cell scale. The phone app logs intake, goals, streaks, and achievements; a Python service on the scale reads the HX711 sensor and streams weight data over Bluetooth.

> This repository is Kareem’s public mirror of the team project originally hosted at [ks1686/DrinkSync](https://github.com/ks1686/DrinkSync).

## Architecture

- **Android (Kotlin):** Compose/Material UI, Bluetooth connectivity, local persistence, notifications, achievements/streaks
- **Python (scale side):** HX711 load-cell driver, scale sampling, Bluetooth data transfer helpers

```
DrinkSync/
├── Android/          # Kotlin Android application
└── Python/           # Scale firmware / Bluetooth helpers
    ├── hx711.py
    ├── scale.py
    ├── bt.py
    └── data_monitor.py
```

## My contributions (Kareem)

- Android UI with Bluetooth integration
- Persistent local intake data on the device
- Achievements system (including daily-goal and streak tracking)
- Midnight daily-intake reset
- Notification updates at intake milestone intervals (25% steps)

## Setup (high level)

### Android

1. Open the `Android/` folder in Android Studio
2. Let Gradle sync; use a device/emulator with Bluetooth as needed
3. Build and run the `app` configuration

### Python scale service

```bash
pip install -r requirements.txt   # if/when a requirements file is present for your board
python Python/scale.py
```

Hardware assumes an HX711-compatible load cell wired to the host running the Python scripts (e.g. Raspberry Pi).

## License

See [LICENSE](LICENSE).

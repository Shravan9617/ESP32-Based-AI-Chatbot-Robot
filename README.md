# ESP32-Based-AI-Chatbot-Robot

An ESP32-S3 based Wi-Fi voice assistant using Xiaozhi AI.

## Hardware

- ESP32-S3 development board
- INMP441 I2S microphone
- MAX98357A I2S amplifier
- 4–8 ohm speaker
- USB cable and jumper wires

## Features

- Wi-Fi voice interaction with Xiaozhi AI
- Digital microphone input through INMP441
- I2S speaker output through MAX98357A
- ESP32-S3 based design

## Wiring

## Pin connections

| Module    | Pin     | ESP32-S3 pin |
|    ---    |   ---   |     ---      |
| INMP441   | VDD     | 3.3 V        |
| INMP441   | GND     | GND          |
| INMP441   | WS      | GPIO 4       |
| INMP441   | SCK     | GPIO 5       |
| INMP441   | SD      | GPIO 6       |
| INMP441   | L/R     | GND          |
| MAX98357A | VIN     | 5 V or 3.3 V, according to the module |
| MAX98357A | GND     | GND          |
| MAX98357A | DIN     | GPIO 7       |
| MAX98357A | BCLK    | GPIO 15      |
| MAX98357A | LRC     | GPIO 16      |
| MAX98357A | SD / EN | 3.3 V        |
| MAX98357A | SPK+    | Speaker +    |
| MAX98357A | SPK-    | Speaker -    |


## Flashing prebuilt firmware

If using Xiaozhi prebuilt ESP32-S3 firmware, flash these files with Espressif
Flash Download Tool:

|          File         | Address  |
|          ---          |   ---    |
| bootloader.bin        | 0x0      |
| partition-table.bin   | 0x8000   |
| ota_data_initial.bin  | 0xD000   |
| xiaozhi.bin           | 0x20000  |
| generated_assets.bin  | 0x800000 |

Use firmware that matches the flash size, PSRAM, display, buttons, and GPIO
connections of the actual board.


###  🌐 Connecting to Xiaozhi AI

Once flashed successfully:

1. **Power On:** ESP32-S3.
2. **Wi-Fi Provisioning:**
   - The device will create an Access Point (AP) or request Wi-Fi configuration via Serial terminal (depending on your build).
   - Connect to the device's Wi-Fi hotspot and enter your home **Wi-Fi SSID & Password**.
3. **Xiaozhi AI Server Bind:**
   - Open your browser or the Xiaozhi App/Console.
   - Enter the Device ID / MAC address shown on your Serial Monitor (at 115200 baud).
   - Once connected, speak to the INMP441 microphone to start chatting with Xiaozhi AI!

---

### ⚠️ Important Notes & Troubleshooting

- **Power Supply:** Ensure a stable 5 V power source (at least 1A–2A) to avoid brownout resets when the speaker plays at high volume.
- **Audio Noise:** Keep I2S wiring as short as possible to prevent signal interference.
- **PSRAM & Flash:** Verify that your ESP32-S3 firmware build matches your board's PSRAM (N8R8 / N16R8, etc.) configuration.

## License

MIT. See LICENSE.


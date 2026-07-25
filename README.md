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


## Important notes

- Connect all GND pins together.
- The INMP441 must use 3.3 V, not 5 V.
- Do not connect MAX98357A SPK+ or SPK- to GND.
- Keep I2S wires short to reduce audio noise.
- Use a stable power supply. A 5 V supply is recommended for louder speaker
  output when the MAX98357A module supports it.
- Verify your prebuilt firmware uses these exact GPIO pins before flashing.

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

## License

MIT. See LICENSE.


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

See CIRCUIT_DIAGRAM.md.

## Flashing prebuilt firmware

If using Xiaozhi prebuilt ESP32-S3 firmware, flash these files with Espressif
Flash Download Tool:

| File | Address |
| --- | ---: |
| bootloader.bin | 0x0 |
| partition-table.bin | 0x8000 |
| ota_data_initial.bin | 0xD000 |
| xiaozhi.bin | 0x20000 |
| generated_assets.bin | 0x800000 |

Use firmware that matches the flash size, PSRAM, display, buttons, and GPIO
connections of the actual board.

## License

MIT. See LICENSE.


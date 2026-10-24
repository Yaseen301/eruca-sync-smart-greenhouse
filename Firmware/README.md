# Eruca Sync firmware

The source in [src/main.cpp](src/main.cpp) and [platformio.ini](platformio.ini) is imported unchanged from Nader Sayed's [Eruca-Sync repository](https://github.com/Nadoooor/Eruca-Sync/tree/49f52b0db70bf52fc38d7b9a41fe47a303049562). See the root [MIT license](../LICENSE) and [import notes](../IMPORT-NOTES.md).

## Build and upload

Open this `Firmware` folder as the PlatformIO project in VS Code. The configuration selects the Arduino framework and environment `esp32-s3-devkitc1-n16r8`.

From the repository root, with PlatformIO installed:

```sh
pio run -d Firmware
pio run -d Firmware -t upload
pio device monitor -d Firmware -b 115200
```

The configuration declares TFT_eSPI, Adafruit TouchScreen, BH1750, ESP32Servo, Adafruit NeoPixel, and the Adafruit AM2320 sensor library.

## Hardware configuration to review

The imported source assigns GPIO 17 to both `FAN2_pin` and `ServoR_pin`. Confirm the actual wiring and resolve that overlap before flashing a device. Check that the selected board definition and TFT_eSPI display setup match the ESP32-S3 board and screen; no custom board definition or explicit TFT_eSPI setup file is supplied in the imported project.

## Supplied binaries

The upstream prebuilt [firmware.bin](../Production/Ready_firmware/firmware.bin) and [firmware.elf](../Production/Ready_firmware/firmware.elf) are retained as supplied. Their build environment and correspondence to a new local build have not been verified. No hardware testing was performed during this import.

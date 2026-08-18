# ESP32-T4-S3-MicroPython-Template

Welcome to the lab using the ESP32-T4-S3 LilyGO!

This repository serves as a foundation for software engineering projects aimed at the ESP32 hardware.
This document will guide you through the setup process and help you prepare to work with your ESP32 hardware.

The supplied firmware already contains MicroPython and LVGL. You write Python;
you do not compile MicroPython, LVGL, or a GUI library.

---

# How to get started

The student workflow works on Windows, Linux, and macOS. The first PlatformIO
setup can take several minutes while tools are installed.

## PlatformIO

1. Install Visual Studio Code
   * Visit [Visual Studio Code's website](https://code.visualstudio.com/download) and download the latest version or use the package manager of your system.
   * Run `Visual Studio Code` and follow the steps.
2. Install the correct extension.
   * Head over to the extensions tab on your left.
   * Search for ["PlatformIO IDE"](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide) and install it.


## How to run the program

1. Open the locally cloned repository with Visual Studio Code
    * If the "Do you trust the authors of the files in this folder?" dialog appears, click on "Yes, I trust the authors"
2. Open up the file `project/project.ino`
3. Connect your ESP32 to your computer via a USB cable.
4. Build and upload the project to the device. See screenshot.

![[screenshot](./assets/screenshot.png)](./assets/screenshot.png)

---

# What to add where

Your code belongs in the `/project` folder. The only place you should add, change, or remove things from is the [**/project**](project/main.py) folder. Changing anything else might break the code and cause a lot of headaches for all involved parties.

## How to connect to Wi-Fi

The T4-S3 has built-in Wi-Fi, but it cannot connect to eduroam. Use another
network or a phone hotspot.

Copy `project/secrets_example.py` to `project/secrets.py`, then set the SSID
(network name) and password in `secrets.py`.

```python
WIFI_SSID      = "SSID"
WIFI_PASSWORD  = "PWD"
```

Never commit real credentials to GitHub. `project/secrets.py` is excluded by
the supplied `.gitignore`, while `secrets_example.py` remains in the template.

---

# Troubleshooting

## The screen still shows the old interface, and touch does nothing

The board is probably still in upload mode. Tap **RESET/RST once**. 
A retained image on the AMOLED does not mean the application is running.

## Upload cannot connect

1. Stop PlatformIO Monitor with `Ctrl+C`.
2. Disconnect and reconnect the USB cable if the port is locked.
3. Repeat the BOOT/RESET upload-mode sequence.
4. Start Upload again.

## The screen is black

Open PlatformIO Monitor after resetting. Startup errors are printed at 115200
baud and also stored as `/debug.log` on the device.


## LilyGo tutorial

Visit LilyGO [link](https://github.com/Xinyuan-LilyGO/LilyGo-AMOLED-Series)

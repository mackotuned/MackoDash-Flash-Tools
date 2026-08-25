<div align="center">

<img src="mackodash-hero.png" alt="MackoDash — Plug &amp; Play Digital Dash for EK &amp; RD1" width="750"/>

# MackoDash Flash Tools

**Official firmware update &amp; custom theme tools for the MackoDash digital gauge cluster**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](#requirements)
[![MCU](https://img.shields.io/badge/MCU-ESP32--P4%20%2B%20ESP32--C6-red.svg)](#requirements)

[Overview](#overview) •
[Compatible Vehicles](#compatible-vehicles) •
[Download](#download) •
[Getting Started](#getting-started) •
[Firmware Update](#firmware-update) •
[Custom Themes](#custom-themes) •
[Troubleshooting](#troubleshooting) •
[Support](#support)

</div>

---

## Overview

**MackoDash** is a plug &amp; play digital gauge cluster built around a dual-ESP32 platform — an **ESP32-P4** running the dashboard application and UI, paired with an **ESP32-C6** co-processor. It's designed as a direct replacement for the OEM instrument cluster.

This repository contains the official MackoDash Windows tools customers use to:

- ⚡ **Update dashboard firmware** on the ESP32-P4
- 🎨 **Build and install custom SD-card themes** designed in SquareLine Studio

Designed to work seamlessly with **Hondata S300 V3**, with minimal wiring and factory connectors — no cutting required.

## Compatible Vehicles

| Chassis | Model |
|---|---|
| EK | Honda Civic |
| RD1 | Honda CR-V |

## Download

`MackoDashUtility.exe` is the only customer application. Its Home screen opens
either **Update Firmware** or **Build a Theme**.

> **Do not mix up the ZIP files:** `MackoDash-Firmware.zip` is an official dashboard update used by the firmware updater. A SquareLine export ZIP is your own theme project used by Theme Builder.

Also included:

| File | Description |
|---|---|
| `MackoDash-Firmware.zip` | Complete validated ESP32-P4 firmware update bundle |
| [`CUSTOMER_INSTRUCTIONS.txt`](CUSTOMER_INSTRUCTIONS.txt) | Quick-start instructions |
| [`MackoDash_SquareLine_Customer_Instructions.txt`](MackoDash_SquareLine_Customer_Instructions.txt) | Printable custom theme reference |
| [squareline-theme-guide.md](squareline-theme-guide.md) | Complete online custom theme guide |

## Requirements

- Windows PC
- USB update cable
- MackoDash dashboard, powered on for the entire process

## Getting Started

1. Click the green **Code** button above → **Download ZIP** (or clone the repo).
2. Extract the downloaded ZIP to a normal folder on your PC.
3. Launch `MackoDashUtility.exe`.

Windows may show a SmartScreen warning because the apps are not Microsoft Store packages. Confirm that the publisher/download source is this official `mackotuned` repository before continuing.

## Firmware Update

> ⚠️ **Keep the dashboard powered and the USB cable connected for the entire update. Do not unplug either until verification finishes.**

1. Connect MackoDash to your Windows PC with its update USB cable.
2. Keep the dashboard powered for the entire update.
3. Open `MackoDashUtility.exe` and choose **Update Firmware**.
4. Select **Download Latest** to fetch and validate the current official firmware, or use **Choose ZIP** for a bundle already on the PC.
5. Confirm the dashboard's COM port.
6. Select **Install Firmware** and wait for verification to finish.

The firmware ZIP updates the ESP32-P4 bootloader, partition table, OTA metadata, dashboard application, and SPIFFS storage. It does **not** erase NVS, so dashboard settings and odometer data remain intact. SD-card themes and ESP32-C6 firmware are not changed.

## Custom Themes

MackoDash supports fully custom dashboard themes designed in **SquareLine Studio** (LVGL 8.4, 1024×600 canvas) and installed via SD card.

**Quick version:**

1. Design your dashboard in SquareLine Studio, naming any live-data objects using the [MackoDash naming convention](squareline-theme-guide.md) (e.g. `dash_rpm_value`, `dash_speed_bar`, `dash_coolant_arc`).
2. Export the complete project and ZIP the exported folder.
3. Open `MackoDashUtility.exe` and choose **Build a Theme**.
4. Select the SquareLine ZIP, enter a theme name and ID, then choose **Build Theme**.
5. Use **Preview Theme** to check typical and longest values, then select **Copy to SD Card**.
6. Insert the SD card into MackoDash and reboot.

📄 **See the full [SquareLine Theming Guide](squareline-theme-guide.md)** for every supported object name, live value, Bar/Arc range, and design rule.

## Troubleshooting

| Issue | Fix |
|---|---|
| USB port shows busy / won't connect | Close serial monitors and any other flashing programs, then retry |
| Firmware doesn't show as Validated | Use **Download Latest**, or re-download the official `MackoDash-Firmware.zip` without modifying it |
| Not sure which ZIP to select | Firmware updater: `MackoDash-Firmware.zip`. Theme Builder: your SquareLine export ZIP |
| Theme fails strict validation | Check object names against the [theming guide](squareline-theme-guide.md) — strict mode is intentional and stops on unsupported fonts/objects rather than guessing |

## Support

- 📧 Email: [mackotuned@gmail.com](mailto:mackotuned@gmail.com)
- 📷 Instagram: [@cream_civic](https://instagram.com/cream_civic)
- 🎵 TikTok: [@mackotuned](https://tiktok.com/@mackotuned)
- 🛒 Shop: coming soon

Found an issue not covered here? Open an [Issue](../../issues) on this repo.

## License

This project is licensed under the [MIT License](LICENSE).

---
<div align="center"><sub>Built for the MackoDash community 🏁</sub></div>


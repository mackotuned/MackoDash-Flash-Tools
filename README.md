<div align="center">

<img src="mackodash-hero.png" alt="MackoDash — Plug &amp; Play Digital Dash for EK &amp; RD1" width="750"/>

# MackoDash Flash Tools

**Official firmware update, custom theme, and driving log tools for the MackoDash digital gauge cluster**

**Current dashboard firmware: 2.1**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](#requirements)
[![MCU](https://img.shields.io/badge/MCU-ESP32--P4%20%2B%20ESP32--C6-red.svg)](#requirements)

[Overview](#overview) •
[Compatible Vehicles](#compatible-vehicles) •
[Download](#download) •
[Getting Started](#getting-started) •
[Firmware Update](#firmware-update) •
[Theme Studio](#theme-studio) •
[SquareLine Themes](#squareline-themes) •
[Boot Logos](#boot-logos) •
[Driving Logs](#driving-logs) •
[Troubleshooting](#troubleshooting) •
[Support](#support)

</div>

---

## Overview

**MackoDash** is a plug &amp; play digital gauge cluster built around a dual-ESP32 platform — an **ESP32-P4** running the dashboard application and UI, paired with an **ESP32-C6** co-processor. It's designed as a direct replacement for the OEM instrument cluster.

This repository contains the official MackoDash Windows tools customers use to:

- **Update dashboard firmware** on the ESP32-P4
- **Design themes directly** with Theme Studio
- **Build themes from SquareLine Studio** exports
- **Create and install custom boot logos** from PNG or JPEG images
- **Download and review driving logs** recorded on the dashboard SD card

Designed to work seamlessly with **Hondata S300 V3**, with minimal wiring and factory connectors — no cutting required.

## Compatible Vehicles

| Chassis | Model |
|---|---|
| EK | Honda Civic |
| RD1 | Honda CR-V |

## Download

Download the complete customer package from the [latest release](../../releases/latest). Every published version remains available on the [Releases page](../../releases), including its matching firmware and utility build.

`MackoDashUtility.exe` is the only customer application. Its Home screen opens
**Update Firmware**, **Theme Studio**, **Build a Theme**, **Boot Logo**, or
**View Driving Logs**.

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

1. Open the [latest release](../../releases/latest), or choose an older version from [all releases](../../releases).
2. Download and extract the customer package to a normal folder on your PC.
3. Launch `MackoDashUtility.exe`.

Windows may show a SmartScreen warning because the apps are not Microsoft Store packages. Confirm that the publisher/download source is this official `mackotuned` repository before continuing.

## Firmware Update

> ⚠️ **Keep the dashboard powered and the USB cable connected for the entire update. Do not unplug either until verification finishes.**

1. Connect MackoDash to your Windows PC with its update USB cable.
2. Keep the dashboard powered for the entire update.
3. Open `MackoDashUtility.exe` and choose **Update Firmware**.
4. Select **Download Latest** to fetch and validate the newest official release, or use **Choose ZIP** with `MackoDash-Firmware.zip` downloaded from any older release.
5. Confirm the dashboard's COM port.
6. Select **Install Firmware** and wait for verification to finish.

The firmware ZIP updates the ESP32-P4 bootloader, partition table, OTA metadata, dashboard application, and SPIFFS storage. It does **not** erase NVS, so dashboard settings and odometer data remain intact. SD-card themes and ESP32-C6 firmware are not changed.

## Theme Studio

Theme Studio creates MackoDash themes directly on a visual 1024x600 canvas.
Add labels, bars, arcs, calibrated path gauges, needles, analog gauges, images,
indicators, and buttons; assign live ECU bindings; preview typical or longest
values; then export a dashboard-ready `.mdtheme.zip` or send it over USB.

Projects can be saved as editable `.mdstudio.json` files. Runtime text uses the
bundled Montserrat SemiBold font with continuous sizes from 8 through 200 px.
Path Gauge supports up to 24 calibrated control points for nonlinear gauge art.

## SquareLine Themes

MackoDash supports fully custom dashboard themes designed in **SquareLine Studio** (LVGL 8.4, 1024×600 canvas) and installed via SD card or the dashboard USB update cable.

**Quick version:**

1. Design your dashboard in SquareLine Studio, naming any live-data objects using the [MackoDash naming convention](squareline-theme-guide.md) (e.g. `dash_rpm_value`, `dash_speed_bar`, `dash_coolant_arc`).
2. Export the complete project and ZIP the exported folder.
3. Open `MackoDashUtility.exe` and choose **Build a Theme**.
4. Select the SquareLine ZIP, enter a theme name and ID, then choose **Build Theme**.
5. Use **Preview Theme** to check typical and longest values.
6. Select **Copy to SD Card**, or connect the dashboard and select **Send over USB**.

An SD card must be inserted in the dashboard for USB theme installation. The
package is verified before installation, and the dashboard restarts when the
transfer completes.

📄 **See the full [SquareLine Theming Guide](squareline-theme-guide.md)** for every supported object name, live value, Bar/Arc range, and design rule.

## Boot Logos

Open **Boot Logo** to convert a PNG or JPEG into the dashboard's validated
1024x600 format. Choose Fit or Fill, select a background color, preview the
result, then export it or send it over USB. Up to 12 logos can be stored on the
SD card and selected or deleted under **Settings > Display > Boot Logo**. The
built-in MackoDash logo always remains available.

## Driving Logs

Open **View Driving Logs** to review a CSV from the PC, find recordings on a
removable SD card, or download recordings through the dashboard USB update
cable. USB downloads are CRC-verified and open directly in the synchronized
graph viewer.

The USB cable uses a serial file-transfer connection. The dashboard SD card
does not appear as a Windows drive. Keep a working SD card inserted and stop
active drive recording before downloading logs or sending a theme.

## Dashboard Quick Controls

- Tap **Settings** for the full menu; hold **Settings** for Day, Dim, and Night brightness presets.
- Configure automatic recording and log filename types under **Settings > Logs > Driving Logs**.
- Configure VTEC, redline, warnings, shift-light RPM, colors, brightness, and optional per-gear targets under **Settings > Engine Limits**.
- Select English, Spanish, Portuguese, or Japanese under **Settings > Display**.
- Configure Hondata Analog 0-6 fuel input and measured empty/full voltages under **Settings > System > Fuel Gauge Setup**.
- Open **Settings > System > Contact & Support** for problem reporting, email, social, and feedback QR codes.
- Critical engine warnings use a compact prioritized banner so the active dashboard remains visible.
- Simulation is hidden by default and can be enabled from Display when needed.

## Troubleshooting

| Issue | Fix |
|---|---|
| USB port shows busy / won't connect | Close serial monitors and any other flashing programs, then retry |
| USB log/theme transfer says SD not found | Insert a working SD card in the dashboard and restart it |
| USB log/theme transfer says recording active | Stop the current driving-log recording, then retry |
| Fuel level is reversed or inaccurate | Confirm the selected analog input and enter measured Empty and Full voltages under Fuel Gauge Setup |
| Firmware doesn't show as Validated | Use **Download Latest**, or re-download the official `MackoDash-Firmware.zip` without modifying it |
| Not sure which ZIP to select | Firmware updater: `MackoDash-Firmware.zip`. Theme Builder: your SquareLine export ZIP |
| Theme fails strict validation | Check object names against the [theming guide](squareline-theme-guide.md) — strict mode is intentional and stops on unsupported fonts/objects rather than guessing |

## Support

- 📧 Email: [mackotuned@gmail.com](mailto:mackotuned@gmail.com)
- 📷 Instagram: [@cream_civic](https://instagram.com/cream_civic)
- 🎵 TikTok: [@mackotuned](https://tiktok.com/@mackotuned)
- 🛒 Shop: coming soon

Found an issue not covered here? Open an [Issue](../../issues) on this repo.

> Hondata analog inputs are limited to 5 V. Disconnect the fuel sender from any
> stock-cluster power feed and verify the signal with a multimeter before
> connecting it to the ECU.

## License

This project is licensed under the [MIT License](LICENSE).

---
<div align="center"><sub>Built for the MackoDash community 🏁</sub></div>


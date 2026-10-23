# Custom ROM Installation Guide

A comprehensive, step-by-step guide to unlocking the full potential of your device. Whether you're switching to **Xiaomi.eu** or an **AOSP-based** build, follow these steps carefully (Other custom ROMs, such as HyperVoltron Elite ROM, may have their own unique flashing methods; please review their methods separately.).

> [!WARNING]  
> **Disclaimer:** Your warranty is now void. I am not responsible for bricked devices, dead SD cards, or you getting fired because the alarm app failed. Proceed at your own risk!

---

## 🛠️ Prerequisites

Before we dive into the rabbit hole, ensure you have:
* **Unlocked Bootloader:** (The hardest part thanks to HyperOS restrictions).
* **ADB & Fastboot Drivers:** Installed on your PC.
* **Platform Tools:** Latest version from Google.
* **Battery:** At least 60% (don't let it die mid-flash!).
* **Backup:** All data will be wiped. **EVERYTHING.**

---

## 🚀 Installation Steps

### 1. Fastboot Mode
Power off your device, then hold **Volume Down + Power** until the Fastboot logo appears. Connect it to your PC.

### 2. Flashing Recovery (TWRP/OrangeFox)
If a custom recovery is available for `Your Device`:

```bash
# Standard devices
fastboot flash recovery recovery.img

# Newer Xiaomi devices (recovery_ab partition)
fastboot flash recovery_ab recovery.img
```

Then boot into it:

```bash
fastboot reboot recovery
```

### 3. The "Clean Slate" (Wipe)
Inside recovery:

1. Go to **Wipe > Format Data**.
2. Type `yes` to confirm.
3. Reboot back to recovery.

### 4. Sideloading the ROM
Connect to PC and use ADB Sideload:

```bash
adb sideload your_rom_file.zip
```

Or transfer the zip to internal storage and install via recovery GUI.

### 5. Final Touch (Rooting)
If you want that sweet Magisk/KernelSU access:

Flash the `Magisk.apk` (renamed to `.zip`) or use the KernelSU manager.

---

## 🧰 Post-Install Essentials (LSPosed)

After booting, don't forget to set up:

- **LSPosed (Zygisk):** For system hooks and customization.
- **Play Integrity Fix:** To keep your banking apps working.
- **Shamiko:** To hide root from nosy apps.

---

## 🤝 Credits & Support

Thanks to the developers of the ROMs and Recoveries.

- Join the [Telegram Community](https://t.me/HyperVoltron) for real-time troubleshooting.

Found this guide helpful? Give it a ⭐ to support the project!

---

## 📄 License

This guide is licensed under [CC BY 4.0](LICENSE). You may share and adapt it, as long as you give appropriate credit.

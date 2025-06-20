# Fedora NVIDIA Driver & Multimedia Setup Script 🚀

This script automates the installation of the correct **NVIDIA driver**, **CUDA support**, and **multimedia codecs** on Fedora (including 41 and 42), with smart GPU detection and optional advanced configuration.

---

## 🎯 Features

- 🔍 Auto-detects your NVIDIA GPU and selects the proper driver (latest or legacy series)
- ⚙️ Installs NVIDIA driver with `akmod` support
- 🚀 Adds optional CUDA support
- 🎞️ Installs full multimedia codec stack:
  - ffmpeg, libdvdcss
  - libva-nvidia-driver (VAAPI bridge)
  - Intel media driver (for hybrid graphics)
- 💡 Prevents accidental removal with `dnf autoremove`
- 🛡️ Optional flags:
  - `--wayland` – Enables Wayland/KMS support (`nvidia-drm.modeset=1`)
  - `--nouveau-disable` – Blacklists the Nouveau driver and regenerates `initramfs`
  - `--secureboot` – Displays instructions if Secure Boot is enabled

---

## 🛠️ How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/mahbub-research/fedora-nvidia-setup-script.git
cd fedora-nvidia-setup-script


## 📁 File Structure

fedora-nvidia-setup-script/
├── nvidia-driver-multimedia-setup.sh
└── README.md

## 🔐 Secure Boot Note
If you have Secure Boot enabled, you’ll need to generate and enroll a MOK key and sign the NVIDIA module manually. The script will warn you if Secure Boot is active. For details, see:
📘 RPM Fusion Secure Boot Guide

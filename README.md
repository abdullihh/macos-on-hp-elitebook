# HP EliteBook 1040 G7 — macOS 26 Tahoe

This repository is a guide to turning the **HP EliteBook 1040 G7** into a smooth and responsive MacBook Pro-like laptop running **macOS 26 Tahoe**. It documents the setup, configuration, working hardware, known limitations, and technical details so the process can be reproduced and improved.

> **Disclaimer:** This is an experimental Hackintosh project for a specific laptop configuration, not an official Apple or HP guide. Hardware revisions, BIOS settings, EFI files, and software versions can change the result. Back up important data before changing partitions or firmware. Use this guide at your own risk, and do not copy another machine's SMBIOS serial numbers or other unique identifiers.

## Laptop specifications

| Component | Specification |
|---|---|
| Laptop | HP EliteBook 1040 G7 |
| CPU | Intel Core i5-10310U (4 cores / 8 threads 1.7-4.4 GHz) |
| Integrated graphics | Intel UHD Graphics 630 |
| Memory | 16 GB dual-channel DDR4 |
| Internal storage | 1 TB NVMe SSD |
| Audio | Realtek ALC285 |
| Wi-Fi / Bluetooth | Intel Wi-Fi 6 AX201 |
| Display | 1080p IPS Touchscreen |
| Camera | Intel HD Camera |
| macOS version | macOS 26 Tahoe |
| Bootloader | OpenCore 1.0.8 |
| SMBIOS | MacBookPro16,2 (2020 13 Inch Macbook Pro) |

## Hardware compatibility

Update the **Status** and **Notes** columns as you test each feature on your own installation. This table describes the current build and is not a guarantee that every EliteBook 1040 G7 will behave identically.

| Component / feature | Status | Notes |
|---|---|---|
| macOS 26 Tahoe boot | ✅ Working | Boots using OpenCore. |
| Intel UHD 630 graphics acceleration | ✅ Working | Graphics acceleration is enabled; macOS reports 1536 MB VRAM. |
| Built-in display | ✅ Working | Set the display color profile to **sRGB** for correct colors on this setup. |
| Touchscreen | ✅ Working | Basic touch input and Gestures work; Srolling has to be done with two fingers |
| Internal audio / speakers | ✅ Working | The correct output appears as the second **Internal Speaker** entry in Sound settings. |
| Intel Wi-Fi | ✅ Working | Wi-Fi works from the native macOS WiFi menu. |
| Bluetooth | 🧪 Verify | Add test results for pairing, audio devices, and sleep/wake behavior. |
| Battery status | ✅ Working | Battery information is detected by macOS. Verify percentage, charging, and battery-health reporting. |
| Lid close / display sleep | ✅ Working | The display turns off when the lid is closed. |
| Wake after opening lid | 🟡 Partially working | Opening the lid alone did not reliably wake the display; keyboard input could wake it. |
| Keyboard | ✅ Working | Brightness/volume keys also function perfectly |
| Trackpad and gestures | 🧪 Verify | Record pointer movement, click, scrolling, and multi-touch gesture support. |
| Camera | ✅ Working | The camera is detected as USB hardware |
| USB-A ports | ✅ Working | Complete USB mapping works |
| USB-C / Thunderbolt | ✅ Working | Complete USB mapping works |
| HDMI / external display | 🟡 Partially working | Native HDMI port does not but USB-C to HDMI converter works |
| Ethernet | ✅ Working  | Depends on the adapter or dock used. |
| Sleep / standby | 🟡 Partially working  | Laptop successfully goes to sleep but waking up sometimes cause problems |
| Microphone | ⛔ Not working | Internal microphone does not work. But USB mics work |
| Fingerprint reader | ⛔ Not working | macOS does not accept any fingerprint reader other than official Apple ones |

## Installation guide

### 1. Preparation

- [ ] Confirm the exact laptop model and hardware revision.
- [ ] Back up personal files and create recovery/install media for existing operating systems.
- [ ] Record the current BIOS/UEFI version and settings.
- [ ] Download the required tools and files; document the source and version of each.
- [ ] Explain any prerequisites, risks, and required storage space.

**Notes / links:**

- `TODO: add preparation notes`
- `TODO: add links to required tools and official documentation`

### 2. BIOS / UEFI configuration

- [ ] Document each required BIOS/UEFI setting.
- [ ] Note settings that must remain unchanged and how to restore defaults.
- [ ] Add screenshots or photos where they make the settings easier to identify.

**Settings used on this laptop:**

- `TODO: add verified BIOS settings`

### 3. Create the installer

- [ ] Document how to obtain the macOS installer/recovery files.
- [ ] Document how to prepare the USB installer.
- [ ] Include integrity checks where applicable.
- [ ] Explain the required folder layout and any files that must be added manually.

**Steps / commands:**

1. `TODO`
2. `TODO`
3. `TODO`

### 4. Build and configure the EFI

- [ ] Explain how the EFI was generated or assembled.
- [ ] Document the OpenCore version and configuration approach.
- [ ] List required kexts, ACPI files, drivers, and their order where relevant.
- [ ] Explain important `config.plist` changes, including graphics, audio, Wi-Fi, USB, and power management.
- [ ] Remove all personal SMBIOS identifiers before sharing the EFI.

**EFI structure:**

```text
EFI/
└── OC/
    ├── ACPI/
    ├── Drivers/
    ├── Kexts/
    ├── Tools/
    └── config.plist
```

`TODO: explain which files are required and how to obtain/build them.`

### 5. Boot and install macOS

- [ ] Explain how to select the installer from the OpenCore picker.
- [ ] Add the exact installation flow and any reboot stages.
- [ ] Document common errors and their known fixes.
- [ ] Explain how to boot the installed system for the first time.

**Steps / troubleshooting:**

1. `TODO`
2. `TODO`
3. `TODO`

### 6. Post-install configuration

- [ ] Configure and verify graphics acceleration.
- [ ] Configure and verify audio output and microphone input.
- [ ] Configure and verify Wi-Fi and Bluetooth.
- [ ] Complete USB port mapping and test every physical port.
- [ ] Test touchscreen, keyboard, trackpad, camera, battery reporting, sleep, and wake.
- [ ] Document any power-management or temperature tuning.
- [ ] Explain how to move the EFI to the internal drive, if applicable, and how to recover if it fails.

**Steps / results:**

- `TODO`

### 7. Updating, recovery, and known issues

- [ ] State which macOS updates have been tested and which have not.
- [ ] Explain how to back up and restore the working EFI.
- [ ] Record known issues, workarounds, and regression risks.
- [ ] Explain how to collect logs for troubleshooting without posting personal identifiers.

**Known issues:**

- `TODO`

## Technical information

This section is a place to document the exact software, files, and configuration used. Verify every entry against the EFI that you intend to publish; do not treat an example or an old configuration as authoritative.

### Core versions and settings

| Setting | Current value | Notes |
|---|---|---|
| macOS | macOS 26 Tahoe | Record the exact build number from **About This Mac** / System Information. |
| OpenCore | 1.0.8 *(reported)* | Verify the version in the published EFI. |
| Configuration tool | OpenCore Simplify / ProperTree / other | `TODO: state the tool actually used and version` |
| SMBIOS | MacBookPro16,2 *(reported)* | Never publish real serial numbers, MLB, ROM, or other unique identifiers. |
| `AAPL,ig-platform-id` | `00009B3E` *(reported)* | Confirm the current `DeviceProperties` value and data encoding. |
| Audio `layout-id` | `71` *(reported)* | Confirm against the working `config.plist`. |
| Boot arguments | `-v debug=0x100 keepsyms=1 -igfxblt -vi2c-force-polling` *(reported)* | Re-test each argument and remove anything no longer needed. |
| USB mapping | USBToolBox workflow *(reported)* | Record the final map and physical port layout once verified. |
| CPU power management | CPUFriend / CPUFriendDataProvider *(tested or being configured)* | Include only if present and working in the final EFI. |

### Kernel extensions (kexts)

List the **exact** kexts included in `EFI/OC/Kexts`, their versions, download/source links, purpose, and any dependencies. Remove rows that do not apply and add every kext in the final EFI.

| Kext | Version / commit | Purpose | Source | Included / tested? |
|---|---|---|---|---|
| `Lilu.kext` | `TODO` | Patching framework used by several plugins | `TODO` | `TODO` |
| `VirtualSMC.kext` | `TODO` | SMC emulation | `TODO` | `TODO` |
| `WhateverGreen.kext` | `TODO` | Intel graphics support and patches | `TODO` | `TODO` |
| `AirportItlwm.kext` | `TODO` | Intel Wi-Fi | `TODO` | `TODO` |
| `AppleALC.kext` **or** chosen audio solution | `TODO` | Audio support, if used by this EFI | `TODO` | `TODO` |
| `USBToolBox.kext` | `TODO` | USB mapping support, if used | `TODO` | `TODO` |
| `UTBMap.kext` | `TODO` | USB port map, if used | `TODO` | `TODO` |
| `CPUFriend.kext` | `TODO` | CPU power-management tuning, if used | `TODO` | `TODO` |
| `CPUFriendDataProvider.kext` | `TODO` | Generated CPU power profile, if used | `TODO` | `TODO` |
| `Other kexts` | `TODO` | `TODO` | `TODO` | `TODO` |

### ACPI files

| File | Purpose | Source / generation method | Notes |
|---|---|---|---|
| `SSDT-*.aml` | `TODO` | `TODO` | `TODO` |
| `Other ACPI files` | `TODO` | `TODO` | `TODO` |

### OpenCore drivers and tools

| File | Purpose | Notes |
|---|---|---|
| `OpenRuntime.efi` | Runtime support, if included | Confirm against the final EFI. |
| `OpenCanopy.efi` | Graphical boot picker, if included | Requires its matching resources and configuration. |
| `Other drivers/tools` | `TODO` | `TODO` |

### `config.plist` areas to document

Describe only settings actually present in your final configuration, and explain why they are needed.

- **ACPI:** `TODO`
- **Booter quirks:** `TODO`
- **Kernel quirks and kext order:** `TODO`
- **DeviceProperties / iGPU:** `TODO`
- **NVRAM / boot arguments:** `TODO`
- **PlatformInfo / SMBIOS:** `TODO` *(redact unique identifiers)*
- **UEFI drivers and quirks:** `TODO`
- **USB map:** `TODO`
- **Audio configuration:** `TODO`
- **Power management:** `TODO`

### Hardware identifiers and useful diagnostics

- PCI device IDs: `TODO`
- Audio codec / layout details: `TODO`
- USB controller and port map: `TODO`
- Wi-Fi / Bluetooth chipset and firmware details: `TODO`
- Relevant OpenCore logs or troubleshooting notes: `TODO`

Do not publish personal data, full serial numbers, Apple account details, device UUIDs, or unredacted diagnostic logs that expose unique identifiers.

## Credits

Thanks to the people and projects whose documentation, tools, patches, and troubleshooting made this build possible. Add the appropriate names and links, and specify what each contribution helped with.

- `TODO — name / project` — `TODO: contribution and link`
- `TODO — name / project` — `TODO: contribution and link`
- `TODO — name / project` — `TODO: contribution and link`

## License and project notes

`TODO: choose a license for your own documentation and original files. Review the licenses and redistribution terms of third-party tools and files before including them in this repository.`

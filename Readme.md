# AMD Radeon Tweaks – Performance

A Windows batch script designed to apply or revert a collection of AMD Radeon driver and Windows registry settings.

The project focuses on experimenting with GPU power-management behavior, driver preferences, clock gating, PCIe power management, and Windows display configuration.

> **Disclaimer:** This is an experimental tweaking script. The registry settings are largely undocumented, driver-dependent, and not guaranteed to improve performance. Use at your own risk.

---

## Features

- **Automatic AMD GPU Detection** – Searches Windows display-adapter registry entries for an AMD graphics adapter.
- **Apply Configuration** – Writes the selected AMD and Windows registry values.
- **Revert Configuration** – Removes the registry values managed by the script.
- **Power Management Tweaks** – Modifies selected GPU power-management and low-power-state settings.
- **Clock Gating Tweaks** – Changes selected graphics, display, and hardware clock-gating options.
- **PCIe Configuration** – Modifies selected PCIe Active State Power Management (ASPM) settings.
- **Windows MPO Configuration** – Applies a Desktop Window Manager Multiplane Overlay (MPO) registry override.
- **AMD Service Configuration** – Changes the startup configuration of selected AMD services.

## Requirements

- Windows 10 or Windows 11.
- An AMD graphics adapter with a compatible AMD driver.

No additional third-party software is required.

## Installation

1. Download or clone this repository.
2. Extract the files if downloaded as a ZIP archive.
3. Locate the `.bat` file.
4. Run it with administrator privileges.
5. Select the desired operation from the menu.

## Usage

The script provides two main options:

| Option | Action | Description |
|---|---|---|
| 1 | Apply | Writes the configured AMD and Windows registry values. |
| 2 | Revert | Deletes the registry values managed by the script. |

After applying the settings, restart Windows so that the graphics driver can reload its configuration.

## Technical Overview

The script modifies several groups of registry settings.

### 1. AMD Driver Preferences

Changes selected driver preferences related to analytics, notifications, stutter handling, frame pacing, Radeon Chill, Radeon Boost, and other driver-specific options.

### 2. GPU Power Management

Modifies selected settings associated with:

- GPU performance states.
- Dynamic Power Management (DPM).
- GPU deep-sleep behavior.
- ULPS (Ultra-Low Power State).
- GFXOFF-related behavior.

### 3. PCIe Power Management

Changes selected PCIe Active State Power Management settings, including L0s, L1, and L1 Substates.

### 4. Clock Gating

Modifies selected clock-gating options for graphics, display, memory, video encoding, video decoding, and other hardware components.

### 5. Power Gating

Changes selected power-gating options for supported AMD GPU hardware blocks.

### 6. Display Configuration

Modifies selected display-engine settings, including display clock behavior and clock-gating options.

### 7. AMD Windows Services

Changes the startup configuration of selected AMD services.

### 8. Windows MPO

Adds the `OverlayTestMode` registry value under:

`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Dwm`

This is an experimental Windows display-composition override and may affect display behavior.

---

## Troubleshooting

### Script closes after requesting administrator privileges

Make sure PowerShell and Windows elevation prompts are functioning correctly. The script uses `fltmc` to check administrator privileges.

### AMD GPU not detected

Check that:

- AMD graphics drivers are installed.
- The AMD adapter appears in Device Manager.
- The AMD display adapter has a valid registry entry.
- The AMD driver provider is identified as Advanced Micro Devices.

### Registry changes do not appear to have an effect

Some registry values may not be supported by your driver or hardware. A Windows restart may also be required.

---

## Disclaimer

This project is provided for educational and experimental purposes.

It is not an official AMD product and is not affiliated with, endorsed by, or supported by AMD.

The author is not responsible for system instability, driver issues, increased power consumption, hardware problems, or data loss resulting from the use of this script.

Use at your own discretion.

---

## Credits

**Author:** infinite667

**Project:** AMD Radeon Tweaks – Performance Configuration

**GitHub:** [github.com/infinite667](https://github.com/infinite667)

Contributions, testing feedback, and technical discussions are welcome.

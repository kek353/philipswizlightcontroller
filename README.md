# kek's WiZ Light Controller
# Author: @kek353 on GitHub, Eshaan Pisal, Release Date 06/01/2026, Version 1.0
A fast, lightweight, and fully-featured desktop controller for **Philips WiZ lights**, built with Python and CustomTkinter for Windows.

This app provides **instant local control** of WiZ lights without relying on cloud services, while offering advanced features like presets, automatic discovery, persistent saved lights, and a custom-built color engine.

<img width="611" height="979" alt="main_rgb" src="https://github.com/user-attachments/assets/3e002b5c-a135-46d4-83aa-0a8d4e54987d" />

---

## Features

### Local, Instant Control
- Direct LAN control of WiZ lights
- Extremely fast response using UDP commands
- Built-in debounce to prevent firmware overload

---

### Automatic Light Discovery
- Scan your local network for WiZ lights
- Lists:
  - Device name
  - IP address
  - MAC address (used as stable identifier)
- Works even if IP addresses change

<img width="462" height="461" alt="discovery" src="https://github.com/user-attachments/assets/d0f83b6a-b38a-4ec3-a0d8-62fb3112cdf7" />

---

### Saved Lights (MAC-Based)
- Save lights permanently using MAC address
- Automatically updates saved IPs when they change
- Supports:
  - Renaming saved lights
  - Deleting saved lights
- Double-click any saved light to connect instantly

---

### Advanced Color Control
- Custom-built **anti-aliased color wheel**
- Fully synced:
  - Color wheel
  - RGB sliders
  - HSV sliders
  - Hex input
- Changes propagate correctly in all directions
- Last used RGB values persist across restarts

---

### White Mode with Temperature Control
- White mode with Kelvin temperature slider
- Temperature rendered as a gradient canvas
- Smooth animated transitions
- Supports:
  - Presets
  - Sync from light
  - Manual adjustment

<img width="611" height="473" alt="2026-01-06 20_48_21-kek&#39;s WiZ Light Controller" src="https://github.com/user-attachments/assets/cfaadca4-fd17-4700-a053-eade6e547521" />

---

### Brightness Control
- Gradient-based brightness slider
- Gradient reflects **actual bulb color**, not UI-only state
- Works consistently across:
  - RGB mode
  - White mode
  - Presets
  - Sync from light
- Smooth animation when changed by presets

---

### Presets System
- Separate presets for:
  - RGB mode
  - White mode
- Presets store:
  - Color / Temperature
  - Brightness
  - Mode
- Features:
  - One-click apply
  - Automatic highlight when active
  - De-highlights if state no longer matches
  - Right-click to:
    - Rename
    - Reorder (Move Left / Right)
    - Inspect values
- Presets persist across restarts

---

### Sync from Light
- Reads the **actual state of the bulb**
- Updates:
  - Mode
  - Color / Temperature
  - Brightness
  - Preset highlight state
- Safe to use at any time
- Optional Auto-Sync on startup

---

### Settings Menu
- Accessible via gear icon
- Supports:
  - Accent color customization
  - Highlighted preset color customization
  - Auto-Sync toggle
- Live preview of color values
- Reset to defaults supported
- All settings persist in AppData

<img width="422" height="360" alt="2026-01-06 20_50_04-Settings" src="https://github.com/user-attachments/assets/2ef31f3e-8ea1-48f8-aa1a-f4e9203984e9" />

---

### Built-in Help Guide
- Full in-app help dialog
- Covers:
  - First-time setup
  - Discovery vs manual IP
  - Presets usage
  - Sync behavior
  - Known WiZ firmware quirks
- Non-modal (can use app while reading)
- 
<img width="542" height="612" alt="2026-01-06 20_50_27-Help   Guide" src="https://github.com/user-attachments/assets/8509e215-ff25-453c-8afa-0207729e4d1a" />

---

### Smart UX & Safety
- Non-blocking discovery (UI never freezes)
- Handles WiZ firmware “micro-sleeps”
- Prevents invalid sync attempts (empty IP)
- Gracefully handles destroyed dialogs
- No duplicate network commands within debounce window

---

##  Platform Support

- Windows (tested)
- Python 3.10+
- Local network required, the same one to which your WiZ lights are connected

---

## Packaging

A pre-packaged EXE is provided in the releases section, but the app can be packaged into a single executable using PyInstaller:
(Assets folder is required in the same location as the .py file)

```bat
pyinstaller --onefile --noconsole --name "KeksWizLightController" --icon=assets/app_icon.ico --add-data "assets;assets" wiz.py
```
You are free to use AND modify the program for personal use, but you must credit this page in the case you decide to publish it anywhere, under the GPL-3.0 license. I am not responsible for any damange caused by the modification of this program.

# 🪟 Windows XP Professional — Wonderland OS Suite (Web + ESP32-S3 + Linux Bridge)

![Build Status](https://img.shields.io/badge/Web_OS-Build_7.0_SP3-0058ee?style=for-the-badge&logo=windows-xp)
![ESP32 Firmware](https://img.shields.io/badge/ESP32--S3_Firmware-Build_3.3-258525?style=for-the-badge&logo=espressif)
![Python Bridge](https://img.shields.io/badge/Linux_UDP_Bridge-Port_4444-00ffcc?style=for-the-badge&logo=python)
![License](https://img.shields.io/badge/License-MIT-ffb900?style=for-the-badge)

> *"Begin at the beginning, and go on till you come to the end: then stop."* — A complete, zero-dependency **Windows XP Professional** operating system environment spanning a **Single-File HTML5 Web Workstation**, physical **ESP32-S3 / CYD 320x240 Touchscreen Hardware**, and a **Linux Desktop UDP/VFD Transceiver**.

Developed by **Magic Goat Studio**.

---

## ✨ Architecture Overview

This repository contains three interconnected environments that can run standalone or communicate with one another over **Wi-Fi UDP (Port 4444)** and **Physical USB/Hardware UART (`WebSerial` / `COM1` / `COM2`)**:

1. 🌐 **`xp_wonderland_os_v7.html` (Build 7.0 Web Workstation):** A 100% self-contained, single-file HTML5/JS/CSS operating system with zero external image or audio dependencies. All icons are rendered via multi-layered vector SVGs, all audio is generated in real time via the **Web Audio API**, and files persist across reboots via `localStorage`.
2. 📟 **`esp32_xp_wonderland.ino` (Build 3.3 Embedded Firmware):** Runs natively on Freenove ESP32-S3 / Cheap Yellow Display (CYD `320x240` ILI9341 + XPT2046 Touch) hardware. Features a custom zero-dependency **16-segment procedural ASCII glyph renderer**, isolated SPI buses (`HSPI` Touch + `VSPI` SD Card), hardware audio mute guards, and live Wi-Fi UDP chat.
3. 🐧 **`msn_vfd_bridge.py` (Linux Desktop Companion):** A Python `tkinter` transceiver with a toggleable **Glowing Cyan VFD** and **MSN Messenger 6.2** skin that chats, beams files to Notepad, and trades window-shaking nudges with the ESP32 over UDP Port `4444`.

---

## 🚀 Complete Inventory of Working Features

### 🖥️ 1. Authentic Boot, BIOS & First-Boot Setup (`CONFIG.SYS`)
* **Award Modular BIOS v6.00PG POST Sequence:**
  * Live RAM counting with synthesized PC speaker clicks, EPA Energy Star badge, and IDE/SPIFFS/SD drive enumeration.
  * **Interactive CMOS Setup Utility (`[DEL]`):** Toggle system audio mute, format/reset the virtual SD card, reset desktop icon positions, or delete `CONFIG.SYS` to re-trigger the First-Boot Wizard.
* **Persistent `D:\CONFIG.SYS` Inspection & First-Boot OOBE Wizard:**
  * On boot, the OS inspects `D:\CONFIG.SYS`. If missing (first boot or deleted), it launches the authentic **Windows XP Welcome / OOBE Setup Screen**.
  * Prompts for a **Username** and **Display Photo Tile** (8 built-in presets + **Custom Image Upload**).
  * Automatically writes `USERNAME`, `AVATAR`, `SCREENSAVER`, `SS_TIMEOUT`, `BSOD_RATE`, and `AUDIO_MUTED` to `D:\CONFIG.SYS`.
  * Editing `D:\CONFIG.SYS` inside Notepad and saving immediately hot-reloads your live system profile!

---

### 🎨 2. Luna Desktop Shell & 8-Way Window Manager
* **Authentic Windows XP Vector Desktop Icons:**
  * Features custom multi-layered SVG artwork for **My Documents**, **My Computer**, **My Network Places**, **Internet Explorer**, and **Recycle Bin** (anchored bottom-right by default).
  * **Free-Draggable & Persistent:** Drag any icon anywhere on the Bliss wallpaper; coordinates save automatically to `localStorage` (with **Snap to Grid** and **Reset Default** options in Control Panel).
* **8-Direction Window Resizing & Window Chrome:**
  * Grab any window's `N, S, E, W, NE, NW, SE, SW` border or corner grip (`◢`) to resize smoothly with live canvas reflow.
  * Full z-index focus stacking, title-bar dragging, Maximize/Restore (`□`), Close (`X`), and interactive Taskbar tabs.
* **Two-Column Luna Start Menu & Cascading "All Programs" Flyout:**
  * **Left Column:** Pinned apps with two-line descriptions + interactive **`All Programs ▸`** cascading drawer (*Microsoft Office XP*, *Accessories*, *Games*, *Multimedia*).
  * **Right Column (`#d3e5fa`):** System places (*My Documents, My Computer, My Network Places, Recycle Bin, About Windows `winver`, Control Panel, Task Manager, DirectX Diagnostics, `CONFIG.SYS`*).

---

### 🏢 3. Working Microsoft Office XP (2002) Productivity Suite
* **📘 Microsoft Word 2002 (`win-word`):**
  * Rich-text WYSIWYG page editor (`contenteditable` print-layout view).
  * Font family selector (*Times New Roman, Tahoma, Courier New, Georgia*), font size (`12pt–24pt`), Bold, Italic, Underline, Left/Center alignment, bulleted lists, and custom font color picker.
  * Live status bar with real-time **Word & Character count**.
  * **Save `.DOC` to `D:\`** and **Load `.DOC` from `D:\`**.
* **📗 Microsoft Excel 2002 (`win-excel`):**
  * Interactive `A1:F10` spreadsheet grid with active cell reference indicator and `fx` formula bar.
  * **Working Formula Engine:** Evaluates `=SUM(A1:A5)`, `=AVG(A1:A5)`, cell references, and arithmetic expressions (`=B2*C2`, `=A1+B1*2`) automatically on blur or recalculation.
  * Includes a pre-loaded **Off-Grid Solar Hardware Budget** template and **Save `.XLS` to `D:\`**.
* **📙 Microsoft PowerPoint 2002 (`win-ppt`):**
  * Left-hand slide thumbnail sorter, editable slide Title and Bullet body fields, **+ New Slide**, **Delete Slide**, and **4 Slide Background Themes**.
  * **Fullscreen Slide Show Mode (`F5`):** Launches an interactive fullscreen presentation overlay (click or press `SPACE` to advance slides, `ESC` to exit) and saves `.PPT` decks to `D:\`.

---

### ℹ️ 4. `winver.exe` (Real Host Hardware Telemetry) & Diagnostics
* **About Windows (`winver.exe`):**
  * Probes and displays **real physical hardware specs** from your host machine using browser & WebGL APIs:
    * **Logical CPU Threads:** via `navigator.hardwareConcurrency` + OS/Architecture (`navigator.platform`).
    * **Physical System RAM & JS Heap:** via `navigator.deviceMemory` and `performance.memory`.
    * **Unmasked Physical GPU Model:** via WebGL `WEBGL_debug_renderer_info` (`UNMASKED_RENDERER_WEBGL`).
    * **Display Output:** Native screen resolution, color depth, and device pixel ratio.
* **Windows Task Manager (`win-taskmgr`):**
  * Live scrolling green-phosphor oscilloscope plotting real-time CPU load and heap allocation + system uptime (`HH:MM:SS`).
* **DirectX Diagnostic Tool (`dxdiag` — `win-dxdiag`):**
  * Real-time 60 FPS 3D perspective wireframe cube with speed multiplier (`1x/2x/3x`), color cycling, and a 4-tone **DirectSound Sweep** synthesizer test.

---

### 🎵 5. Multimedia, Web Portal & P2P Communications
* **⚡ Winamp 2.91 Hybrid Audio Player (`win-winamp`):**
  * Authentic graphite & gold Winamp 2.91 skin with green LED clock, scrolling marquee ticker, `kbps`/`kHz` badges, Volume slider, Stereo Pan slider (`StereoPannerNode`), and toggleable Playlist Editor (`PL`).
  * **Real-Time WebAudio FFT Visualizer:** Click the visualizer box to toggle between the **16-Band Spectrum Analyzer** (with gravity-falling white peak-hold dots) and **Green Phosphor Oscilloscope**.
  * **5 Built-In Polyphonic Chiptune Tracks:** Includes *Men Without Hats - The Safety Dance*, *a-ha - Take On Me*, *Rush - Tom Sawyer*, *Bobby Prince - At Doom's Gate (E1M1)*, and *DJ Mike Llama Intro*.
  * **`⏏ OPEN` Real Audio Loader:** Load real `.mp3`, `.wav`, `.ogg`, or `.flac` files from your computer; routes audio straight through the WebAudio FFT spectrum analyzer!
* **🌐 Internet Explorer 6.0 & Recreated Albino Blacksheep Portal (`win-ie6`):**
  * Interactive 2003 **Albino Blacksheep** Flash portal with 4 animated HTML5 Canvas SWF stages and synthesized audio:
    1. *The End of Ze World (`wtfmate.swf`)*
    2. *Badger Badger Badger (`badgers.swf`)*
    3. *The Llama Song (`llama.swf`)*
    4. *Shfifty Five (`shfiftyfive.swf`)*
  * Address bar also supports navigating to external URLs via a sandboxed iframe view.
* **💬 MSN Messenger 6.2 (`win-msn`):**
  * Multi-tab real-time P2P chat and window-shaking **`NUDGE!`** alerts via `BroadcastChannel` (open two browser tabs side-by-side to chat live!) plus an automated Cheshire Bot responder.
* **🎨 MS Paint (`win-paint`):**
  * Pencil, Brush, Line, Rectangle, Circle, Flood Fill, Eraser, 16-color Luna palette, and **Save `.BMP` to `D:\`**.

---

### 🎮 6. Classic Games &Playable 3D DOOM Clone
* **💀 DOOM95 (`win-doom` — *Knee-Deep in Wonderland*):**
  * 60 FPS DDA 3D raycasting engine with textured/shaded walls, floor/ceiling gradients, top-left automap minimap, and the classic DOOM status bar (animated marine face, Ammo, Health, Armor, Kill counter).
  * Full movement (`WASD`/Arrows, `Q/E` strafe), roaming Cyber-Imp AI enemies, hitscan pump-action shotgun with muzzle flash/recoil, ammo drops, and `IDDQD` God Mode toggle.
* **🚀 3D Pinball — Space Cadet (`win-pinball`):**
  * 60 FPS physics table with glowing neon hyperspace bumpers (`150–500 pts`), gravity/restitution ball physics, spring plunger (`SPACE`), left/right flippers (`Z` and `/` keys or mouse buttons), and arcade SFX.
* **🃏 Solitaire (`win-solitaire`):**
  * Full Klondike 7-column tableau, stock/waste draw pile, 4 suit foundations, click-to-auto-move stacking, and the iconic **bouncing card waterfall** win animation.
* **💣 Minesweeper (`win-mines`):**
  * 9x9 grid, 10 mines, recursive flood-fill zero clearing, right-click red flags (`🚩`), LED counters, and reactive smiley button (`🙂 / 😵 / 😎`).

---

### 🗑️ 7. Virtual SD File System (`D:\`), Functional Recycle Bin, Screensavers & BSOD
* **Virtual SD Card Explorer (`My Computer` — `win-mycomp`):**
  * Create log files, open `.TXT`/`.SYS` in Notepad or `.DOC` in Word, upload real files from your PC, or download virtual files to your hard drive.
* **Functional Recycle Bin (`win-recycle`):**
  * Deleting files in `My Computer` moves them to the **Recycle Bin** with deletion timestamps.
  * Desktop Recycle Bin SVG icon dynamically changes to show crumpled paper balls when full!
  * Supports **Restore Selected**, **Restore All**, and **Empty Recycle Bin** with a **synthesized WebAudio paper-crumple noise burst**.
* **6 Classic Windows Screensavers (`win-display`):**
  * Includes live miniature CRT monitor preview + fullscreen idle/manual mode for: **3D Pipes**, **Starfield Simulation**, **Mystify Your Mind**, **3D Maze (Autonomous Raycaster)**, **Beziers**, and **Windows XP Floating 3D Flag**.
* **Authentic Random BSOD Fault Injector (`#bsod-overlay`):**
  * Configurable frequency in Control Panel (*Disabled, Rare ~1.5%/30s, Unstable, or Chaotic*).
  * Displays authentic stop codes, hex parameters, driver addresses, and a `0% -> 100%` physical memory dump counter. Press **`ESC`** to resume your desktop without losing work, or **`ENTER`** to reboot.

---

### 🔌 8. Hardware ESP32-S3 Firmware (`Build 3.3`) & Serial/UDP Bridges
* **Zero-Dependency 5x7 Procedural Glyph Engine:** Renders crisp ASCII text on `TFT_eSPI` using geometric segment bitmasks—never breaks regardless of `User_Setup.h` font configurations.
* **Isolated Dual-SPI Bus Architecture:**
  * `HSPI` dedicated to XPT2046 Touch (`SCK:25, MISO:39, MOSI:32, CS:33`) with 2-point inset linear extrapolation calibration saved to NVS `Preferences`.
  * `VSPI` dedicated to MicroSD Card (`SCK:18, MISO:19, MOSI:23, CS:5`) with an automatic hardware mute guard on `AUDIO_EN (GPIO 4)` so `GPIO 23` MOSI traffic never screeches through the `SC8002B` speaker amplifier.
* **Live Wi-Fi UDP Port `4444` & WebSerial Bridge:**
  * Chat and trade window-shaking nudges between ESP32 boards and the Linux `msn_vfd_bridge.py` client, or connect the Web OS directly to the ESP32 over USB via the **WebSerial API** inside `HyperTerminal (COM1)`.

---

## 🛠️ Quick Start Guide

### 1. Run the Web OS (Zero Install)
Simply open `xp_wonderland_os_v7.html` in any modern web browser (Firefox, Chromium, Brave, Edge):
```bash
firefox xp_wonderland_os_v7.html
# Or for WebSerial USB hardware access:
chromium xp_wonderland_os_v7.html

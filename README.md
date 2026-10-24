<div align="center">

<img src="assets/banner.svg" alt="ASNIPP - The Windows Snipping Tool Killer" width="100%">

<br><br>

<a href="https://github.com/Akhouri-Systems/ASNIPP/releases/download/v1.0.0/ASNIPP_v1.zip"><img src="assets/download.svg" alt="Download ASNIPP for Windows" width="420"></a>

<sub>Direct download &nbsp;·&nbsp; no installer &nbsp;·&nbsp; extract the zip and run <code>ASNIPP_v1.exe</code></sub>

<br><br>

![Version](https://img.shields.io/badge/version-1.0.0-30d158?style=for-the-badge)
&nbsp;
![Platform](https://img.shields.io/badge/platform-Windows_10_/_11-0078d4?style=for-the-badge&logo=windows&logoColor=white)

![Python](https://img.shields.io/badge/Python-3.12-3776ab?style=flat-square&logo=python&logoColor=white)
![PyQt6](https://img.shields.io/badge/UI-PyQt6-41cd52?style=flat-square&logo=qt&logoColor=white)
![Compiled with Nuitka](https://img.shields.io/badge/compiled_with-Nuitka-ff9f0a?style=flat-square)

<br>

**[Download](https://github.com/Akhouri-Systems/ASNIPP/releases/download/v1.0.0/ASNIPP_v1.zip)** &nbsp;·&nbsp;
**[Features](#-features)** &nbsp;·&nbsp;
**[Shortcuts](#-keyboard-shortcuts)** &nbsp;·&nbsp;
**[Run from source](#-run-from-source)** &nbsp;·&nbsp;
**[FAQ](#-faq)**

</div>

<br>

---

## ✨ Features

<table>
<tr>
<td width="50%" valign="top">

### 📸 Capture
- Region **photo**, **video** or full **screen**
- Frozen-screen selection, like a real snipping tool
- Auto-saved **and** copied to your clipboard
- 📌 **Pin to screen**: floating, always-on-top screenshots

### 🎥 Record
- Smooth 30 FPS screen recording
- 🔊 **System audio** + 🎙 **microphone**, with live level meters
- Pause, restart and stop from the island
- The ASNIPP UI never appears in your recording

### ✏️ Live drawing
- Pen, highlighter, arrow, rectangle, circle
- Laser pointer and eraser
- Auto-fade ink for presentations
- Works **while recording**: your drawing goes into the video

</td>
<td width="50%" valign="top">

### 🖌 Editor
- Pen, highlighter, arrows, shapes, text
- Pixelate to hide sensitive info
- Crop with a visible grid and handles
- Aspect ratios: 16:9, 9:16, 1:1, 4:5, 4:3
- 🔍 **OCR**: extract text from any image

### 🎞 Video tools
- Trim, split and join clips
- Looks and filters, brightness, contrast, saturation
- Speed, reverse, rotate, flip, fade in/out
- Export **MP4, AVI, WMV, MOV, GIF**

### 🧰 Extras
- 🎨 **Color picker** with a pixel magnifier
- 📏 **Pixel ruler** with distance and angle
- 📚 **Library** of your last 50 captures (favorites are kept forever)

</td>
</tr>
</table>

---

## ⌨️ Keyboard shortcuts

| Shortcut | Action |
|---|---|
| <kbd>Win</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> &nbsp;/&nbsp; <kbd>PrtScn</kbd> &nbsp;/&nbsp; <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>S</kbd> | 📸 Photo capture |
| <kbd>Win</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> | 🎥 Start video, press again to stop |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>D</kbd> | ✏️ Live screen drawing |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>P</kbd> | 🎨 Color picker + pixel ruler |
| <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>L</kbd> | 📚 Capture library |
| <kbd>Esc</kbd> | Cancel / close |

> [!NOTE]
> On first launch ASNIPP takes over **Win+Shift+S**, **Win+Shift+R** and **PrintScreen** from Windows Snipping Tool.
> You can hand them back at any time: right-click the tray icon and untick **“Use Win+Shift+S for ASNIPP”**.

---

## 📥 Install

1. **[Download `ASNIPP_v1.zip`](https://github.com/Akhouri-Systems/ASNIPP/releases/download/v1.0.0/ASNIPP_v1.zip)**
2. Extract it
3. Run **`ASNIPP_v1.exe`**. No installer needed

ASNIPP lives in the **system tray** (the `^` near the clock).
Right-click the icon to turn on **Start with Windows**, which is off by default and starts silently in the tray.

> [!TIP]
> Windows SmartScreen may warn about a new, unsigned app. Click **More info → Run anyway**.

---

## 🛠 Run from source

```bash
pip install PyQt6 mss opencv-python numpy

# audio (optional)
pip install sounddevice PyAudioWPatch imageio-ffmpeg

# GIF export (optional)
pip install pillow

python asnipp.py
```

<details>
<summary><b>Build the .exe with Nuitka</b></summary>

```bat
python -m nuitka --onefile --enable-plugin=pyqt6 --windows-console-mode=disable ^
  --windows-icon-from-ico="asnipp.ico" --company-name="Akhouri Systems" ^
  --product-name="ASNIPP_v1" --file-version=1.0.0 --product-version=1.0.0 ^
  --file-description="Windows Snipping Tool Killer" ^
  --include-package-data=imageio_ffmpeg --include-module=sounddevice ^
  --include-package=pyaudiowpatch --output-filename=ASNIPP_v1.exe ^
  --output-dir=build --assume-yes-for-downloads --remove-output asnipp.py
```

</details>

---

## ❓ FAQ

<details>
<summary><b>Where are my captures saved?</b></summary>
<br>
Photos go to <code>Pictures\ASNIPP Pics</code> and videos to <code>Pictures\ASNIPP Vid</code>. Every capture is also listed in the in-app library.
</details>

<details>
<summary><b>How do I get Windows Snipping Tool back?</b></summary>
<br>
Right-click the ASNIPP tray icon and untick <b>“Use Win+Shift+S for ASNIPP”</b>. Quitting ASNIPP also frees the shortcuts it was holding.
</details>

<details>
<summary><b>There is no sound in my recording</b></summary>
<br>
Turn on 🔊 (system audio) and/or 🎙 (microphone) on the island <i>before</i> you start recording. Check that Windows allows apps to use your microphone.
</details>

<details>
<summary><b>Does ASNIPP record my keystrokes?</b></summary>
<br>
No. To claim Win+Shift+S it watches only the <kbd>S</kbd> and <kbd>R</kbd> keys while <kbd>Win</kbd> and <kbd>Shift</kbd> are held. Nothing is logged, stored or sent anywhere. ASNIPP works fully offline.
</details>

---

<div align="center">

Made with ❤️ by **Akhouri Systems**

⭐ If ASNIPP made your day easier, star the repo!

</div>

# 👻 Ghosty — Desktop AI Assistant

Ghosty is a floating, always-on-top desktop AI assistant powered by local LLMs (Ollama), built with PySide6 and designed for real-time interaction, personality, and persistent presence.

This is not just a chatbot — it’s a desktop entity.

<img width="855" height="553" alt="Screenshot 2026-03-26 at 11 36 20 AM" src="https://github.com/user-attachments/assets/b500abca-e561-4f23-bd65-c1efe0804f4b" />

---
## ✨ Core Features

- Animated ghost sprite (procedural, no external assets)
- Always-on-top overlay (macOS native window level control)
- Local LLM integration via Ollama
- Streaming responses (real-time typing)
- Floating speech bubble UI
- Frosted-glass input bar with shimmer animation
- Reminder + inactivity behavior system
- Native macOS-style settings panel
- Fully self-contained runtime

---

## 🧠 Architecture

GhostApp (controller)

├── GhostOverlay (sprite + animation + window control)

├── BubbleOverlay (speech UI)

├── InputOverlay (input UI)

├── LLMWorker (threaded Ollama client)

├── SettingsDialog (config UI)

└── GhostStats (XP system)

---

## ⚙️ Requirements

pip install PySide6 Pillow requests

Optional:
pip install pynput

---

## 🚀 Run

python agentGHOSTX4final.py

Ghost will:
- auto-launch Ollama (if installed)
- generate sprite assets
- appear as a floating overlay

---

## 🧠 LLM Integration

Uses:
POST /api/generate

Supports:
- streaming responses
- temperature control
- token limits
- system prompt injection

Default model:
qwen2.5:latest

Quick-start model:
qwen3:0.6b (~500MB)

---

## 🖥 macOS Behavior

Ghost uses native NSWindow controls:

- setLevel(1000)
- orderFrontRegardless
- setHidesOnDeactivate(False)

This ensures:
- always visible
- above fullscreen apps
- persists across spaces

---

## 🎮 Interaction

Type naturally in the input bar.

Examples:
hello
tell me something weird
/boo

---

## 👻 Behavior System

BOO logic:
- /boo → immediate
- inactivity → only when app inactive
- never interrupts responses

---

## 🎬 Animation System

- Procedural sprite generation (Pillow)
- Idle + directional movement
- Bobbing + tilt physics
- Smooth shrink-to-corner
- 60 FPS UI loop

---

## 🧊 UI Design

Input Overlay:
- frosted glass effect
- animated shimmer
- custom Qt rendering

Bubble Overlay:
- auto-wrap text
- click to dismiss
- anchored to ghost

---

## ⚙️ Settings

Saved to:
ghost_settings.json

Includes:
- LLM config
- opacity controls
- always-on-top toggle
- BOO behavior
- shrink behavior

---

## 📁 Runtime Files

ghost_settings.json
ghost_assets/

Fully portable — no external dependencies beyond Python libs.

---

## 🧩 Extending Ghost

Add commands in controller:

if text.startswith("/yourcommand"):
    ...

---

## ⚠️ Known Issues

- Ollama must be installed locally
- Large models may slow responses
- macOS window layering depends on OS behavior

---

## 🔮 Roadmap

- voice input (speech-to-text)
- plugin system
- persistent memory
- multi-agent modes
- mobile companion

---

## 👤 Author
Tidewater Studios / THNDRTHF

---

## 💡 Philosophy

Ghost is:
- local-first
- always present
- lightweight but expressive

This is the foundation of a desktop agent system.

QUICK ERROR FIXES: 
Open settings and set your model and save. qwen3:0.6b is an easy choice, but feel free to experiment. It seems to work with other models well. 

IF YOU GET A "NOT OPENED" / WARNING MESSAGE:

<img width="276" height="299" alt="Screenshot 2026-03-23 at 10 12 00 AM" src="https://github.com/user-attachments/assets/3af5decd-29b5-4598-a8fe-18f6b086e07c" />

GO TO PRIVACY AND SECURITY AND CLICK "OPEN ANYWAY":

<img width="475" height="181" alt="Screenshot 2026-03-23 at 10 12 13 AM" src="https://github.com/user-attachments/assets/05d09187-3bd3-4212-9ea9-70e5c99ca1f7" />

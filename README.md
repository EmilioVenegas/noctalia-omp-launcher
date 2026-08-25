# Noctalia OMP Launcher Plugin

An interactive, native bar launcher button for **[Oh My Pi (`omp`)](https://github.com/can1357/oh-my-pi)** built for the [Noctalia](https://noctalia.dev) desktop shell.

Features a vector $\pi$ logo with a diagonal magenta-to-cyan gradient, real-time background session detection, recent project tracking, and one-click session resume.

---

## ✨ Features

- **Geometric $\boldsymbol{\pi}$ Logo**: Vector-rendered $\pi$ glyph styled with a diagonal hot pink/magenta (`#F43F5E`) to sky blue (`#38BDF8`) linear gradient.
- **Active Session Indicator**: Real-time status dot (`#38BDF8`) that lights up whenever an `omp` session is running in the background.
- **Recent Project Intelligence**: Scans `~/.omp/agent/sessions/` to discover your most recently touched projects with relative timestamps.
- **Dynamic Context Tooltip**: Hovering over the button displays active session counts, the latest project path, and quick shortcuts.

---

## 🖱️ Click Actions

| Gesture | Action | Command Triggered |
|---|---|---|
| **Left Click** | Open interactive project picker via `vicinae dmenu` | `omp-launch` |
| **Middle Click** | Resume the most recent project session immediately | `omp-launch --continue` |
| **Right Click** | Launch a new OMP session in `$HOME` | `omp-launch --home` (`omp --allow-home`) |

---

## 📦 Installation

### Option 1: Via Noctalia CLI
```bash
noctalia msg plugins source add emiliovenegas git https://github.com/EmilioVenegas/noctalia-omp-launcher
noctalia msg plugins enable emiliovenegas/omp-launcher
```

### Option 2: Local Installation
Clone directly into your local Noctalia plugins directory:
```bash
git clone https://github.com/EmilioVenegas/noctalia-omp-launcher.git ~/.config/noctalia/plugins-local/omp-launcher
noctalia msg plugins enable emilio/omp-launcher
```

---

## ⚙️ Configuration

Place `omp-launcher` in your bar layout inside `~/.config/noctalia/config.toml` or `~/.local/state/noctalia/settings.toml`:

```toml
[bar.default]
center = [ "workspaces", "clock", "omp" ]

[widget.omp]
capsule = true
type = "emiliovenegas/omp-launcher:omp-launcher"
```

Then reload Noctalia:
```bash
noctalia msg config-reload
```

---

## 🛠️ Companion Script (`omp-launch`)

The included companion script `bin/omp-launch` manages project resolution and terminal invocation:
- Copy `bin/omp-launch` to your `$PATH` (e.g. `~/.local/bin/omp-launch`).
- Ensure it is executable: `chmod +x ~/.local/bin/omp-launch`.

---

## 📄 License

MIT License © 2026 Emilio Venegas

# ⏳ Hourglass

A modern, highly customizable countdown timer for Windows, built with C# and WPF. Hourglass is designed for power users, developers, and anyone who needs precise, flexible, and beautiful timer functionality.

---

## 🚀 Features

- **Natural Language Input**: Start timers using intuitive phrases (e.g., `5 minutes`, `2:30 pm`, `Friday`).
- **Multiple Timer Windows**: Run and manage several timers simultaneously.
- **Themes & Colors**: Choose from built-in light/dark themes or create your own.
- **Taskbar Progress**: Visual progress in the Windows taskbar.
- **Notification Area Icon**: Optional tray icon for quick access.
- **Sound & Alerts**: Play custom sounds, loop on expiration, pop up or close windows, or even shut down your PC.
- **Always-on-Top & Full-Screen**: Keep timers visible or go distraction-free.
- **Persistence**: Save and restore timers across sessions.
- **Command-Line Control**: Launch and configure timers with rich CLI options.
- **Extensible**: Clean architecture for adding new features, themes, or integrations.

---

## 🖥️ Quick Start

1. **Build**: Open `Hourglass.sln` in Visual Studio 2013+ and build the solution.
2. **Run**: Launch the app (`Hourglass.exe`).
3. **Start a Timer**: Enter a time (e.g., `10 minutes`, `3:00 pm`, `Friday`) and hit Start.

---

## 📝 Usage Examples

```shell
Hourglass.exe [OPTIONS] [<input>]
```

**Inputs:**
- `5` → 5 minutes
- `5:30` → 5 minutes 30 seconds
- `7:30:00` → 7 hours 30 minutes
- `01/01/2025` → until January 1, 2025
- `2 pm` → until 2 pm
- `Friday` → until midnight Friday

**Options:**
- `--title <title>`: Set timer title
- `--always-on-top on|off`: Keep window on top
- `--full-screen on|off`: Full-screen mode
- `--theme <theme>`: Choose theme (e.g., `red-dark`)
- `--sound <sound>`: Play sound on expiration
- `--loop-timer on|off`: Repeat timer
- `--show-progress-in-taskbar on|off`: Taskbar progress
- `--show-in-notification-area on|off`: Tray icon
- ...and many more! See [`Hourglass/Resources/Usage.txt`](Hourglass/Resources/Usage.txt) for full CLI reference.

---

## 🛠️ Architecture Overview

- **Hourglass/**: Main app logic, UI, and core classes
  - `Timing/Timer.cs`: Countdown timer logic
  - `Timing/TimerOptions.cs`: Configurable options for timers
  - `Timing/Theme.cs`: Theme and color management
  - `Managers/`: Singleton managers for timers, options, notifications, etc.
  - `Windows/TimerWindow.xaml(.cs)`: Main timer window UI and event handling
  - `Parsing/`: Natural language date/time parsing
  - `Resources/`: Icons, sounds, usage docs
- **Hourglass.Test/**: Unit tests for core parsing and timer logic
- **Hourglass.Setup/`, `Hourglass.Bundle/`: Installer and bundle projects (WiX)

---

## 👩‍💻 Developer Guide

### Building
- Requires **.NET Framework 4.8** and **Visual Studio 2013+**
- Open `Hourglass.sln` and build all projects
- Main output: `Hourglass/bin/Release/Hourglass.exe`

### Extending
- **Themes**: Add new themes via `ThemeManager` or user config
- **Sounds**: Place `.wav` files in `Resources/` and reference in options
- **Parsing**: Extend natural language support in `Parsing/`
- **Managers**: Add new singleton managers for global features

### Key Classes
- `TimerManager`: Handles multiple timers, persistence
- `TimerOptionsManager`: Manages user and CLI options
- `TimerWindow`: UI logic, event handling, animations
- `ThemeManager`: Built-in and custom themes

### Testing
- Unit tests in `Hourglass.Test/`
- Run via Visual Studio Test Explorer

---

## 📦 Packaging & Distribution
- WiX installer projects: `Hourglass.Setup/`, `Hourglass.Bundle/`
- Build with Visual Studio to generate `.msi` installers

---

## 📚 Resources
- [Usage.txt](Hourglass/Resources/Usage.txt): Full CLI and feature documentation
- [License.txt](Hourglass/Resources/License.txt): MIT License
- [AppIcon.ico](Hourglass/Resources/AppIcon.ico): App icon

---

## 📝 License

This project is licensed under the MIT License. See [`LICENSE.md`](LICENSE.md) for details.

---

## 🤝 Contributing

Pull requests, issues, and feature suggestions are welcome! Please follow standard C# and WPF best practices.

---

## 🙏 Credits

Originally created by Chris Dziemborowicz. Maintained by the open-source community.

```markdown
# x11-selection-logger

A lightweight C++ daemon that captures X11 text selection and saves it to dated log files with a single `Ctrl + M` keystroke.

## ✨ Features
- **Instant Capture**: Save mouse-selected text (Primary Selection) without manual copy-pasting.
- **Smart Organization**: Automatically categorizes logs into `~/memories/Year/Month.txt`.
- **Low Overhead**: A minimal background process designed for X11 environments.
- **Timestamped**: Every entry is recorded with a precise timestamp for later reference.

## 📋 Prerequisites
You need the X11 development libraries and `xclip` installed on your system.
```bash
sudo apt update
sudo apt install libx11-dev xclip
```

## 🛠 Installation & Build
Clone this repository and compile the source code using `g++`.
```bash
g++ -o x11-selection-logger memory_daemon.cpp -lX11
```

## 🚀 Usage
1. Start the daemon in the background:
   ```bash
   ./x11-selection-logger &
   ```
2. Highlight any text with your mouse.
3. Press **`Ctrl + M`**.
4. Your snippet is now saved in `~/memories/2026/03.txt` (example path).

## 📂 Directory Structure
```text
/home/USER/memories/
└── 2026/
    ├── 03.txt  <-- New snippets are appended here
    └── 04.txt
```

## 📝 Log Format
Entries are saved in the following format:
```text
--- Mon Mar 30 12:59:50 2026 ---
Your captured text selection appears here.
```

## 💡 Pro Tip
To run this tool automatically on startup, add the binary path to your `.xinitrc` or your desktop environment's "Startup Applications" list.

## License
MIT License
```

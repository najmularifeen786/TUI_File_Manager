# 📂 File Ranger

**A high-performance terminal file manager built with C++ and Python.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![C++](https://img.shields.io/badge/C%2B%2B-17-blue)](https://isocpp.org/)
[![CMake](https://img.shields.io/badge/CMake-3.15%2B-blue)](https://cmake.org/)
[![Build](https://img.shields.io/badge/Build-Passing-brightgreen)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey)]()

File Ranger is a terminal-based file manager developed as a **Data Structures & Algorithms semester project** at COMSATS University Lahore. It pairs a high-performance **C++ backend** with a modern **Python Textual** interface, demonstrating real-world application of custom data structures including an N-ary Tree, Merge Sort, and a Dual-Stack navigation system.

![File Ranger](./assets/image.png)

## 📽️ Demo Video

> Watch the full project walkthrough:

**[▶ Click here to watch the demo](https://youtu.be/Wc0XyFCvwr4)**

---

## Download

Pre-built standalone executables are available in the [Releases](https://github.com/najmularifeen786/TUI_File_Manager/releases) section.

1. Go to [Releases](https://github.com/najmularifeen786/TUI_File_Manager/releases).
2. Download the latest `file_ranger.exe` (Windows) or `file_ranger` (Linux/macOS).
3. Run the executable — no installation required.

Developers who want to build from source can follow the [Installation](#installation) guide below.

---

## ✨ Features

### File Operations
- Create, rename, delete, copy, and paste files and directories
- Recursive directory traversal with no depth limit
- Automatic duplicate name prevention with error handling
- Real-time binary file size display

### Navigation
- Browser-style back/forward history via a dual-stack architecture
- Three-pane layout: directory tree, file list, and live preview
- Vim-style keyboard shortcuts and full mouse support

### Interface
- Modern TUI built with Python Textual and Rich
- Multiple color themes, color-coded items, and file icons
- Command palette for quick access to actions

### Performance
- C++ backend with custom N-ary Tree for filesystem representation
- Manual Merge Sort — O(N log N) guaranteed, no STL sort dependency
- O(1) navigation operations via the dual-stack system
- Smart pointer memory management throughout the C++ codebase
- Zero-copy data transfer between C++ and Python via pybind11

---

## 🎯 System Requirements

- **Operating System**: Windows, Linux, or macOS
- **Python**: 3.8 or higher
- **CMake**: 3.15 or higher - [Download CMake](https://cmake.org/download/)
- **C++ Compiler**: 
  - Windows: Visual Studio Build Tools with C++ support
  - Linux: GCC 7+ or Clang 5+
  - macOS: Xcode Command Line Tools


### Prerequisites

Before installation, ensure you have:

1. **CMake** installed and accessible from command line
   - Verify with: `cmake --version`

2. **C++ Compiler and Build Tools**
   - **Windows**: Visual Studio Build Tools with "Desktop development with C++" workload
   - **Linux**: `sudo apt-get install build-essential` (Debian/Ubuntu) or equivalent
   - **macOS**: `xcode-select --install`

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/najmularifeen786/TUI_File_Manager.git
cd TUI_File_Manager
```

### 2. Create a Virtual Environment

**Linux / macOS:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows:**
```powershell
python -m venv venv
.\venv\Scripts\activate
```

> If PowerShell blocks activation, run: `Set-ExecutionPolicy Unrestricted -Scope Process`

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Build the Application

This single command compiles the C++ backend, creates the Python extension, and packages the project with PyInstaller:

```bash
python build_release.py
```

On success, the executable will be available at:

```
dist/
└── file_ranger.exe   # Windows
└── file_ranger       # Linux / macOS
```

---

## Usage

### Running the Executable

**Windows:**
```
dist\file_ranger.exe
```

**Linux / macOS:**
```bash
./dist/file_ranger
```

### Running from Source (Developers)

```bash
python ui/app.py
```

---

## 🖥️ Usage

Launch File Ranger from the project directory:
```bash
python -m file_ranger
```

---

## ⌨️ Keyboard Shortcuts

| Key                 | Action                           |
|---------------------|----------------------------------|
| `j` / `↓`           | Move down                        |
| `k` / `↑`           | Move up                          |
| `h` / `←`           | Go to parent directory / Go back |
| `l` / `→` / `Enter` | Enter directory / Go forward     |
| `L`                 | Go forward in history            |
| `n`                 | Create new file                  |
| `N`                 | Create new directory             |
| `r`                 | Rename file/directory            |
| `d`                 | Delete file/directory            |
| `c`                 | Copy file/directory              |
| `p`                 | Paste copied item                |
| `q`                 | Quit application                 |
| `Ctrl + P`          | Command palette                  |
| **Mouse**           | Click to navigate and select     |

---

## 🏗️ Architecture & Data Structures

### Backend (C++)

| Structure | Purpose |
|-----------|---------|
| N-ary Tree | Represents the filesystem hierarchy |
| Merge Sort | Sorts directory entries in O(N log N) |
| Dual-Stack ADT | Powers forward/backward navigation in O(1) |
| Recursive Algorithms | Directory traversal and file operations |
| Smart Pointers | Memory-safe ownership throughout the codebase |

### Frontend (Python)

Built with **Textual** and **Rich**. The UI is event-driven, supporting both keyboard and mouse input, with a live-updating three-pane layout and a pluggable theme system.

### Integration

**pybind11** provides type-safe C++ to Python bindings, with a **CMake** build system for cross-platform compilation. Data is transferred between layers with zero-copy semantics for optimal performance.

---

## 📁 Project Structure
```
file_ranger/
├── backend/              # C++ backend implementation
│   ├── include/          # Header files
│   │   ├── tree.hpp      # N-ary tree structure
│   │   ├── stack.hpp     # Custom stack ADT
│   │   └── file_ops.hpp  # File operations
│   └── src/              # Implementation files
│       ├── tree.cpp
│       ├── stack.cpp
│       └── file_ops.cpp
├── bindings/             # pybind11 bindings
│   ├── bindings.cpp      # C++ to Python interface
│   └── build/            # Built backend module
├── ui/                   # Python UI components
│   ├── app.py            # Main application
│   ├── themes.py         # Theme definitions
│   └── components/       # UI widgets
├── requirements.txt      # Python dependencies
├── CMakeLists.txt        # Build configuration
└── build_release.py      # Build script
```

---

## 🛠️ Troubleshooting

### Build Issues

**Error: 'cmake' is not recognized**
- **Solution**: Ensure CMake is installed and added to system PATH. Verify with `cmake --version`

**Error: C++ compiler not found**
- **Linux/macOS**: Install build tools (`build-essential` or Xcode Command Line Tools)
- **Windows**: Install Visual Studio Build Tools with C++ workload

**Error: No module named 'backend'**
- **Solution**: The C++ backend build failed. Run `python build_release.py` and check for errors

### Runtime Issues

**Poor visual display**
- **Solution**: Use a modern terminal (Windows Terminal, iTerm2, or Alacritty)
- Install a Nerd Font for optimal icon display
- Ensure terminal supports 256 colors or true color

**Performance issues with large directories**
- **Solution**: The merge sort algorithm handles large datasets efficiently. Check system resources

**Navigation history not working**
- **Solution**: The dual-stack system should handle unlimited history. Report if issues persist

### Platform-Specific Notes

**Linux**: Ensure you have `libstdc++` development packages installed

**macOS**: If build fails, try: `export MACOSX_DEPLOYMENT_TARGET=10.15`

**Windows**: Use Developer Command Prompt for Visual Studio if standard terminal fails

---

## 🎨 Customization

### Themes
Access multiple built-in themes through the command palette (`Ctrl + P`) or modify theme files in `ui/themes.py`

### Key Bindings
Customize keyboard shortcuts in `ui/app.py` - look for the key binding configuration section

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow C++17 standards for backend code
- Use type hints in Python code
- Maintain O(N log N) or better complexity for algorithms
- Add tests for new features
- Update documentation for user-facing changes

---

## 📊 Performance Benchmarks

| Operation | Complexity |
|-----------|------------|
| Directory traversal | O(N) |
| Sorting (Merge Sort) | O(N log N) |
| Navigation (back/forward) | O(1) |
| Copy / Delete | Recursive |

---

## 📝 License

This project is open source and available under the  [MIT License](LICENSE).

---

## 🙏 Acknowledgments

Built with cutting-edge technologies:
- **C++ (C++17)** - High-performance backend with custom data structures
- **Python** - Elegant UI and application logic
- **Textual** - Modern terminal UI framework
- **Rich** - Beautiful terminal formatting and rendering
- **pybind11** - Seamless C++/Python integration
- **CMake** - Cross-platform build system

---

## 👥 Authors

### Najmul Arifeen
**Data Structures**
* najmularifeen786@gmail.com
* **[GitHub](https://github.com/najmularifeen786)**
* **[LinkedIn](https://www.linkedin.com/in/najmularifeen/)**

### Waqar Ahmad
**Frontend UI, Backend Architecture & Integration**
* codewithwaqarahmad@gmail.com
* **[GitHub](https://github.com/WaqarAhmad321)**
* **[LinkedIn](https://www.linkedin.com/in/waqar-ahmad321/)**

---

## 🌟 Star History

If you find File Ranger useful, please consider giving it a star on GitHub!

---

*Built as a Data Structures & Algorithms semester project at COMSATS University Lahore.*
**Built as a DSA semester project at COMSATS University Lahore** - Demonstrating that data structures and algorithms aren't just theory, but the foundation of efficient, real-world systems.

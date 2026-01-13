# 📂 File Ranger - High-Performance TUI File Manager

A high-performance terminal-based file manager built with a hybrid architecture that combines the speed of **C++** for backend operations with the modern UI capabilities of **Python (Textual)**. File Ranger delivers a seamless, efficient file management experience directly in your terminal with advanced data structures and algorithms at its core.

![File Ranger Demo](./assets/image.png)

---

## 📋 Table of Contents

- [Features](#-features)
- [System Requirements](#-system-requirements)
- [Installation](#-installation)
- [Usage](#️-usage)
- [Keyboard Shortcuts](#️-keyboard-shortcuts)
- [Architecture & Data Structures](#️-architecture--data-structures)
- [Project Structure](#-project-structure)
- [Troubleshooting](#️-troubleshooting)
- [Customization](#-customization)
- [Contributing](#-contributing)
- [Performance Benchmarks](#-performance-benchmarks)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)
- [Authors](#-authors)
---

## ✨ Features

### Core Functionality
- **Lightning-Fast Performance**: C++ backend with custom N-ary tree structure for filesystem hierarchy
- **Smart Sorting**: Manual merge sort implementation with guaranteed O(N log N) performance
- **Browser-Style Navigation**: Dual-stack architecture enabling forward/backward navigation with O(1) operations
- **Full File Operations**: Create, rename, delete, copy, paste files and directories with recursive algorithms
- **Binary Size Display**: Real-time file and directory size calculation in binary format
- **Duplicate Name Prevention**: Intelligent validation system that prevents naming conflicts with error handling

### User Interface
- **Modern TUI**: Beautiful, responsive terminal interface built with Textual and Rich
- **Three-Pane Layout**: Organized view with directory tree, file list, and real-time preview
- **Multiple Themes**: Customizable color schemes to personalize your experience
- **Color-Coded Items**: Visual distinction between files (white) and folders (blue)
- **Dual Input Support**: Full keyboard shortcuts (Vim-style) and mouse navigation
- **File Icons**: Enhanced visual representation with icon support
- **Unlimited Depth**: Handle any directory depth without stack overflow

### Technical Highlights
- **Zero-Copy Architecture**: Efficient data transfer between C++ and Python
- **Memory-Safe Design**: Smart pointers throughout C++ codebase
- **Custom Stack ADT**: Complete stack implementation for navigation system
- **Cross-Language Integration**: Seamless C++/Python binding via pybind11

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
cd file_ranger
```

### 2. Create Virtual Environment

**Linux/macOS:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows:**
```powershell
python -m venv venv
.\venv\Scripts\activate
```

**Note for Windows**: If you encounter a security error, run:
```powershell
Set-ExecutionPolicy Unrestricted -Scope Process
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Build the C++ Backend

This compiles the C++ source code into a Python extension module:
```bash
python build_release.py
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
- **N-ary Tree**: Custom implementation for filesystem hierarchy representation
- **Merge Sort**: Manual O(N log N) sorting without STL dependencies
- **Dual-Stack System**: Efficient forward/backward navigation with O(1) operations
- **Custom Stack ADT**: Full-featured stack implementation
- **Recursive Algorithms**: Efficient directory traversal and manipulation

### Frontend (Python)
- **Textual Framework**: Modern TUI with rich components
- **Event-Driven Architecture**: Responsive keyboard and mouse handling
- **Theme System**: Multiple customizable color schemes
- **Real-Time Preview**: Dynamic content updates

### Integration Layer
- **pybind11**: Type-safe C++ to Python bindings
- **CMake Build System**: Cross-platform compilation
- **Zero-Copy Data Transfer**: Optimal performance between languages

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

- **Directory Loading**: O(N) where N is number of items
- **Sorting**: O(N log N) guaranteed with merge sort
- **Navigation**: O(1) with dual-stack architecture
- **Memory**: Efficient with smart pointers and zero-copy transfers

---

## 📝 License

This project is open source and available under the MIT License.

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
**Backend Architecture & Data Structures**
* najmularifeen786@gmail.com
* **[GitHub](https://github.com/najmularifeen786)**
* **[LinkedIn](https://www.linkedin.com/in/najmularifeen/)**

### Waqar Ahmad
**Frontend UI & Integration - Project Lead**
* codewithwaqarahmad@gmail.com
* **[GitHub](https://github.com/WaqarAhmad321)**
* **[LinkedIn](https://www.linkedin.com/in/waqar-ahmad321/)**

---

## 🌟 Star History

If you find File Ranger useful, please consider giving it a star on GitHub!

---

**Built as a DSA semester project at COMSATS University Lahore** - Demonstrating that data structures and algorithms aren't just theory, but the foundation of efficient, real-world systems.

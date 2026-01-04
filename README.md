# 📂 File Ranger - TUI File Manager

A high-performance, terminal-based file manager for Windows built with a hybrid architecture. This project combines the speed of **C++** for backend file operations with the modern, rich user interface capabilities of **Python (Textual)** to deliver a seamless file management experience directly in your terminal.

![File Ranger Demo](./assets/image.png)

## ✨ Features

- **High Performance**: C++ backend ensures lightning-fast file system operations
- **Modern TUI**: Beautiful, mouse-supported terminal interface built with Textual and Rich
- **Full File Operations**: Create, rename, delete, copy, and paste files and directories
- **Vim-like Navigation**: Efficient keyboard shortcuts for power users
- **Directory Preview**: Real-time preview of directory contents in the sidebar
- **Intuitive Interface**: Clean, organized layout with file icons and status indicators

## 🎯 System Requirements

- Windows 10/11
- Python 3.8 or higher
- CMake 3.15+: [Download CMake](https://cmake.org/download/)
- Visual Studio Build Tools: [Download Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

### Important Prerequisites

Before installation, ensure you have:

1. **CMake** installed and added to system PATH
   - During CMake installation, select "Add CMake to the system PATH for all users"

2. **Visual Studio Build Tools** with C++ support
   - Install the "Desktop development with C++" workload
   - This includes the C++ compiler and build tools required for the project

## 🚀 Installation

Follow these steps to set up File Ranger on your Windows system:

### 1. Clone the Repository

```powershell
git clone https://github.com/WaqarAhmad321/file_ranger.git
cd file_ranger
```

### 2. Create Virtual Environment

```powershell
python -m venv venv
.\venv\Scripts\activate
```

**Note**: If you encounter a security error, run:
```powershell
Set-ExecutionPolicy Unrestricted -Scope Process
```

### 3. Install Dependencies

```powershell
pip install -r requirements.txt
```

### 4. Build the C++ Backend

This compiles the C++ source code into a Python extension module:

```powershell
python build_release.py
```

## 🖥️ Usage

Launch File Ranger from the project directory:

```powershell
python -m file_ranger
```

## ⌨️ Keyboard Shortcuts

| Key                 | Action                           |
|---------------------|----------------------------------|
| `j` / `↓`           | Move down                        |
| `k` / `↑`           | Move up                          |
| `h` / `←`           | Go to parent directory / Go back |
| `l` / `→` / `Enter` | Enter directory                  |
| `L`                 | Go forward                       |
| `n`                 | Create new file                  |
| `N`                 | Create new directory             |
| `r`                 | Rename file/directory            |
| `d`                 | Delete file/directory            |
| `c`                 | Copy file/directory              |
| `p`                 | Paste copied item                |
| `q`                 | Quit application                 |

## 📁 Project Structure

```
file_ranger/
├── backend/           # C++ backend code
│   ├── include/       # Header files
│   └── src/           # Implementation files
├── bindings/          # pybind11 bindings
│   └── build/         # Built backend module
├── ui/                # Python UI components
│   └── app.py         # Main application
├── requirements.txt   # Python dependencies
└── build_release.py   # Build script
```

## 🛠️ Troubleshooting

### Error: 'cmake' is not recognized

**Solution**: CMake is not in your system PATH. Reinstall CMake and ensure you check the box "Add CMake to the system PATH for all users", or manually add it to your Environment Variables.

### Error: 'nmake' failed or CMAKE_CXX_COMPILER not set

**Solution**: Visual Studio Build Tools are not installed or incomplete. Install the **"Desktop development with C++"** workload from the Visual Studio Build Tools installer.

### Error: No module named 'backend'

**Solution**: The C++ backend wasn't built successfully. Ensure you've run `python build_release.py` and check for any error messages during the build process.

### Virtual Environment Activation Issues

**Solution**: If PowerShell blocks script execution, run:
```powershell
Set-ExecutionPolicy Unrestricted -Scope Process
```

## Tips for Best Experience

- Use a terminal with Unicode support (Windows Terminal recommended)
- Install a Nerd Font for optimal icon display
- Ensure your terminal supports true color for the best visual experience

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the MIT License.

## Acknowledgments

Built with:
- **Python** - High-level UI and application logic
- **C++** - High-performance file system operations
- **Textual** - Modern TUI framework
- **Rich** - Beautiful terminal formatting
- **pybind11** - Seamless Python-C++ integration

---

If you find this project useful, please consider giving it a star on GitHub!

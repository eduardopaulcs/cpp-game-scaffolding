# C++ Game Scaffolding

A modern C++ game development template with SDL3, CMake, and vcpkg integration.

## Features

- **Modern C++20** with CMake build system
- **SDL3** for cross-platform graphics, input, and audio
- **vcpkg** for dependency management

## Quick Start

### 1. Prerequisites

Before you begin, ensure you have the following installed:

1. **Visual Studio**
   - Download from: https://visualstudio.microsoft.com/downloads/
   - During installation, make sure to include the "Desktop development with C++" workload

2. **Visual Studio Build Tools**
   - Download from: https://visualstudio.microsoft.com/downloads/
   - Scroll down to All Downloads > Tools for Visual Studio, and download "Build Tools for Visual Studio"
   - During installation, make sure to include the "Desktop development with C++" workload

2. **vcpkg**
   - First, check if vcpkg is already installed in `C:\vcpkg`. If it is installed you can skip this step
   - If vcpkg is not installed, install it by running these commands in PowerShell:
     ```bash
     git clone --depth 1 --branch 2025.07.25 https://github.com/Microsoft/vcpkg.git C:\vcpkg
     ```
     ```bash
     C:\vcpkg\bootstrap-vcpkg.bat
     ```

3. **MSYS2** (optional, for debugging)
   - Download from: https://www.msys2.org/
   - After installation, open MSYS2 MinGW x64 and run:
     ```bash
     pacman -Syu
     ```
     ```bash
     pacman -S mingw-w64-x86_64-gdb
     ```
   - This is required to use the launch options integrated in the IDE

4. **Recommended Extensions** (VS Code)
   - clangd
   - CMake Tools
   - Hex Editor

### 2. Installation

1. Use the template
   1. Click the "Use this template" button on GitHub
   2. Create a new repository with your project name
   3. Clone your new repository:
      ```bash
      git clone https://github.com/your-username/your-project-name
      ```
      ```bash
      cd your-project-name
      ```

2. Replace the project name with your own
   - Open `CMakeLists.txt` and replace `cpp-game` with your project name
   - Open `vcpkg.json` and replace `cpp-game` with your project name

3. Configure CI/CD (optional)
   - The scaffolding includes a GitHub Actions workflow in `.github/workflows/ci.yml`. This provides automated building and testing on Windows and Ubuntu (GCC and Clang)
   - If you want to use it, keep the `.github` folder. If you don't need CI/CD, you can safely delete the `.github` folder

### 3. Build and Run

**Build your project:**
```bash
scripts/build.bat
```

**Run your project:**
```bash
scripts/run.bat
```

**Clean build (if needed):**
```bash
scripts/build.bat clean
```

### 4. Try your game

You can find your game's executable in `your-project-name\build\win-msvc\Debug\game.exe`

## Project Structure

```
├── assets/              # Textures, sprites, sounds
├── scripts/             # Build and utility scripts
├── src/
│   └── main.cpp         # Application entry point
├── CMakeLists.txt       # CMake configuration
├── CMakePresets.json    # CMake presets
└── vcpkg.json           # Dependency management
```

## Development Workflow

### Debugging with the IDE

The project includes VS Code launch configurations for debugging:

- **Debug**: Standard debug build and launch
- **Debug Clean**: Clean build before debugging

**Prerequisites for debugging:**
- MSYS2 with MinGW-w64 toolchain
- GDB available at `C:\msys64\mingw64\bin\gdb.exe`

### Adding Dependencies

Add new dependencies to `vcpkg.json`:

```json
{
    "dependencies": [
        "sdl3",
        "your-new-dependency"
    ]
}
```

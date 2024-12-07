
# stm32f7_scope

A simple oscilloscope for the STM32F7 Discovery board. Forked from [kchojnowski/stm32f7_scope](https://github.com/kchojnowski/stm32f7_scope).

## Building the Project

This project uses **CMake** and **Ninja** for compilation and can be debugged with **OpenOCD** and **VSCode**.

### Prerequisites

Ensure you have the following tools installed:

- **CMake** (version 3.16 or higher)
- **Ninja** build system
- **GNU Arm Embedded Toolchain**
- **OpenOCD**
- **Visual Studio Code** (optional, for debugging)
- **Git**

### Clone the Repository

```bash
git clone https://github.com/AlphaIndiaMike/stm32f7_scope.git
cd stm32f7_scope
```

### Build Instructions

#### On Linux/macOS

1. Make the build script executable (if necessary):

    ```bash
    chmod +x build.sh
    ```

2. Run the build script:

    ```bash
    ./build.sh
    ```

#### On Windows

1. **Clone the Repository**

    ```batch
    git clone https://github.com/AlphaIndiaMike/stm32f7_scope.git
    cd stm32f7_scope
    ```

2. **Create a Build Script**

    Create a `build.bat` file with the following content:

    ```batch
    @echo off
    mkdir build
    cd build
    cmake -G "Ninja" ..
    ninja
    ```

3. **Run the Build Script**

    Execute the batch script by double-clicking `build.bat` or running it from the Command Prompt:

    ```batch
    build.bat
    ```

## Debugging

To debug the project using **OpenOCD** and **Visual Studio Code**:

1. **Install VSCode Extensions**
    - **Cortex-Debug** by marus25

2. **Connect Your STM32F7 Discovery Board**

3. **Start Debugging**
    - Press `F5` in VSCode to begin the debugging session. vscode configuration provided.


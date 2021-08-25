# NES Emulator

NES(Nintendo Entertainment System) emulator written in C++. This project was intended to learn about the 

<div align="center">
<img src="demo.gif">
</div>

## How to Build

### Dependencies

Before building this project the following must be installed :
- [GLEW](http://glew.sourceforge.net/) - `libglew-dev` on Ubuntu
- [GLFW](https://www.glfw.org/download.html) - `libglfw3-dev` on Ubuntu
- [PortAudio](http://www.portaudio.com/) - `portaudio19-dev` on Ubuntu

### CMake

To keep this project platform independent CMake is used to generate the build files.

The following definitions can be used to locate the dependencies if they are not found automatically:
- CMAKE\_INCLUDE\_PATH
- CMAKE\_LIBRARY\_PATH

### Windows

I use [vcpkg](https://github.com/microsoft/vcpkg) to install the dependencies on Windows.
To install cmake, I used [chocolatey](https://chocolatey.org/) which is a package manager.

```
vcpkg install glfw3:x64-windows
vcpkg install glew:x64-windows
vcpkg install portaudio:x64-windows
git clone https://github.com/Sarvesh2k/NES_Emulator
cd NES_Emulator
mkdir build
cd build
cmake -G"Visual Studio 16 2019" -A x64 -DCMAKE_TOOLCHAIN_FILE=<path-to-vcpkg>/scripts/buildsystems/vcpkg.cmake ..
cmake --build . --target ALL_BUILD --config Release
```

### Linux

```
sudo apt install libglew-dev libglfw3-dev portaudio19-dev
git clone https://github.com/jmckiern/NES-Emulator
cd NES-Emulator
mkdir build
cd build
cmake ..
make
```

## How to Use

### Running the emulator

This emulator opens the file passed through the command line arguments. A game can also be dragged onto the executable.

### Controls

The controls can be set in a `settings.ini` file.

The default controls are

Player 1:
```
Directional Pad - WASD
Select - G
Start - H
A - K
B - J
```

Player 2:
```
Directional Pad - Arrow Keys
Select - Keypad 1
Start - Keypad 2
A - Keypad 3
B - Keypad 0
```

## Mappers supported

The mappers currently supported are NROM (0), MMC1 (1), UxROM (2), CNROM (3) and MMC3 (4).
Games tested are only from the US released version.

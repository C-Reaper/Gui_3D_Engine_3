# Project README

## Overview
This project is a 3D GUI engine written in C. It supports building for Linux, Windows (using Wine), WebAssembly (emscripten), and includes debug options.

## Features
- Basic GUI components
- Support for custom shaders
- Input handling
- Cross-platform compilation via makefiles

## Project Structure
```
Gui_3D_Engine/
├── build/              # .exe files produced by Main.c
├── libs/               # *.c for bin
├── lib/                # librarys for my own languages
├── code/               # scripts from my custom languages for example .rex, .ll, .omml
├── data/               # Datafile for example .txt or dumped files
├── assets/             # images and sound files
├── src/                # src code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration for cross-compiling to windows on linux
└── README.md           # This file
└── LICENSE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - Linux: `X11`, `png`, `jpeg`
  - Windows: `user32`, `gdi32`, `winmm` (using Wine for cross-compilation to windows on linux)

## Build & Run

### Building the Project
To build the project, navigate to the project directory and run the appropriate makefile:

```sh
cd Gui_3D_Engine/
make -f Makefile.linux all    # For Linux
make -f Makefile.windows all  # For Windows (using Wine)
make -f Makefile.wine all     # For cross-compiling to windows on linux
make -f Makefile.web all      # For WebAssembly with emscripten
```

### Clean and Rebuild
To clean the build artifacts and rebuild:

```sh
make -f Makefile.linux clean  # Remove build artifacts for Linux
make -f Makefile.windows clean # Remove build artifacts for Windows (using Wine)
make -f Makefile.wine clean  # Remove build artifacts for cross-compiling to windows on linux
make -f Makefile.web clean    # Remove build artifacts for WebAssembly with emscripten
```

### Running the Executable
After building, run the executable using make:

```sh
make -f Makefile.linux exe      # For Linux
make -f Makefile.windows exe   # For Windows (using Wine)
make -f Makefile.wine exe     # For cross-compiling to windows on linux (use WINE to run the .exe)
```

### Debugging
For debugging, use:

```sh
make -f Makefile.linux debug      # For Linux
make -f Makefile.windows debug   # For Windows (using Wine) - requires winebuild and winedbg
make -f Makefile.wine debug     # For cross-compiling to windows on linux - requires WINE
```

### Build Options
- `all`: Build output.
- `do`: Build + executable output.
- `clean`: Remove build artifacts.

These steps ensure a structured and reproducible build process for the 3D GUI engine.
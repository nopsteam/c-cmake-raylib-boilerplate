# C, Cmake and Raylib Boilerplate [![CI](https://github.com/nopsteam/c-cmake-raylib-boilerplate/actions/workflows/main.yml/badge.svg)](https://github.com/nopsteam/c-cmake-raylib-boilerplate/actions/workflows/main.yml)

This is a C project template with the following features:

 - CMake build scripts for building libraries, applications, and tests.
 - Integrated with [Raylib](https://www.raylib.com/).
 - Integrated with [Unity unit test framework](https://github.com/ThrowTheSwitch/Unity).
 - Integrated with [FetchContent](https://cmake.org/cmake/help/latest/module/FetchContent.html) for library dependencies like [Unity](https://github.com/rafaeldelboni/c-cmake-raylib-boilerplate/blob/main/CMakeLists.txt#L19-L25).
 - Resource folder to include assets
 - Updated and improved version of [C-project-template](https://github.com/peterdn/C-project-template)

## Compiling / Building

### Installing Dependencies

#### Arch Linux
```bash
yay -Sy clang cmake lcov glfw libx11 libxcursor libxinerama libxrandr vulkan-headers xorg-server-devel xorg-xinput
```

#### Ubuntu
```bash
sudo apt-get install clang cmake lcov libasound2-dev mesa-common-dev libx11-dev libxrandr-dev libxi-dev xorg-dev libgl1-mesa-dev libglu1-mesa-dev
```

## Usage

### Setup
This will build cmake files and download dependencies
```bash
make setup
```

### Build
```bash
# Debug build
make debug
# Release build
make release
```

### Run Tests
This will build and run unity tests
```bash
make test
```

#### Code Coverage Checks
This will build and run unity tests and generate reports for coverage (depends on lcov)
```bash
make coverage
# This part is optional: Generates a html with more coverage details
genhtml build/coverage/coverage.info --output-directory build/coverage/out
```

### Clean
This will delete generated files for debug and release
```bash
make clean
```

### Run Binary
This will open an Raylib white window with the unlicense logo on it.
```bash
# Debug bin
./build/debug/bin/example_app
# Release bin
./build/release/bin/example_app
```

## Directory Structure
```
./
????????? .github
???   ????????? workflows -- Github workflows folder.
????????? app -- Application source code
????????? build
???   ????????? cmake -- Cmake Finders for external compiled libs.
???   ????????? debug -- Cmake debug build generated files.
???   ???   ????????? bin -- Application debug binaries.
???   ???   ????????? resources -- Application resources assets symbolic link.
???   ????????? release -- Cmake release build generated files.
???       ????????? bin -- Application release binaries.
???       ????????? resources -- Application resources assets symbolic link.
????????? resources -- Application resources assets folder.
????????? src -- Library source code and headers.
????????? test -- Test source code.
    ????????? unity -- Unity test framework source.
```

## Dependencies
 - [Clang](https://clang.llvm.org/)
 - [Make](https://www.gnu.org/software/make/)
 - [CMake](https://cmake.org/)
 - [Raylib](https://www.raylib.com/)
 - [Lcov](https://github.com/linux-test-project/lcov)

## License
This is free and unencumbered software released into the public domain.  
For more information, please refer to <http://unlicense.org/>

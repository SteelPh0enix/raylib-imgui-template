# Raylib + ImGUI CMake project template

This repository contains an example project for Raylib with ImGui, along with custom ImGui backend for Raylib (created by Jeffery Myers).

## Project description

The project consists of four files:

* [raylib_helloworld.cpp](./project/raylib_helloworld.cpp) - the main file
* [CMakeLists.txt](./project/CMakeLists.txt) - CMake file
* [rlImGui.cpp](./project/rlImGui.cpp) - implementation of Raylib backend for ImGui
* [rlImGui.h](./project/rlImGui.h) - header of Raylib backend for ImGui

## Configuration

To build this project, CMakeLists needs two definitions:

* `RAYLIB_DIR` - directory where the Raylib is installed after build (with `lib` and `include` dir)
* `IMGUI_DIR` - directory with ImGui sources and headers (just download the latest release or clone the repository)

ImGui is added directly to the project, Raylib is added as external, linked dependency.
This example should work with both statically and dynamically linked versions of Raylib, but i haven't tested the latter yet.

### Why not just use `find_package`?

Because i hate it, at least under Windows, feel free to modify the template and use the CMake config files.
Last time i checked, you'd have to point the CMake to the `[install_directory]/lib/cmake/raylib` in order for it to find the configuration script.

## Platform support

At this moment, this CMakeLists should work under Windows.
It won't build out-of-the-box on other OSes, because i haven't adjusted it properly, however - if you want to add a platform support to this template, feel free to contact me or make a pull request.

## Contact and support

My Discord handle: SteelPh0enix#6969
Raylib Discord server: <https://discord.gg/raylib>
Raylib homepage: <https://www.raylib.com/>

## License

The code is licensed under ZLIB license, where the original authors and copyright owners are stated in source files.

Special thanks to Jeffery Myers (original creator of Raylib ImGui backend) and Ramon Santamaria (creator of Raylib).

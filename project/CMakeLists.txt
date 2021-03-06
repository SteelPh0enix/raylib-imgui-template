﻿# Copyright (c) 2021 Wojciech Olech
#
# This software is provided 'as-is', without any express or implied warranty. In no event will the authors be held liable for any damages arising from the use of this software.
#
# Permission is granted to anyone to use this software for any purpose, including commercial applications, and to alter it and redistribute it freely, subject to the following restrictions:
#
# 1. The origin of this software must not be misrepresented; you must not claim that you wrote the original software. If you use this software in a product, an acknowledgment in the product documentation would be appreciated but is not required.
#
# 2. Altered source versions must be plainly marked as such, and must not be misrepresented as being the original software.
#
# 3. This notice may not be removed or altered from any source distribution.

cmake_minimum_required (VERSION 3.12)

project ("raylib_helloworld")
set(CMAKE_CXX_STANDARD 17)

# Raylib vars
set(RAYLIB_DIR "" CACHE PATH "Raylib install directory")
message("Raylib directory: " ${RAYLIB_DIR})

# ImGui vars
set(IMGUI_DIR "" CACHE PATH "ImGui source directory")
message("ImGui directory: " ${IMGUI_DIR})
file(GLOB IMGUI_SOURCES CONFIGURE_DEPENDS ${IMGUI_DIR}/*.cpp)

include_directories(${RAYLIB_DIR}/include ${IMGUI_DIR})
link_directories(${RAYLIB_DIR}/lib)

add_executable (raylib_helloworld ${IMGUI_SOURCES} "raylib_helloworld.cpp"  "rlImGui.cpp")

# Winmm is necessary under Windows. I haven't tested it under Linux, MacOS, or other platforms - feel free to make pull requests with properly modified CMakeLists for any platform you want.
target_link_libraries(raylib_helloworld Winmm raylib)


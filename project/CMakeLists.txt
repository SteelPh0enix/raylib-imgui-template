# CMakeList.txt: projekt CMake dla elementu raylib_helloworld, dołącz źródło i zdefiniuj
# tutaj logikę specyficzną dla projektu.
#
cmake_minimum_required (VERSION 3.8)

project ("raylib_helloworld")
set(CMAKE_CXX_STANDARD 17)

# Adding raylib
set(RAYLIB_DIR "" CACHE PATH "Raylib install directory")
message("Raylib directory: " ${RAYLIB_DIR})

set(IMGUI_DIR "" CACHE PATH "ImGui source directory")
message("ImGui directory: " ${IMGUI_DIR})
file(GLOB IMGUI_SOURCES CONFIGURE_DEPENDS ${IMGUI_DIR}/*.cpp)

include_directories(${RAYLIB_DIR}/include ${IMGUI_DIR})
link_directories(${RAYLIB_DIR}/lib)

# Dodaj źródło do pliku wykonywalnego tego projektu.
add_executable (raylib_helloworld ${IMGUI_SOURCES} "raylib_helloworld.cpp"  "rlImGui.cpp")
target_link_libraries(raylib_helloworld Winmm raylib)

# TODO: Dodaj testy i zainstaluj elementy docelowe w razie potrzeby.

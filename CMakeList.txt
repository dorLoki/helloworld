cmake_minimum_required(VERSION 3.10)
project(helloworld VERSION 1.0 LANGUAGES CXX)

# C++ Standard festlegen
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include-Verzeichnis hinzufügen
include_directories(${PROJECT_SOURCE_DIR}/include)

# Erzeugt die statische Bibliothek (.lib unter Windows)
add_library(helloworldlib STATIC src/helloworld.cpp)

# Erzeugt das ausführbare Programm und linkt die Bibliothek
add_executable(helloworld src/helloworld.cpp)
target_link_libraries(helloworld PRIVATE helloworldlib)

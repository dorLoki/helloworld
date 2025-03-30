cmake_minimum_required(VERSION 3.10)
project(helloworld VERSION 1.0 LANGUAGES CXX)

# C++ Standard festlegen
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Erzeugt die statische Bibliothek
add_library(helloworld STATIC src/helloworld.cpp)

# Stellt das Include-Verzeichnis öffentlich zur Verfügung
target_include_directories(helloworld PUBLIC ${PROJECT_SOURCE_DIR}/include)

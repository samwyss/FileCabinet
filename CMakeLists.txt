cmake_minimum_required(VERSION 3.27)

project(FileCabinet VERSION 0.0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

add_executable(FileCabinet src/main.cpp)

target_link_libraries(FileCabinet)
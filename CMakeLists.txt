cmake_minimum_required(VERSION 3.27)

project(FileCabinet VERSION 0.0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)

include(FetchContent)
set(FETCHCONTENT_UPDATES_DISCONNECTED ON)
set(FETCHCONTENT_QUIET OFF)

# fetch FTXUI
FetchContent_Declare(ftxui
        GIT_REPOSITORY https://github.com/arthursonzogni/ftxui.git
        GIT_TAG v5.0.0
        GIT_PROGRESS TRUE
        GIT_SHALLOW TRUE
        EXCLUDE_FROM_ALL
)
FetchContent_MakeAvailable(ftxui)

add_executable(FileCabinet src/main.cpp)

target_include_directories(FileCabinet PRIVATE src)

target_link_libraries(FileCabinet
        PRIVATE ftxui::screen
        PRIVATE ftxui::dom
        PRIVATE ftxui::component
)
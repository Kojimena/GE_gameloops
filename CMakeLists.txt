cmake_minimum_required(VERSION 3.25)

project(GAME VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED true)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_EXPORT_COMPILE_COMMANDS ON)

find_package(raylib REQUIRED)

file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS "${PROJECT_SOURCE_DIR}/src/*.cpp")

add_executable(${PROJECT_NAME} src/main.cpp ${SOURCES} src/Game/Game.cpp src/Game/Game.h)

target_include_directories(${PROJECT_NAME}
        PRIVATE ${PROJECT_SOURCE_DIR}/include
        PUBLIC ${PROJECT_SOURCE/DIR}/src
        )

target_link_libraries(${PROJECT_NAME}
        raylib
        )
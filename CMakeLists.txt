set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "../bin")

cmake_minimum_required(VERSION 3.16)
project(ecurecetas)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED IMPORTED_TARGET gtk+-3.0)

file(GLOB_RECURSE SOURCE_FILES ./src/headers/*.h ./src/widgets/*.c)

add_executable(${PROJECT_NAME} src/main.c ${SOURCE_FILES})

target_link_libraries(${PROJECT_NAME} PRIVATE PkgConfig::GTK3)

target_include_directories(${PROJECT_NAME} PRIVATE src/headers)

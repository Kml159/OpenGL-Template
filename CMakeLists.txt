cmake_minimum_required(VERSION 3.5.0)
project(FV)

add_executable(FV src/config.h src/main.cpp)

find_package(OpenGL REQUIRED QUIET)
find_package(glfw3 REQUIRED)

target_include_directories(FV PRIVATE deps)

find_library(COCOA_LIBRARY Cocoa)
find_library(OBJC_LIBRARY objc)
find_library(IOKIT_LIBRARY IOKit)

target_link_libraries(FV glfw)
target_link_libraries(FV ${OPENGL_LIBRARIES})
target_link_libraries(FV ${COCOA_LIBRARY})
target_link_libraries(FV ${OBJC_LIBRARY})
target_link_libraries(FV ${IOKIT_LIBRARY})
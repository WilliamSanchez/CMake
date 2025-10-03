# 0-> Create Source and CMakefile
# 1-> mkdir build
# 2-> cd build
# 3-> cmake ..
# 4-> cmake --build .
# 5-> ./Executable

cmake_minimum_required(VERSION 3.22)

project(CppProjectTemplate 
        VERSION 1.0.0 
        LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS        OFF)

set(EXECUTABLE_NAME Executable)
set(LIBRARY_NAME Library)
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake/")

include(AddGitSubmodule)
add_git_submodule(external/json)

option(COMPILE_EXECUTABLE "Whether to compile the executable" ON)

add_subdirectory(configured)
add_subdirectory(src)
add_subdirectory(external)

if(COMPILE_EXECUTABLE)
        add_subdirectory(app)
else()
        message("W/o exe compiling")
endif()

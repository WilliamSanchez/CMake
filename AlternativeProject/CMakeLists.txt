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

set(EXECUTABLE Executable)
set(LIBRARY_NAME Library)

add_subdirectory(src)
add_subdirectory(inc)
add_subdirectory(app)

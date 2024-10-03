cmake_minimum_required(VERSION 3.29)
project(MyCrypto)

set(CMAKE_CXX_STANDARD 17)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(EXPORT_COMPILE_COMMANDS ON)

# add the executable
file(GLOB SOURCES "src/*.cpp")
add_executable(MyCrypto ${SOURCES})

set(CMAKE_AR gcc-ar)
set(CMAKE_EXE_LINKER_FLAGS ${CMAKE_EXE_LINKER_FLAGS} "-static-libstdc++ -static-libgcc")

target_compile_options(MyCrypto PRIVATE -fdiagnostics-color=always -pedantic)

target_include_directories(MyCrypto PRIVATE ${CMAKE_SOURCE_DIR}/header)

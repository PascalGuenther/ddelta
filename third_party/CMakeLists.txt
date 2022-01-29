cmake_minimum_required(VERSION 3.18)

option (BUILD_SHARED_LIBS "Build shared libraries" OFF)
set(BUILD_SHARED_LIBS OFF)
option(BUILD_EXAMPLES "Build examples" OFF)
set(BUILD_EXAMPLES OFF)
option(WITH_LFS "Enable Large File Support" OFF)
set(WITH_LFS OFF)
add_subdirectory(libdivsufsort)
target_include_directories(divsufsort PUBLIC
    ${CMAKE_CURRENT_BINARY_DIR}/libdivsufsort/include
)



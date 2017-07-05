cmake_minimum_required (VERSION 3.3)

project (revo)

set (REVO_SOURCES main.cpp)

include_directories("${PROJECT_BINARY_DIR}")

if (NOT DEFINED OPENCL_INCLUDE_DIRS)
    set (OPENCL_INCLUDE_DIRS ./inc)
endif ()

include_directories (${OPENCL_INCLUDE_DIRS})

add_library (OpenCL SHARED ${REVO_SOURCES})

add_executable(revo main.cpp)

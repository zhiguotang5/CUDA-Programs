cmake_minimum_required(VERSION 3.10)

# Set the project name
project(CUDA_Example LANGUAGES CXX CUDA)

# Set the C++ standard (optional)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include_directories(${CMAKE_SOURCE_DIR}/include)

# Find the CUDA toolkit
find_package(CUDAToolkit REQUIRED)
if (NOT CUDAToolkit_FOUND)
    message(WARNING "CUDA toolkit not found")
endif ()

# Find OpenMP
find_package(OpenMP REQUIRED)

# Add the executable
add_executable(cpusum Chapter01/cpusum/cpusum.cpp)

add_executable(gpusum Chapter01/gpusum/gpusum.cu)

add_executable(opmsum Chapter01/ompsum/ompsum.cpp)
target_link_libraries(opmsum PRIVATE OpenMP::OpenMP_CXX)




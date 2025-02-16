cmake_minimum_required(VERSION 3.10)
project(LlamaTerminalApp)

set(CMAKE_CXX_STANDARD 11)

add_executable(LlamaTerminalApp main.cpp)

find_package(CURL REQUIRED)
find_package(OpenMP REQUIRED)

set(CUDA_TOOLKIT_ROOT_DIR /usr/local/cuda)
find_package(CUDA REQUIRED)

target_link_libraries(LlamaTerminalApp PRIVATE CURL::libcurl OpenMP::OpenMP_CXX CUDA::cudart)

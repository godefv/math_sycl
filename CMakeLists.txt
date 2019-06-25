cmake_minimum_required(VERSION 3.8)
project(math_sycl CXX)

add_subdirectory(extern/godefv/math)
add_subdirectory(extern/Xilinx/triSYCL)

add_executable(main main.cpp)
target_link_libraries(main math triSYCL)

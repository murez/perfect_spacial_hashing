cmake_minimum_required(VERSION 3.21)
project(psh)

list(APPEND CMAKE_MODULE_PATH "/opt/spack/opt/spack/linux-ubuntu22.04-zen2/gcc-11.2.0/intel-tbb-2021.5.0-bldra3wfdovxy2exkhrhhv4dcvwe3lkj/lib/cmake/")

find_package(TBB REQUIRED)

add_definitions(-D__TBB_PREVIEW_MUTEXES)

add_executable(main main.cpp)
target_link_libraries(main PRIVATE TBB::tbb)
# target_compile_features(main PRIVATE cxx_std_11)
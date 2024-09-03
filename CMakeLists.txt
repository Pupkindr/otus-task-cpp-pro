cmake_minimum_required(VERSION 3.22 FATAL_ERROR)

project(OtusTaskCppPro VERSION 1.0)

add_executable(helloworld_cli hw.cpp)

target_include_directories(helloworld_cli PUBLIC ${PROJECT_BINARY_DIR})

configure_file(hw.hpp.in hw.hpp)


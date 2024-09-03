cmake_minimum_required(VERSION 3.22 FATAL_ERROR)

project(OtusTaskCppPro VERSION 1.0)

add_executable(main main.cpp)

target_include_directories(main PUBLIC ${PROJECT_BINARY_DIR})

configure_file(main.hpp.in main.hpp)


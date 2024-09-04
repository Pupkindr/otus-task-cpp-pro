cmake_minimum_required(VERSION 3.22 FATAL_ERROR)

project(OtusTaskCppPro
    VERSION 1.0
    LANGUAGES CXX)

include_directories(${PROJECT_SOURCE_DIR}/src)
add_executable(helloworld_cli src/hw.cpp)

target_include_directories(helloworld_cli PUBLIC ${PROJECT_BINARY_DIR})

set(BUILD_HEADER ${PROJECT_SOURCE_DIR}/src/build_counter.hpp)
set(BUILD_INDEX ${PROJECT_SOURCE_DIR}/build_index)

add_custom_target( build_index
    COMMAND ${PROJECT_SOURCE_DIR}/build_index_gen "${BUILD_INDEX}" "${BUILD_HEADER}"
)

add_dependencies( helloworld_cli
    build_index
)
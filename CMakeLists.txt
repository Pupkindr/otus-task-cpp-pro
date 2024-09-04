cmake_minimum_required(VERSION 3.22 FATAL_ERROR)

project(OtusTaskCppPro VERSION 1.0)

add_executable(helloworld_cli hw.cpp)

target_include_directories(helloworld_cli PUBLIC ${PROJECT_BINARY_DIR})

set(BUILD_VERSION "build_counter")
set(BUILD_HEADER "build_counter.hpp")

if(EXISTS ${BUILD_VERSION})
    file(READ ${BUILD_VERSION} VERSION_VALUE)
    math(EXPR VERSION_VALUE "${VERSION_VALUE}+1")
else()
    set(VERSION_VALUE "0")
endif()

file(WRITE ${BUILD_VERSION} "${VERSION_VALUE}")

file(WRITE ${BUILD_HEADER} "#pragma once\n#define BUILD_NUMBER ${VERSION_VALUE}\n")

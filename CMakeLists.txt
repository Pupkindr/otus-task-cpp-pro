# Требуем как можно более высокую версию.
cmake_minimum_required(VERSION 3.22 FATAL_ERROR)

# Инструкция project не может быть помещена в функцию.
project(otus-task-cpp-pro)

include(cmake/functions.cmake)

add_subdirectory(src)

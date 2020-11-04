cmake_minimum_required(VERSION 3.15)

project(wiko)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

enable_testing()

add_subdirectory(src)
add_subdirectory(external)

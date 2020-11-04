cmake_minimum_required(VERSION 3.15)

project(wiko)

option(WIKO_BUILD_TESTS "Build wiko unit tests" ON)

if (MSVC)
    # warning level 4 and all warnings as errors
    add_compile_options(/W4 /WX)
else()
    # lots of warnings and all warnings as errors
    add_compile_options(-Wall -Wextra -pedantic -Werror)
endif()

add_subdirectory(core)
add_subdirectory(gpu)

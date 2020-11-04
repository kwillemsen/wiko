cmake_minimum_required(VERSION 3.15)

project(external)

set(EXT_FOLDER "external-projects")

if (WIKO_BUILD_TESTS)
    add_subdirectory(googletest)
    set_target_properties(
        gmock
        gmock_main
        gtest
        gtest_main
        PROPERTIES
        FOLDER "${EXT_FOLDER}"
    )
endif()

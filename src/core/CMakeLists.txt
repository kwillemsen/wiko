set(NAME wiko-core)

project(${NAME})

add_library(${NAME}
    include/wiko-core/core.h
    src/core.cpp
    )

target_include_directories(${NAME} PUBLIC "include")

if (WIKO_BUILD_TESTS)
    set(TST_NAME "${NAME}-test")
    add_executable(${TST_NAME}
        tests/main.cpp
        tests/test-logging.cpp
        )
    add_test(NAME "${TST_NAME}" COMMAND ${TST_NAME})
    target_link_libraries(${TST_NAME}
        googletest
        wiko-core
        )
endif()

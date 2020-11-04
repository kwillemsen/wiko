set(NAME wiko-gpu)

project(${NAME})

add_library(${NAME}
    include/wiko-gpu/gpu.h
    src/gpu.cpp
    )
    
target_include_directories(${NAME} PUBLIC "include")
target_link_libraries(${NAME}
    wiko-core
    )

if (WIKO_BUILD_TESTS)
    set(TST_NAME "${NAME}-test")
    add_executable(${TST_NAME}
        tests/main.cpp
        tests/test-gpu.cpp
        )
    add_test(NAME "${TST_NAME}" COMMAND ${TST_NAME})
    target_link_libraries(${TST_NAME}
        googletest
        wiko-gpu
        )
endif()

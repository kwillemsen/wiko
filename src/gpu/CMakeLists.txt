set(NAME wiko-gpu)

project(${NAME})

set(HDRS
    include/wiko-gpu/gpu.h
    )

set(SRCS
    src/gpu.cpp
    )

add_library(${NAME} ${HDRS} ${SRCS})
target_include_directories(${NAME} PUBLIC include)
target_link_libraries(${NAME}
    wiko-core
    )

set(TST_NAME "${NAME}-test")
add_executable(${TST_NAME}
    tests/main.cpp
    tests/test-gpu.cpp
    )

# target_link_libraries(${TST_NAME} wiko-gpu gtest)


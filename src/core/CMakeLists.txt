set(NAME wiko-core)

project(${NAME})

set(HDRS
    include/wiko-core/core.h
    )

set(SRCS
    src/core.cpp
    )

add_library(${NAME} ${HDRS} ${SRCS})

target_include_directories(${NAME} PUBLIC include)

set(TST_NAME "${NAME}-test")
add_executable(${TST_NAME}
    tests/main.cpp
    tests/test-logging.cpp
    )

# target_link_libraries(${TST_NAME} wiko-core gtest)


project(ServicesTests)

find_package(gtest REQUIRED)

include_directories(
    ${gtest_INCLUDE_DIRS}
    ${gmock_INCLUDE_DIRS}
)

set(SOURCES
    TaxService_tests.cpp
)

add_executable(${PROJECT_NAME} ${SOURCES})

target_link_libraries(${PROJECT_NAME} PRIVATE
    GTest::gtest
    GTest::Main
    gmock
    gmock_main
    Interfaces
    Servers
    Mocks
    Services
    Storage
    Common
)

add_test(${PROJECT_NAME} ${PROJECT_NAME})
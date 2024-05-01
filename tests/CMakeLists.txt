include(GoogleTest)

find_package(GTest CONFIG REQUIRED)

add_executable(test-project-template test.cpp)
target_link_libraries(test-project-template GTest::gtest_main)

gtest_discover_tests(test-project-template)

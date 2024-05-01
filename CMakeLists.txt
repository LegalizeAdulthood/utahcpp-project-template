cmake_minimum_required(VERSION 3.23)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

project(project-template CXX)

include(CTest)

add_executable(project-template main.cpp)
set_target_properties(project-template PROPERTIES
    CXX_STANDARD 11
    CXX_STANDARD_REQUIRED ON)

if(BUILD_TESTING)
    add_subdirectory(tests)
endif()

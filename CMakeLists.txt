cmake_minimum_required(VERSION 3.23)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(PROJECT_TEMPLATE_PROJECT_NAME "Project Template" CACHE "STRING" "Default project name for IDEs")
project("${PROJECT_TEMPLATE_PROJECT_NAME}" CXX)

include(CTest)

add_executable(project-template main.cpp)

if(BUILD_TESTING)
    add_subdirectory(tests)
endif()

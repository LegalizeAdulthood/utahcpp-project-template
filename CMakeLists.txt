cmake_minimum_required(VERSION 3.23)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")
include(target_folder)

set(PROJECT_TEMPLATE_PROJECT_NAME "Project Template" CACHE "STRING" "Default project name for IDEs")
project("${PROJECT_TEMPLATE_PROJECT_NAME}" CXX)

include(CTest)

add_subdirectory(libs)
add_subdirectory(tools)

set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT project-template)

if(BUILD_TESTING)
    add_subdirectory(tests)
endif()

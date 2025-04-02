cmake_minimum_required(VERSION 3.23...3.31)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")
include(set_cxx_standard)
include(target_folder)
include(vs_startup_project)

set_cxx_standard(17)

set(PROJECT_TEMPLATE_PROJECT_NAME "Project Template" CACHE "STRING" "Default project name for IDEs")
project("${PROJECT_TEMPLATE_PROJECT_NAME}" CXX)

include(CTest)

add_subdirectory(libs)
add_subdirectory(tools)

vs_startup_project(project-template)

if(BUILD_TESTING)
    add_subdirectory(tests)
endif()

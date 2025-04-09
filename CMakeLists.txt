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

add_custom_target(Miscelleanous)
target_sources(Miscelleanous PRIVATE
    ".clang-format"
    ".editorconfig"
    ".gitignore"
    ".gitmodules"
    ".github/workflows/cmake.yml"
    "CMakePresets.json"
    "ReadMe.md"
    "vcpkg.json"
    "cmake/set_cxx_standard.cmake"
    "cmake/target_folder.cmake"
    "cmake/vs_startup_project.cmake")
source_group("CMake Scripts" FILES
    "cmake/set_cxx_standard.cmake"
    "cmake/target_folder.cmake"
    "cmake/vs_startup_project.cmake")
source_group("Editing" FILES
    ".clang-format"
    ".editorconfig")
source_group("Git" FILES
    ".gitignore"
    ".gitmodules")
source_group("GitHub" FILES
    ".github/workflows/cmake.yml")
source_group("VcPkg" FILES
    "vcpkg.json")

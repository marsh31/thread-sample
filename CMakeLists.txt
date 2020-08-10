cmake_minimum_required(VERSION 3.10)

project(
        Project_name
        VERSION 1.0.0
        DESCRIPTION "description"
        LANGUAGES CXX
)

set(CMAKE_CXX_FLAGS "-O2 -std=c++14 -Wall")
add_library(
        xxx
        SHARED

        ./src.cpp
)

set_target_properties(
        xxx
        PROPERTIES
        VERSION ${PROJECT_VERSION}
)


enable_testing()
add_subdirectory(test)

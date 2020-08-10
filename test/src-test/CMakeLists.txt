cmake_minimum_required(VERSION 3.10)

# project name: test
include(${PROJECT_SOURCE_DIR}/cmake/DownloadProject/DownloadProject.cmake)
download_project(PROJ googletest
                GIT_REPOSITORY https://github.com/google/googletest.git
                GIT_TAG master
                UPDATE_DISCONNECTED 1
)

add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR})


set(CMAKE_C_FLAGS_RELEASE "-std=c++14 -Wall -Wextra -O2")
set(GTEST_ROOT ${CMAKE_SOURCE_DIR}/build)
add_executable(
  src-test
  ./main.cpp
  )

target_link_libraries(
  src-test
  xxx
  gtest_main
  )

include_directories(${PROJECT_SOURCE_DIR})

include(GoogleTest)
gtest_add_tests(TARGET src-test)

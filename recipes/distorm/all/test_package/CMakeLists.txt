cmake_minimum_required(VERSION 3.1)
project(test_package C)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

add_executable(${CMAKE_PROJECT_NAME} test_package.c)

conan_target_link_libraries(${CMAKE_PROJECT_NAME})

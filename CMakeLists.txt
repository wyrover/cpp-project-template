cmake_minimum_required(VERSION 3.1)
project(cpp-project-template)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -O0")
set(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -O0")


add_subdirectory(3rdparty/googletest)
enable_testing()
include_directories("${PROJECT_SOURCE_DIR}/3rdparty/googletest/googletest/include"
                    "${PROJECT_SOURCE_DIR}/3rdparty/googletest/googlemock/include")

add_executable(test1 test1.cpp)
target_link_libraries(test1 gtest gtest_main)
add_test(test1 test1)

add_executable(main src/main.cpp)



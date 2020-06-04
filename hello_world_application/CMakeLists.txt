cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello_world_application)

include_directories(../formatter_ex_lib)
add_subdirectory(../formatter_ex formatter_ex)

add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp) 
target_link_libraries(hello_world formatter_ex)
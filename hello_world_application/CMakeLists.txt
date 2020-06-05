cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello_world_application)

add_library(formatter STATIC ../formatter_lib/formatter.cpp)
include_directories(../formatter_lib)

add_library(formatter_ex STATIC ../formatter_ex_lib/formatter_ex.cpp)
include_directories(../formatter_ex_lib)

target_link_libraries(formatter_ex formatter)

add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp) 
target_link_libraries(hello_world formatter_ex)

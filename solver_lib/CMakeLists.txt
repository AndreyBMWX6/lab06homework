cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(solver)

add_library(formatter STATIC ../formatter_lib/formatter.cpp)
include_directories(../formatter_lib)

add_library(formatter_ex STATIC ../formatter_ex_lib/formatter_ex.cpp)
include_directories(../formatter_ex_lib)

target_link_libraries(formatter_ex formatter)

add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

add_executable(solver ../solver_application/equation.cpp)
target_link_libraries(solver formatter_ex)
target_link_libraries(solver solver_lib)

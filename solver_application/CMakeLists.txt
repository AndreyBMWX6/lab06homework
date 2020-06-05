cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(solver)

include_directories(../formatter_ex_lib)
add_subdirectory(../formatter_ex_lib formatter_ex)

include_directories(../solver_lib)
add_subdirectory(../solver_lib solver_lib)

add_executable(solver ../solver_application/equation.cpp)
target_link_libraries(solver formatter_ex)
target_link_libraries(solver solver_lib)

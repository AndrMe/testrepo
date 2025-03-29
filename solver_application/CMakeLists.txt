cmake_minimum_required(VERSION 3.3)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(solver_app)

add_executable(solver_app equation.cpp)

set(f_ex_path ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
set(s_lib_path ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)

add_subdirectory(${f_ex_path} ${CMAKE_BINARY_DIR}/formatter_ex_lib)

add_subdirectory(${s_lib_path} ${CMAKE_BINARY_DIR}/solver_lib)

target_include_directories(solver_app PUBLIC ${f_ex_path} ${s_lib_path})

target_link_libraries(solver_app formatter_ex solver)
cmake_minimum_required(VERSION 3.18)

project(ddelta VERSION 1.0)

add_executable(ddelta_apply ddelta_apply.c)

add_executable(ddelta_generate ddelta_generate.c)

target_link_libraries(ddelta_generate PUBLIC
  divsufsort
)

add_subdirectory(third_party)

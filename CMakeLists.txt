cmake_minimum_required(VERSION 3.18)

project(ddelta VERSION 1.0)

add_executable(ddelta_apply ddelta_apply.c)

add_executable(ddelta_generate ddelta_generate.c)

option(DDELTA_LIBSAIS "Use libsais for suffix sorting" OFF)

if(DDELTA_LIBSAIS)
  target_link_libraries(ddelta_generate PUBLIC
    libsais
  )
  target_compile_definitions(ddelta_generate PUBLIC
    USE_LIBSAIS=1
  )
else()
  target_link_libraries(ddelta_generate PUBLIC
    divsufsort
  )
endif()

add_subdirectory(third_party)

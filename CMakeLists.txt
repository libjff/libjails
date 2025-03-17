cmake_minimum_required(VERSION 3.0)
project(libjails)
set ( CMAKE_C_FLAGS "-DKDTRACE_HOOKS")

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
add_library(jail SHARED
	jail.c
	jail_getid.c
)

add_executable(joker main.cc)
target_link_libraries(joker jail)


cmake_minimum_required(VERSION 3.16)
project(mujs)

set(CMAKE_C_FLAGS "-std=c99 -pedantic -Wall -Wextra -Wno-unused-parameter -O2 -DHAVE_READLINE")

include_directories(.)


add_library(libmujs STATIC ./one.c)
add_library(main STATIC ./main.c)
add_library(pp STATIC ./pp.c)

#mujs
add_executable(${PROJECT_NAME} ./one.c ./main.c)
target_link_libraries(${PROJECT_NAME} m readline)

#mujs-pp
add_executable(mujs-pp ./pp.c ./one.c)
target_link_libraries(mujs-pp m readline)

message(STATUS "CMAKE_C_COMPILER = ${CMAKE_C_COMPILER}")
message(STATUS "CMAKE_CXX_COMPILER = ${CMAKE_CXX_COMPILER}")
message(STATUS "CMAKE_AR = ${CMAKE_AR}")
message(STATUS "CMAKE_RANLIB = ${CMAKE_RANLIB}")
message(STATUS "CMAKE_ASM_COMPILER = ${CMAKE_ASM_COMPILER}")
message(STATUS "CMAKE_LINKER = ${CMAKE_LINKER}")
message(STATUS "CMAKE_NM = ${CMAKE_NM}")
message(STATUS "CMAKE_OBJCOPY = ${CMAKE_OBJCOPY}")
message(STATUS "CMAKE_OBJDUMP = ${CMAKE_OBJDUMP}")
message(STATUS "CMAKE_STRIP = ${CMAKE_STRIP}")
message(STATUS "CMAKE_CXX_FLAGS = ${CMAKE_CXX_FLAGS}")
message(STATUS "CMAKE_C_FLAGS = ${CMAKE_C_FLAGS}")

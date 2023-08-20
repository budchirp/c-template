cmake_minimum_required(VERSION 3.25)

set(EXEC_NAME "out")
project(c-template VERSION 0.1.0)

if(NOT DEFINED CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE "Debug")
endif()

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
  set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
endif()

file(GLOB HEADERS
  "include/*.h"
  "include/*.hh"
  "include/*.hpp"
  "include/*.hxx"
)

file(GLOB SRC
  "src/*.c"
  "src/*.cc"
  "src/*.cpp"
  "src/*.cxx"
)

include_directories(include)

add_executable(${EXEC_NAME} ${SRC} ${HEADERS})
target_include_directories(${EXEC_NAME} PUBLIC ${HEADERS})

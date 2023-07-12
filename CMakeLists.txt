cmake_minimum_required(VERSION 3.18)

# EDIT HERE
set(EXEC_NAME "out")
project(c-template VERSION 0.1.0)

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

target_include_directories(out PUBLIC ${HEADERS})

if(CMAKE_BUILD_TYPE MATCHES "Debug")
  set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -Werror -fsanitize=undefined -fsanitize=address")
  target_link_options(${EXEC_NAME} BEFORE PUBLIC -fsanitize=undefined PUBLIC -fsanitize=address)
endif()

if(CMAKE_BUILD_TYPE MATCHES "Release")
  set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -O3")
endif()

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${TARGET_SOURCES})
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

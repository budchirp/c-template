cmake_minimum_required(VERSION 3.18)

project(c-template VERSION 1.0.0)

file(GLOB SRC
  "src/*.c"
  "src/include/*.h"
)

add_executable(out ${SRC})

cmake_minimum_required(VERSION 3.25)

project(c-template VERSION 0.1.0 LANGUAGES C)

set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

if(NOT DEFINED CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE "Debug")
endif()

add_compile_options(
  -Wall -Wextra -Wpedantic
)

file(GLOB HEADERS "include/*.h" "include/*.hpp" "include/*.hh" "include/*.hxx")
message(STATUS "Found headers: ${HEADERS}")
file(GLOB SOURCES "src/*.c" "src/*.cpp" "src/*.cc" "src/*.cxx")
message(STATUS "Found sources: ${SOURCES}")

add_executable(${PROJECT_NAME} ${HEADERS} ${SOURCES})
target_include_directories(${PROJECT_NAME} PRIVATE include)

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
  target_compile_definitions(${PROJECT_NAME} PRIVATE DEBUG_MODE=1)
  target_compile_options(${PROJECT_NAME} PRIVATE -Og -g3 -DDEBUG)
  target_link_options(${PROJECT_NAME} PRIVATE -fsanitize=address)
elseif(CMAKE_BUILD_TYPE STREQUAL "Release")
  target_compile_options(${PROJECT_NAME} PRIVATE -O3 -march=native -flto -DNDEBUG)
  target_link_options(${PROJECT_NAME} PRIVATE -flto)
endif()

source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR}/include PREFIX "Header Files" FILES ${HEADERS})
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR}/src PREFIX "Source Files" FILES ${SOURCES})

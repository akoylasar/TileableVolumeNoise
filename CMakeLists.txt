cmake_minimum_required(VERSION 3.12 FATAL_ERROR)

project(TileableVolumeNoise)

set(CMAKE_CXX_STANDARD 11)
set(BUILD_SHARED_LIBS OFF CACHE INTERNAL "")

find_package(Threads REQUIRED)

add_executable(${PROJECT_NAME})
target_include_directories(${PROJECT_NAME} PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/glm
)
target_sources(${PROJECT_NAME} PUBLIC 
  ${CMAKE_CURRENT_SOURCE_DIR}/main.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/TileableVolumeNoise.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/TileableVolumeNoise.h
  ${CMAKE_CURRENT_SOURCE_DIR}/libtarga.c
  ${CMAKE_CURRENT_SOURCE_DIR}/libtarga.h
  ${CMAKE_CURRENT_SOURCE_DIR}/parallel-util.hpp
)
target_link_libraries(${PROJECT_NAME} INTERFACE Threads::Threads)
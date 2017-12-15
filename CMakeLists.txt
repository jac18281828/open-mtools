cmake_minimum_required(VERSION 2.8)

project(open-mtools)

set(CMAKE_VERBOSE_MAKEFILE on)

find_package(Threads REQUIRED)

set(SOURCE_FILES
  mtools.h
  tgetopt.c
  udp.c)

add_executable(mdump mdump.c ${SOURCE_FILES})
target_link_libraries(mdump ${CMAKE_THREAD_LIBS_INIT} m)

add_executable(mpong mpong.c ${SOURCE_FILES})
target_link_libraries(mpong ${CMAKE_THREAD_LIBS_INIT} m)

add_executable(msend msend.c ${SOURCE_FILES})
target_link_libraries(msend ${CMAKE_THREAD_LIBS_INIT} m)

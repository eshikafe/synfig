cmake_minimum_required(VERSION 2.8)

project(ETL)

find_package(Threads)
if (CMAKE_USE_PTHREADS_INIT)
    set(HAVE_LIBPTHREAD ON)
endif()

# TODO: check for it
set(HAVE_VASPRINTF ON)

## for tests
include_directories(${CMAKE_SOURCE_DIR})

## for test to find generated etl_profile.h
include_directories(${CMAKE_CURRENT_BINARY_DIR}/ETL)

add_subdirectory(ETL)

enable_testing()
add_subdirectory(test)

CMAKE_MINIMUM_REQUIRED(VERSION 3.0...3.20)
PROJECT(gear-lib)

INCLUDE_DIRECTORIES(. ${POSIX_INCLUDE_DIR})
AUX_SOURCE_DIRECTORY(. SOURCE_FILES)

add_library(plugin ${SOURCE_FILES})

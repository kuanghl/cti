CMAKE_MINIMUM_REQUIRED(VERSION 3.0...3.20)
PROJECT(gear-lib)

INCLUDE_DIRECTORIES(. ${POSIX_INCLUDE_DIR} ${MEDIA_IO_INCLUDE_DIR} ${THREAD_INCLUDE_DIR})

LIST(APPEND SOURCE_FILES libavcap.c)

IF (DEFINED OS_LINUX)
FIND_PACKAGE(libuvc REQUIRED)
FIND_PACKAGE(PulseAudio REQUIRED)
LIST(APPEND SOURCE_FILES v4l2.c uvc.c pulseaudio.c)
ELSEIF (DEFINED OS_WINDOWS)
LIST(APPEND SOURCE_FILES dshow.c)
ENDIF ()

ADD_LIBRARY(avcap ${SOURCE_FILES})

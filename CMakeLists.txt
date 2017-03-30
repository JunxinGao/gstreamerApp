cmake_minimum_required(VERSION 3.6)
project(gstreamerApp)

set(CMAKE_CXX_STANDARD 11)
include(FindGStreamer.cmake)

if(GStreamer_FOUND)
    message(STATUS "GStreamer FOUND!!!")
    include_directories(${GSTREAMER_INCLUDE_DIRS})
endif()
set(SOURCE_FILES main.cpp)
add_executable(gstreamerApp ${SOURCE_FILES} )
target_link_libraries(gstreamerApp ${GSTREAMER_LIBRARIES} glib-2.0 gobject-2.0 gio-2.0)
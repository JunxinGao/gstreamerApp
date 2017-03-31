cmake_minimum_required(VERSION 3.6)
project(dataProbes)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/)

find_package(GStreamer)
if(GStreamer_FOUND)
    message(STATUS "GStreamer FOUND!!!")
    include_directories(${GSTREAMER_INCLUDE_DIRS})
endif()
set(SOURCE_FILES DataProbes.cpp)
add_executable(dataProbes ${SOURCE_FILES} )
target_link_libraries(dataProbes ${GSTREAMER_LIBRARIES} glib-2.0 gobject-2.0 gio-2.0)
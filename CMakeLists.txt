cmake_minimum_required (VERSION 2.6)
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/CMakeModules")

project(app_mp4)

find_package(asterisk REQUIRED)
find_library(LIBMP4V2_LIBRARY NAMES mp4v2 DOC "mp4v2 Library")


add_library(app_mp4 SHARED src/app_mp4.c)
set_target_properties(app_mp4 PROPERTIES PREFIX "")

target_link_libraries (app_mp4 mp4v2) 


install (TARGETS app_mp4 DESTINATION ${ASTERISK_LIBRARY_DIR})

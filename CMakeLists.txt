cmake_minimum_required(VERSION 2.8.9)
include(GNUInstallDirs)
project (mytimer)

add_library(mytimer STATIC mytimer.c)
TARGET_LINK_LIBRARIES(mytimer rt)

set_target_properties(mytimer PROPERTIES
  PUBLIC_HEADER mytimer.h)

SET(prefix ${CMAKE_INSTALL_PREFIX})

install(TARGETS mytimer
  PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}

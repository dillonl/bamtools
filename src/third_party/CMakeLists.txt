# ==========================
# BamTools CMakeLists.txt
# (c) 2010 Derek Barnett
#
# src/third-party/
# ==========================

option (ZLIB_LIBRARY_PATH "Use tutorial provided math implementation" OFF)
option (ZLIB_INCLUDE "Use tutorial provided math implementation" OFF)

if (NOT ZLIB_LIBRARY_PATH)
  include(zlib.cmake)
  SET(ADD_ZLIB_PROJECT TRUE CACHE INTERNAL "" FORCE)
endif()

SET(ZLIB_LIBRARY_STATIC ${ZLIB_LIBRARY_PATH}/libz.a CACHE INTERNAL "" FORCE)
SET(ZLIB_LIBRARY_SHARED ${ZLIB_LIBRARY_PATH}/libz.so.1.2.8 CACHE INTERNAL "" FORCE)

# list third-party subdirectories to build in
add_subdirectory( jsoncpp )

################################################################################
# Babylon root project
################################################################################
cmake_minimum_required(VERSION 3.30.0 FATAL_ERROR)

# Definitions
set(BABYLON_ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR} CACHE INTERNAL "Babylon root directory")

# Includes
include(${CMAKE_CURRENT_SOURCE_DIR}/tools/cmake/babylon.cmake)

# Configure Babylon
babylon_global_configure()

# Collect internal Babylon modules
babylon_collect_internal_modules()

# Enable all Babylon modules if root project
if(${CMAKE_CURRENT_SOURCE_DIR} STREQUAL ${CMAKE_SOURCE_DIR})
    babylon_enable_modules(ALL)
    project(Babylon)
endif()
